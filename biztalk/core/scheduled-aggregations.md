---
title: Agregaciones programadas | Microsoft Docs
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
ms.openlocfilehash: 04aaf0a3eefb018dbe23f3e05e7e684b595820d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998479"
---
# <a name="scheduled-aggregations"></a><span data-ttu-id="55202-102">Agregaciones programadas</span><span class="sxs-lookup"><span data-stu-id="55202-102">Scheduled Aggregations</span></span>
<span data-ttu-id="55202-103">BAM basa las agregaciones programadas en cubos OLAP generados dinámicamente y paquetes de Servicios de transformación de datos (DTS).</span><span class="sxs-lookup"><span data-stu-id="55202-103">BAM bases scheduled aggregations on dynamically generated OLAP cubes and Data Transformation Services (DTS) packages.</span></span> <span data-ttu-id="55202-104">Los datos de las agregaciones programadas representan una instantánea de sus actividades de negocio en el momento de iniciar su paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="55202-104">The data in scheduled aggregations represents a snapshot of your business activities when you start your DTS package.</span></span> <span data-ttu-id="55202-105">Para lograr esto, el primer paso del paquete DTS para el análisis es una llamada al procedimiento almacenado **bam_Metadata_BeginAnalysis** que recuperará una instantánea que consta de:</span><span class="sxs-lookup"><span data-stu-id="55202-105">To achieve this, the first step of the DTS package for analysis is a call to the stored procedure **bam_Metadata_BeginAnalysis** that will retrieve a snapshot consisting of:</span></span>  
  
- <span data-ttu-id="55202-106">Una copia instantánea de todas las instancias de actividad en ejecución.</span><span class="sxs-lookup"><span data-stu-id="55202-106">A snapshot copy of all activity instances in progress</span></span>  
  
- <span data-ttu-id="55202-107">Una vista que representa una ventana incremental de las instancias de actividad completadas desde el momento en que ejecutó el paquete DTS por última vez hasta el momento de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="55202-107">A view that represents an incremental window on the completed activity instances from the moment that you ran the DTS package for the last time to the moment of the snapshot</span></span>  
  
  <span data-ttu-id="55202-108">BAM la archiva mediante un bloqueo exclusivo en el almacenamiento de la actividad durante poco tiempo, lo que impide que se escriba cualquier dato a la misma vez.</span><span class="sxs-lookup"><span data-stu-id="55202-108">BAM achieves this by taking an exclusive lock on the Activity Storage for a very short time, thus preventing any data writing at the same time.</span></span> <span data-ttu-id="55202-109">Una vez que BAM ha realizado la instantánea, puede que el paquete DTS tarde en ejecutarse, pero BAM omitirá cualquier dato nuevo que se reciba durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="55202-109">Once BAM takes the snapshot, the DTS package might take a long time to run, but BAM will ignore any new data that arrives during the processing.</span></span> <span data-ttu-id="55202-110">En la siguiente ilustración se muestra esta actividad:</span><span class="sxs-lookup"><span data-stu-id="55202-110">The following figure illustrates this activity:</span></span>  
  
  <span data-ttu-id="55202-111">![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")</span><span class="sxs-lookup"><span data-stu-id="55202-111">![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")</span></span>  
  <span data-ttu-id="55202-112">Agregaciones programadas de BAM</span><span class="sxs-lookup"><span data-stu-id="55202-112">BAM Scheduled Aggregations</span></span>  
  
  <span data-ttu-id="55202-113">En la ilustración, BAM transporta datos sobre las instancias de actividad completadas al cubo OLAP de instancias completas.</span><span class="sxs-lookup"><span data-stu-id="55202-113">In the figure, BAM moves data about the completed activity instances to the Completed Instances OLAP cube.</span></span> <span data-ttu-id="55202-114">BAM procesa este cubo de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="55202-114">BAM incrementally processes this cube.</span></span>  
  
  <span data-ttu-id="55202-115">A la misma vez, BAM transporta los datos sobre las actividades que todavía están en ejecución al cubo de instancias activas, que procesará por completo el paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="55202-115">At the same time, BAM moves the data about the activities still in progress to the Active Instances cube, which the DTS package fully processes.</span></span> <span data-ttu-id="55202-116">Se puede aceptar porque BAM asume que solo un número relativamente pequeño de actividades están en ejecución en un momento en concreto.</span><span class="sxs-lookup"><span data-stu-id="55202-116">This is acceptable, because BAM assumes that only a relatively small number of activities are in progress at any given moment.</span></span>  
  
  <span data-ttu-id="55202-117">Los datos de las agregaciones programadas están disponibles en el cubo virtual que oculta la diferencia entre las actividades actuales y completas.</span><span class="sxs-lookup"><span data-stu-id="55202-117">Data for the scheduled aggregations is available from a virtual cube that hides the difference between the completed and current activities.</span></span> <span data-ttu-id="55202-118">Para obtener más información, consulte [consultar datos agregados programados](../core/querying-scheduled-aggregated-data.md).</span><span class="sxs-lookup"><span data-stu-id="55202-118">For more information, see [Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55202-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="55202-119">See Also</span></span>  
 [<span data-ttu-id="55202-120">¿Qué es una agregación?</span><span class="sxs-lookup"><span data-stu-id="55202-120">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)