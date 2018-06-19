---
title: Cómo ampliar el nivel de servidor BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55176072cd33e20dd1024bf2d9d1c39bca4567a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270140"
---
# <a name="scaling-up-the-biztalk-server-tier"></a><span data-ttu-id="fddbd-102">Escalar el nivel de BizTalk Server verticalmente</span><span class="sxs-lookup"><span data-stu-id="fddbd-102">Scaling Up the BizTalk Server Tier</span></span>
<span data-ttu-id="fddbd-103">Para escalar el nivel de BizTalk verticalmente, debe actualizar la CPU, memoria, E/S y otros recursos.</span><span class="sxs-lookup"><span data-stu-id="fddbd-103">To scale up the BizTalk tier, you upgrade the CPU, memory, IO and other resources.</span></span> <span data-ttu-id="fddbd-104">En la siguiente ilustración se muestra un ejemplo de cómo escalar verticalmente el nivel de BizTalk de un equipo con dos procesadores a un equipo con cuatro procesadores.</span><span class="sxs-lookup"><span data-stu-id="fddbd-104">The following figure shows an example of how you might scale up the BizTalk tier from a two processor computer to a four processor computer.</span></span>  
  
 <span data-ttu-id="fddbd-105">![Escala &#45; una copia de seguridad BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span><span class="sxs-lookup"><span data-stu-id="fddbd-105">![Scale&#45;up BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span></span>  
  
 <span data-ttu-id="fddbd-106">Los escenarios para escalar el nivel de BizTalk verticalmente son similares a aquellos para escalar horizontalmente:</span><span class="sxs-lookup"><span data-stu-id="fddbd-106">The scenarios for scaling up your BizTalk tier are similar to when you choose to scale out:</span></span>  
  
-   <span data-ttu-id="fddbd-107">BizTalk Server se convierte en un cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="fddbd-107">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="fddbd-108">Alguno de los problemas siguientes puede causar el cuello de botella:</span><span class="sxs-lookup"><span data-stu-id="fddbd-108">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="fddbd-109">CPU: si el escenario utiliza canalizaciones, asignaciones u orquestaciones que hacen un uso intensivo de CPU, los servidores BizTalk Server no tendrán ningún espacio en cabeza adicional de CPU.</span><span class="sxs-lookup"><span data-stu-id="fddbd-109">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
-   <span data-ttu-id="fddbd-110">Memoria y E/S: si los equipos existentes han alcanzado su límite máximo de memoria y E/S y el equipo debe actualizarse.</span><span class="sxs-lookup"><span data-stu-id="fddbd-110">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, and the computer needs to be upgraded.</span></span>  
  
-   <span data-ttu-id="fddbd-111">Si escalar horizontalmente es demasiado costoso.</span><span class="sxs-lookup"><span data-stu-id="fddbd-111">Scaling out is too expensive.</span></span>  
  
-   <span data-ttu-id="fddbd-112">Si escalar horizontalmente no resuelve el cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="fddbd-112">If scale-out does not address the bottleneck.</span></span> <span data-ttu-id="fddbd-113">Por ejemplo, escalar horizontalmente no soluciona los siguientes cuellos de botella:</span><span class="sxs-lookup"><span data-stu-id="fddbd-113">For example, scaling out does not address the following bottlenecks:</span></span>  
  
    -   <span data-ttu-id="fddbd-114">Transformaciones de mensajes de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="fddbd-114">Large Message Transforms</span></span>  
  
    -   <span data-ttu-id="fddbd-115">Gran número de mensajes por intercambio</span><span class="sxs-lookup"><span data-stu-id="fddbd-115">Large number of messages per interchange</span></span>  
  
    -   <span data-ttu-id="fddbd-116">Alta utilización de memoria por parte de algunos componentes de BTS, como las canalizaciones o los adaptadores,</span><span class="sxs-lookup"><span data-stu-id="fddbd-116">High memory utilization by some of BTS components, such as pipelines or adapters</span></span>  
  
    -   <span data-ttu-id="fddbd-117">Un protocolo de transporte, por ejemplo EDI</span><span class="sxs-lookup"><span data-stu-id="fddbd-117">A transport, such as EDI</span></span>  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a><span data-ttu-id="fddbd-118">Si no se puede escalar el nivel de BizTalk verticalmente</span><span class="sxs-lookup"><span data-stu-id="fddbd-118">When You Can’t Scale Up the BizTalk Tier</span></span>  
  
-   <span data-ttu-id="fddbd-119">En la base de datos de cuadro de mensaje se produce el cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="fddbd-119">The MessageBox database is the bottleneck.</span></span>  
  
-   <span data-ttu-id="fddbd-120">El cuello de botella se produce en un adaptador.</span><span class="sxs-lookup"><span data-stu-id="fddbd-120">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="fddbd-121">Por ejemplo, si está utilizando un adaptador, después de aumentar el número de receptores de BizTalk, puede aumentar contención de bloqueo en la aplicación de back-end que extrae datos desde el adaptador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fddbd-121">For example, if you are using an adapter, after you increase the number of BizTalk receivers, lock contention might increase on the backend application where the BizTalk adapter is pulling data from.</span></span> <span data-ttu-id="fddbd-122">Esto limita su capacidad para escalar el adaptador verticalmente.</span><span class="sxs-lookup"><span data-stu-id="fddbd-122">This limits your ability to scale up the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fddbd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fddbd-123">See Also</span></span>  
 <span data-ttu-id="fddbd-124">[Escalar horizontalmente el nivel de servidor BizTalk Server](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-124">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="fddbd-125">[Cómo ampliar el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-125">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="fddbd-126">[Escalar horizontalmente el nivel de servidor SQL](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-126">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="fddbd-127">[Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-127">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="fddbd-128">[Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-128">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="fddbd-129">[Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-129">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="fddbd-130">[Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-130">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="fddbd-131">[Bases de datos de escala horizontal](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="fddbd-131">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="fddbd-132">Agrupación en clústeres las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fddbd-132">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)