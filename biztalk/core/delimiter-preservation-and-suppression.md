---
title: Conservar y suprimir delimitadores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30985b94-625e-411a-8137-1c129bc197bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0b5a5c60d42892479feacc93aedb3802b11308c
ms.sourcegitcommit: d572ae5c887898adedcb3dfc5f83841beedd3434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
ms.locfileid: "26335504"
---
# <a name="delimiter-preservation-and-suppression"></a><span data-ttu-id="bc4be-102">Supresión y conservación de delimitador</span><span class="sxs-lookup"><span data-stu-id="bc4be-102">Delimiter Preservation and Suppression</span></span>

## <a name="overview"></a><span data-ttu-id="bc4be-103">Información general</span><span class="sxs-lookup"><span data-stu-id="bc4be-103">Overview</span></span>
<span data-ttu-id="bc4be-104">Hay dos propiedades que se aplican a los registros delimitados: **conservar delimitador para datos vacíos** y **Suprimir delimitadores finales**.</span><span class="sxs-lookup"><span data-stu-id="bc4be-104">There are two properties that apply to delimited records: **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters**.</span></span> <span data-ttu-id="bc4be-105">Utilice estas propiedades para controlar la forma en que el ensamblador de archivo sin formato utiliza delimitadores asociados con datos que no existen y delimitadores finales.</span><span class="sxs-lookup"><span data-stu-id="bc4be-105">Use these properties to control how the flat file assembler handles delimiters associated with nonexistent data and trailing delimiters.</span></span> <span data-ttu-id="bc4be-106">Al establecer el **conservar delimitador para datos vacíos** propiedad **Sí** (que es el valor predeterminado), los delimitadores se incluyen en el mensaje de archivo sin formato traducido de:</span><span class="sxs-lookup"><span data-stu-id="bc4be-106">When you set the **Preserve Delimiter For Empty Data** property to **Yes** (which is the default setting), delimiters are included in the translated flat file message for:</span></span>  
  
-   <span data-ttu-id="bc4be-107">Los campos sin datos</span><span class="sxs-lookup"><span data-stu-id="bc4be-107">Fields without data.</span></span>  
  
-   <span data-ttu-id="bc4be-108">Los registros inmediatamente subordinados sin datos que no tienen una etiqueta asociada a ellos</span><span class="sxs-lookup"><span data-stu-id="bc4be-108">Immediately subordinate records without data that do not have a tag associated with them.</span></span>  
  
 <span data-ttu-id="bc4be-109">Al establecer el **conservar delimitador para datos vacíos** propiedad **n**, delimitadores no se incluyen en el archivo sin formato traducido para los registros y campos sin datos.</span><span class="sxs-lookup"><span data-stu-id="bc4be-109">When you set the **Preserve Delimiter For Empty Data** property to **No**, delimiters are not included in the translated flat file for records and fields without data.</span></span> <span data-ttu-id="bc4be-110">Además, independientemente de la configuración de la **conservar delimitador para datos vacíos** propiedad delimitadores no se incluirá en el mensaje de archivo sin formato traducido de registros inmediatamente subordinados sin datos para el que se define una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bc4be-110">Further, regardless of the setting of the **Preserve Delimiter For Empty Data** property, delimiters will not be included in the translated flat file message for immediately subordinate records without data for which a tag is defined.</span></span>  
  
 <span data-ttu-id="bc4be-111">Al establecer el **Suprimir delimitadores finales** propiedad **No** (que es el valor predeterminado), uno o más delimitadores finales pueden incluirse en el mensaje de archivo sin formato traducido.</span><span class="sxs-lookup"><span data-stu-id="bc4be-111">When you set the **Suppress Trailing Delimiters** property to **No** (which is the default setting), one or more trailing delimiters may be included in the translated flat file message.</span></span> <span data-ttu-id="bc4be-112">Al establecer el **Suprimir delimitadores finales** propiedad **Sí**, finales delimitadores no se incluyen en el mensaje de archivo sin formato traducido.</span><span class="sxs-lookup"><span data-stu-id="bc4be-112">When you set the **Suppress Trailing Delimiters** property to **Yes**, trailing delimiters are not included in the translated flat file message.</span></span>  

