---
title: Consultar datos de instancia | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, instance data
- queries [BAM], instance data
ms.assetid: ae4a8854-d5c2-4b36-a0ef-3f74e138306e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 762ad9dd241f65db700e452a2ac181442c863607
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="querying-instance-data"></a>Consultar datos de instancia
Los datos sobre instancias de actividad individuales están disponibles para consultas en una vista SQL creada dinámicamente en la base de datos de importación principal de BAM.  
  
 El nombre de esta vista es  
  
 **bam_\<**  *ViewName* **> _\<**  *ActivityName* **> _View**  
  
 Where  
  
 **\<***ViewName*  **>**  es el atributo de nombre del elemento de vista en el XML de definición de BAM, que es el mismo que el nombre de vista especificado en los asistentes de Microsoft Excel relacionados.  
  
 **\<***ActivityName*  **>**  es el atributo de nombre del elemento de actividad en el XML de definición de BAM, que es el mismo que el nombre de actividad especificado en los asistentes de Excel.  
  
 Es importante tener en cuenta las siguientes condiciones a la hora de realizar consultas en datos de instancia:  
  
-   Si envía los datos de actividad a BAM a través de DirectEventStream, los datos de instancia no tendrán latencia, lo que significa que aparecerán inmediatamente al confirmarse la transacción de la aplicación que realiza la llamada.  
  
-   Si los datos de actividad se envían a BAM a través de BufferedEventStream, los datos de instancia aparecerán en las consultas unos segundos más tarde, dependiendo de la carga del servicio de bus de eventos BAM y del servidor SQL Server que aloja la base de datos de importación principal de BAM.  
  
-   La estructura real de las tablas que están detrás de esta vista es más compleja, a fin de garantizar que los datos de las actividades actuales o recientes estén disponibles para consulta, mientras que los datos de las actividades que se han completado y que ya no son necesarias para consultas activas se archivan o se purgan sin necesidad de dejar el sistema sin conexión. Para obtener más información, consulte [almacenamiento de datos de actividad](../core/activity-data-storage.md).  
  
## <a name="see-also"></a>Vea también  
 [Almacenamiento de datos de actividad](../core/activity-data-storage.md)   
 [Consultar datos de BAM](../core/querying-bam-data.md)