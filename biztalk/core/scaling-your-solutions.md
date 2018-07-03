---
title: Escalar soluciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7587c25a752c8613701c9177c42fad001e0e267
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994045"
---
# <a name="scaling-your-solutions"></a><span data-ttu-id="ed15e-102">Escalar soluciones</span><span class="sxs-lookup"><span data-stu-id="ed15e-102">Scaling Your Solutions</span></span>
<span data-ttu-id="ed15e-103">BizTalk Server proporciona una arquitectura que resulta muy adecuada para la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="ed15e-103">BizTalk Server architecture provides a very good support for scalability.</span></span> <span data-ttu-id="ed15e-104">Los patrones de escalamiento que se seleccionen dependerán de la complejidad de su escenario, así como de los requisitos de hardware y de latencia o rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ed15e-104">The scaling patterns that you choose depend on complexity of your scenario, hardware and the throughput/Latency requirements.</span></span> <span data-ttu-id="ed15e-105">Es aconsejable comenzar con una topología más pequeña en un principio e intentar escalarla verticalmente o abreviarla en función de las directrices de esta sección.</span><span class="sxs-lookup"><span data-stu-id="ed15e-105">You should start with a smaller topology initially and try to scale-up or down based on the guidelines in this section.</span></span>  
  
## <a name="scaling-out-and-scaling-up"></a><span data-ttu-id="ed15e-106">Escalar de forma horizontal y vertical</span><span class="sxs-lookup"><span data-stu-id="ed15e-106">Scaling Out and Scaling Up</span></span>  
 <span data-ttu-id="ed15e-107">El sistema de BizTalk Server puede escalarse de dos formas:</span><span class="sxs-lookup"><span data-stu-id="ed15e-107">There are two ways to scale your BizTalk Server system:</span></span>  
  
- <span data-ttu-id="ed15e-108">El escalamiento horizontal es el proceso que consiste en agregar más equipos.</span><span class="sxs-lookup"><span data-stu-id="ed15e-108">Scaling-out is the process of adding additional computers.</span></span> <span data-ttu-id="ed15e-109">Por ejemplo, si se produce un cuello de botella en BizTalk Server debido a los recursos de CPU, la agregación de otro servidor proporcionaría el doble de recursos de CPU y, con ello, el doble de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ed15e-109">For example, if BizTalk Server is bottlenecked by CPU resources, adding another server provides double the CPU resources which may provide double the throughput.</span></span>  
  