## <a name="special-scenarios"></a><span data-ttu-id="bc4be-113">Escenarios especiales</span><span class="sxs-lookup"><span data-stu-id="bc4be-113">Special scenarios</span></span>  
 <span data-ttu-id="bc4be-114">Hay algunos casos especiales en los comportamientos ocasionados por la configuración de la **conservar delimitador para datos vacíos** y **Suprimir delimitadores finales** propiedades pueden entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="bc4be-114">There are some special cases where the behaviors caused by the settings of the **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters** properties can conflict.</span></span> <span data-ttu-id="bc4be-115">En tales casos, los comportamientos asociados con la última propiedad, **Suprimir delimitadores finales**, tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="bc4be-115">In such cases, the behaviors associated with the latter property, **Suppress Trailing Delimiters**, will take precedence.</span></span> <span data-ttu-id="bc4be-116">Además, en algunos casos especiales, se le advertirá de que pueden existir conflictos potenciales entre los valores configurados para estas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="bc4be-116">Further, there are some special cases where you will be warned about potential conflicts between the settings you have chosen for these two properties.</span></span>  
  
 <span data-ttu-id="bc4be-117">Por ejemplo, considere un **registro** nodo definido con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc4be-117">For example, consider a **Record** node defined with the following property values:</span></span>  
  
-   <span data-ttu-id="bc4be-118">Nombre de nodo = MyRec</span><span class="sxs-lookup"><span data-stu-id="bc4be-118">Node Name is MyRec</span></span>  
  
-   <span data-ttu-id="bc4be-119">Identificador de etiquetas = Rec</span><span class="sxs-lookup"><span data-stu-id="bc4be-119">Tag Identifier is Rec</span></span>  
  
-   <span data-ttu-id="bc4be-120">Delimitador secundario = ,</span><span class="sxs-lookup"><span data-stu-id="bc4be-120">Child Delimiter is ,</span></span>  
  
-   <span data-ttu-id="bc4be-121">Orden secundario = Infijo</span><span class="sxs-lookup"><span data-stu-id="bc4be-121">Child Order is Infix</span></span>  
  
 <span data-ttu-id="bc4be-122">Y definido para contener cinco **elemento de campo** nodos con los siguientes nombres (también podrían ser **atributo de campo** nodos o subordinado **registro** nodos):</span><span class="sxs-lookup"><span data-stu-id="bc4be-122">And defined to contain five **Field Element** nodes with the following names (they could also be **Field Attribute** nodes or subordinate **Record** nodes):</span></span>  
  
-   <span data-ttu-id="bc4be-123">FieldElem1</span><span class="sxs-lookup"><span data-stu-id="bc4be-123">FieldElem1</span></span>  
  
-   <span data-ttu-id="bc4be-124">FieldElem2</span><span class="sxs-lookup"><span data-stu-id="bc4be-124">FieldElem2</span></span>  
  
-   <span data-ttu-id="bc4be-125">FieldElem3</span><span class="sxs-lookup"><span data-stu-id="bc4be-125">FieldElem3</span></span>  
  
-   <span data-ttu-id="bc4be-126">FieldElem4</span><span class="sxs-lookup"><span data-stu-id="bc4be-126">FieldElem4</span></span>  
  
-   <span data-ttu-id="bc4be-127">FieldElem5</span><span class="sxs-lookup"><span data-stu-id="bc4be-127">FieldElem5</span></span>  
  
 <span data-ttu-id="bc4be-128">A continuación, se supone que la siguiente principalmente vacía fragmento XML, que representa este **registro** nodo, se pasa para el ensamblador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="bc4be-128">Next, assume that the following mainly empty XML fragment, representing this **Record** node, is passed to the flat file assembler.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="bc4be-129">En la tabla siguiente muestra el resultado generado y la propiedad adicional asociada establecer requisitos para los nodos de esquema correspondiente, según la configuración para la **conservar delimitador para datos vacíos** (PDFED) y **Suprimir delimitadores finales** propiedades (STD).</span><span class="sxs-lookup"><span data-stu-id="bc4be-129">The following table shows the output produced, and the associated additional property setting requirements for the relevant schema nodes, based on different settings for the **Preserve Delimiter For Empty Data** (PDFED) and **Suppress Trailing Delimiters** (STD) properties.</span></span>  
  
