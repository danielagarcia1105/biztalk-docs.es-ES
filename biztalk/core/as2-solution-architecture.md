---
title: "AS2 Arquitectura de la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22557059bd13dd99e0b24a2291b7f121d561bbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="as2-solution-architecture"></a><span data-ttu-id="99f2a-102">Arquitectura de solución AS2</span><span class="sxs-lookup"><span data-stu-id="99f2a-102">AS2 Solution Architecture</span></span>
<span data-ttu-id="99f2a-103">El procesamiento AS2 se realiza de forma independiente al procesamiento EDI.</span><span class="sxs-lookup"><span data-stu-id="99f2a-103">AS2 processing is performed separately from EDI processing.</span></span> <span data-ttu-id="99f2a-104">Se reciben los mensajes AS2, se procesan y se envía una confirmación además del procesamiento de la carga EDI.</span><span class="sxs-lookup"><span data-stu-id="99f2a-104">AS2 messages are received, processed, and an acknowledgment sent apart from the processing of the EDI payload.</span></span> <span data-ttu-id="99f2a-105">Como resultado, el procesamiento AS2 se diseña y configura además del procesamiento EDI.</span><span class="sxs-lookup"><span data-stu-id="99f2a-105">As a result, AS2 processing is designed and configured apart from EDI processing.</span></span> <span data-ttu-id="99f2a-106">Además, puede usar AS2 para transportar mensajes que sean o no EDI.</span><span class="sxs-lookup"><span data-stu-id="99f2a-106">In addition, you can use AS2 to transport either EDI messages or non-EDI messages.</span></span>  
  
 <span data-ttu-id="99f2a-107">En esta sección se describe la arquitectura de soluciones AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], incluidos el procesamiento de envío, de recepción y de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="99f2a-107">This section describes the architecture of AS2 solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including end-to-end, receive-side, and send-side processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99f2a-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="99f2a-108">In This Section</span></span>  
  
-   [<span data-ttu-id="99f2a-109">Mensajería AS2</span><span class="sxs-lookup"><span data-stu-id="99f2a-109">AS2 Messaging</span></span>](../core/as2-messaging.md)  
  
-   [<span data-ttu-id="99f2a-110">Rol de los acuerdos de AS2 de procesamiento</span><span class="sxs-lookup"><span data-stu-id="99f2a-110">The Role of Agreements in AS2 Processing</span></span>](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [<span data-ttu-id="99f2a-111">Cómo BizTalk Server recibe mensajes AS2</span><span class="sxs-lookup"><span data-stu-id="99f2a-111">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [<span data-ttu-id="99f2a-112">Cómo BizTalk Server envía mensajes AS2</span><span class="sxs-lookup"><span data-stu-id="99f2a-112">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)