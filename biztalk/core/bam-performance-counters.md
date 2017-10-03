---
title: Contadores de rendimiento de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4307f72f149405fbc04e4e6cc51efe87229c2bff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-performance-counters"></a><span data-ttu-id="7b877-102">Contadores de rendimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="7b877-102">BAM Performance Counters</span></span>
<span data-ttu-id="7b877-103">Los contadores de rendimiento permiten controlar aspectos específicos del trabajo llevado a cabo por el servicio de bus de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="7b877-103">Performance counters allow you to monitor specific aspects of work performed by the BAM Event Bus Service.</span></span> <span data-ttu-id="7b877-104">Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="7b877-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="7b877-105">En la tabla siguiente se enumeran los contadores de rendimiento disponibles en la Supervisión de la actividad económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="7b877-105">The following table lists the performance counters available in Business Activity Monitoring.</span></span>  
  
|<span data-ttu-id="7b877-106">Contador</span><span class="sxs-lookup"><span data-stu-id="7b877-106">Counter</span></span>|<span data-ttu-id="7b877-107">Description</span><span class="sxs-lookup"><span data-stu-id="7b877-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b877-108">Eventos que se están procesando</span><span class="sxs-lookup"><span data-stu-id="7b877-108">Events being processed</span></span>|<span data-ttu-id="7b877-109">Número de eventos que está procesando actualmente el servicio de bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="7b877-109">The number of events the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="7b877-110">Lotes que se están procesando</span><span class="sxs-lookup"><span data-stu-id="7b877-110">Batches being processed</span></span>|<span data-ttu-id="7b877-111">Número de lotes que está procesando actualmente el servicio de bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="7b877-111">The number of batches the BAM Event Bus Service is currently processing</span></span>|  
|<span data-ttu-id="7b877-112">eventos asignados</span><span class="sxs-lookup"><span data-stu-id="7b877-112">Events Committed</span></span>|<span data-ttu-id="7b877-113">Número de eventos que el servicio de bus de eventos BAM ha asignado al servidor SQL Server en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="7b877-113">The number of events the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="7b877-114">Registros asignados</span><span class="sxs-lookup"><span data-stu-id="7b877-114">Records Committed</span></span>|<span data-ttu-id="7b877-115">Número de registros que el servicio de bus de eventos BAM ha asignado al servidor SQL Server en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="7b877-115">The number of records the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="7b877-116">Lotes asignados</span><span class="sxs-lookup"><span data-stu-id="7b877-116">Batches Committed</span></span>|<span data-ttu-id="7b877-117">Número de lotes que el servicio de bus de eventos BAM ha asignado al servidor SQL Server en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="7b877-117">The number of batches the BAM Event Bus Service has committed to SQL Server in the last second.</span></span>|  
|<span data-ttu-id="7b877-118">N.º total de eventos</span><span class="sxs-lookup"><span data-stu-id="7b877-118">Total Events</span></span>|<span data-ttu-id="7b877-119">Número de eventos que el servicio de bus de eventos BAM ha procesado desde que fue iniciado.</span><span class="sxs-lookup"><span data-stu-id="7b877-119">The number of events the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="7b877-120">N.º total de registros</span><span class="sxs-lookup"><span data-stu-id="7b877-120">Total Records</span></span>|<span data-ttu-id="7b877-121">Número de registros que el servicio de bus de eventos BAM ha procesado desde que fue iniciado.</span><span class="sxs-lookup"><span data-stu-id="7b877-121">Then number of records the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="7b877-122">N.º total de lotes</span><span class="sxs-lookup"><span data-stu-id="7b877-122">Total Batches</span></span>|<span data-ttu-id="7b877-123">Número de lotes que el servicio de bus de eventos BAM ha procesado desde que fue iniciado.</span><span class="sxs-lookup"><span data-stu-id="7b877-123">Then number of batches the BAM Event Bus Service has processed since you started it.</span></span>|  
|<span data-ttu-id="7b877-124">N.º total de lotes erróneos</span><span class="sxs-lookup"><span data-stu-id="7b877-124">Total Failed Batches</span></span>|<span data-ttu-id="7b877-125">Número de lotes que el servicio de bus de eventos BAM no ha podido procesar desde que fue iniciado.</span><span class="sxs-lookup"><span data-stu-id="7b877-125">Then number of batches the BAM Event Bus Service has failed to process since you started it.</span></span>|  
|<span data-ttu-id="7b877-126">N.º total de eventos erróneos</span><span class="sxs-lookup"><span data-stu-id="7b877-126">Total Failed Events</span></span>|<span data-ttu-id="7b877-127">Número de eventos que el servicio de bus de eventos BAM no ha podido procesar desde que fue iniciado.</span><span class="sxs-lookup"><span data-stu-id="7b877-127">Then number of events the BAM Event Bus Service has failed to process since you started it.</span></span>|  
  
 <span data-ttu-id="7b877-128">Los contadores de rendimiento están ubicados en el monitor de rendimiento (perfmon), bajo el objeto de rendimiento BizTalk:TDDS.</span><span class="sxs-lookup"><span data-stu-id="7b877-128">The performance counters are located in the Performance Monitor (perfmon) under the BizTalk:TDDS performance object.</span></span> <span data-ttu-id="7b877-129">El nombre de instancia de los contadores de rendimiento es una combinación del nombre del servidor de origen y el nombre de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="7b877-129">The instance name of the performance counters are a combination of the source server name and the name of the source database.</span></span> <span data-ttu-id="7b877-130">Si dos de los servicios de bus de eventos BAM se están ejecutando en el mismo equipo, utilizando dos bases de datos de origen distintas, verá dos instancias de los contadores de servicios de bus de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="7b877-130">If two of the BAM Event Bus Services are running on the same computer against two different source databases, you will see two instances of the BAM Event Bus Service counters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b877-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b877-131">See Also</span></span>  
 <span data-ttu-id="7b877-132">[Administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="7b877-132">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="7b877-133">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="7b877-133">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="7b877-134">Administración de BAM</span><span class="sxs-lookup"><span data-stu-id="7b877-134">Managing BAM</span></span>](../core/managing-bam.md)