|<span data-ttu-id="bc4be-130">Configuración de PDFED</span><span class="sxs-lookup"><span data-stu-id="bc4be-130">PDFED setting</span></span>|<span data-ttu-id="bc4be-131">Configuración de STD</span><span class="sxs-lookup"><span data-stu-id="bc4be-131">STD setting</span></span>|<span data-ttu-id="bc4be-132">Salida</span><span class="sxs-lookup"><span data-stu-id="bc4be-132">Output</span></span>|<span data-ttu-id="bc4be-133">Requisitos adicionales del nodo</span><span class="sxs-lookup"><span data-stu-id="bc4be-133">Additional node requirements</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="bc4be-134">Sí</span><span class="sxs-lookup"><span data-stu-id="bc4be-134">Yes</span></span>|<span data-ttu-id="bc4be-135">No</span><span class="sxs-lookup"><span data-stu-id="bc4be-135">No</span></span>|<span data-ttu-id="bc4be-136">Rec,,,Val,,</span><span class="sxs-lookup"><span data-stu-id="bc4be-136">Rec,,,Val,,</span></span>|<span data-ttu-id="bc4be-137">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bc4be-137">None.</span></span>|  
|<span data-ttu-id="bc4be-138">No</span><span class="sxs-lookup"><span data-stu-id="bc4be-138">No</span></span>|<span data-ttu-id="bc4be-139">Sí</span><span class="sxs-lookup"><span data-stu-id="bc4be-139">Yes</span></span>|<span data-ttu-id="bc4be-140">Rec,Val</span><span class="sxs-lookup"><span data-stu-id="bc4be-140">Rec,Val</span></span>|<span data-ttu-id="bc4be-141">Todos los **elemento de campo** nodos deben estar configurados como opcionales.</span><span class="sxs-lookup"><span data-stu-id="bc4be-141">All **Field Element** nodes must be configured as optional.</span></span>|  
|<span data-ttu-id="bc4be-142">Sí</span><span class="sxs-lookup"><span data-stu-id="bc4be-142">Yes</span></span>|<span data-ttu-id="bc4be-143">Sí</span><span class="sxs-lookup"><span data-stu-id="bc4be-143">Yes</span></span>|<span data-ttu-id="bc4be-144">Rec,,,Val</span><span class="sxs-lookup"><span data-stu-id="bc4be-144">Rec,,,Val</span></span>|<span data-ttu-id="bc4be-145">Nodos denominados **FieldElem4** y **FieldElem5** se deben configurar como opcionales.</span><span class="sxs-lookup"><span data-stu-id="bc4be-145">Nodes named **FieldElem4** and **FieldElem5** must be configured as optional.</span></span>|  
|<span data-ttu-id="bc4be-146">No</span><span class="sxs-lookup"><span data-stu-id="bc4be-146">No</span></span>|<span data-ttu-id="bc4be-147">No</span><span class="sxs-lookup"><span data-stu-id="bc4be-147">No</span></span>|<span data-ttu-id="bc4be-148">Rec,Val,,</span><span class="sxs-lookup"><span data-stu-id="bc4be-148">Rec,Val,,</span></span>|<span data-ttu-id="bc4be-149">Todos los **elemento de campo** nodos deben estar configurados como opcionales.</span><span class="sxs-lookup"><span data-stu-id="bc4be-149">All **Field Element** nodes must be configured as optional.</span></span>|  
  
 <span data-ttu-id="bc4be-150">Si la configuración de estas propiedades especifica que los delimitadores no se deben conservar o suprimir, se generará un mensaje de advertencia para indicar que puede que no sea posible analizar los datos de archivo sin formato serializados mediante el mismo esquema en los dos casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc4be-150">When these property settings specify that delimiters should either not be preserved or should be suppressed, a message warning that it might not be possible to parse the serialized flat file data using the same schema will be issued in the following two cases:</span></span>  
  
-   <span data-ttu-id="bc4be-151">Cuando el **registro** nodo para el que el **conservar delimitador para datos vacíos** propiedad está establecida en **No** o **Suprimir delimitadores finales**propiedad está establecida en **Sí**, respectivamente, contiene subordinados **elemento de campo** nodos, **atributo de campo** nodos, o **registro**  nodos para el que no se ha especificado ninguna etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bc4be-151">When the **Record** node for which the **Preserve Delimiter For Empty Data** property is set to **No** and/or the **Suppress Trailing Delimiters** property is set to **Yes**, respectively, contains subordinate **Field Element** nodes, **Field Attribute** nodes, or **Record** nodes for which no tag is specified.</span></span>  
  
