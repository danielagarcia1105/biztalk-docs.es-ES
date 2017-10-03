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
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a>Cambios en la directiva de deshidratación desde BizTalk Server 2004
La directiva de deshidratación de BizTalk Server ha cambiado de [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. La explicación de la diferencia entre [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] y [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se puede resumir de la siguiente expresión booleana que determina la deshidratación en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] (true = deshidratar)  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 La directiva de deshidratación para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ha cambiado de esta manera menor. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]siempre se deshidrata en recepción/retraso/escuchar si hay una espera más de 2 ***MaxThreshold**.