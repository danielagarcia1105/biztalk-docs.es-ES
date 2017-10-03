---
title: "Anexar nodos a mensajes en el código de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, nodes
- messages, cloning
ms.assetid: 636e0064-095e-49d1-850f-eaee0f0ffe77
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0376094f31478c74a408eacab6c363ce22c9d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="appending-nodes-to-messages-in-user-code"></a>Anexar nodos a mensajes en el código de usuario
Debido al modo en que BizTalk Server controla los mensajes, no basta con anexar directamente un nodo nuevo a un mensaje existente. En lugar de ello, se debe clonar el mensaje existente como se indica a continuación:  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 Ahora podrá utilizar myModifiedMsg, que incluye el nodo nuevo. Si por alguna razón desea volver a utilizar myExistingMsg, puede construir una copia nueva (vacía) y asignarle myModifiedMsg.  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a>Vea también  
 [Construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md)   
 [Construir mensajes](../core/constructing-messages.md)