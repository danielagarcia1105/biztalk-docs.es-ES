---
title: Consultar datos de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, instance data
- queries [BAM], instance data
ms.assetid: ae4a8854-d5c2-4b36-a0ef-3f74e138306e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43310756cf12c0c2a48eb6716221afc5395ecb0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971834"
---
# <a name="querying-instance-data"></a>Consultar datos de instancia
Los datos sobre instancias de actividad individuales están disponibles para consultas en una vista SQL creada dinámicamente en la base de datos de importación principal de BAM.  
  
 El nombre de esta vista es  
  
 **bam_\<**  *ViewName*  **\>_\<**  *ActivityName*  **\>_View**  
  
 Where  
  
 **\<***ViewName*  **\>**  es el atributo de nombre del elemento de vista en el XML de definición de BAM, que es el mismo que el nombre de vista especificado en los asistentes de Microsoft Excel relacionados.  
  
 **\<***ActivityName*  **\>**  es el atributo de nombre del elemento de actividad en el XML de definición de BAM, que es el mismo que el nombre de actividad especificado en los asistentes de Excel.  
  
 Es importante tener en cuenta las siguientes condiciones a la hora de realizar consultas en datos de instancia:  
  
-   Si envía los datos de actividad a BAM a través de DirectEventStream, los datos de instancia no tendrán latencia, lo que significa que aparecerán inmediatamente al confirmarse la transacción de la aplicación que realiza la llamada.  
  
-   Si los datos de actividad se envían a BAM a través de BufferedEventStream, los datos de instancia aparecerán en las consultas unos segundos más tarde, dependiendo de la carga del servicio de bus de eventos BAM y del servidor SQL Server que aloja la base de datos de importación principal de BAM.  
  
-   La estructura real de las tablas que están detrás de esta vista es más compleja, a fin de garantizar que los datos de las actividades actuales o recientes estén disponibles para consulta, mientras que los datos de las actividades que se han completado y que ya no son necesarias para consultas activas se archivan o se purgan sin necesidad de dejar el sistema sin conexión. Para obtener más información, consulte [almacenamiento de datos de actividad](../core/activity-data-storage.md).  
  
## <a name="see-also"></a>Vea también  
 [Almacenamiento de datos de actividad](../core/activity-data-storage.md)   
 [Consulta de datos de BAM](../core/querying-bam-data.md)