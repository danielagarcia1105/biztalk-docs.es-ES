---
title: Valor de asignación de Functoid (sin formato) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping (Flattening) functoids
ms.assetid: d30c3ffe-d3ed-46fd-a692-cd26d042033c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d17d5d64409cd434075dfd4c556209864784e4d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287876"
---
# <a name="value-mapping-flattening-functoid"></a><span data-ttu-id="5b661-102">Asignación de valores (sin formato) (functoid)</span><span class="sxs-lookup"><span data-stu-id="5b661-102">Value Mapping (Flattening) Functoid</span></span>
<span data-ttu-id="5b661-103">El **asignación de valores (sin formato)** functoid permite aplanar una parte de un mensaje de instancia de entrada convirtiendo varios registros en un único registro.</span><span class="sxs-lookup"><span data-stu-id="5b661-103">The **Value Mapping (Flattening)** functoid enables you to flatten a portion of an input instance message by converting multiple records into a single record.</span></span> <span data-ttu-id="5b661-104">Ésta es una operación común para convertir catálogos de Microsoft Commerce Server.</span><span class="sxs-lookup"><span data-stu-id="5b661-104">This is a common operation in converting Microsoft Commerce Server catalogs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b661-105">El **asignación de valores (sin formato)** functoid no debe combinarse con la **bucle** functoid o **bucle de tabla** functoid.</span><span class="sxs-lookup"><span data-stu-id="5b661-105">The **Value Mapping (Flattening)** functoid should not be combined with the **Looping** functoid or the **Table Looping** functoid.</span></span> <span data-ttu-id="5b661-106">Si se combinan, se produce una asignación compilada que considera que no hay dependencia de los nodos de destino que están por debajo de bucle de origen el **bucle** o **bucle de tabla** functoid.</span><span class="sxs-lookup"><span data-stu-id="5b661-106">If they are combined, it results in a compiled map that assumes there is no source looping dependency for the target nodes that are below the **Looping** or **Table Looping** functoid.</span></span>  
  
 <span data-ttu-id="5b661-107">En el siguiente código se muestra una parte de un catálogo que enumera variantes de producto, con cada característica de la variante en un registro independiente.</span><span class="sxs-lookup"><span data-stu-id="5b661-107">The following code shows a portion of a catalog listing product variants with each feature of the variant in a separate record.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsIn">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather" />  
        <Feature Name="Color" Value="Black" />  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl" />  
        <Feature Name="Color" Value="Brown" />  
    </ProductVariant>  
</nso0:Root>  
```  
  
 <span data-ttu-id="5b661-108">Reducción de esta parte del catálogo convertiría la **característica** registros a atributos de la **ProductVariant** registro.</span><span class="sxs-lookup"><span data-stu-id="5b661-108">Flattening this portion of the catalog would convert the **Feature** records into attributes of the **ProductVariant** record.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsOut">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 <span data-ttu-id="5b661-109">En la ilustración siguiente se muestra una asignación que realiza esta conversión.</span><span class="sxs-lookup"><span data-stu-id="5b661-109">The following figure shows a map that performs this conversion.</span></span>  
  
 <span data-ttu-id="5b661-110">![Asignar registros de origen mediante un functoid. ](../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")</span><span class="sxs-lookup"><span data-stu-id="5b661-110">![Map source records using a functoid.](../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")</span></span>  
<span data-ttu-id="5b661-111">Asignación del functoid de asignación de valores (sin formato)</span><span class="sxs-lookup"><span data-stu-id="5b661-111">Value Mapping (Flattening) Functoid Map</span></span>  
  
 <span data-ttu-id="5b661-112">El **asignación de valores (sin formato)** functoid devuelve el valor de su segundo parámetro si el primer parámetro es true.</span><span class="sxs-lookup"><span data-stu-id="5b661-112">The **Value Mapping (Flattening)** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="5b661-113">En esta asignación, la primera **igual** functoid comprueba si el **nombre** atributo es igual a "Material".</span><span class="sxs-lookup"><span data-stu-id="5b661-113">In this map, the first **Equal** functoid tests to see if the **Name** attribute is equal to "Material".</span></span> <span data-ttu-id="5b661-114">Si el atributo es igual a "Material", la **igual** functoid devuelve **True**.</span><span class="sxs-lookup"><span data-stu-id="5b661-114">If the attribute is equal to "Material", the **Equal** functoid returns **True**.</span></span> <span data-ttu-id="5b661-115">A su vez, esto hace que la **asignación de valores (sin formato)** functoid para asignar el valor de la **valor** atributo al campo en el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="5b661-115">In turn, this causes the **Value Mapping (Flattening)** functoid to assign the value of the **Value** attribute to the field in the output message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b661-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b661-116">See Also</span></span>  
 <span data-ttu-id="5b661-117">[Cómo agregar la asignación de valores (sin formato) Functoids a una asignación](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="5b661-117">[How to Add Value Mapping (Flattening) Functoids to a Map](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="5b661-118">[Esquema sin formato a catálogo](../core/flat-schema-to-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="5b661-118">[Flat Schema to Catalog](../core/flat-schema-to-catalog.md) </span></span>  
 [<span data-ttu-id="5b661-119">Functoids avanzados</span><span class="sxs-lookup"><span data-stu-id="5b661-119">Advanced Functoids</span></span>](../core/advanced-functoids.md)