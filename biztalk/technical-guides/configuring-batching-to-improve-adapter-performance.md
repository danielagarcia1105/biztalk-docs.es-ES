---
title: Configurar el procesamiento por lotes para mejorar el rendimiento del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65589925-af94-45f1-b501-37c21618b2cf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dbee8e5b238af0a6dc7f15d54b85d85e0c4b26c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300388"
---
# <a name="configuring-batching-to-improve-adapter-performance"></a><span data-ttu-id="256cd-102">Configurar el procesamiento por lotes para mejorar el rendimiento del adaptador</span><span class="sxs-lookup"><span data-stu-id="256cd-102">Configuring Batching to Improve Adapter Performance</span></span>
<span data-ttu-id="256cd-103">La forma en que un adaptador procesa un lote puede tener un efecto significativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="256cd-103">The way an adapter processes a batch can have a significant effect on performance.</span></span> <span data-ttu-id="256cd-104">Puesto que hay un retraso fijo con cada transacción, debe tratar de minimizar el número de transacciones mediante la combinación de varias operaciones en un solo lote.</span><span class="sxs-lookup"><span data-stu-id="256cd-104">Because there is a fixed delay associated with each transaction, you should try to minimize the number of transactions by combining more than one operation into a single batch.</span></span>  
  
 <span data-ttu-id="256cd-105">Si va a enviar mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en lotes, no limitan el tamaño del lote basándose solo en el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="256cd-105">If you are submitting messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in batches, do not limit the batch size based only on the message count.</span></span> <span data-ttu-id="256cd-106">Por ejemplo, si el tamaño del lote es dos y el adaptador obtiene cuatro mensajes de tamaño de 4 KB, 8 KB, 1 MB y 5 MB respectivamente, será el primer lote del tamaño de 12 KB y el segundo lote será de 6 MB de tamaño.</span><span class="sxs-lookup"><span data-stu-id="256cd-106">For example, if the batch size is two and the adapter gets four messages of size 4 KB, 8 KB, 1 MB, and 5 MB respectively, the first batch will be of size 12 KB, and the second batch will be of size 6 MB.</span></span> <span data-ttu-id="256cd-107">Puesto que el motor de mensajería de BizTalk procesa todos los mensajes en un solo lote de forma secuencial, el segundo lote de este ejemplo se procesará mucho más lento que el primero.</span><span class="sxs-lookup"><span data-stu-id="256cd-107">Because the BizTalk Messaging Engine processes all messages in a single batch sequentially, the second batch in this example will be processed much more slowly than the first batch.</span></span> <span data-ttu-id="256cd-108">El efecto de esto es el rendimiento reducido.</span><span class="sxs-lookup"><span data-stu-id="256cd-108">The effect of this is reduced throughput.</span></span>  
  
 <span data-ttu-id="256cd-109">Para resolver este problema, se recomienda que procesa por lotes según el número de mensajes y el número total de bytes en el lote (es decir, el tamaño de lote en bytes).</span><span class="sxs-lookup"><span data-stu-id="256cd-109">To handle this problem, we recommend that you batch based on both the message count and the total number of bytes in the batch (that is, batch size in bytes).</span></span> <span data-ttu-id="256cd-110">No hay ningún número óptimo de bytes totales.</span><span class="sxs-lookup"><span data-stu-id="256cd-110">There is no optimal number for total bytes.</span></span> <span data-ttu-id="256cd-111">Sin embargo, en un escenario de procesamiento normal, si el tamaño del lote supera 1 MB, iniciará encontrar rendimiento y simultaneidad deficiente.</span><span class="sxs-lookup"><span data-stu-id="256cd-111">However, in a normal processing scenario, if the batch size exceeds 1 MB, you will start encountering poor concurrency and throughput.</span></span>  
  
 <span data-ttu-id="256cd-112">Adaptadores generalmente procesan mensajes de tamaño variable en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="256cd-112">Adapters generally process messages of varying size in the production environment.</span></span> <span data-ttu-id="256cd-113">Los tamaños de los mensajes entrantes son propensos a variar considerablemente.</span><span class="sxs-lookup"><span data-stu-id="256cd-113">The sizes of incoming messages are likely to vary significantly.</span></span> <span data-ttu-id="256cd-114">Como resultado, use siempre mensaje recuento y los bytes totales para generar el lote.</span><span class="sxs-lookup"><span data-stu-id="256cd-114">As a result, always use message count and total bytes to build the batch.</span></span>