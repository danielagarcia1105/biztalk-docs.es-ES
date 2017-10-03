---
title: "Cambios en la directiva de deshidratación de BizTalk Server 2004 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c760bffe-5f64-4eb2-bc23-89d7c9310f39
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9daf93fd6c925e5412aef3f4e985dd966f576eee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a><span data-ttu-id="bcbc5-102">Cambios en la directiva de deshidratación desde BizTalk Server 2004</span><span class="sxs-lookup"><span data-stu-id="bcbc5-102">Changes in Dehydration Policy from BizTalk Server 2004</span></span>
<span data-ttu-id="bcbc5-103">La directiva de deshidratación de BizTalk Server ha cambiado de [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcbc5-103">BizTalk Server dehydration policy has changed from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="bcbc5-104">La explicación de la diferencia entre [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] y [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se puede resumir de la siguiente expresión booleana que determina la deshidratación en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] (true = deshidratar)</span><span class="sxs-lookup"><span data-stu-id="bcbc5-104">The explanation for the difference between [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] and [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] can be summarized by the following Boolean that determines dehydration in [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] (true = dehydrate)</span></span>  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 <span data-ttu-id="bcbc5-105">La directiva de deshidratación para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ha cambiado de esta manera menor.</span><span class="sxs-lookup"><span data-stu-id="bcbc5-105">Dehydration policy for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] has changed in this minor way.</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="bcbc5-106">siempre se deshidrata en recepción/retraso/escuchar si hay una espera más de 2 ***MaxThreshold**.</span><span class="sxs-lookup"><span data-stu-id="bcbc5-106"> always dehydrates at a receive/delay/listen if there is a wait longer than 2***MaxThreshold**.</span></span>