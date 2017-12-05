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
ms.openlocfilehash: 2b71c3adbcbe5aaaea4d9fa4bf25b2aa4191c580
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="querying-real-time-aggregated-data"></a><span data-ttu-id="9dbc6-102">Consultar datos agregados en tiempo real</span><span class="sxs-lookup"><span data-stu-id="9dbc6-102">Querying Real-Time Aggregated Data</span></span>
<span data-ttu-id="9dbc6-103">Los datos de agregación en tiempo real (ATR) están disponibles para consulta en una vista SQL creada dinámicamente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-103">The real-time aggregation (RTA) data is available for queries in a dynamically created SQL View in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="9dbc6-104">El nombre de esta vista es</span><span class="sxs-lookup"><span data-stu-id="9dbc6-104">The name of this view is</span></span>  
  
 <span data-ttu-id="9dbc6-105">**bam_\<**  *ViewName*  **\>_\<**  *RTAName*  **\>_RTAView**</span><span class="sxs-lookup"><span data-stu-id="9dbc6-105">**bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**</span></span>  
  
 <span data-ttu-id="9dbc6-106">Where</span><span class="sxs-lookup"><span data-stu-id="9dbc6-106">Where</span></span>  
  
 <span data-ttu-id="9dbc6-107">**\<***ViewName*  **\>**  es el atributo de nombre del elemento de vista en la definición de BAM XML, que es el mismo que el nombre de vista especificado en los asistentes de Microsoft Excel relacionados.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-107">**\<** *ViewName* **\>** is the Name attribute of the View element in the BAM definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="9dbc6-108">**\<***RTAName*  **\>**  se basa el atributo Name del elemento RealTimeAggregation del XML de definición de BAM, que BAM genera sean únicos en el nombre de vista.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-108">**\<** *RTAName* **\>** is the Name attribute of the RealTimeAggregation element in the BAM Definition XML, which BAM generates to be unique based on the view name.</span></span>  
  
 <span data-ttu-id="9dbc6-109">Es importante tener en cuenta las siguientes condiciones a la hora de consultar datos agregados en tiempo real:</span><span class="sxs-lookup"><span data-stu-id="9dbc6-109">It is important to note the following conditions when querying real-time aggregated data:</span></span>  
  
-   <span data-ttu-id="9dbc6-110">Las agregaciones en tiempo real deben configurarse para conservar las agregaciones durante un tiempo determinado (el valor predeterminado es 1 día) y evitar que adquieran un tamaño excesivo.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-110">The real-time aggregations must be configured to keep the aggregations for a given amount of time (the default is one day) and to never grow very large.</span></span> <span data-ttu-id="9dbc6-111">En su lugar, las agregaciones más antiguas deberán estar disponibles en los cubos OLAP.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-111">The older aggregations should be available in the OLAP cubes instead.</span></span>  
  
-   <span data-ttu-id="9dbc6-112">Las consultas sobre datos ATR deben incluir filtros para una dimensión de tiempo que se encuentre en la ventana en línea de los datos ATR.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-112">Any query against RTA must include filtering on a time dimension that will be inside the online window for the RTA data.</span></span> <span data-ttu-id="9dbc6-113">Esto es necesario porque BAM lleva a acabo el mantenimiento de datos para las ATR en función de la marca de hora de los datos de BAM, y los datos se optimizan para descargarse en porciones.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-113">This is necessary because BAM performs data maintenance for RTAs based  on the  timestamp on the BAM dataand is optimized to drop the data in chunks.</span></span> <span data-ttu-id="9dbc6-114">Por lo tanto, si simplemente envía el comando Transact-SQL “`select *`”, los resultados fluctuarán de forma impredecible.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-114">Thus if you simply send the Transact-SQL command "`select *`", the results will fluctuate unpredictably.</span></span>  
  
-   <span data-ttu-id="9dbc6-115">Si se envían los datos de actividad a BAM mediante DirectEventStream, los datos agregados en tiempo real no tendrán latencia, sino que aparecerán instantáneamente al confirmarse la transacción de la aplicación que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-115">If the activity data is sent to BAM via the DirectEventStream, the real-time aggregated data has no latency – it appears instantaneously when the transaction in the calling Application commits.</span></span>  
  
-   <span data-ttu-id="9dbc6-116">Si los datos de actividad se envían a BAM mediante BufferedEventStream, los datos ATR se mostrarán para las consultas unos segundos después, dependiendo de la carga de servicios de bus de eventos BAM y del servidor SQL Server que actúa como host de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-116">If the activity data is sent to BAM via the BufferedEventStream, the RTA data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service(s) and the SQL server that hosts the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="9dbc6-117">BAM basa la agregación en tiempo real en una tabla que mantiene sincronizada con los cambios o inserciones en los registros de almacenamiento de datos de actividad mediante el uso de desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-117">BAM bases the real-time aggregation on a table that it maintains in synchronization with the changes or insertions in the activity data storage records using triggers.</span></span> <span data-ttu-id="9dbc6-118">Para obtener más información, consulte [almacenamiento de datos de actividad](../core/activity-data-storage.md).</span><span class="sxs-lookup"><span data-stu-id="9dbc6-118">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span> <span data-ttu-id="9dbc6-119">Por lo tanto, la agregación en tiempo real puede tener un impacto significativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9dbc6-119">Thus, the real-time aggregation can have a significant performance impact.</span></span> <span data-ttu-id="9dbc6-120">Para obtener más información, consulte [agregaciones en tiempo real](../core/real-time-aggregations.md).</span><span class="sxs-lookup"><span data-stu-id="9dbc6-120">For more information, see [Real-Time Aggregations](../core/real-time-aggregations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbc6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dbc6-121">See Also</span></span>  
 <span data-ttu-id="9dbc6-122">[Consultar datos agregados programados](../core/querying-scheduled-aggregated-data.md) </span><span class="sxs-lookup"><span data-stu-id="9dbc6-122">[Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md) </span></span>  
 [<span data-ttu-id="9dbc6-123">Consulta de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="9dbc6-123">Querying BAM Data</span></span>](../core/querying-bam-data.md)