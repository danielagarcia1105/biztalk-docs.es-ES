---
title: Agregaciones programadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- scheduling, aggregations [BAM]
- aggregations [BAM], scheduling
ms.assetid: 4e2da2eb-b1fc-4b27-98d6-564e6df719e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cf2558b046d53deb6036553c5206beebd4d80ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269092"
---
# <a name="scheduled-aggregations"></a><span data-ttu-id="3d7b3-102">Agregaciones programadas</span><span class="sxs-lookup"><span data-stu-id="3d7b3-102">Scheduled Aggregations</span></span>
<span data-ttu-id="3d7b3-103">BAM basa las agregaciones programadas en cubos OLAP generados dinámicamente y paquetes de Servicios de transformación de datos (DTS).</span><span class="sxs-lookup"><span data-stu-id="3d7b3-103">BAM bases scheduled aggregations on dynamically generated OLAP cubes and Data Transformation Services (DTS) packages.</span></span> <span data-ttu-id="3d7b3-104">Los datos de las agregaciones programadas representan una instantánea de sus actividades de negocio en el momento de iniciar su paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-104">The data in scheduled aggregations represents a snapshot of your business activities when you start your DTS package.</span></span> <span data-ttu-id="3d7b3-105">Para lograr esto, el primer paso del paquete DTS para el análisis es una llamada al procedimiento almacenado **bam_Metadata_BeginAnalysis** que recuperará una instantánea que se compone de:</span><span class="sxs-lookup"><span data-stu-id="3d7b3-105">To achieve this, the first step of the DTS package for analysis is a call to the stored procedure **bam_Metadata_BeginAnalysis** that will retrieve a snapshot consisting of:</span></span>  
  
-   <span data-ttu-id="3d7b3-106">Una copia instantánea de todas las instancias de actividad en ejecución.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-106">A snapshot copy of all activity instances in progress</span></span>  
  
-   <span data-ttu-id="3d7b3-107">Una vista que representa una ventana incremental de las instancias de actividad completadas desde el momento en que ejecutó el paquete DTS por última vez hasta el momento de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-107">A view that represents an incremental window on the completed activity instances from the moment that you ran the DTS package for the last time to the moment of the snapshot</span></span>  
  
 <span data-ttu-id="3d7b3-108">BAM la archiva mediante un bloqueo exclusivo en el almacenamiento de la actividad durante poco tiempo, lo que impide que se escriba cualquier dato a la misma vez.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-108">BAM achieves this by taking an exclusive lock on the Activity Storage for a very short time, thus preventing any data writing at the same time.</span></span> <span data-ttu-id="3d7b3-109">Una vez que BAM ha realizado la instantánea, puede que el paquete DTS tarde en ejecutarse, pero BAM omitirá cualquier dato nuevo que se reciba durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-109">Once BAM takes the snapshot, the DTS package might take a long time to run, but BAM will ignore any new data that arrives during the processing.</span></span> <span data-ttu-id="3d7b3-110">En la siguiente ilustración se muestra esta actividad:</span><span class="sxs-lookup"><span data-stu-id="3d7b3-110">The following figure illustrates this activity:</span></span>  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")  
<span data-ttu-id="3d7b3-111">Agregaciones programadas de BAM</span><span class="sxs-lookup"><span data-stu-id="3d7b3-111">BAM Scheduled Aggregations</span></span>  
  
 <span data-ttu-id="3d7b3-112">En la ilustración, BAM transporta datos sobre las instancias de actividad completadas al cubo OLAP de instancias completas.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-112">In the figure, BAM moves data about the completed activity instances to the Completed Instances OLAP cube.</span></span> <span data-ttu-id="3d7b3-113">BAM procesa este cubo de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-113">BAM incrementally processes this cube.</span></span>  
  
 <span data-ttu-id="3d7b3-114">A la misma vez, BAM transporta los datos sobre las actividades que todavía están en ejecución al cubo de instancias activas, que procesará por completo el paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-114">At the same time, BAM moves the data about the activities still in progress to the Active Instances cube, which the DTS package fully processes.</span></span> <span data-ttu-id="3d7b3-115">Se puede aceptar porque BAM asume que solo un número relativamente pequeño de actividades están en ejecución en un momento en concreto.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-115">This is acceptable, because BAM assumes that only a relatively small number of activities are in progress at any given moment.</span></span>  
  
 <span data-ttu-id="3d7b3-116">Los datos de las agregaciones programadas están disponibles en el cubo virtual que oculta la diferencia entre las actividades actuales y completas.</span><span class="sxs-lookup"><span data-stu-id="3d7b3-116">Data for the scheduled aggregations is available from a virtual cube that hides the difference between the completed and current activities.</span></span> <span data-ttu-id="3d7b3-117">Para obtener más información, consulte [consultar datos agregados programados](../core/querying-scheduled-aggregated-data.md).</span><span class="sxs-lookup"><span data-stu-id="3d7b3-117">For more information, see [Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d7b3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d7b3-118">See Also</span></span>  
 [<span data-ttu-id="3d7b3-119">¿Qué es una agregación?</span><span class="sxs-lookup"><span data-stu-id="3d7b3-119">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)