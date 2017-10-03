---
title: Arquitectura de BizTalk Adapter para TIBCO Enterprise Message Service | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transmit adapter
- one-way receive operations
- architecture
- one-way send operations
- receive adapter
ms.assetid: 304c7236-aacd-4761-8c33-e876b53e84ff
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c7bc6420efb67085e4f3a05f6daf0c5dbd2feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="657ef-102">Arquitectura del adaptador de BizTalk para TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="657ef-102">Architecture of BizTalk Adapter for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="657ef-103">El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona un medio de intercambiar datos empresariales en tiempo real entre sistemas TIBCO EMS y BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="657ef-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="657ef-104">El adaptador permite la interacción entre una aplicación XML y TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="657ef-104">The adapter enables interaction between an XML application and TIBCO EMS.</span></span>  
  
 <span data-ttu-id="657ef-105">El adaptador acepta mensajes XML que permiten que las aplicaciones de BizTalk se comuniquen con TIBCO EMS usando uno de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="657ef-105">The adapter accepts XML messages that enable BizTalk applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="657ef-106">**Adaptador de transmisión**: usa un puerto de envío unidireccional estático para enviar un mensaje a TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="657ef-106">**Transmit Adapter**: Uses a static one-way send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="657ef-107">**Adaptador de recepción**: utiliza un unidireccional estático puerto de recepción para recibir mensajes de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="657ef-107">**Receive Adapter**: Uses a static one-way receive port to receive messages from TIBCO EMS.</span></span>  
  
## <a name="one-way-send-operation"></a><span data-ttu-id="657ef-108">Operación de envío unidireccional</span><span class="sxs-lookup"><span data-stu-id="657ef-108">One-Way Send Operation</span></span>  
 <span data-ttu-id="657ef-109">En la siguiente ilustración se muestra la arquitectura de una operación de envío unidireccional que usa el Adaptador de BizTalk para TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="657ef-109">The following figure shows the architecture of a one-way send operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a><span data-ttu-id="657ef-110">Operación de recepción unidireccional</span><span class="sxs-lookup"><span data-stu-id="657ef-110">One-Way Receive Operation</span></span>  
 <span data-ttu-id="657ef-111">En la siguiente ilustración se muestra la arquitectura de una operación de recepción unidireccional que usa el Adaptador de BizTalk para TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="657ef-111">The following figure shows the architecture for a one-way receive operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a><span data-ttu-id="657ef-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="657ef-112">See Also</span></span>  
 <span data-ttu-id="657ef-113">[Características del adaptador](../core/adapter-features.md) </span><span class="sxs-lookup"><span data-stu-id="657ef-113">[Adapter Features](../core/adapter-features.md) </span></span>  
 [<span data-ttu-id="657ef-114">Planeamiento y arquitectura</span><span class="sxs-lookup"><span data-stu-id="657ef-114">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)