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
ms.openlocfilehash: 167c53d953369d7b35138995b4f38ad8994c18cb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a><span data-ttu-id="f867e-102">Cambios en la directiva de deshidratación desde BizTalk Server 2004</span><span class="sxs-lookup"><span data-stu-id="f867e-102">Changes in Dehydration Policy from BizTalk Server 2004</span></span>
<span data-ttu-id="f867e-103">La directiva de deshidratación de BizTalk Server ha cambiado de [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f867e-103">BizTalk Server dehydration policy has changed from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to BizTalk Server.</span></span> <span data-ttu-id="f867e-104">La explicación de la diferencia entre [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] y BizTalk Server se puede resumir de la siguiente expresión booleana que determina la deshidratación en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] (true = deshidratar)</span><span class="sxs-lookup"><span data-stu-id="f867e-104">The explanation for the difference between [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] and BizTalk Server can be summarized by the following Boolean that determines dehydration in [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] (true = dehydrate)</span></span>  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 <span data-ttu-id="f867e-105">La directiva de deshidratación de BizTalk Server ha cambiado de esta manera menor.</span><span class="sxs-lookup"><span data-stu-id="f867e-105">Dehydration policy for BizTalk Server has changed in this minor way.</span></span> <span data-ttu-id="f867e-106">BizTalk Server siempre se deshidrata en recepción/retraso/escuchar si hay una espera más de 2 ***MaxThreshold**.</span><span class="sxs-lookup"><span data-stu-id="f867e-106">BizTalk Server always dehydrates at a receive/delay/listen if there is a wait longer than 2***MaxThreshold**.</span></span>