---
title: Arquitectura de BizTalk Adapter para TIBCO Rendezvous | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- architecture
- message passing
- messages, passing
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 801f92453ffc85d83d57c1caa5c89ec618b96ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="87d71-102">Arquitectura del adaptador de BizTalk para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="87d71-102">Architecture of BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="87d71-103">El Adaptador de Microsoft BizTalk para TIBCO Rendezvous proporciona conectividad bidireccional entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="87d71-103">Microsoft BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="87d71-104">Este adaptador utiliza tanto la API TIBCO Rendezvous como la API del marco de trabajo de adaptadores BizTalk para proporcionar una elevada integración.</span><span class="sxs-lookup"><span data-stu-id="87d71-104">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
 <span data-ttu-id="87d71-105">TIBCO Rendezvous es un producto de software que proporciona un bus de mensaje para la integración de aplicaciones empresariales(EAI).</span><span class="sxs-lookup"><span data-stu-id="87d71-105">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="87d71-106">TIBCO proporciona API de mensajería en C, C++, Java, Visual Basic y Microsoft .NET Framework para recibir canales de datos en hojas de cálculo de Microsoft Office Excel y otras aplicaciones de su elección.</span><span class="sxs-lookup"><span data-stu-id="87d71-106">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="87d71-107">Pasar mensajes</span><span class="sxs-lookup"><span data-stu-id="87d71-107">Message Passing</span></span>  
 <span data-ttu-id="87d71-108">El concepto básico de pasar mensajes es bastante sencillo:</span><span class="sxs-lookup"><span data-stu-id="87d71-108">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="87d71-109">Un mensaje tiene un único asunto formado por elementos separados por puntos.</span><span class="sxs-lookup"><span data-stu-id="87d71-109">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="87d71-110">Se envía a un único daemon de Rendezvous (aunque podría transmitirse a otros daemons).</span><span class="sxs-lookup"><span data-stu-id="87d71-110">It is sent to a single Rendezvous daemon (though it might eventually be broadcast onto other daemons).</span></span>  
  
-   <span data-ttu-id="87d71-111">Un escucha anuncia sus asuntos de interés a un daemon (con una función de comodín básica), y los mensajes con asuntos coincidentes se le entregan si los dos daemons están "conectados" entre sí o son el mismo daemon.</span><span class="sxs-lookup"><span data-stu-id="87d71-111">A listener announces its subjects of interest to a daemon (with a basic wildcard facility), and messages that have matching subjects are delivered to it if the two daemons are 'connected' to each other, or are indeed the same daemon.</span></span> <span data-ttu-id="87d71-112">Para obtener más información, consulte mensajes en [mensajes en el adaptador de BizTalk para TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span><span class="sxs-lookup"><span data-stu-id="87d71-112">For more information, see Messages in [Messages in BizTalk Adapter for TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span></span>  
  
 <span data-ttu-id="87d71-113">En la siguiente ilustración se muestra la arquitectura para el Adaptador de BizTalk para TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="87d71-113">The following figure shows the architecture for BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
 ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a><span data-ttu-id="87d71-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="87d71-114">See Also</span></span>  
 <span data-ttu-id="87d71-115">[Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="87d71-115">[Getting Started](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="87d71-116">Planeamiento y arquitectura</span><span class="sxs-lookup"><span data-stu-id="87d71-116">Planning and Architecture</span></span>](../core/planning-and-architecture15.md)