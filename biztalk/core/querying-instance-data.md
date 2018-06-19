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
# <a name="querying-instance-data"></a><span data-ttu-id="5c0e5-102">Consultar datos de instancia</span><span class="sxs-lookup"><span data-stu-id="5c0e5-102">Querying Instance Data</span></span>
<span data-ttu-id="5c0e5-103">Los datos sobre instancias de actividad individuales están disponibles para consultas en una vista SQL creada dinámicamente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="5c0e5-103">The data about individual activity instances is available for queries in a dynamically created SQL View in the BAM Primary Import Database.</span></span>  
  
 <span data-ttu-id="5c0e5-104">El nombre de esta vista es</span><span class="sxs-lookup"><span data-stu-id="5c0e5-104">The name of this view is</span></span>  
  
 <span data-ttu-id="5c0e5-105">**bam_\<**  *ViewName*  **\>_\<**  *ActivityName*  **\>_View**</span><span class="sxs-lookup"><span data-stu-id="5c0e5-105">**bam_\<** *ViewName* **\>_\<** *ActivityName* **\>_View**</span></span>  
  
 <span data-ttu-id="5c0e5-106">Where</span><span class="sxs-lookup"><span data-stu-id="5c0e5-106">Where</span></span>  
  
 <span data-ttu-id="5c0e5-107">**\<***ViewName*  **\>**  es el atributo de nombre del elemento de vista en el XML de definición de BAM, que es el mismo que el nombre de vista especificado en los asistentes de Microsoft Excel relacionados.</span><span class="sxs-lookup"><span data-stu-id="5c0e5-107">**\<** *ViewName* **\>** is the Name Attribute of the View element in the BAM Definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="5c0e5-108">**\<***ActivityName*  **\>**  es el atributo de nombre del elemento de actividad en el XML de definición de BAM, que es el mismo que el nombre de actividad especificado en los asistentes de Excel.</span><span class="sxs-lookup"><span data-stu-id="5c0e5-108">**\<** *ActivityName* **\>** is the Name Attribute of the Activity element in the BAM Definition XML, which is the same as the Activity Name entered in the Excel wizards.</span></span>  
  
 <span data-ttu-id="5c0e5-109">Es importante tener en cuenta las siguientes condiciones a la hora de realizar consultas en datos de instancia:</span><span class="sxs-lookup"><span data-stu-id="5c0e5-109">It is important to note the following conditions when querying instance data:</span></span>  
  
-   <span data-ttu-id="5c0e5-110">Si envía los datos de actividad a BAM a través de DirectEventStream, los datos de instancia no tendrán latencia, lo que significa que aparecerán inmediatamente al confirmarse la transacción de la aplicación que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c0e5-110">If you send activity data to BAM via the DirectEventStream, the instance data has no latency, meaning that it appears instantaneously when the transaction in the calling application commits.</span></span>  
  
-   <span data-ttu-id="5c0e5-111">Si los datos de actividad se envían a BAM a través de BufferedEventStream, los datos de instancia aparecerán en las consultas unos segundos más tarde, dependiendo de la carga del servicio de bus de eventos BAM y del servidor SQL Server que aloja la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="5c0e5-111">If the activity data is sent to BAM via the BufferedEventStream, the instance data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service and the SQL server that hosts the BAM Primary Import Database.</span></span>  
  
-   <span data-ttu-id="5c0e5-112">La estructura real de las tablas que están detrás de esta vista es más compleja, a fin de garantizar que los datos de las actividades actuales o recientes estén disponibles para consulta, mientras que los datos de las actividades que se han completado y que ya no son necesarias para consultas activas se archivan o se purgan sin necesidad de dejar el sistema sin conexión.</span><span class="sxs-lookup"><span data-stu-id="5c0e5-112">The actual structure of tables behind this view is more complex to ensure that the data for the current or recent activities is available for queries, while data for activities that have completed and is no longer required for active queries is archived or purged without taking the system offline.</span></span> <span data-ttu-id="5c0e5-113">Para obtener más información, consulte [almacenamiento de datos de actividad](../core/activity-data-storage.md).</span><span class="sxs-lookup"><span data-stu-id="5c0e5-113">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0e5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c0e5-114">See Also</span></span>  
 <span data-ttu-id="5c0e5-115">[Almacenamiento de datos de actividad](../core/activity-data-storage.md) </span><span class="sxs-lookup"><span data-stu-id="5c0e5-115">[Activity Data Storage](../core/activity-data-storage.md) </span></span>  
 [<span data-ttu-id="5c0e5-116">Consulta de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="5c0e5-116">Querying BAM Data</span></span>](../core/querying-bam-data.md)