---
title: Realizar consultas en tiempo real de datos agregan | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f02ec8a33fdb050462860efc6c6a0cd5f8fa5650
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="querying-real-time-aggregated-data"></a>Consultar datos agregados en tiempo real
Los datos de agregación en tiempo real (ATR) están disponibles para consulta en una vista SQL creada dinámicamente en la base de datos de importación principal de BAM.  
  
 El nombre de esta vista es  
  
 **bam_\<**  *ViewName* **> _\<**  *RTAName* **> _RTAView**  
  
 Where  
  
 **\<***ViewName*  **>**  es el atributo de nombre del elemento de vista en la definición de BAM XML, que es el mismo que el nombre de vista especificado en los asistentes de Microsoft Excel relacionados.  
  
 **\<***RTAName*  **>**  se basa el atributo Name del elemento RealTimeAggregation del XML de definición de BAM, que BAM genera sean únicos en el nombre de vista.  
  
 Es importante tener en cuenta las siguientes condiciones a la hora de consultar datos agregados en tiempo real:  
  
-   Las agregaciones en tiempo real deben configurarse para conservar las agregaciones durante un tiempo determinado (el valor predeterminado es 1 día) y evitar que adquieran un tamaño excesivo. En su lugar, las agregaciones más antiguas deberán estar disponibles en los cubos OLAP.  
  
-   Las consultas sobre datos ATR deben incluir filtros para una dimensión de tiempo que se encuentre en la ventana en línea de los datos ATR. Esto es necesario porque BAM lleva a acabo el mantenimiento de datos para las ATR en función de la marca de hora de los datos de BAM, y los datos se optimizan para descargarse en porciones. Por lo tanto, si simplemente envía el comando Transact-SQL “`select *`”, los resultados fluctuarán de forma impredecible.  
  
-   Si se envían los datos de actividad a BAM mediante DirectEventStream, los datos agregados en tiempo real no tendrán latencia, sino que aparecerán instantáneamente al confirmarse la transacción de la aplicación que realiza la llamada.  
  
-   Si los datos de actividad se envían a BAM mediante BufferedEventStream, los datos ATR se mostrarán para las consultas unos segundos después, dependiendo de la carga de servicios de bus de eventos BAM y del servidor SQL Server que actúa como host de la base de datos de importación principal de BAM.  
  
-   BAM basa la agregación en tiempo real en una tabla que mantiene sincronizada con los cambios o inserciones en los registros de almacenamiento de datos de actividad mediante el uso de desencadenadores. Para obtener más información, consulte [almacenamiento de datos de actividad](../core/activity-data-storage.md). Por lo tanto, la agregación en tiempo real puede tener un impacto significativo en el rendimiento. Para obtener más información, consulte [agregaciones en tiempo real](../core/real-time-aggregations.md).  
  
## <a name="see-also"></a>Vea también  
 [Consultar datos agregados programados](../core/querying-scheduled-aggregated-data.md)   
 [Consultar datos de BAM](../core/querying-bam-data.md)