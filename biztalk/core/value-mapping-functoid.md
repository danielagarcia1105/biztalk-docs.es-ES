---
title: El Functoid de asignación de valor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038d59827a62c9f4e83879ec7cf2e0b47fd738f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973786"
---
# <a name="value-mapping-functoid"></a><span data-ttu-id="9f4a7-102">Asignación de valores (functoid)</span><span class="sxs-lookup"><span data-stu-id="9f4a7-102">Value Mapping Functoid</span></span>
<span data-ttu-id="9f4a7-103">El **Value Mapping** functoid devuelve el valor de su segundo parámetro si el primer parámetro es true.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="9f4a7-104">Una utilización común del functoid es cambiar los atributos de un campo a los atributos de un registro.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span> <span data-ttu-id="9f4a7-105">Para eliminar la estructura de una parte de un mensaje de entrada convirtiendo varios registros en un único registro, use el [Functoid de asignación de valores (sin formato)](../core/value-mapping-flattening-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="9f4a7-105">To flatten a portion of an input message by converting multiple records into a single record, use the [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
 <span data-ttu-id="9f4a7-106">La siguiente ilustración muestra un mapa con la **Value Mapping** functoid utilizado para cambiar los atributos de un campo en los atributos de un registro.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-106">The following figure shows a map with the **Value Mapping** functoid used to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="9f4a7-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="9f4a7-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span></span>  
<span data-ttu-id="9f4a7-108">Asignación de functoid de asignación de valores</span><span class="sxs-lookup"><span data-stu-id="9f4a7-108">Value Mapping Functoid Map</span></span>  
  
 <span data-ttu-id="9f4a7-109">El código siguiente muestra un mensaje de instancia de entrada en los pares de nombres y valores se asignan a **nombre** y **valor** atributos.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-109">The following code shows an input instance message in which pairs of names and values are assigned to **Name** and **Value** attributes.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherIn">  
    <Record>  
        <Field Name="WindSpeed" Value="5"/>   
        <Field Name="Temperature" Value="20" />  
    </Record>  
    <Record>  
        <Field Name="WindSpeed" Value="15" />  
        <Field Name="Temperature" Value="18" />  
    </Record>  
</ns0:Root>  
```  
  
 <span data-ttu-id="9f4a7-110">La asignación anterior puede convertir este mensaje en otro en el que los valores se asignen a atributos con los correspondientes nombres en registros separados.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-110">The preceding map can convert this message into one in which the values are assigned to attributes with the corresponding names in separate records.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 <span data-ttu-id="9f4a7-111">El **igual** functoids probar los valores de la **nombre** atributo.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-111">The **Equal** functoids test the values of the **Name** attribute.</span></span> <span data-ttu-id="9f4a7-112">La primera **igual** pruebas de functoid para el valor de **nombre** es "WindSpeed."</span><span class="sxs-lookup"><span data-stu-id="9f4a7-112">The first **Equal** functoid tests for the value of **Name** being "WindSpeed."</span></span> <span data-ttu-id="9f4a7-113">Cuando el **nombre** es "WindSpeed," la primera **igual** functoid devuelve **True**.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-113">When the **Name** is "WindSpeed," the first **Equal** functoid returns **True**.</span></span> <span data-ttu-id="9f4a7-114">Esto, a su vez, permite la **Value Mapping** functoid para establecer el valor de la **WindSpeed** atributo en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-114">This, in turn, allows the **Value Mapping** functoid to set the value of the **WindSpeed** attribute in the output instance message.</span></span>  
  
## <a name="suppressing-the-creation-of-empty-tags"></a><span data-ttu-id="9f4a7-115">Suprimir la creación de etiquetas vacías</span><span class="sxs-lookup"><span data-stu-id="9f4a7-115">Suppressing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="9f4a7-116">Para suprimir etiquetas vacías, utilice el functoid de asignación de valores para controlar si una etiqueta se crea o no.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-116">To suppress empty tags, use the Value Mapping functoid to control if a tag gets created or not.</span></span> <span data-ttu-id="9f4a7-117">Si el valor se evalúa como, se creará el campo de destino; de lo contrario, el campo de destino no se creará.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-117">If the value is evaluated to true, the destination field will be created; otherwise the destination field will not be created.</span></span> <span data-ttu-id="9f4a7-118">En un escenario de bucle, utilice un functoid lógico y conéctelo al registro o al campo de destino.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-118">In a looping scenario, use a logical functoid and connect it to the destination record or field.</span></span> <span data-ttu-id="9f4a7-119">Si la condición se evalúa como false, la etiqueta no se creará.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-119">If the condition is evaluated to false, the tag will not be created.</span></span> <span data-ttu-id="9f4a7-120">Para obtener un ejemplo, vea [bucle condicional](../core/conditional-looping.md).</span><span class="sxs-lookup"><span data-stu-id="9f4a7-120">For an example, see [Conditional Looping](../core/conditional-looping.md).</span></span>  
  
## <a name="forcing-the-creation-of-empty-tags"></a><span data-ttu-id="9f4a7-121">Forzar la creación de etiquetas vacías</span><span class="sxs-lookup"><span data-stu-id="9f4a7-121">Forcing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="9f4a7-122">Para forzar la creación de etiquetas vacías, puede agregar un valor en la propiedad de valor del campo de destino o vincular una **Concatenate** functoid para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-122">To force empty tags to be created, you can add a value in the Value property of the destination field or link a **Concatenate** functoid to the destination field.</span></span>  <span data-ttu-id="9f4a7-123">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible forzar la generación de etiquetas vacías seleccionando el "\<vacía\>" valor de la propiedad Value del campo de destino.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-123">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is possible to force the generation of empty tags by selecting the "\<empty\>" value in the Value property of the destination field.</span></span> <span data-ttu-id="9f4a7-124">En este caso, el campo se creará con el valor  vacío.</span><span class="sxs-lookup"><span data-stu-id="9f4a7-124">In this case the field will be created with the empty value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f4a7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f4a7-125">See Also</span></span>  
 <span data-ttu-id="9f4a7-126">[Valor de asignación de Functoid (sin formato)](../core/value-mapping-flattening-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9f4a7-126">[Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md) </span></span>  
 <span data-ttu-id="9f4a7-127">[Cómo agregar Functoids de asignación a una asignación de valores](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="9f4a7-127">[How to Add Value Mapping Functoids to a Map](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="9f4a7-128">Functoids avanzados</span><span class="sxs-lookup"><span data-stu-id="9f4a7-128">Advanced Functoids</span></span>](../core/advanced-functoids.md)