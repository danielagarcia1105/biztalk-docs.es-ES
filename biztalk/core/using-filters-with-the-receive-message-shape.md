---
title: "Uso de filtros con la forma de mensaje de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filters, receive messages
- messages, filters
ms.assetid: 5310039b-6719-4971-933a-2da0573fb5e7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1434e9704e073cfef1503ef550409e6d6414bb7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-filters-with-the-receive-message-shape"></a><span data-ttu-id="1d0d4-102">Uso de filtros con la forma de mensaje de recepción</span><span class="sxs-lookup"><span data-stu-id="1d0d4-102">Using Filters With the Receive Message Shape</span></span>
<span data-ttu-id="1d0d4-103">Una expresión de filtro es un parámetro opcional que puede aplicarse a una forma Recepción de una orquestación que especifica un valor True para la propiedad Activar.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-103">A filter expression is an optional parameter that can be applied to an orchestration receive shape that specifies a value of True for the Activate property.</span></span> <span data-ttu-id="1d0d4-104">Si se especifica una expresión de filtro, la orquestación solo se activará si un mensaje entrante cumple la condición o condiciones especificadas en dicha expresión.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-104">If a filter expression is specified then the orchestration will only be activated if an incoming message matches the condition(s) specified in the filter expression.</span></span> <span data-ttu-id="1d0d4-105">Si no se especifica ninguna expresión de filtro, ningún mensaje entrante al que se suscriba la orquestación la activará.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-105">If no filter expression is specified then any incoming message that the orchestration subscribes to will activate the orchestration.</span></span>  
  
 <span data-ttu-id="1d0d4-106">Para crear una expresión de filtro, hay que comparar una propiedad de un mensaje entrante a la izquierda de la expresión con una constante a la derecha de ésta.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-106">To create a filter expression, you compare a property of an incoming message on the left side of the expression with a constant on the right side of the expression.</span></span> <span data-ttu-id="1d0d4-107">También se pueden crear expresiones compuestas aplicando los operadores AND y OR a dos expresiones o más.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-107">You can also create compound expressions by applying the AND and OR operators to two or more expressions.</span></span> <span data-ttu-id="1d0d4-108">Asimismo, se puede dejar en blanco la expresión de filtro, en cuyo caso se aceptarán todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-108">You can also leave blank the filter expression, in which case all messages will be accepted.</span></span>  
  
 <span data-ttu-id="1d0d4-109">Una expresión de filtro podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="1d0d4-109">A filter expression might look like the following:</span></span>  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 <span data-ttu-id="1d0d4-110">En este ejemplo, se presenta un mensaje entrante a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-110">In this example, an incoming message is presented to the orchestration.</span></span> <span data-ttu-id="1d0d4-111">La orquestación tiene una activación **recepción** forma (la **activación** propiedad está establecida en **True** para que la recepción de un determinado mensaje hará que la orquestación para ejecutarse ) con la expresión de filtro anterior aplicada a él.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-111">The orchestration has an activation **Receive** shape (the **Activation** property is set to **True** so that receipt of a certain message will cause the orchestration to be run) with the preceding filter expression applied to it.</span></span> <span data-ttu-id="1d0d4-112">El mensaje entrante se espera que tenga la propiedad Quantity en el espacio de nombres **InvoiceSchema**.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-112">The incoming message is expected to have property called Quantity in the namespace **InvoiceSchema**.</span></span> <span data-ttu-id="1d0d4-113">La orquestación solo acepta facturas para 1000 elementos o más, de modo que el motor de tiempo de ejecución comprueba el mensaje entrante antes de que se ejecute.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-113">The orchestration accepts only invoices for 1000 or more items, so the runtime engine checks the incoming message before it runs.</span></span>  
  
 <span data-ttu-id="1d0d4-114">La siguiente tabla muestra los operadores que se pueden utilizar en expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-114">The following table shows operators that you can use in filter expressions.</span></span>  
  
