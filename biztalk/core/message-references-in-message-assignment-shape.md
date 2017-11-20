---
title: "Las referencias de la forma asignación de mensajes de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, code samples
- code samples, messages
- messages, objects
ms.assetid: 428f7eb8-001e-4147-b1c8-f9bb6f3a80f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834eefa991b6cad89a04a836f63d1b9af73fc04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-references-in-message-assignment-shape"></a><span data-ttu-id="9b1a6-102">Referencias de mensaje en la forma asignación de mensajes</span><span class="sxs-lookup"><span data-stu-id="9b1a6-102">Message References in Message Assignment Shape</span></span>
<span data-ttu-id="9b1a6-103">La primera vez que se asigna un objeto basado en .NET a un mensaje o a una parte de mensaje, ese mensaje contiene y mantiene una referencia al objeto.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-103">When you first assign a .NET-based object to a message or message part, that message holds and maintains a reference to the object.</span></span>  
  
 <span data-ttu-id="9b1a6-104">Para la eficacia y la escalabilidad, el motor de orquestaciones no realiza una "copia en profundidad" del objeto: es decir, no copiar todo el contenido del objeto para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-104">For efficiency and scalability, the orchestration engine does not do a "deep copy" of the object: that is, it does not copy the entire contents of the object to the message.</span></span>  
  
 <span data-ttu-id="9b1a6-105">Posteriormente, si asigna el objeto a otro mensaje o a otra parte de mensaje, todas las modificaciones que haya realizado en el original también se realizarán en el segundo mensaje o segunda parte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-105">If you subsequently assign the object to another message or message part, any modifications to the original results in modifications to the second message or message part.</span></span> <span data-ttu-id="9b1a6-106">Debería evitar esta situación, ya que los resultados son impredecibles.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-106">You should avoid this practice, because results are unpredictable.</span></span>  
  
 <span data-ttu-id="9b1a6-107">Si necesita que el segundo mensaje tenga una copia distinta del objeto, debería asignar el primer mensaje o primera parte de mensaje al segundo mensaje o segunda parte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-107">If you need your second message to have a distinct copy of the object, you should assign the first message or message part to the second message or message part.</span></span>  
  
 <span data-ttu-id="9b1a6-108">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b1a6-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="9b1a6-109">Erróneo:</span><span class="sxs-lookup"><span data-stu-id="9b1a6-109">Wrong way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="9b1a6-110">En este caso, myMsg2.myInt se ha sobrescrito y ahora tiene el valor 5.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-110">In this case, myMsg2.myInt has been overwritten, and now has the value 5.</span></span>  
  
 <span data-ttu-id="9b1a6-111">Correcto:</span><span class="sxs-lookup"><span data-stu-id="9b1a6-111">Right way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="9b1a6-112">En este caso, myMsg2.myInt sigue teniendo el valor 100, como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-112">In this case, myMsg2.myInt still has the value 100, as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b1a6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b1a6-113">See Also</span></span>  
 [<span data-ttu-id="9b1a6-114">Construir mensajes</span><span class="sxs-lookup"><span data-stu-id="9b1a6-114">Constructing Messages</span></span>](../core/constructing-messages.md)