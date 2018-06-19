---
title: Arquitectura del adaptador de TIBCO Rendezvous | Documentos de Microsoft
description: Obtenga información acerca del adaptador de BizTalk para TIBCO Rendezvous funciona, incluidos pasar mensajes, en el servidor BizTalk Server
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3bfee2b51df8781091ea30e512810bae21a5f2a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013435"
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a><span data-ttu-id="41add-103">Arquitectura del adaptador de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="41add-103">Architecture of the TIBCO Rendezvous adapter</span></span>

## <a name="overview"></a><span data-ttu-id="41add-104">Información general</span><span class="sxs-lookup"><span data-stu-id="41add-104">Overview</span></span>
<span data-ttu-id="41add-105">El Adaptador de Microsoft BizTalk para TIBCO Rendezvous proporciona conectividad bidireccional entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="41add-105">Microsoft BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="41add-106">Este adaptador utiliza tanto la API TIBCO Rendezvous como la API del marco de trabajo de adaptadores BizTalk para proporcionar una elevada integración.</span><span class="sxs-lookup"><span data-stu-id="41add-106">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
 <span data-ttu-id="41add-107">TIBCO Rendezvous es un producto de software que proporciona un bus de mensaje para la integración de aplicaciones empresariales(EAI).</span><span class="sxs-lookup"><span data-stu-id="41add-107">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="41add-108">TIBCO proporciona API de mensajería en C, C++, Java, Visual Basic y Microsoft .NET Framework para recibir canales de datos en hojas de cálculo de Microsoft Office Excel y otras aplicaciones de su elección.</span><span class="sxs-lookup"><span data-stu-id="41add-108">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="41add-109">Pasar mensajes</span><span class="sxs-lookup"><span data-stu-id="41add-109">Message Passing</span></span>  
 <span data-ttu-id="41add-110">El concepto básico de pasar mensajes es bastante sencillo:</span><span class="sxs-lookup"><span data-stu-id="41add-110">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="41add-111">Un mensaje tiene un único asunto formado por elementos separados por puntos.</span><span class="sxs-lookup"><span data-stu-id="41add-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="41add-112">Se envía a un único daemon de Rendezvous (aunque podría transmitirse a otros daemons).</span><span class="sxs-lookup"><span data-stu-id="41add-112">It is sent to a single Rendezvous daemon (though it might eventually be broadcast onto other daemons).</span></span>  
  
-   <span data-ttu-id="41add-113">Un escucha anuncia sus asuntos de interés a un daemon (con una función de comodín básica), y los mensajes con asuntos coincidentes se le entregan si los dos daemons están "conectados" entre sí o son el mismo daemon.</span><span class="sxs-lookup"><span data-stu-id="41add-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility), and messages that have matching subjects are delivered to it if the two daemons are 'connected' to each other, or are indeed the same daemon.</span></span> <span data-ttu-id="41add-114">Para obtener más información, consulte mensajes en [mensajes en el adaptador de BizTalk para TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span><span class="sxs-lookup"><span data-stu-id="41add-114">For more information, see Messages in [Messages in BizTalk Adapter for TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span></span>  
  
 <span data-ttu-id="41add-115">En la siguiente ilustración se muestra la arquitectura para el Adaptador de BizTalk para TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="41add-115">The following figure shows the architecture for BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
 ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a><span data-ttu-id="41add-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="41add-116">See Also</span></span>  
 [<span data-ttu-id="41add-117">Introducción</span><span class="sxs-lookup"><span data-stu-id="41add-117">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)  