---
title: "Contadores de rendimiento de deshidratación de orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ab92e0e-6a33-4aaa-ab14-0c82322b04d5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e81052f0061ff4ad802a084536c09d48cb6cb55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-dehydration-performance-counters"></a><span data-ttu-id="64590-102">Contadores de rendimiento de deshidratación de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="64590-102">Orchestration Dehydration Performance Counters</span></span>
<span data-ttu-id="64590-103">En la tabla siguiente se incluyen los nombres de los contadores de rendimiento del motor de orquestaciones que son específicos para la supervisión del comportamiento de deshidratación.</span><span class="sxs-lookup"><span data-stu-id="64590-103">The following table lists the names of Orchestration Engine performance counters that are specific to monitoring the behavior of dehydration.</span></span> <span data-ttu-id="64590-104">Use el monitor de rendimiento para observar estos contadores mientras ajusta los parámetros de deshidratación.</span><span class="sxs-lookup"><span data-stu-id="64590-104">Use Performance Monitor to watch these counters while tuning your dehydration parameters.</span></span>  
  
|<span data-ttu-id="64590-105">Contador de rendimiento de deshidratación</span><span class="sxs-lookup"><span data-stu-id="64590-105">Dehydration Performance Counter</span></span>|<span data-ttu-id="64590-106">Description</span><span class="sxs-lookup"><span data-stu-id="64590-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="64590-107">Orquestaciones deshidratables</span><span class="sxs-lookup"><span data-stu-id="64590-107">Dehydratable orchestrations</span></span>|<span data-ttu-id="64590-108">Número de instancias de orquestación que se pueden deshidratar y que están actualmente alojadas por la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="64590-108">Number of orchestrations instances that can be dehydrated which are currently hosted by the host instance.</span></span>|  
|<span data-ttu-id="64590-109">Deshidratando orquestaciones</span><span class="sxs-lookup"><span data-stu-id="64590-109">Dehydrating orchestrations</span></span>|<span data-ttu-id="64590-110">Número de orquestaciones que se están deshidratando.</span><span class="sxs-lookup"><span data-stu-id="64590-110">Number of orchestrations that are in the process of dehydrating.</span></span>|  
|<span data-ttu-id="64590-111">Ciclo de deshidratación en curso</span><span class="sxs-lookup"><span data-stu-id="64590-111">Dehydration cycle in progress</span></span>|<span data-ttu-id="64590-112">Indica si es actualmente hay un ciclo de deshidratación en curso.</span><span class="sxs-lookup"><span data-stu-id="64590-112">Indicates whether there is a dehydration cycle currently in progress.</span></span>|  
|<span data-ttu-id="64590-113">Ciclos de deshidratación</span><span class="sxs-lookup"><span data-stu-id="64590-113">Dehydration cycles</span></span>|<span data-ttu-id="64590-114">Número de ciclos de deshidratación completados.</span><span class="sxs-lookup"><span data-stu-id="64590-114">Number of dehydration cycles completed.</span></span>|  
|<span data-ttu-id="64590-115">Umbral de deshidratación</span><span class="sxs-lookup"><span data-stu-id="64590-115">Dehydration threshold</span></span>|<span data-ttu-id="64590-116">Número en milisegundos que determina la forma agresiva en que se deshidratan orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="64590-116">Number in milliseconds that determines how aggressively orchestrations are being dehydrated.</span></span> <span data-ttu-id="64590-117">Si el motor de orquestaciones predice que una instancia será deshidratable durante un período superior a este umbral, deshidratará la instancia.</span><span class="sxs-lookup"><span data-stu-id="64590-117">If the orchestration engine predicts that an instance will be dehydratable for an amount of time longer than this threshold, it will dehydrate the instance.</span></span>|  
|<span data-ttu-id="64590-118">Orquestaciones deshidratadas</span><span class="sxs-lookup"><span data-stu-id="64590-118">Orchestrations dehydrated</span></span>|<span data-ttu-id="64590-119">Número de instancias de orquestación deshidratadas desde que se inició la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="64590-119">Number of orchestration instances dehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="64590-120">Orquestaciones deshidratadas/seg.</span><span class="sxs-lookup"><span data-stu-id="64590-120">Orchestrations dehydrated/sec</span></span>|<span data-ttu-id="64590-121">Número promedio deshidratado por segundo.</span><span class="sxs-lookup"><span data-stu-id="64590-121">Average number dehydrated per second.</span></span>|  
|<span data-ttu-id="64590-122">Orquestaciones rehidratadas</span><span class="sxs-lookup"><span data-stu-id="64590-122">Orchestrations rehydrated</span></span>|<span data-ttu-id="64590-123">Número de instancias de orquestación rehidratadas desde que se inició la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="64590-123">Number of orchestration instances rehydrated since the host instance started.</span></span>|  
|<span data-ttu-id="64590-124">Orquestaciones rehidratadas/seg.</span><span class="sxs-lookup"><span data-stu-id="64590-124">Orchestrations rehydrated/sec</span></span>|<span data-ttu-id="64590-125">Número promedio rehidratado por segundo</span><span class="sxs-lookup"><span data-stu-id="64590-125">Average number rehydrated per second</span></span>|  
|<span data-ttu-id="64590-126">Orquestaciones programadas para deshidratación</span><span class="sxs-lookup"><span data-stu-id="64590-126">Orchestrations scheduled for dehydration</span></span>|<span data-ttu-id="64590-127">Número de orquestaciones deshidratables para las que existe una solicitud de deshidratación pendiente.</span><span class="sxs-lookup"><span data-stu-id="64590-127">Number of dehydratable orchestrations for which there is a dehydration request pending.</span></span>|