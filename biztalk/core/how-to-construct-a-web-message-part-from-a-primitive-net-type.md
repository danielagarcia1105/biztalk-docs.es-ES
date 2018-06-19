---
title: Cómo construir una parte de mensaje Web desde un tipo .NET primitivo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, Message Assignment shape [Orchestration Designer]
- Web messages, creating
- Message Assignment shape [Orchestration Designer], Web messages
- Web messages, parts
- Web messages, .NET types
ms.assetid: 1fe52412-d2bc-484c-8925-c7ff3ca7704b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991970d5b0d40da1ec00b54919d2742cfd48353c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248028"
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="b741f-102">Cómo construir una parte de mensaje web a partir de un tipo .NET primitivo</span><span class="sxs-lookup"><span data-stu-id="b741f-102">How to Construct a Web Message Part from a Primitive .NET Type</span></span>
<span data-ttu-id="b741f-103">Crear una parte de mensaje Web desde un tipo .NET primitivo mediante un **asignación de mensajes** forma.</span><span class="sxs-lookup"><span data-stu-id="b741f-103">You create a Web message part from a primitive .NET type by using a **Message Assignment** shape.</span></span> <span data-ttu-id="b741f-104">Como alternativa, puede crear una parte de mensaje Web a partir de un tipo .NET primitivo mediante la utilización de una clase .NET auxiliar para establecer las partes.</span><span class="sxs-lookup"><span data-stu-id="b741f-104">Alternatively, you can create a Web message part from a primitive .NET type by using a .NET helper class to set the parts.</span></span> <span data-ttu-id="b741f-105">Para obtener más información sobre cómo crear tipos de mensaje mediante una clase. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).</span><span class="sxs-lookup"><span data-stu-id="b741f-105">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="b741f-106">Para construir una parte de mensaje Web a partir de un tipo .NET primitivo</span><span class="sxs-lookup"><span data-stu-id="b741f-106">To construct a Web message part from a primitive .NET type</span></span>  
  
1.  <span data-ttu-id="b741f-107">Con una orquestación abierta, abra el **cuadro de herramientas** y haga clic en el **orquestaciones de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="b741f-107">With an orchestration open, open the **Toolbox** and click the **BizTalk Orchestrations** tab.</span></span>  
  
2.  <span data-ttu-id="b741f-108">Arrastre un **construir mensaje** forma a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="b741f-108">Drag a **Construct Message** shape to the orchestration.</span></span>  
  
3.  <span data-ttu-id="b741f-109">Editar la **construir mensaje** propiedad para incluir la instancia de mensaje que ha creado para el tipo de mensaje Web.</span><span class="sxs-lookup"><span data-stu-id="b741f-109">Edit the **Message Constructed** property to include the message instance that you created for the Web message type.</span></span>  
  
4.  <span data-ttu-id="b741f-110">Arrastre un **asignación de mensajes** forma en la **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="b741f-110">Drag a **Message Assignment** shape onto the **Construct Message** shape.</span></span>  
  
5.  <span data-ttu-id="b741f-111">Haga doble clic en el **asignación de mensajes** forma para abrir el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b741f-111">Double-click the **Message Assignment** shape to open the BizTalk Expression Editor.</span></span>  
  
6.  <span data-ttu-id="b741f-112">Establezca las partes del tipo de mensaje Web en sus valores necesarios en la casilla Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b741f-112">Set the parts of the Web message type to their required values in the BizTalk Expression Editor box.</span></span>  
  
     <span data-ttu-id="b741f-113">Por ejemplo, el siguiente código establece la expresión en una cadena:</span><span class="sxs-lookup"><span data-stu-id="b741f-113">For example, the following code sets the expression to a string:</span></span>  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b741f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b741f-114">See Also</span></span>  
 [<span data-ttu-id="b741f-115">Construcción de mensajes Web</span><span class="sxs-lookup"><span data-stu-id="b741f-115">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)