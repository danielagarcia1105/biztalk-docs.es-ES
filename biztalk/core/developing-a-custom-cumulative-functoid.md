---
title: Desarrollar un Functoid acumulado personalizado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea2c5fa-ed50-4b76-aee9-0d4adf9e6d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f69ae870269948358f117b07f37d481faced160
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242332"
---
# <a name="developing-a-custom-cumulative-functoid"></a>Desarrollar un functoid acumulativo personalizado
Utilice un functoid acumulado personalizado para realizar operaciones de acumulación para los valores que aparecen varias veces en un mensaje de instancia.  
  
 Debe implementar tres funciones al desarrollar un functoid acumulativo. Las tres funciones corresponden a las acciones de inicializar, acumular y obtener que la asignación necesita para realizar la acumulación. Antes de describir estas funciones, es importante abordar el tema de la seguridad de los subprocesos.  
  
## <a name="writing-a-thread-safe-functoid"></a>Escribir un functoid que sea seguro para subprocesos  
 El código de un functoid debe ser seguro para subprocesos, ya que se pueden ejecutar simultáneamente varias instancias de una asignación en circunstancias de mucha actividad. Algunos de los puntos que debe recordar son:  
  
-   El estado estático debe ser seguro para subprocesos.  
  
-   El estado de la instancia no siempre tiene que ser seguro para subprocesos.  
  
-   El diseño debe tener en cuenta la ejecución en condiciones de mucha actividad. Evite los bloqueos en la medida de lo posible.  
  
-   Evite la necesidad de sincronización si es posible.  
  
 BizTalk Server proporciona un mecanismo sencillo para reducir la complejidad de escritura de un functoid acumulado que sea seguro para subprocesos. Las tres funciones tienen el mismo primer parámetro, un valor de índice entero. BizTalk Server asigna un número único al valor de índice cuando llama a la función de inicialización. Puede usar este valor como un índice en una matriz que almacene los valores acumulados, tal como se muestra en el siguiente código:  
  
```  
private HashTable cumulativeArray = new HashTable();  
…  
// Initialization function  
public string InitCumulativeMultiply(int index)  
{  
    cumulativeArray[index] = 1.0;  
    return string.Empty;  
}  
```  
  
 Este ejemplo utiliza una tabla HashTable en lugar de una lista ArrayList, ya que la función de inicialización no se puede llamar con valores de índice por orden.  
  
## <a name="implementing-the-three-cumulative-functions"></a>Implementar las tres funciones acumuladas  
 Deberá implementar tres funciones para cada functoid acumulado personalizado que desarrolle. En la siguiente tabla se describen las funciones y los métodos que debe llamar en el constructor para establecerlos. Todas las funciones devuelven valores de cadena.  
  
> [!NOTE]
>  Determine el nombre más adecuado para cada función, pero considere que cada función debe tener el número y el tipo de argumentos especificados.  
  
|Propósito de la función|Argumentos|Para establecer una referencia|Para establecer la secuencia de comandos en línea|  
|----------------------|---------------|------------------------|--------------------------|  
|Inicialización|**índice de int**|**SetExternalFunctionName**|**SetScriptBuffer** con `functionNumber` = 0|  
|Cumulation|**int de índice, val, ámbito de la cadena de cadena**|**SetExternalFunctionName2**|**SetScriptBuffer** con `functionNumber` = 1|  
|Obtener|**índice de int**|**SetExternalFunctionName3**|**SetScriptBuffer** con `functionNumber` = 2|  
  
### <a name="initialization"></a>Inicialización  
 La función initialization le permite preparar los mecanismos que usará para realizar la acumulación. Puede inicializar una matriz, restablecer uno o más valores, o cargar otros recursos según sea necesario. No se utiliza el valor devuelto por la cadena.  
  
### <a name="cumulation"></a>Cumulation  
 Aquí es donde se realiza la operación de acumulación apropiada para el functoid. BizTalk Server pasa los tres parámetros siguientes:  
  
-   **Índice.** un valor de entero que representa una instancia de asignación. Puede haber en ejecución varias instancias de asignación a la vez.  
  
