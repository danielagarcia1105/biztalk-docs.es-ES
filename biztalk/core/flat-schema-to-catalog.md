---
title: Planos esquema al catálogo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0e37afa-2329-4691-9fa1-82b8c7bcd59a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f3a45ad66ca10ab829a4cc7279891487124c3cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246260"
---
# <a name="flat-schema-to-catalog"></a><span data-ttu-id="088f6-102">De esquema sin formato a catálogo</span><span class="sxs-lookup"><span data-stu-id="088f6-102">Flat Schema to Catalog</span></span>

## <a name="overview"></a><span data-ttu-id="088f6-103">Información general</span><span class="sxs-lookup"><span data-stu-id="088f6-103">Overview</span></span>
<span data-ttu-id="088f6-104">Puede usar el **bucle** functoid para convertir un esquema sin formato en un esquema jerárquico asignando un único registro a múltiples registros.</span><span class="sxs-lookup"><span data-stu-id="088f6-104">You can use the **Looping** functoid to convert a flat schema to an hierarchical schema by mapping a single record to multiple records.</span></span> <span data-ttu-id="088f6-105">Ésta es una operación común para convertir esquemas sin formato en catálogos de Microsoft Commerce Server.</span><span class="sxs-lookup"><span data-stu-id="088f6-105">This is a common operation in converting flat schemas to Microsoft Commerce Server catalogs.</span></span>  
  
 <span data-ttu-id="088f6-106">En el siguiente código se muestra una parte de un catálogo que enumera variantes de producto, y cada variante como su propio registro.</span><span class="sxs-lookup"><span data-stu-id="088f6-106">The following code shows a portion of a catalog listing product variants with each variant as its own record.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 <span data-ttu-id="088f6-107">Expandir esta parte del catálogo convertiría algunos o todos los **ProductVariant** atributos en registros.</span><span class="sxs-lookup"><span data-stu-id="088f6-107">Expanding this portion of the catalog would convert some or all of the **ProductVariant** attributes into records.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.Catalog">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather"/>  
        <Feature Name="Color" Value="Black"/>  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl"/>  
        <Feature Name="Color" Value="Brown"/>  
    </ProductVariant>  
</ns0:Root>  
```  
  
 <span data-ttu-id="088f6-108">En la ilustración siguiente se muestra una asignación que realiza esta conversión.</span><span class="sxs-lookup"><span data-stu-id="088f6-108">The following figure shows a map that performs this conversion.</span></span>  
  
 <span data-ttu-id="088f6-109">![Mapa que muestra el uso del functoid de bucle. ] (../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")</span><span class="sxs-lookup"><span data-stu-id="088f6-109">![Map showing the use of the looping functoid.](../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")</span></span>  
<span data-ttu-id="088f6-110">Functoid de bucle, asignación de esquema sin formato</span><span class="sxs-lookup"><span data-stu-id="088f6-110">Looping Functoid, Flat Schema Map</span></span>  

## <a name="set-the-schema"></a><span data-ttu-id="088f6-111">Establecer el esquema</span><span class="sxs-lookup"><span data-stu-id="088f6-111">Set the schema</span></span>  
 <span data-ttu-id="088f6-112">Para que este tipo de asignación funcione correctamente, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="088f6-112">For this type of map to work correctly, you must do the following:</span></span>  
  
-   <span data-ttu-id="088f6-113">Para cada vínculo que conecte con el **nombre** campo del esquema de destino, establezca propiedades de vínculo para copiar el nombre de esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="088f6-113">For each link connecting to the **Name** field in the destination schema, set the source-schema link properties to copy the name.</span></span> <span data-ttu-id="088f6-114">Para obtener más información, consulte [configurar vínculos](../core/configuring-links.md).</span><span class="sxs-lookup"><span data-stu-id="088f6-114">For more information, see [Configuring Links](../core/configuring-links.md).</span></span> <span data-ttu-id="088f6-115">Consulte también **propiedades de vínculo de** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="088f6-115">Also see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
-   <span data-ttu-id="088f6-116">Para cada vínculo que conecte con el **valor** campo del esquema de destino, establezca el esquema de origen propiedades de vínculo para copiar el valor (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="088f6-116">For each link connecting to the **Value** field in the destination schema, set the source-schema link properties to copy the value (the default).</span></span>  
  
-   <span data-ttu-id="088f6-117">Para el vínculo al conectar el **bucle** functoid con el registro denominado **característica** en el esquema de destino, establezca el esquema de destino propiedades de vínculo debe coincidir vínculos de arriba a abajo.</span><span class="sxs-lookup"><span data-stu-id="088f6-117">For the link connecting the **Looping** functoid to the record named **Feature** in the destination schema, set the destination-schema link properties to match links top-down.</span></span>  
  
 <span data-ttu-id="088f6-118">Para el inverso de esta asignación, convertir un esquema de catálogo a un esquema sin formato, vea [Functoid de asignación de valores (sin formato)](../core/value-mapping-flattening-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="088f6-118">For the inverse of this mapping, converting a catalog schema to a flat schema, see [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088f6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="088f6-119">See Also</span></span>  
 <span data-ttu-id="088f6-120">[Cómo agregar Functoids a una asignación de bucle](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="088f6-120">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="088f6-121">[Functoid de bucle](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="088f6-121">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="088f6-122">Valor de asignación de Functoid (sin formato)</span><span class="sxs-lookup"><span data-stu-id="088f6-122">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)