- <span data-ttu-id="ed15e-110">El escalamiento vertical es el proceso que consiste en actualizar el equipo existente.</span><span class="sxs-lookup"><span data-stu-id="ed15e-110">Scaling-up is process of upgrading the existing computer.</span></span> <span data-ttu-id="ed15e-111">Por ejemplo, puede actualizar el equipo que tiene instalado BizTalk Server de 4 a 8 procesadores.</span><span class="sxs-lookup"><span data-stu-id="ed15e-111">For example, you can upgrade a BizTalk Server computer from a 4 processor machine to an 8 processor.</span></span>  
  
  <span data-ttu-id="ed15e-112">Un sistema de BizTalk Server tiene dos niveles: el nivel de servidor BizTalk Server y el nivel de SQL Server, que contiene las bases de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ed15e-112">A BizTalk Server system has two tiers: the BizTalk Server tier and the SQL Server tier, which contains your MessageBox databases.</span></span> <span data-ttu-id="ed15e-113">Los dos niveles pueden escalarse de forma horizontal o vertical, independientemente del escenario que posea.</span><span class="sxs-lookup"><span data-stu-id="ed15e-113">In any scenario, you can scale out or scale up each tier.</span></span> <span data-ttu-id="ed15e-114">Por tanto, puede escalar BizTalk Server y la base de datos de cuadro de mensajes de forma horizontal o vertical.</span><span class="sxs-lookup"><span data-stu-id="ed15e-114">That is, you can scale-out BizTalk Server and the MessageBox database, or scale up both of them.</span></span>  
  
  <span data-ttu-id="ed15e-115">En la mayoría de los casos, el nivel de BizTalk Server es el primer lugar en que se produce un cuello de botella, por lo que se mejora el rendimiento escalando este nivel de forma horizontal. No obstante, en un momento determinado, en función de la complejidad del sistema y del hardware, es posible que no pueda seguir escalando el nivel de BizTalk de forma horizontal y que se produzca el cuello de botella en el nivel de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed15e-115">In most cases, the BizTalk tier becomes a bottleneck first, and you start improving performance by scaling it out. But, at some point, depending on complexity of your system and the hardware you use, you can’t scale out the BizTalk tier anymore and the SQL Server tier becomes the bottleneck.</span></span> <span data-ttu-id="ed15e-116">Por tanto, escalará de forma vertical el nivel de SQL Server y, más adelante, lo escalará de forma horizontal agregando más bases de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ed15e-116">Then, you scale up the SQL Server tier, and next scale it out by adding more MessageBox databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed15e-117">Una base de datos de cuadro de mensajes nueva no implica la instalación de otro servidor.</span><span class="sxs-lookup"><span data-stu-id="ed15e-117">A new MessageBox database does not necessarily mean another server here.</span></span> <span data-ttu-id="ed15e-118">Un único servidor SQL Server puede disponer de varias bases de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ed15e-118">A single SQL server can have multiple MessageBox databases.</span></span> <span data-ttu-id="ed15e-119">Además, disponer de varias bases de datos de cuadro de mensajes puede provocar un aumento del costo de DTC y saltos de red cuando las bases de datos se encuentran en distintos equipos.</span><span class="sxs-lookup"><span data-stu-id="ed15e-119">Also, multiple MessageBox databases incur DTC cost and network hop if the databases are on different computers.</span></span>  
  
 <span data-ttu-id="ed15e-120">En teoría, puede escalar el nivel de SQL Server de forma horizontal cuantas veces desee, siempre que no se sature la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ed15e-120">In theory, the SQL Server tier can scale out indefinitely as long as the master MessageBox database is not saturated.</span></span>  
  
 <span data-ttu-id="ed15e-121">En los temas de esta sección se describen con mayor detalle los patrones de escalamiento.</span><span class="sxs-lookup"><span data-stu-id="ed15e-121">The topics in this section describe these scaling patterns in more detail.</span></span> <span data-ttu-id="ed15e-122">Además, se explica cómo debe escalarse cada patrón y cómo determinar cuándo no se puede seguir utilizando un patrón determinado de escalamiento en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ed15e-122">They also explain how to scale each pattern and how to determine when you can no longer use that pattern to scale your system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed15e-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ed15e-123">In This Section</span></span>  
  
-   [<span data-ttu-id="ed15e-124">¿Qué es la escalabilidad?</span><span class="sxs-lookup"><span data-stu-id="ed15e-124">What Is Scalability?</span></span>](../core/what-is-scalability.md)  
  
-   [<span data-ttu-id="ed15e-125">Escalar horizontalmente el nivel de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ed15e-125">Scaling Out the BizTalk Server Tier</span></span>](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="ed15e-126">Escalar verticalmente el nivel de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ed15e-126">Scaling Up the BizTalk Server Tier</span></span>](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="ed15e-127">Escalar horizontalmente el nivel de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed15e-127">Scaling Out the SQL Server Tier</span></span>](../core/scaling-out-the-sql-server-tier.md)  
  
-   [<span data-ttu-id="ed15e-128">Escalar verticalmente el nivel de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed15e-128">Scaling Up the SQL Server Tier</span></span>](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed15e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed15e-129">See Also</span></span>  
 <span data-ttu-id="ed15e-130">[Hosts de recepción escalados horizontalmente](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ed15e-130">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="ed15e-131">[Hosts de procesamiento escalados horizontalmente](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ed15e-131">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="ed15e-132">[Hosts de envío escalados horizontalmente](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ed15e-132">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="ed15e-133">[Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="ed15e-133">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="ed15e-134">[Bases de datos escaladas horizontalmente](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="ed15e-134">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="ed15e-135">Agrupación en clústeres de las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ed15e-135">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)