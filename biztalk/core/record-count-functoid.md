---
title: "El Functoid de número de registros | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Record Count functoids
ms.assetid: e6aab13f-afbe-4401-abbe-020570e2ff16
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87653709bf5d52c21537064bad286078ad625cf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="record-count-functoid"></a><span data-ttu-id="75d9e-102">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="75d9e-102">Record Count Functoid</span></span>
<span data-ttu-id="75d9e-103">El **número de registros** functoid recuentos de registros en el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="75d9e-103">The **Record Count** functoid counts records in the input instance message.</span></span>  
  
 <span data-ttu-id="75d9e-104">El **número de registros** functoid tiene una entrada y una salida.</span><span class="sxs-lookup"><span data-stu-id="75d9e-104">The **Record Count** functoid has one input and one output.</span></span> <span data-ttu-id="75d9e-105">La entrada es un vínculo de un registro de bucle en el esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="75d9e-105">The input is a link from a looping record in the source schema.</span></span> <span data-ttu-id="75d9e-106">El resultado de la **número de registros** functoid es el número de registro de bucle en un mensaje de instancia de entrada real.</span><span class="sxs-lookup"><span data-stu-id="75d9e-106">The output of the **Record Count** functoid is the count of the looping record in an actual input instance message.</span></span>  
  
 <span data-ttu-id="75d9e-107">Los registros de bucle corresponden a los elementos que se repiten un número impredecible de veces en un mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="75d9e-107">Looping records correspond to elements that repeat an unpredictable number of times in an input instance message.</span></span> <span data-ttu-id="75d9e-108">Por ejemplo, en un pedido de compra, la **elemento** elemento podría aparecer muchas veces.</span><span class="sxs-lookup"><span data-stu-id="75d9e-108">For example, in a purchase order, the **Item** element might occur many times.</span></span> <span data-ttu-id="75d9e-109">Y el **elemento** elemento puede incluir productos, descripciones, precios y cantidades.</span><span class="sxs-lookup"><span data-stu-id="75d9e-109">And, the **Item** element might include products, descriptions, prices, and quantities.</span></span> <span data-ttu-id="75d9e-110">El siguiente código es un ejemplo simplificado de este pedido.</span><span class="sxs-lookup"><span data-stu-id="75d9e-110">The following code is a simplified example of such a purchase order.</span></span>  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://RecordFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  
  
 <span data-ttu-id="75d9e-111">El **Max Occurs** propiedad para la **elemento** registro se establece como ilimitado.</span><span class="sxs-lookup"><span data-stu-id="75d9e-111">The **Max Occurs** property for the **Item** record is set as unbounded.</span></span> <span data-ttu-id="75d9e-112">Esto indica que la **elemento** bucles de registro y el asignador de BizTalk compila este registro como un bucle.</span><span class="sxs-lookup"><span data-stu-id="75d9e-112">This indicates that the **Item** record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="75d9e-113">Imagine que desea buscar el número total de **elementos** elementos de la instancia de entrada de pedido de compra de mensajes y colocar el resultado en un campo en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="75d9e-113">Suppose you want to find the total number of **Item** elements in the purchase order input instance message and place the result in a field in the output instance message.</span></span>  
  
 <span data-ttu-id="75d9e-114">La siguiente ilustración muestra un **número de registros** functoid que cuenta el número de elementos de un pedido entrante y escribe ese valor en el **ItemCount** campo el **SummedPO**mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="75d9e-114">The following figure shows a **Record Count** functoid that counts the number of items in an incoming purchase order and puts that value in the **ItemCount** field in the **SummedPO** output instance message.</span></span>  
  
 <span data-ttu-id="75d9e-115">![Mapa que muestra el uso del functoid de número de registros. ] (../core/media/recordcountfunctoid.gif "recordcountfunctoid")</span><span class="sxs-lookup"><span data-stu-id="75d9e-115">![Map showing the use of the record count functoid.](../core/media/recordcountfunctoid.gif "recordcountfunctoid")</span></span>  
<span data-ttu-id="75d9e-116">Asignación de functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="75d9e-116">Record Count Functoid Map</span></span>  
  
 <span data-ttu-id="75d9e-117">Tenga en cuenta que la **Max Occurs** propiedad para la **elemento** registro sería **unbounded**.</span><span class="sxs-lookup"><span data-stu-id="75d9e-117">Notice that the **Max Occurs** property for the **Item** record would be **unbounded**.</span></span> <span data-ttu-id="75d9e-118">Esto indica que la **elemento** bucles de registro y el asignador de BizTalk compila este registro como un bucle.</span><span class="sxs-lookup"><span data-stu-id="75d9e-118">This indicates that the **Item** record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="75d9e-119">Para el anterior ejemplo instancia mensaje de pedido, que contiene dos **elemento** elementos, el valor de la **ItemCount** campo se establecerá en 2.</span><span class="sxs-lookup"><span data-stu-id="75d9e-119">For the preceding sample purchase order instance message, which contained two **Item** elements, the value of the **ItemCount** field will be set to 2.</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://RecordCountFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
    <ItemCount>2</ItemCount>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  <span data-ttu-id="75d9e-120">También puede usar el **número de registros** functoid para contar los elementos de campo de repetición.</span><span class="sxs-lookup"><span data-stu-id="75d9e-120">You can also use the **Record Count** functoid to count repeating field elements.</span></span> <span data-ttu-id="75d9e-121">No está restringido para los registros.</span><span class="sxs-lookup"><span data-stu-id="75d9e-121">It is not restricted to records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d9e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="75d9e-122">See Also</span></span>  
 <span data-ttu-id="75d9e-123">[Cómo agregar Functoids de número de registros a un mapa](../core/how-to-add-record-count-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="75d9e-123">[How to Add Record Count Functoids to a Map](../core/how-to-add-record-count-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="75d9e-124">[Functoids avanzados](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="75d9e-124">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="75d9e-125">[Functoid de índice](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="75d9e-125">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="75d9e-126">[Functoid de iteración](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="75d9e-126">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 [<span data-ttu-id="75d9e-127">Functoid de bucle</span><span class="sxs-lookup"><span data-stu-id="75d9e-127">Looping Functoid</span></span>](../core/looping-functoid.md)