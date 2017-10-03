---
title: Funcionalidad de AS2 de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c16c017e-b68b-483b-a4af-e47eb229de00
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72e8acf77f57c18a87a44de365ea1ab611e49c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-as2-functionality"></a><span data-ttu-id="c405c-102">Funcionalidad de AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c405c-102">BizTalk Server AS2 Functionality</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c405c-103"> procesa mensajes AS2 mediante una combinación de características principales de BizTalk Server y características de BizTalk Server específicas de AS2.</span><span class="sxs-lookup"><span data-stu-id="c405c-103"> processes AS2 messages using a combination of core BizTalk Server features and AS2-specific BizTalk Server features.</span></span> <span data-ttu-id="c405c-104">Esto permite que BizTalk Server lleve a cabo el procesamiento que es exclusivo de la mensajería AS2, al mismo tiempo que aprovecha su funcionalidad de mensajería principal.</span><span class="sxs-lookup"><span data-stu-id="c405c-104">This enables BizTalk Server to perform the processing that is unique to AS2 messaging, while leveraging its core messaging functionality.</span></span> <span data-ttu-id="c405c-105">Si los documentos EDI se transportan mediante AS2, también se usará alguna funcionalidad específica de EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c405c-105">If EDI documents are transported over AS2, some of the EDI-specific functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also be used.</span></span>  
  
 <span data-ttu-id="c405c-106">En esta sección se describe la mensajería básica de AS2 y cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] la implementa.</span><span class="sxs-lookup"><span data-stu-id="c405c-106">This section describes basic AS2 messaging and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="c405c-107">También se describe cómo una definición de acuerdo entre socios comerciales se puede aprovechar para el procesamiento de AS2, el procesamiento de AS2 del lado de recepción y el procesamiento de AS2 del lado de envío.</span><span class="sxs-lookup"><span data-stu-id="c405c-107">It also describes how a trading partner agreement definition can be leveraged for AS2 processing, receive-side AS2 processing, and send-side AS2 processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c405c-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c405c-108">In This Section</span></span>  
  
-   [<span data-ttu-id="c405c-109">AS2 Compatibilidad en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c405c-109">AS2 Support in BizTalk Server</span></span>](../core/as2-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="c405c-110">AS2 Procesamiento en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c405c-110">AS2 Processing in BizTalk Server</span></span>](../core/as2-processing-in-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="c405c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c405c-111">See Also</span></span>  
 <span data-ttu-id="c405c-112">[Funcionalidad de EDI de BizTalk Server](../core/biztalk-server-edi-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="c405c-112">[BizTalk Server EDI Functionality](../core/biztalk-server-edi-functionality.md) </span></span>  
 [<span data-ttu-id="c405c-113">AS2 Arquitectura de la solución</span><span class="sxs-lookup"><span data-stu-id="c405c-113">AS2 Solution Architecture</span></span>](../core/as2-solution-architecture.md)