-   <span data-ttu-id="bc4be-152">Cuando el subordinado **elemento de campo** nodos, **atributo de campo** nodos, y **registro** para el que no se ha especificado ninguna etiqueta no están configurados para que sean opcionales (estableciendo la **Min Occurs** propiedad establecida en cero) en el esquema.</span><span class="sxs-lookup"><span data-stu-id="bc4be-152">When the subordinate **Field Element** nodes, **Field Attribute** nodes, and **Record** nodes for which no tag is specified are not configured to be optional (by setting the **Min Occurs** property set to zero) in the schema.</span></span> <span data-ttu-id="bc4be-153">Cuando el **Suprimir delimitadores finales** propiedad está establecida en **Sí**, solo la última esos nodos subordinados debe configurarse como opcional.</span><span class="sxs-lookup"><span data-stu-id="bc4be-153">When the **Suppress Trailing Delimiters** property is set to **Yes**, only the last such subordinate nodes need to be configured as optional.</span></span> <span data-ttu-id="bc4be-154">Cuando el **conservar delimitador para datos vacíos** propiedad está establecida en **No**, al final de todos los nodos subordinados debe configurarse como opcional.</span><span class="sxs-lookup"><span data-stu-id="bc4be-154">When the **Preserve Delimiter For Empty Data** property is set to **No**, all trailing subordinate nodes need to be configured as optional.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc4be-155">Siempre se conservan los delimitadores cuando el elemento XML asociado a un (presumiblemente opcional) **registro**, **elemento de campo**, o **atributo de campo** nodo son falta por completo en la representación XML del documento empresarial, excepto cuando un registro sigue a un campo opcional ausente.</span><span class="sxs-lookup"><span data-stu-id="bc4be-155">Delimiters are always preserved when the XML element associated with a (presumably optional) **Record**, **Field Element**, or **Field Attribute** node are entirely missing from the XML representation of the business document except when a Record follows a missing optional Field.</span></span> <span data-ttu-id="bc4be-156">En otras palabras, cuando faltan los datos y las etiquetas XML que los rodean, el delimitador correspondiente siempre se incluye en la representación de archivo sin formato del documento empresarial.</span><span class="sxs-lookup"><span data-stu-id="bc4be-156">In other words, when the data and its surrounding XML tags are both missing, the corresponding delimiter is always included in the flat file representation of the business document.</span></span>  
  
 <span data-ttu-id="bc4be-157">Ahora, cambie el esquema para incluir un registro secundario con dos Elemento de campo que sigan inmediatamente a un Elemento de campo ausente.</span><span class="sxs-lookup"><span data-stu-id="bc4be-157">Now change the schema to include a child record with two Field Element immediately following a missing Field Element.</span></span> <span data-ttu-id="bc4be-158">Los elementos del registro secundario se configuran para usar la &#124; carácter (barra vertical) como delimitador.</span><span class="sxs-lookup"><span data-stu-id="bc4be-158">The child record elements are configured to use the &#124; (pipe) character as a delimiter.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <!-- <FieldElem4 /> -->  
    <ChildRec>  
        <InnerFieldElement1>Inner1</InnerFieldElement1>   
        <InnerFieldElement2>Inner2</InnerFieldElement1>  
    </ChildRec>  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="bc4be-159">Si lo anterior se pasa al desensamblador de archivos sin formato, los delimitadores de FieldElem4 no se conservarán, aunque los registros posteriores se delimitarán según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="bc4be-159">If this is passed to the flat file disassembler, the delimiters for FieldElem4 will not be preserved but subsequent records will be delimited as expected.</span></span>  
  
```  
,,Val,,Inner1,Inner2,,  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc4be-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc4be-160">See Also</span></span>  
-  [<span data-ttu-id="bc4be-161">Consideraciones acerca de los registros delimitados</span><span class="sxs-lookup"><span data-stu-id="bc4be-161">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
-  <span data-ttu-id="bc4be-162">**Conservar delimitador para datos vacíos (propiedad de nodo de esquemas de archivo sin formato)** y **Suprimir delimitadores (propiedad de nodo de esquemas de archivo sin formato) finales**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="bc4be-162">**Preserve Delimiter For Empty Data (Node Property of Flat File Schemas)** and **Suppress Trailing Delimiters (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
