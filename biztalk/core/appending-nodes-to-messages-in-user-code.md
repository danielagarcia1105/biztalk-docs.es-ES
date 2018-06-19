---
title: Anexar nodos a mensajes en el código de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, nodes
- messages, cloning
ms.assetid: 636e0064-095e-49d1-850f-eaee0f0ffe77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0376094f31478c74a408eacab6c363ce22c9d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229980"
---
# <a name="appending-nodes-to-messages-in-user-code"></a><span data-ttu-id="8dec7-102">Anexar nodos a mensajes en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="8dec7-102">Appending Nodes to Messages in User Code</span></span>
<span data-ttu-id="8dec7-103">Debido al modo en que BizTalk Server controla los mensajes, no basta con anexar directamente un nodo nuevo a un mensaje existente.</span><span class="sxs-lookup"><span data-stu-id="8dec7-103">Because of the way BizTalk Server handles messages, you cannot simply append a new node directly to an existing message.</span></span> <span data-ttu-id="8dec7-104">En lugar de ello, se debe clonar el mensaje existente como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8dec7-104">Instead, you must clone the existing message, as follows:</span></span>  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 <span data-ttu-id="8dec7-105">Ahora podrá utilizar myModifiedMsg, que incluye el nodo nuevo.</span><span class="sxs-lookup"><span data-stu-id="8dec7-105">Now you can use myModifiedMsg, which includes the new node.</span></span> <span data-ttu-id="8dec7-106">Si por alguna razón desea volver a utilizar myExistingMsg, puede construir una copia nueva (vacía) y asignarle myModifiedMsg.</span><span class="sxs-lookup"><span data-stu-id="8dec7-106">If for some reason you want to reuse myExistingMsg, you can construct a new (empty) copy and assign myModifiedMsg to it.</span></span>  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8dec7-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dec7-107">See Also</span></span>  
 <span data-ttu-id="8dec7-108">[Construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md) </span><span class="sxs-lookup"><span data-stu-id="8dec7-108">[Constructing Messages in User Code](../core/constructing-messages-in-user-code.md) </span></span>  
 [<span data-ttu-id="8dec7-109">Construir mensajes</span><span class="sxs-lookup"><span data-stu-id="8dec7-109">Constructing Messages</span></span>](../core/constructing-messages.md)