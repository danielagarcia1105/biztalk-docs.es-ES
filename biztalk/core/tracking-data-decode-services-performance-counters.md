---
title: "Contadores de rendimiento de servicios de descodificación de datos de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99ec03138e455c671e9ccb69aa8bc4c5588d287c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-data-decode-services-performance-counters"></a><span data-ttu-id="7a3fd-102">Contadores de rendimiento del Servicio de descodificación de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7a3fd-102">Tracking Data Decode Services Performance Counters</span></span>
<span data-ttu-id="7a3fd-103">Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="7a3fd-104">Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="7a3fd-105">Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: TDDS** categoría de objeto de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="7a3fd-105">The following performance counters are accessible for each host instance under the **BizTalk:TDDS** performance object category:</span></span>  
  
|<span data-ttu-id="7a3fd-106">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="7a3fd-106">**Category**</span></span>|<span data-ttu-id="7a3fd-107">**Contador**</span><span class="sxs-lookup"><span data-stu-id="7a3fd-107">**Counter**</span></span>|<span data-ttu-id="7a3fd-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="7a3fd-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="7a3fd-109">BizTalk:TDDS</span><span class="sxs-lookup"><span data-stu-id="7a3fd-109">BizTalk:TDDS</span></span>|<span data-ttu-id="7a3fd-110">Lotes que se están procesando</span><span class="sxs-lookup"><span data-stu-id="7a3fd-110">Batches being processed</span></span>|<span data-ttu-id="7a3fd-111">Número de lotes que se procesan dentro de la transacción actual SQL.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-111">The number of batches that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="7a3fd-112">Lotes asignados</span><span class="sxs-lookup"><span data-stu-id="7a3fd-112">Batches committed</span></span>|<span data-ttu-id="7a3fd-113">Número de lotes asignados a la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-113">The number of batches committed to the destination database.</span></span>|  
||<span data-ttu-id="7a3fd-114">Eventos que se están procesando</span><span class="sxs-lookup"><span data-stu-id="7a3fd-114">Events being processed</span></span>|<span data-ttu-id="7a3fd-115">Número de eventos que se procesan dentro de la transacción actual SQL.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-115">The number of events that are being processed inside of the current SQL transaction.</span></span>|  
||<span data-ttu-id="7a3fd-116">Eventos asignados</span><span class="sxs-lookup"><span data-stu-id="7a3fd-116">Event Committed</span></span>|<span data-ttu-id="7a3fd-117">Número de eventos asignados a la base de datos de destino en este segundo.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-117">The number of events committed to the destination database within this second.</span></span>|  
||<span data-ttu-id="7a3fd-118">Registros que se están procesando</span><span class="sxs-lookup"><span data-stu-id="7a3fd-118">Records being processed</span></span>|<span data-ttu-id="7a3fd-119">Número de registros que se procesan dentro de la transacción actual SQL.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-119">The number of records that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="7a3fd-120">Registros asignados</span><span class="sxs-lookup"><span data-stu-id="7a3fd-120">Records Committed</span></span>|<span data-ttu-id="7a3fd-121">Número de registros asignados a la base de datos de destino durante este segundo.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-121">The number of records committed to the destination database during this second.</span></span>|  
||<span data-ttu-id="7a3fd-122">N.º total de lotes</span><span class="sxs-lookup"><span data-stu-id="7a3fd-122">Total Batches</span></span>|<span data-ttu-id="7a3fd-123">Nº total de lotes procesados por TDDS.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-123">Total batches processed by TDDS.</span></span>|  
||<span data-ttu-id="7a3fd-124">N.º total de eventos</span><span class="sxs-lookup"><span data-stu-id="7a3fd-124">Total Events</span></span>|<span data-ttu-id="7a3fd-125">Nº total de eventos procesados por TDDS.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-125">Total events processed by TDDS.</span></span>|  
||<span data-ttu-id="7a3fd-126">N.º total de lotes erróneos</span><span class="sxs-lookup"><span data-stu-id="7a3fd-126">Total Failed Batches</span></span>|<span data-ttu-id="7a3fd-127">Número total de lotes que no pudo ejecutar TDDS</span><span class="sxs-lookup"><span data-stu-id="7a3fd-127">Total batches failed to run by TDDS.</span></span>|  
||<span data-ttu-id="7a3fd-128">N.º total de eventos erróneos</span><span class="sxs-lookup"><span data-stu-id="7a3fd-128">Total Failed Events</span></span>|<span data-ttu-id="7a3fd-129">Número total de eventos que no pudo ejecutar TDDS.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-129">Total events failed to run by TDDS.</span></span>|  
||<span data-ttu-id="7a3fd-130">N.º total de registros</span><span class="sxs-lookup"><span data-stu-id="7a3fd-130">Total Records</span></span>|<span data-ttu-id="7a3fd-131">Nº total de registros procesados por TDDS.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-131">Total records processed by TDDS.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="7a3fd-132">Para tener acceso a los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="7a3fd-132">To access performance counters</span></span>  
 <span data-ttu-id="7a3fd-133">Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-133">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="7a3fd-134">Si está usando Windows 2008</span><span class="sxs-lookup"><span data-stu-id="7a3fd-134">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="7a3fd-135">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-135">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="7a3fd-136">En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-136">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="7a3fd-137">En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk: TDDS** objeto de contador de rendimiento y seleccione los contadores que desea supervisar</span><span class="sxs-lookup"><span data-stu-id="7a3fd-137">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:TDDS** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="7a3fd-138">En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-138">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="7a3fd-139">Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-139">To select all available counter instances, select \<**All instances**>.</span></span>  
  
5.  <span data-ttu-id="7a3fd-140">Después de agregar los contadores, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-140">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="7a3fd-141">Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.</span><span class="sxs-lookup"><span data-stu-id="7a3fd-141">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a3fd-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a3fd-142">See Also</span></span>  
 <span data-ttu-id="7a3fd-143">[Trucos y sugerencias de rendimiento](../core/performance-tips-and-tricks.md) </span><span class="sxs-lookup"><span data-stu-id="7a3fd-143">[Performance Tips and Tricks](../core/performance-tips-and-tricks.md) </span></span>  
 <span data-ttu-id="7a3fd-144">[Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="7a3fd-144">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="7a3fd-145">[Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="7a3fd-145">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 [<span data-ttu-id="7a3fd-146">Optimizar el uso de recursos mediante la limitación de Host</span><span class="sxs-lookup"><span data-stu-id="7a3fd-146">Optimizing Resource Usage Through Host Throttling</span></span>](../core/optimizing-resource-usage-through-host-throttling.md)