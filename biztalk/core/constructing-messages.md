---
title: Construir mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fa87c4f3400a80ce83df132747d0004232323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="constructing-messages"></a><span data-ttu-id="fcd07-102">Construir mensajes</span><span class="sxs-lookup"><span data-stu-id="fcd07-102">Constructing Messages</span></span>
<span data-ttu-id="fcd07-103">Construya un mensaje en el momento en que escriba un mensaje en la orquestación, mediante la recepción o asignación de valores a una variable de mensaje.</span><span class="sxs-lookup"><span data-stu-id="fcd07-103">You construct a message any time that you introduce a message into your orchestration, either by receiving it or by assigning values to a message variable.</span></span> <span data-ttu-id="fcd07-104">Cualquier mensaje que construya debe tener un tipo de mensaje, de modo que el motor de tiempo de ejecución tenga una descripción completa del objeto con el que se está trabajando.</span><span class="sxs-lookup"><span data-stu-id="fcd07-104">Any message that you construct must have a message type, so that the runtime engine has a complete description of the object that it is working with.</span></span> <span data-ttu-id="fcd07-105">El tipo de mensajes de varias partes puede estar definido por el usuario; puede ser una clase .NET o un esquema.</span><span class="sxs-lookup"><span data-stu-id="fcd07-105">The multi-part message type can be user-defined, it can be a .NET class, or it can be a schema.</span></span> <span data-ttu-id="fcd07-106">Puede construir mensajes de varias formas: puede invocar una clase .NET para crear un mensaje, asignar un mensaje a otro o usar una transformación para asignar determinados valores dentro de un mensaje a valores dentro de otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="fcd07-106">You can construct messages in various ways: you can invoke a .NET class to create a message, assign one message to another, or use a transform to map certain values within a message to values within another message.</span></span> <span data-ttu-id="fcd07-107">Los mensajes también se construyen mediante una acción de recepción o cuando la orquestación acepta un mensaje como parámetro.</span><span class="sxs-lookup"><span data-stu-id="fcd07-107">Messages are also constructed by a receive action or when your orchestration accepts a message as a parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcd07-108">Un tipo de mensaje de varias partes no tiene por qué contener varias partes; puede que solo contenga una.</span><span class="sxs-lookup"><span data-stu-id="fcd07-108">A multi-part message type does not necessarily contain multiple parts; it might contain just one.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fcd07-109">Los mensajes son inmutables en BizTalk; es decir, una vez que lo haya construido, no puede modificar el original.</span><span class="sxs-lookup"><span data-stu-id="fcd07-109">Messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span> <span data-ttu-id="fcd07-110">Si es necesario realizar un cambio, debe construir una copia nueva del mensaje y asignarle valores de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="fcd07-110">If you need to make a change, you must construct a new copy of the message and assign values to it appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcd07-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fcd07-111">In This Section</span></span>  
 [<span data-ttu-id="fcd07-112">Cómo configurar la forma construir mensaje</span><span class="sxs-lookup"><span data-stu-id="fcd07-112">How to Configure the Construct Message Shape</span></span>](../core/how-to-configure-the-construct-message-shape.md)  
  
 [<span data-ttu-id="fcd07-113">Cómo configurar la forma asignación de mensajes</span><span class="sxs-lookup"><span data-stu-id="fcd07-113">How to Configure the Message Assignment Shape</span></span>](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [<span data-ttu-id="fcd07-114">Cómo configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="fcd07-114">How to Configure the Transform Shape</span></span>](../core/how-to-configure-the-transform-shape.md) 
  
 [<span data-ttu-id="fcd07-115">Referencias de mensaje en la forma asignación de mensajes</span><span class="sxs-lookup"><span data-stu-id="fcd07-115">Message References in Message Assignment Shape</span></span>](../core/message-references-in-message-assignment-shape.md)  
  
 [<span data-ttu-id="fcd07-116">Referencias de mensaje en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="fcd07-116">Message References in User Code</span></span>](../core/message-references-in-user-code.md)  
  
 [<span data-ttu-id="fcd07-117">Usar XPaths en las asignaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="fcd07-117">Using XPaths in Message Assignments</span></span>](../core/using-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="fcd07-118">Usar XPaths no canónicos en las asignaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="fcd07-118">Using Non-Canonical XPaths in Message Assignments</span></span>](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="fcd07-119">Construir mensajes en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="fcd07-119">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)  
  
 [<span data-ttu-id="fcd07-120">Anexar nodos a mensajes en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="fcd07-120">Appending Nodes to Messages in User Code</span></span>](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a><span data-ttu-id="fcd07-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcd07-121">See Also</span></span>  
 [<span data-ttu-id="fcd07-122">Usar mensajes en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="fcd07-122">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)