|<span data-ttu-id="1d0d4-115">Operador</span><span class="sxs-lookup"><span data-stu-id="1d0d4-115">Operator</span></span>|<span data-ttu-id="1d0d4-116">Description</span><span class="sxs-lookup"><span data-stu-id="1d0d4-116">Description</span></span>|<span data-ttu-id="1d0d4-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d0d4-117">Example</span></span>|  
|--------------|-----------------|-------------|  
|==|<span data-ttu-id="1d0d4-118">igual a</span><span class="sxs-lookup"><span data-stu-id="1d0d4-118">equal to</span></span>|<span data-ttu-id="1d0d4-119">ReqMsg(Total) == 100</span><span class="sxs-lookup"><span data-stu-id="1d0d4-119">ReqMsg(Total) == 100</span></span>|  
|<span data-ttu-id="1d0d4-120">!=</span><span class="sxs-lookup"><span data-stu-id="1d0d4-120">!=</span></span>|<span data-ttu-id="1d0d4-121">no es igual a</span><span class="sxs-lookup"><span data-stu-id="1d0d4-121">not equal to</span></span>|<span data-ttu-id="1d0d4-122">ReqMsg(Total) != 100</span><span class="sxs-lookup"><span data-stu-id="1d0d4-122">ReqMsg(Total) != 100</span></span>|  
|<|<span data-ttu-id="1d0d4-123">menor que</span><span class="sxs-lookup"><span data-stu-id="1d0d4-123">less than</span></span>|<span data-ttu-id="1d0d4-124">ReqMsg(Total) \< 100</span><span class="sxs-lookup"><span data-stu-id="1d0d4-124">ReqMsg(Total) \< 100</span></span>|  
|>|<span data-ttu-id="1d0d4-125">mayor que</span><span class="sxs-lookup"><span data-stu-id="1d0d4-125">greater than</span></span>|<span data-ttu-id="1d0d4-126">ReqMsg(Total) > 100</span><span class="sxs-lookup"><span data-stu-id="1d0d4-126">ReqMsg(Total) > 100</span></span>|  
|<=|<span data-ttu-id="1d0d4-127">menor que o igual a</span><span class="sxs-lookup"><span data-stu-id="1d0d4-127">less than or equal to</span></span>|<span data-ttu-id="1d0d4-128">ReqMsg(Total) \<= 100</span><span class="sxs-lookup"><span data-stu-id="1d0d4-128">ReqMsg(Total) \<= 100</span></span>|  
|>=|<span data-ttu-id="1d0d4-129">mayor que o igual a</span><span class="sxs-lookup"><span data-stu-id="1d0d4-129">greater than or equal to</span></span>|<span data-ttu-id="1d0d4-130">ReqMsg(Total) > = 100</span><span class="sxs-lookup"><span data-stu-id="1d0d4-130">ReqMsg(Total) >= 100</span></span>|  
|<span data-ttu-id="1d0d4-131">exists</span><span class="sxs-lookup"><span data-stu-id="1d0d4-131">exists</span></span>|<span data-ttu-id="1d0d4-132">exists</span><span class="sxs-lookup"><span data-stu-id="1d0d4-132">exists</span></span>|<span data-ttu-id="1d0d4-133">ReqMsg(Description) existe</span><span class="sxs-lookup"><span data-stu-id="1d0d4-133">ReqMsg(Description) exists</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="1d0d4-134">Valores de cadena en expresiones de filtro están entre comillas, por ejemplo: reqmsg (Description) = "Estado de pedido de compra".</span><span class="sxs-lookup"><span data-stu-id="1d0d4-134">String values in filter expressions are enclosed in quotation marks, for example: ReqMsg(Description) = "Purchase Order Status".</span></span> <span data-ttu-id="1d0d4-135">No se puede utilizar un valor de carácter en una expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-135">You cannot use a character value in a filter expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d0d4-136">Si la recepción de activación está asociada a un puerto de enlace directo y posteriormente se envía un mensaje del mismo tipo con el mismo valor para la propiedad probada en el filtro, se creará un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-136">If your activate receive is associated with a direct-bound port, and you subsequently send a message of the same type with the same value for the property tested in your filter, you will create an infinite loop.</span></span> <span data-ttu-id="1d0d4-137">El mensaje irá al cuadro de mensajes, de donde se recuperará porque coincide con los criterios del filtro.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-137">The message will go to the MessageBox, where it will be picked up again because it matches the filter criteria.</span></span> <span data-ttu-id="1d0d4-138">Para evitarlo, se debe filtrar según una propiedad diferente, enviar un mensaje de un tipo distinto o asegurarse de cambiar el valor de la propiedad antes de enviar un mensaje del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="1d0d4-138">To avoid this, you should either filter on a different property, send a message of a different type, or be sure to change the value of the property before sending out a message of the same type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d0d4-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d0d4-139">See Also</span></span>  
 <span data-ttu-id="1d0d4-140">[Cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="1d0d4-140">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 <span data-ttu-id="1d0d4-141">[Usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="1d0d4-141">[Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md) </span></span>  
 <span data-ttu-id="1d0d4-142">[Usar campos distintivos y campos de propiedades](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="1d0d4-142">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="1d0d4-143">Usar mensajes en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="1d0d4-143">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)