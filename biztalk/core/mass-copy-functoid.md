---
title: Functoid de copia masiva | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- anyAttribute node
- Mass Copy functoids, about Mass Copy functoids
- any node
- Mass Copy functoids
ms.assetid: 228ff569-2e21-4e81-b564-6936241cdf6b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe0a9bc65369327a17591fb6adecb6bd6105333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mass-copy-functoid"></a><span data-ttu-id="ab63b-102">Copia masiva (functoid)</span><span class="sxs-lookup"><span data-stu-id="ab63b-102">Mass Copy Functoid</span></span>
<span data-ttu-id="ab63b-103">El **copia masiva** functoid permite que las asignaciones usen esquemas que incluyen **cualquier** y **anyAttribute** elementos.</span><span class="sxs-lookup"><span data-stu-id="ab63b-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="ab63b-104">Estos elementos son, fundamentalmente, caracteres comodín proporcionados en el lenguaje de definición de esquemas XML para coincidir con estructuras o atributos desconocidos.</span><span class="sxs-lookup"><span data-stu-id="ab63b-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or attributes.</span></span>  
  
 <span data-ttu-id="ab63b-105">Además de controlar datos de estructura desconocida, el **copia masiva** functoid permite simplificar el desarrollo de esquemas: solo las partes de un esquema que se procesarán deben especificarse en detalle.</span><span class="sxs-lookup"><span data-stu-id="ab63b-105">In addition to handling data with unknown structure, the **Mass Copy** functoid enables you to simplify schema development: only the portions of a schema that will be processed need to be specified in detail.</span></span>  
  
 <span data-ttu-id="ab63b-106">El **copia masiva** functoid copia el elemento en el mensaje de instancia de entrada correspondiente al nodo de esquema de origen conectado a la **copia masiva** functoid.</span><span class="sxs-lookup"><span data-stu-id="ab63b-106">The **Mass Copy** functoid copies the element in the input instance message corresponding to the source schema node connected to the **Mass Copy** functoid.</span></span> <span data-ttu-id="ab63b-107">El functoid también copia toda la subestructura y vuelve a crearla en el mensaje de instancia de salida en el nodo vinculado del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="ab63b-107">The functoid also copies any and all of its substructure, and re-creates it in the output instance message at the linked node in the destination schema.</span></span> <span data-ttu-id="ab63b-108">Por lo tanto, también puede usar el **copia masiva** functoid para copiar los registros de origen y de destino que tenga subestructuras idénticas.</span><span class="sxs-lookup"><span data-stu-id="ab63b-108">Thus, you can also use the **Mass Copy** functoid to copy any source and destination records having identical substructures.</span></span>  
  
 <span data-ttu-id="ab63b-109">La siguiente ilustración muestra la **copia masiva** usado en una asignación de functoid.</span><span class="sxs-lookup"><span data-stu-id="ab63b-109">The following figure shows the **Mass Copy** functoid used in a map.</span></span>  
  
 <span data-ttu-id="ab63b-110">![Mapa que ilustra el uso del functoid de copia masiva](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span><span class="sxs-lookup"><span data-stu-id="ab63b-110">![Map illustrating the use of the mass copy functoid](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span></span>  
<span data-ttu-id="ab63b-111">Asignación de functoid de copia masiva</span><span class="sxs-lookup"><span data-stu-id="ab63b-111">Mass Copy Functoid Map</span></span>  
  
 <span data-ttu-id="ab63b-112">Imagine el siguiente mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="ab63b-112">Consider the following input instance message.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://MassCopy.ComplexDocument">  
    <PurchaseOrder>  
        <From>Kevin F. Browne</From>  
        <To>Northwind Traders</To>  
        <LineItems>  
            <Item>  
                <Product>Laptop Computer</Product>  
                <Description>Thin profile laptop</Description>  
                <Price>1999.95</Price>  
                <Quantity>1</Quantity>  
            </Item>  
        </LineItems>  
    </PurchaseOrder>  
</ns0:Root>  
```  
  
 <span data-ttu-id="ab63b-113">Si la asignación anterior se utilizara para procesar este mensaje, el mensaje de instancia de salida sería idéntico al mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="ab63b-113">If the preceding map were used to process this message, the output instance message would be identical to the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab63b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab63b-114">See Also</span></span>  
 <span data-ttu-id="ab63b-115">[Cómo agregar Functoids de copia masiva a un mapa](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="ab63b-115">[How to Add Mass Copy Functoids to a Map](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="ab63b-116">[Functoids avanzados](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="ab63b-116">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="ab63b-117">[Functoids básicos](../core/basic-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="ab63b-117">[Basic Functoids](../core/basic-functoids.md) </span></span>  
 [<span data-ttu-id="ab63b-118">Vínculos a y desde el elemento Any y anyAttribute nodos</span><span class="sxs-lookup"><span data-stu-id="ab63b-118">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)