-   **Val.** una cadena que contiene el valor que se debe acumular. Será un valor numérico salvo si escribe un functoid acumulado de tipo cadena.  
  
-   **Ámbito.** una cadena que contiene un número que indica qué valor de atributo o elemento se debe acumular. Los valores reales se determinan mediante una implementación.  
  
 Decida los valores que se van acumular y los que se van a omitir. Por ejemplo, puede omitir los valores que no estén por debajo de 0 pero que produzcan una excepción cuando el valor no sea numérico. **BaseFunctoid** proporciona dos funciones:**IsDate** y **IsNumeric**: para ayudar con la validación.  
  
> [!NOTE]
>  Si usa **IsDate** o **IsNumeric** en un script en línea, asegúrese de establecer **RequiredGlobalHelperFunctions** para que las funciones se ponen a disposición del script.  
  
 No se utiliza el valor devuelto por la cadena.  
  
### <a name="get"></a>Obtener  
 Cuando BizTalk Server termina la iteración de todos los valores determinados por la configuración del functoid en la asignación, solicita el valor acumulado. La función get tiene un argumento, `Index`, que es un valor entero que representa una instancia de asignación. El functoid debe usar el valor Index para buscar y devolver el valor acumulado como una cadena.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo ilustra cómo crear un functoid personalizado para realizar multiplicaciones acumuladas. Se basa en un archivo de recursos que contiene tres recursos de cadena y un recurso de mapa de bits de 16 x 16 píxeles.  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
using System.Collections;  
using System.Globalization;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    public class CumulativeMultiplyFunctoid : BaseFunctoid  
    {  
        private ArrayList myCumulativeArray = new ArrayList();  
  
        public CumulativeMultiplyFunctoid() : base()  
        {  
            //ID for this functoid  
            ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUMULATIVEMULTIPLYFUNCTOID_NAME");  
            SetTooltip("IDS_CUMULATIVEMULTIPLYFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUMULATIVEMULTIPLYFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUMULATIVEMULTIPLYFUNCTOID_BITMAP");  
  
            // Put this string handling function under the Cumulative  
            // Functoid tab in the Visual Studio toolbox for functoids  
            Category = FunctoidCategory.Cumulative;  
  
            // 2 required parameters, no optional parameters  
            SetMinParams(1);  
            SetMaxParams(2);  
  
            // Functoid accepts three inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType((~ConnectionType.FunctoidCount) & (~ConnectionType.FunctoidIndex) & (~ConnectionType.FunctoidIteration) & (~ConnectionType.FunctoidCumulative) & (~ConnectionType.FunctoidLooping) & (~ConnectionType.Record));  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Set the Initialize, Cumulative and Get functions  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CumulativeMultiplyFunctoid", "InitCumulativeMultiply");  
            SetExternalFunctionName2("AddToCumulativeMultiply");  
            SetExternalFunctionName3("GetCumulativeMultiply");  
        }  
  
        // Initialization function  
        public string InitCumulativeMultiply(int index)  
        {  
            if (index >= 0)  
            {  
                if (index >= myCumulativeArray.Count)  
                {  
                    myCumulativeArray.Add(1.0);  
                }  
                else  
                {  
                    myCumulativeArray[index] = 1.0;  
                }  
            }  
  
            return "";  
        }  
  
        // Cumulative function  
        public string AddToCumulativeMultiply(int index, string val, string reserved)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            if (IsNumeric(val))  
            {  
                double dval = Convert.ToDouble(val, CultureInfo.InvariantCulture);  
                myCumulativeArray[index] = (double)(myCumulativeArray[index]) * dval;  
            }  
            return myCumulativeArray[index].ToString();  
        }  
  
        // Get Function  
        public string GetCumulativeMultiply(int index)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            return myCumulativeArray[index].ToString();  
        }  
    }  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilizar BaseFunctoid](../core/using-basefunctoid.md)   
 [Desarrollar un Functoid en línea personalizado](../core/developing-a-custom-inline-functoid.md)   
 [Functoid personalizado (ejemplo de BizTalk Server)](../core/custom-functoid-biztalk-server-sample.md)