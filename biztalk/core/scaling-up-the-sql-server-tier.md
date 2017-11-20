---
title: "Cómo ampliar el nivel de SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- SQL Server, scaling
- scaling, scaling up
- scaling, strategies
ms.assetid: 4352c4af-6861-43d9-b433-9ca25668b439
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c654c4a3b1bba166ae8a49918f6ef31827cf041
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-up-the-sql-server-tier"></a><span data-ttu-id="690ed-102">Escalar el nivel del servidor SQL Server verticalmente</span><span class="sxs-lookup"><span data-stu-id="690ed-102">Scaling Up the SQL Server Tier</span></span>
<span data-ttu-id="690ed-103">En este modelo, la base de datos de cuadro de mensajes SQL existente se actualiza para escalarse según los requisitos de rendimiento o latencia.</span><span class="sxs-lookup"><span data-stu-id="690ed-103">In this pattern, the existing SQL MessageBox database is upgraded to scale according to the requirements in throughput or latency.</span></span>  
  
 <span data-ttu-id="690ed-104">La siguiente ilustración muestra un caso donde la base de datos de cuadro de mensajes principal se actualiza del servidor del procesador quad al servidor del procesador 8.</span><span class="sxs-lookup"><span data-stu-id="690ed-104">The following figure shows a scenario where the master MessageBox database is upgraded from quad processor server to 8 processor server.</span></span>  
  
 <span data-ttu-id="690ed-105">![Escala &#45; una copia de seguridad MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span><span class="sxs-lookup"><span data-stu-id="690ed-105">![Scale&#45;up MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span></span>  
  
## <a name="when-to-scale-up-the-sql-tier"></a><span data-ttu-id="690ed-106">Cuándo se debe escalar el nivel SQL verticalmente</span><span class="sxs-lookup"><span data-stu-id="690ed-106">When to Scale-up the SQL Tier</span></span>  
  
-   <span data-ttu-id="690ed-107">Cuando pueda realizar el escalamiento vertical de la base de datos de cuadro de mensajes principal.</span><span class="sxs-lookup"><span data-stu-id="690ed-107">When you can scale up the master MessageBox database.</span></span>  
  
-   <span data-ttu-id="690ed-108">Cuando la base de datos de cuadro de mensajes principal forme un cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="690ed-108">When the master MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="690ed-109">Estos cuellos de botella pueden ser:</span><span class="sxs-lookup"><span data-stu-id="690ed-109">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="690ed-110">**CPU** en el caso de escenarios de orquestación muy caros y complejos, cuadro de mensajes consume muchos recursos de CPU.</span><span class="sxs-lookup"><span data-stu-id="690ed-110">**CPU** In case of very expensive and complex orchestration scenarios, Message box consumes heavy CPU resources.</span></span> <span data-ttu-id="690ed-111">Escalar el servidor SQL verticalmente, aumentando el número de CPU, debería ampliar el escenario.</span><span class="sxs-lookup"><span data-stu-id="690ed-111">Scaling-up the SQL server by adding more CPUs should scale the scenario.</span></span>  
  
    -   <span data-ttu-id="690ed-112">**Memoria o E/S** memoria o E/S puede ser el cuello de botella y se pueden actualizar.</span><span class="sxs-lookup"><span data-stu-id="690ed-112">**Memory or I/O** Memory or I/O can be bottleneck and can be upgraded.</span></span>  
  
-   <span data-ttu-id="690ed-113">Cuando el escalamiento vertical resulta más económico que el escalamiento horizontal, y el escalamiento vertical puede solucionar el cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="690ed-113">When scaling-up is cheaper than scaling-out and scaling-up can address the bottleneck.</span></span> <span data-ttu-id="690ed-114">Por ejemplo, si la base de datos de cuadro de mensajes principal tiene un problema con la contención de bloqueos de SQL, el escalamiento vertical no puede resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="690ed-114">For example, if the master MessageBox database has an issue with SQL lock contention, this issue cannot be solved by scaling-up.</span></span>  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a><span data-ttu-id="690ed-115">¿Cuándo se decide que no se puede realizar el escalamiento vertical en SQL?</span><span class="sxs-lookup"><span data-stu-id="690ed-115">When do you decide SQL cannot scale-up?</span></span>  
 <span data-ttu-id="690ed-116">El escalamiento vertical no puede solucionar los cuellos de botella de la contención de bloqueos en el nivel SQL.</span><span class="sxs-lookup"><span data-stu-id="690ed-116">Scale-up cannot address lock contention bottlenecks on the SQL tier.</span></span> <span data-ttu-id="690ed-117">Si se alcanzan estos tipos de cuellos de botella, el escalamiento horizontal resulta una mejor opción que el vertical.</span><span class="sxs-lookup"><span data-stu-id="690ed-117">If these kinds of bottlenecks are hit, scale-out is better option than scale-up.</span></span>  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a><span data-ttu-id="690ed-118">Estrategias y consideraciones para realizar el escalamiento vertical del nivel SQL</span><span class="sxs-lookup"><span data-stu-id="690ed-118">Strategies and Considerations for Scaling Up the SQL Tier</span></span>  
  
-   <span data-ttu-id="690ed-119">Realice primero un escalamiento vertical de la base de datos de cuadro de mensajes principal, y luego lleve a cabo el escalamiento horizontal.</span><span class="sxs-lookup"><span data-stu-id="690ed-119">Scale-up the master MessageBox database first and then scale-out.</span></span>  
  
-   <span data-ttu-id="690ed-120">La base de datos de cuadro de mensajes principal será finalmente el cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="690ed-120">The master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="690ed-121">Por lo tanto, la base de datos de cuadro de mensajes principal debería ser más rápida y más grande (por ejemplo, un equipo de 64 bits basado en Itanium o x64 con doble núcleo).</span><span class="sxs-lookup"><span data-stu-id="690ed-121">So, the master MessageBox database should be faster and bigger (for example, an Itanium-based 64-bit or x64-based, dual core computer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="690ed-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="690ed-122">See Also</span></span>  
 <span data-ttu-id="690ed-123">[Escalar horizontalmente el nivel de servidor BizTalk Server](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-123">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="690ed-124">[Cómo ampliar el nivel de servidor BizTalk Server](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-124">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="690ed-125">[Escalar horizontalmente el nivel de servidor SQL](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-125">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="690ed-126">[Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-126">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="690ed-127">[Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-127">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="690ed-128">[Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-128">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="690ed-129">[Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-129">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="690ed-130">[Bases de datos de escala horizontal](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="690ed-130">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="690ed-131">Agrupación en clústeres las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="690ed-131">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)