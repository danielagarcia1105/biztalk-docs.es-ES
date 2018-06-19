---
title: Consultar datos agregados programados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, scheduled data
- queries [BAM], scheduled data
ms.assetid: fb785ec0-7862-4d83-bb6f-0ebd69a28ce6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aed1d63b1ebd1e54fd229236a94f3ac9a5f6837
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970866"
---
# <a name="querying-scheduled-aggregated-data"></a><span data-ttu-id="91ae0-102">Consultar datos agregados programados</span><span class="sxs-lookup"><span data-stu-id="91ae0-102">Querying Scheduled Aggregated Data</span></span>
<span data-ttu-id="91ae0-103">Los datos de agregación programados están disponibles para consultas mediante cubos OLAP creados de forma dinámica en la base de datos de análisis de BAM.</span><span class="sxs-lookup"><span data-stu-id="91ae0-103">Scheduled aggregation data is available to queries through dynamically created OLAP cubes in the  BAM Analysis database.</span></span>  
  
 <span data-ttu-id="91ae0-104">El nombre de este cubo coincide con el atributo Nombre del elemento Vista del XML de definición de BAM, que coincide, a su vez, con el nombre de vista especificado en los asistentes de Excel.</span><span class="sxs-lookup"><span data-stu-id="91ae0-104">The name of this cube is the same as the Name attribute of the View element in the BAM definition XML, which is the same as the view name entered in the Excel wizards.</span></span> <span data-ttu-id="91ae0-105">BAM actualiza este cubo al ejecutar el paquete de servicios de transformación de datos (DTS) BAM_AN_\<*ViewName*\>, donde el \< *ViewName* \> es que el nombre de la vista que se utilizan en los asistentes de Excel describe.</span><span class="sxs-lookup"><span data-stu-id="91ae0-105">BAM refreshes this cube when you run the Data Transformation Services (DTS) package BAM_AN_\<*ViewName*\>, where the \<*ViewName*\> is the name of the view described you used in the Excel wizards.</span></span>  
  
 <span data-ttu-id="91ae0-106">Es importante tener en cuenta las siguientes condiciones a la hora de consultar datos agregados programados:</span><span class="sxs-lookup"><span data-stu-id="91ae0-106">It is important to note the following conditions when querying scheduled aggregated data:</span></span>  
  
-   <span data-ttu-id="91ae0-107">Éste es un cubo virtual que contiene una instantánea de la empresa en el momento exacto en que se inició la ejecución del paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="91ae0-107">This is a virtual cube containing a snapshot of the business at the exact moment that the DTS package execution started.</span></span> <span data-ttu-id="91ae0-108">Contiene agregaciones tanto para las actividades completadas como para las que aún están en ejecución.</span><span class="sxs-lookup"><span data-stu-id="91ae0-108">It contains aggregations both for the completed activities and for the ones still in progress.</span></span> <span data-ttu-id="91ae0-109">Puede utilizar la dimensión de progreso para filtrar o agrupar las agregaciones según corresponda.</span><span class="sxs-lookup"><span data-stu-id="91ae0-109">You can use the progress dimension to filter or group the aggregations accordingly.</span></span>  
  
-   <span data-ttu-id="91ae0-110">Si está interesado en las actividades actuales (por ejemplo, si se completan rápidamente) puede consultar el cubo real correspondiente \< *ViewName*\>#Completed.</span><span class="sxs-lookup"><span data-stu-id="91ae0-110">If you are never interested in the current activities (for example, if they complete very fast) you can query the corresponding real cube \<*ViewName*\>#Completed.</span></span>  
  
-   <span data-ttu-id="91ae0-111">Si tiene también agregaciones en tiempo real, programe el paquete DTS para actualizar el cubo con más frecuencia que la ventana en línea definida para las agregaciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="91ae0-111">If you also have real-time aggregations, schedule the DTS package for refreshing the cube more frequently than the online window you set for the real-time aggregations.</span></span> <span data-ttu-id="91ae0-112">De lo contrario, habrá un intervalo de tiempo para el que no tendrá agregaciones.</span><span class="sxs-lookup"><span data-stu-id="91ae0-112">Otherwise, there will be a window of time for which you do not have aggregations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ae0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="91ae0-113">See Also</span></span>  
 [<span data-ttu-id="91ae0-114">Consulta de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="91ae0-114">Querying BAM Data</span></span>](../core/querying-bam-data.md)