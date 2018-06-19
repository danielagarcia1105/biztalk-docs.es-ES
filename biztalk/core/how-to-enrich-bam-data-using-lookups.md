---
title: Cómo enriquecer datos de BAM mediante búsquedas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data lookups
ms.assetid: 8d10659e-97d6-4cd1-9b4d-307afd43c763
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43b42b42158bc3b3c179d624340a97a890072a17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253916"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a>Cómo enriquecer datos de BAM mediante búsquedas
Hay casos en los que los datos que están disponibles en el tiempo de funcionamiento no contienen todo lo necesario para realizar informes. Por ejemplo, puede que se haya instalado un ProductID pero no un ProductName en tiempo de ejecución. Ya que la actividad de BAM representa una abstracción independiente de cómo se recopilan los datos realmente, debería contener un elemento con el mismo nombre que los datos finales que desea ver en el “ProductName” del informe. Como el resto de elementos, puede utilizarse en construcciones interpretativas, como grupos de hitos, duraciones, dimensiones y medidas. Ya que ProductName no está disponible en tiempo de ejecución, debe obtener algunos datos adicionales que sean suficientes para realizar la búsqueda, como el ProductID.  
  
 Debe recopilar los datos de la misma columna, en lugar de los datos que necesita para los informes. Por ejemplo, debe recopilar el ProductID en lugar del ProductName en tiempo de ejecución. Si son necesarias más columnas, deberá crear más elementos en la actividad, pero no utilizarlos en ninguna vista.  
  
### <a name="to-enrich-bam-data-via-lookups"></a>Para enriquecer datos de BAM mediante búsquedas  
  
1.  Implemente su definición de BAM.  
  
2.  En SQL Server Management Studio, agregue el servidor que contiene los datos de interés como servidor remoto.  
  
3.  Localice el paquete de análisis de datos denominado BAM_AN_`<View Name>`. Por ejemplo, si la vista es SalesMgr, será BAM_AN_SalesMgr.  
  
4.  Aumente el zoom de la vista del paquete (p.ej. 100%).  
  
5.  Agregue la conexión de SQL que utilizará en las búsquedas.  
  
6.  Encuentre la tarea Transformar datos después del paso “Fase de limpieza”. En este momento se transportan los datos de la base de datos PrimaryImport a la base de datos StarSchema. Hay dos instancias de esta tarea: uno para las actividades completadas y otra para la que está en curso. Aplique el resto de pasos a las dos tareas.  
  
7.  Haga clic en la transformación.  
  
8.  Seleccione Búsquedas y agregue su búsqueda “LookupProductByID” mediante la conexión de búsqueda (consulte Libros en pantalla de SQL Server para búsquedas). Por ejemplo, si la búsqueda es una tabla sencilla “LookupProduct”, con columnas ProductID y ProductName, el texto de la búsqueda será:  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. Haga clic en la pestaña Transformación. Elimine la transformación de datos predeterminada “Transformación”, y cree una transformación ActiveX en su lugar. Haga clic en Columnas de origen y agregue todas las columnas. Haga clic en Columnas de destino y agregue todas las columnas.  
  
10. Haga clic en la pestaña General y, a continuación, en Propiedades. Esto da lugar a la generación automática de una secuencia de comandos que realiza una transformación trivial de la copia, tal como se muestra:  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. Cambie el valor mediante la búsqueda, tal como se muestra:  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. Guarde y ejecute el paquete.  
  
13. Asegúrese de que el cubo OLAP recibe los datos apropiados. Debería guardar el paquete como VBScript o archivo de almacenamiento estructurado, ya que contiene su código personalizado, no solo el que se generó automáticamente desde BAM.  
  
> [!NOTE]
>  La búsqueda solo funciona para los informes programados que se realizan con DTS y OLAP. Si necesita datos diferentes de los que recopiló en la agregación en tiempo real, recupere los datos antes de llamar a la API de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la actividad económica de supervisión](../core/using-business-activity-monitoring.md)   
 [Implementar archivos XML de BAM localizados](../core/deploying-localized-bam-xml-files.md)