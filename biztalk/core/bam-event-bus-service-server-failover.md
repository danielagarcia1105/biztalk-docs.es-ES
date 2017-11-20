---
title: "Conmutación por error el servidor de servicio BAM eventos Bus | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f12378c8-09bb-45c1-ade1-d9b20131461f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c1fafc3e97d9905a6efd0de8ff0f389c2a389bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-event-bus-service-server-failover"></a><span data-ttu-id="0127a-102">Conmutación por error del servicio de bus de eventos de BAM</span><span class="sxs-lookup"><span data-stu-id="0127a-102">BAM Event Bus Service Server Failover</span></span>
<span data-ttu-id="0127a-103">El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos.</span><span class="sxs-lookup"><span data-stu-id="0127a-103">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span>  
  
 <span data-ttu-id="0127a-104">Cuando habilite el servicio de bus de eventos BAM en varios equipos y se produzca un error en el servicio, la conmutación por errores lógicos detectará que un servicio de bus de eventos BAM ha terminado y la lógica iniciará automáticamente una nueva instancia del servicio de eventos BAM en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="0127a-104">When you enable the BAM Event Bus service on multiple computers, and the service fails, failover logic will detect that a BAM Event Bus service has terminated, and the logic automatically starts a new instance of the BAM Event Bus service on another computer.</span></span>  
  
 <span data-ttu-id="0127a-105">La siguiente ilustración muestra el modo en que el bus de eventos BAM controla el equipo o los errores de red mediante la realización de un equilibrio de carga simple.</span><span class="sxs-lookup"><span data-stu-id="0127a-105">The following figure displays how the BAM Event Bus handles computer or network failures by performing simple load balancing.</span></span> <span data-ttu-id="0127a-106">Se han configurado dos orígenes y un destino antes de que se inicie el servicio de bus de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="0127a-106">Two sources and one destination were configured before the BAM Event Bus service starts.</span></span>  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
<span data-ttu-id="0127a-107">Cómo se equilibra la carga del servicio de bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="0127a-107">How the BAM Event Bus service load balances</span></span>  
  
 <span data-ttu-id="0127a-108">La carga del servicio de bus de eventos BAM se equilibra mediante la realización de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0127a-108">The BAM Event Bus service load balances by performing the following:</span></span>  
  
-   <span data-ttu-id="0127a-109">**R: Server1 procesa los datos del evento desde 2 orígenes (sesiones)**.</span><span class="sxs-lookup"><span data-stu-id="0127a-109">**A: Server1 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="0127a-110">Antes de que se cree una instancia del servicio de bus de eventos BAM en Server2, se crea una instancia de orquestación de bus de eventos BAM en Server1.</span><span class="sxs-lookup"><span data-stu-id="0127a-110">Before an instance of the BAM Event Bus service is created on Server2, a BAM Event Bus orchestration instance is created on Server1.</span></span> <span data-ttu-id="0127a-111">El servidor encuentra que no hay otros servidores disponibles y por tanto, recoge ambas sesiones para Src1 y Src2.</span><span class="sxs-lookup"><span data-stu-id="0127a-111">The server finds that there are no other servers available, and therefore picks up both sessions for Src1 and Src2.</span></span>  
  
-   <span data-ttu-id="0127a-112">**B: Server2 se pone en línea y se une al grupo de Bus de sucesos SAE**.</span><span class="sxs-lookup"><span data-stu-id="0127a-112">**B: Server2 is brought online and joins the BAM Event Bus pool**.</span></span> <span data-ttu-id="0127a-113">Después de que se cree una instancia del servicio de bus de eventos BAM en Server2, Server1 coloca una sesión de servicio de bus de eventos BAM y Server2 la recoge.</span><span class="sxs-lookup"><span data-stu-id="0127a-113">After an instance of the BAM Event Bus service is created on Server2, Server1 drops one BAM Event Bus service session and Server2 picks it up.</span></span>  
  
-   <span data-ttu-id="0127a-114">**C: se produce un error en Server1**.</span><span class="sxs-lookup"><span data-stu-id="0127a-114">**C: Server1 fails**.</span></span> <span data-ttu-id="0127a-115">Se produce un error en Server1 después de que Server2 se une al grupo de bus de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="0127a-115">Server1 fails after Server2 joins the BAM Event Bus pool.</span></span>  
  
-   <span data-ttu-id="0127a-116">**D: Server2 procesa los datos del evento desde 2 orígenes (sesiones)**.</span><span class="sxs-lookup"><span data-stu-id="0127a-116">**D: Server2 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="0127a-117">Server2 recoge ambas sesiones para Src1 y Src2.</span><span class="sxs-lookup"><span data-stu-id="0127a-117">Server2 picks up both sessions for Src1 and Src2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0127a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0127a-118">See Also</span></span>  
 <span data-ttu-id="0127a-119">[Administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="0127a-119">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="0127a-120">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="0127a-120">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="0127a-121">Actividad económica (BAM) de supervisión</span><span class="sxs-lookup"><span data-stu-id="0127a-121">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)