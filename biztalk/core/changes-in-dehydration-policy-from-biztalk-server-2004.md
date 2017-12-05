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
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a>Cambios en la directiva de deshidratación desde BizTalk Server 2004
La directiva de deshidratación de BizTalk Server ha cambiado de [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] a BizTalk Server. La explicación de la diferencia entre [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] y BizTalk Server se puede resumir de la siguiente expresión booleana que determina la deshidratación en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] (true = deshidratar)  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 La directiva de deshidratación de BizTalk Server ha cambiado de esta manera menor. BizTalk Server siempre se deshidrata en recepción/retraso/escuchar si hay una espera más de 2 ***MaxThreshold**.