---
title: "Opciones de implementación del adaptador de MQSeries | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88fa674c38df8b31c1954234846fd3939ed8568
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-deployment-options"></a><span data-ttu-id="fc5c2-102">Opciones de implementación del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="fc5c2-102">MQSeries Adapter Deployment Options</span></span>
<span data-ttu-id="fc5c2-103">El adaptador de MQSeries le ofrece una gran flexibilidad a la hora de configurar su hardware.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-103">The MQSeries adapter gives you great flexibility in configuring your hardware.</span></span> <span data-ttu-id="fc5c2-104">Al menos hay tres patrones principales de uso:</span><span class="sxs-lookup"><span data-stu-id="fc5c2-104">There are at least three main patterns of use:</span></span>  
  
-   <span data-ttu-id="fc5c2-105">BizTalk Server, el adaptador y MQSeries Server para Windows en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-105">BizTalk Server, the adapter, and MQSeries Server for Windows on the same computer.</span></span>  
  
-   <span data-ttu-id="fc5c2-106">BizTalk Server y el adaptador en un equipo, y MQSeries Server para Windows (incluido MQSAgent) en otro equipo que se conecta a uno o más equipos adicionales que ejecutan MQSeries Server.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-106">BizTalk Server and the adapter on one computer, and MQSeries Server for Windows (including the MQSAgent) on a second computer, which connects to one or more additional computers that are running MQSeries Server.</span></span>  
  
-   <span data-ttu-id="fc5c2-107">Varias instalaciones de BizTalk Server en un grupo y el adaptador, y MQSeries Server (que incluye MQSAgent) en otro equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-107">Multiple BizTalk Server installations in a group and the adapter, and MQSeries Server (including MQSAgent) on a separate computer.</span></span>  
  
-   <span data-ttu-id="fc5c2-108">El adaptador funciona perfectamente si agrupa MQSeries Server y los administradores de colas de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-108">The adapter functions correctly if you cluster MQSeries Server and the MQSeries Queue Managers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fc5c2-109">En este caso, la aplicación MQSAgent COM+ no se debería agrupar.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-109">The MQSAgent COM+ application should not be clustered in this case.</span></span> <span data-ttu-id="fc5c2-110">En su lugar, los nodos del clúster deberían tener instalada y configurada la aplicación MQSAgent COM+.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-110">Instead, both nodes of the cluster should have the MQSAgent COM+ application installed and configured.</span></span> <span data-ttu-id="fc5c2-111">En este escenario, si la aplicación MQSAgent COM+ se detiene, la siguiente llamada del cliente la reiniciará.</span><span class="sxs-lookup"><span data-stu-id="fc5c2-111">In this scenario, if the MQSAgent COM+ application stops, the next call from the client will restart it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5c2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc5c2-112">See Also</span></span>  
 [<span data-ttu-id="fc5c2-113">Uso del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="fc5c2-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)