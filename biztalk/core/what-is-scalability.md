---
title: ¿Qué es la escalabilidad? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, scalability
ms.assetid: ac6acefd-864a-4f22-a136-a1951fe71e96
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6208319fb8c195558101433cd1668ab0e0f064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-scalability"></a><span data-ttu-id="90749-103">¿Qué es la escalabilidad?</span><span class="sxs-lookup"><span data-stu-id="90749-103">What Is Scalability?</span></span>
<span data-ttu-id="90749-104">La escalabilidad es la capacidad de ampliación de un sistema para satisfacer las necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="90749-104">Scalability is the ability of a system to expand to meet your business needs.</span></span> <span data-ttu-id="90749-105">Para escalar un sistema, debe agregar hardware adicional o actualizar el hardware existente sin modificar mucho la aplicación.</span><span class="sxs-lookup"><span data-stu-id="90749-105">You scale a system by adding extra hardware or by upgrading the existing hardware without changing much of the application.</span></span> <span data-ttu-id="90749-106">En el contexto de un sistema con BizTalk Server, la escalabilidad hace referencia a la capacidad de escalar BizTalk cuando aumentan las necesidades de rendimiento y se necesitan reducir los tiempos de latencia.</span><span class="sxs-lookup"><span data-stu-id="90749-106">In the context of a BizTalk Server system, scalability refers to the ability of BizTalk to scale as your throughput needs increase, and if you need to reduce latency times.</span></span>  
  
 <span data-ttu-id="90749-107">Después de optimizar y ajustar varios componentes de BizTalk, es posible que observe que siguen existiendo cuellos de botella en los equipos con BizTalk o en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="90749-107">After you optimize and tune various components of BizTalk, you might still encounter bottlenecks on BizTalk computers or on the MessageBox database.</span></span> <span data-ttu-id="90749-108">Los tipos de cuello de botella habituales en los entornos de BizTalk son cuellos de botella de CPU, memoria, E/S y contención de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="90749-108">The types of bottlenecks that usually occur in BizTalk environments are CPU, memory, IO and lock contention bottlenecks.</span></span> <span data-ttu-id="90749-109">Cuando empiece a observar que hay cuellos de botella, tal vez deba actualizar el hardware o agregar nuevo hardware a la topología existente.</span><span class="sxs-lookup"><span data-stu-id="90749-109">When you start to encounter bottlenecks, you may need to either upgrade the hardware or add new hardware into the existing topology.</span></span> <span data-ttu-id="90749-110">Afortunadamente, la arquitectura de BizTalk Server le permite realizar fácilmente un escalamiento vertical y horizontal. Por ejemplo, puede agregar varios equipos con BizTalk Server al grupo, además de bases de datos de cuadro de mensajes adicionales.</span><span class="sxs-lookup"><span data-stu-id="90749-110">Fortunately, BizTalk Server architecture enables you to easily scale-up and scale-out. For example, you can add multiple BizTalk Server computers into the group and also add extra MessageBox databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90749-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="90749-111">See Also</span></span>  
 <span data-ttu-id="90749-112">[Escalar horizontalmente el nivel de servidor BizTalk Server](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="90749-112">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="90749-113">[Escalar horizontalmente el nivel de servidor SQL](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="90749-113">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="90749-114">[Cómo ampliar el nivel de servidor BizTalk Server](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="90749-114">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="90749-115">[Cómo ampliar el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="90749-115">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="90749-116">[Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="90749-116">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="90749-117">[Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="90749-117">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="90749-118">[Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="90749-118">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="90749-119">[Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="90749-119">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="90749-120">[Bases de datos de escala horizontal](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="90749-120">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="90749-121">Agrupación en clústeres las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="90749-121">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)