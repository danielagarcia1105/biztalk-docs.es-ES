---
title: Ejecutar la operación SQLEXECUTE en la base de datos de Oracle mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2aedcd9874682ed71af774db72979c152836ab3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004861"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a>Ejecutar la operación SQLEXECUTE en la base de datos de Oracle mediante el modelo de servicio de WCF
La[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un conjunto estándar de operaciones en los artefactos de base de datos de Oracle. Mediante el uso de estas operaciones, puede hacer cosas como la llamada a una función de Oracle o un procedimiento, o realizar operaciones del lenguaje (DML) de manipulación de datos de básica SQL en tablas. Sin embargo, puede haber escenarios controlados por la lógica de negocios que necesitan realizar operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no se exponen. Por ejemplo, es posible que desee:  
  
- Realizar una operación en artefactos de base de datos que no se exponen mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo, obtener el CURVAL o NEXTVAL de una secuencia de Oracle.  
  
- Realizar operaciones de lenguaje de definición de datos; Por ejemplo, cree una tabla.  
  
- Realizar operaciones en un artefacto de la base de datos que no estaba presente en tiempo de diseño; Por ejemplo, actualizar registros en una tabla temporal creada por la lógica de negocios.  
  
- Realizar operaciones más complejas de DML en tablas que las operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies; por ejemplo, para realizar una consulta que incluye una cláusula JOIN.  
  
  Para estos tipos de escenarios, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone la operación SQLEXECUTE. Mediante el uso de la operación SQLEXECUTE, puede realizar una instrucción SQL con parámetros en la base de datos de Oracle. La operación SQLEXECUTE admite un bloque de parámetro de entrada consta de conjuntos de parámetros que permiten ejecutar la misma instrucción SQL una vez para cada conjunto. La operación SQLEXECUTE devuelve los resultados de la instrucción SQL en un conjunto de registros genérico.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos de este tema se usa una secuencia de Oracle denominan TID_SEQ. Una secuencia de comandos para generar esta secuencia se suministra con los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El modelo de servicio WCF genera un cliente WCF dedicado, **SQLEXECUTEClient**, para la operación SQLEXECUTE. El siguiente código muestra la **SQLEXECUTEClient** y la firma del método que se llama para invocar la operación SQLEXECUTE.  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 La operación SQLEXECUTE devuelve un conjunto de registros genérico. Este conjunto de registros contiene los valores (si existe) que son devueltos por las instrucciones que se ejecuta la operación SQLEXECUTE. Puede pasar conjuntos de parámetros de entrada a la operación SQLEXECUTE en una colección de objetos PARAMETERDATA, cada uno de los cuales contiene una colección de parámetros de entrada representada como cadenas. El código siguiente muestra la definición de un conjunto PARAMETERDATA.  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class PARAMETERDATA : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private string[] PARAMETERField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public string[] PARAMETER {  
            get {  
                return this.PARAMETERField;  
            }  
            set {  
                this.PARAMETERField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="invoking-the-sqlexecute-operation"></a>Invocar la operación SQLEXECUTE  
 Para invocar la operación SQLEXECUTE mediante un cliente WCF, realice los pasos siguientes.  
  
1. Generar un **SQLEXECUTEClient** clase para la tabla de destino o vista.  
  
   > [!IMPORTANT]
   >  La operación SQLEXECUTE aparece bajo el nodo raíz (**/**) en el **seleccionar una categoría** panel en el **Add Adapter Service Reference** cuadro de diálogo.  
  
2. Cree una instancia de la **SQLEXECUTEClient** clase e invocar el **SQLEXECUTE** método para ejecutar instrucciones SQL en la base de datos de Oracle.  
  
   Para obtener más información acerca de cómo crear una clase de cliente WCF e invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [general del modelo de servicio WCF con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).  
  
   En el ejemplo siguiente se usa el **SQLEXECUTEClient** para obtener el siguiente valor de una secuencia de Oracle, TID_SEQ, mediante la ejecución de la siguiente instrucción SQL: `SELECT tid_seq.nextval id from DUAL`. La salida, a continuación, se escribe en la consola.  
  
```  
using (SQLEXECUTEClient sqlClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE"))  
{  
    sqlClient.ClientCredentials.UserName.UserName = "SCOTT";  
    sqlClient.ClientCredentials.UserName.Password = "TIGER";  
    try  
    {  
        sqlClient.Open();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error opening SQL client " + ex.Message);  
        throw;  
    }  
    microsoft.lobservices.oracledb._2007._03.GenRecordRow[] sequenceRec =   
        new microsoft.lobservices.oracledb._2007._03.GenRecordRow[0];  
  
    try  
    {  
        sequenceRec = sqlClient.SQLEXECUTE("SELECT tid_seq.nextval id from DUAL", null, null);  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error executing SQL client " + ex.Message);  
        throw;  
    }  
  
    if (sequenceRec.Length > 0)  
    {  
        Console.WriteLine("TID_SEQUENCE value is {0}", sequenceRec[0].GenRecordColumn[0].ColumnValue);  
    }  
    else  
    {  
    Console.WriteLine("Couldn't get next TID_SEQUENCE value");  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)