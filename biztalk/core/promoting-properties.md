---
title: "Promoción de propiedades | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1c5ac3e6e9aeadccc4eaefcb1457821ef36a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="promoting-properties"></a><span data-ttu-id="c9eb7-102">Promoción de propiedades</span><span class="sxs-lookup"><span data-stu-id="c9eb7-102">Promoting Properties</span></span>
<span data-ttu-id="c9eb7-103">Promoción de propiedades implica cualquier promoción **elemento de campo** o **atributo de campo** nodos en un esquema para que sea **campos distintivos** o **propiedad Campos**.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-103">Promotion of properties involves either promoting **Field Element** or **Field Attribute** nodes in a schema to be **Distinguished Fields** or **Property Fields**.</span></span> <span data-ttu-id="c9eb7-104">También puede promocionar **registro** nodos como **campos de propiedades** si tienen contenido simple (**Content Type** propiedad de la **registro** nodo establecido en **SimpleContent**).</span><span class="sxs-lookup"><span data-stu-id="c9eb7-104">You can also promote **Record** nodes as **Property Fields** if they have simple content (**Content Type** property of the **Record** node set to **SimpleContent**).</span></span> <span data-ttu-id="c9eb7-105">Esta sección proporciona instrucciones paso a paso para promocionar nodos como **campos distintivos** o como **campos de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-105">This section provides step-by-step instructions for promoting nodes as either **Distinguished Fields** or as **Property Fields**.</span></span>  
  
 <span data-ttu-id="c9eb7-106">Para promover un **registro** (con contenido simple), **elemento de campo**, o **atributo de campo** nodo como un **campo de propiedad**, primero debe definir un tipo especial de esquema denominado esquema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-106">To promote a **Record** (with simple content), **Field Element**, or **Field Attribute** node as a **Property Field**, you may first define a special type of schema called a property schema.</span></span> <span data-ttu-id="c9eb7-107">Esquemas de propiedad definen un conjunto no estructurado de **elemento de campo** nodos en el que se promueve **registro** (con contenido simple), **elemento de campo**, o  **Atributo de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-107">Property schemas define an unstructured set of **Field Element** nodes into which you promote **Record** (with simple content), **Field Element**, or **Field Attribute** nodes.</span></span> <span data-ttu-id="c9eb7-108">Para obtener instrucciones paso a paso para crear un esquema de propiedades, vea [cómo crear esquemas de propiedad](../core/how-to-create-property-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="c9eb7-108">For step-by-step instructions for creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
 <span data-ttu-id="c9eb7-109">Como alternativa, puede usar el **promoción rápida** característica, que se creará automáticamente y actualizar un esquema de propiedades individual cada vez que promocione un nuevo **elemento de campo**, **atributo de campo** , o **registro** (con contenido simple) nodo.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-109">Alternatively, you can use the **Quick Promotion** feature, which will automatically create and update a single property schema whenever you promote a new **Field Element**, **Field Attribute**, or **Record** (with simple content) node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9eb7-110">Puede promover un campo como un **campo distintivo** y un **campo de la propiedad**.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-110">You can promote a field as both a **Distinguished Field** and a **Property Field**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9eb7-111">El **promoción rápida** característica modifica el esquema de propiedades mediante la inserción de una nueva propiedad con el nombre del nodo promocionado.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-111">The **Quick Promotion** feature modifies the property schema by inserting a new property with the name of the promoted node.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9eb7-112">No mueva ni cambie el nombre de un campo en el esquema después de haberlo promocionado.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-112">Do not move or rename a field in the schema once you have promoted it.</span></span> <span data-ttu-id="c9eb7-113">Al mover o cambiar el nombre de un campo del esquema, el Editor de BizTalk no actualiza el XPath que define la ubicación del campo promocionado.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-113">When you move or rename a schema field, BizTalk Editor does not update the XPath defining the location of the promoted field.</span></span>  
  
## <a name="xsd-and-clr-data-types"></a><span data-ttu-id="c9eb7-114">Tipos de datos XSD y CLR</span><span class="sxs-lookup"><span data-stu-id="c9eb7-114">XSD and CLR Data Types</span></span>  
 <span data-ttu-id="c9eb7-115">En algunos lugares, como en la promoción de propiedades, los tipos de datos XSD se promoción a tipos de datos CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="c9eb7-115">In some places, such as in property promotion, XSD data types are promoted to Common Language Runtime (CLR) data types.</span></span> <span data-ttu-id="c9eb7-116">La siguiente tabla muestra los tipos de datos XSD que se pueden promocionar y los tipos de datos CLR correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-116">The following table shows the XSD data types that can be promoted and the corresponding CLR data types.</span></span>  
  
|<span data-ttu-id="c9eb7-117">Tipo de datos XSD</span><span class="sxs-lookup"><span data-stu-id="c9eb7-117">XSD Data Type</span></span>|<span data-ttu-id="c9eb7-118">Tipo de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="c9eb7-118">CLR Data Type</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="c9eb7-119">anyURI</span><span class="sxs-lookup"><span data-stu-id="c9eb7-119">anyURI</span></span>|<span data-ttu-id="c9eb7-120">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-120">String</span></span>|  
|<span data-ttu-id="c9eb7-121">Boolean</span><span class="sxs-lookup"><span data-stu-id="c9eb7-121">Boolean</span></span>|<span data-ttu-id="c9eb7-122">Boolean</span><span class="sxs-lookup"><span data-stu-id="c9eb7-122">Boolean</span></span>|  
|<span data-ttu-id="c9eb7-123">Byte</span><span class="sxs-lookup"><span data-stu-id="c9eb7-123">Byte</span></span>|<span data-ttu-id="c9eb7-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="c9eb7-124">sbyte</span></span>|  
|<span data-ttu-id="c9eb7-125">Date</span><span class="sxs-lookup"><span data-stu-id="c9eb7-125">Date</span></span>|<span data-ttu-id="c9eb7-126">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-126">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-127">dateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-127">dateTime</span></span>|<span data-ttu-id="c9eb7-128">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-128">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="c9eb7-129">Decimal</span></span>|<span data-ttu-id="c9eb7-130">Decimal</span><span class="sxs-lookup"><span data-stu-id="c9eb7-130">Decimal</span></span>|  
|<span data-ttu-id="c9eb7-131">Doble</span><span class="sxs-lookup"><span data-stu-id="c9eb7-131">Double</span></span>|<span data-ttu-id="c9eb7-132">Doble</span><span class="sxs-lookup"><span data-stu-id="c9eb7-132">Double</span></span>|  
|<span data-ttu-id="c9eb7-133">ENTITY</span><span class="sxs-lookup"><span data-stu-id="c9eb7-133">ENTITY</span></span>|<span data-ttu-id="c9eb7-134">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-134">String</span></span>|  
|<span data-ttu-id="c9eb7-135">Float</span><span class="sxs-lookup"><span data-stu-id="c9eb7-135">Float</span></span>|<span data-ttu-id="c9eb7-136">Único</span><span class="sxs-lookup"><span data-stu-id="c9eb7-136">Single</span></span>|  
|<span data-ttu-id="c9eb7-137">gDay</span><span class="sxs-lookup"><span data-stu-id="c9eb7-137">gDay</span></span>|<span data-ttu-id="c9eb7-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-138">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-139">gMonth</span><span class="sxs-lookup"><span data-stu-id="c9eb7-139">gMonth</span></span>|<span data-ttu-id="c9eb7-140">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-140">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-141">gMonthDay</span><span class="sxs-lookup"><span data-stu-id="c9eb7-141">gMonthDay</span></span>|<span data-ttu-id="c9eb7-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-142">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-143">gYear</span><span class="sxs-lookup"><span data-stu-id="c9eb7-143">gYear</span></span>|<span data-ttu-id="c9eb7-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-144">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-145">gYearMonth</span><span class="sxs-lookup"><span data-stu-id="c9eb7-145">gYearMonth</span></span>|<span data-ttu-id="c9eb7-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-146">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-147">ID</span><span class="sxs-lookup"><span data-stu-id="c9eb7-147">ID</span></span>|<span data-ttu-id="c9eb7-148">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-148">String</span></span>|  
|<span data-ttu-id="c9eb7-149">IDREF</span><span class="sxs-lookup"><span data-stu-id="c9eb7-149">IDREF</span></span>|<span data-ttu-id="c9eb7-150">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-150">String</span></span>|  
|<span data-ttu-id="c9eb7-151">int</span><span class="sxs-lookup"><span data-stu-id="c9eb7-151">Int</span></span>|<span data-ttu-id="c9eb7-152">Int32</span><span class="sxs-lookup"><span data-stu-id="c9eb7-152">Int32</span></span>|  
|<span data-ttu-id="c9eb7-153">Integer</span><span class="sxs-lookup"><span data-stu-id="c9eb7-153">Integer</span></span>|<span data-ttu-id="c9eb7-154">Decimal</span><span class="sxs-lookup"><span data-stu-id="c9eb7-154">Decimal</span></span>|  
|<span data-ttu-id="c9eb7-155">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="c9eb7-155">Language</span></span>|<span data-ttu-id="c9eb7-156">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-156">String</span></span>|  
|<span data-ttu-id="c9eb7-157">Nombre</span><span class="sxs-lookup"><span data-stu-id="c9eb7-157">Name</span></span>|<span data-ttu-id="c9eb7-158">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-158">String</span></span>|  
|<span data-ttu-id="c9eb7-159">NCName</span><span class="sxs-lookup"><span data-stu-id="c9eb7-159">NCName</span></span>|<span data-ttu-id="c9eb7-160">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-160">String</span></span>|  
|<span data-ttu-id="c9eb7-161">negativeInteger</span><span class="sxs-lookup"><span data-stu-id="c9eb7-161">negativeInteger</span></span>|<span data-ttu-id="c9eb7-162">Decimal</span><span class="sxs-lookup"><span data-stu-id="c9eb7-162">Decimal</span></span>|  
|<span data-ttu-id="c9eb7-163">NMTOKEN</span><span class="sxs-lookup"><span data-stu-id="c9eb7-163">NMTOKEN</span></span>|<span data-ttu-id="c9eb7-164">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-164">String</span></span>|  
|<span data-ttu-id="c9eb7-165">nonNegativeInteger</span><span class="sxs-lookup"><span data-stu-id="c9eb7-165">nonNegativeInteger</span></span>|<span data-ttu-id="c9eb7-166">Decimal</span><span class="sxs-lookup"><span data-stu-id="c9eb7-166">Decimal</span></span>|  
|<span data-ttu-id="c9eb7-167">nonPositiveInteger</span><span class="sxs-lookup"><span data-stu-id="c9eb7-167">nonPositiveInteger</span></span>|<span data-ttu-id="c9eb7-168">Decimal</span><span class="sxs-lookup"><span data-stu-id="c9eb7-168">Decimal</span></span>|  
|<span data-ttu-id="c9eb7-169">normalizedString</span><span class="sxs-lookup"><span data-stu-id="c9eb7-169">normalizedString</span></span>|<span data-ttu-id="c9eb7-170">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-170">String</span></span>|  
|<span data-ttu-id="c9eb7-171">NOTATION</span><span class="sxs-lookup"><span data-stu-id="c9eb7-171">NOTATION</span></span>|<span data-ttu-id="c9eb7-172">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-172">String</span></span>|  
|<span data-ttu-id="c9eb7-173">positiveInteger</span><span class="sxs-lookup"><span data-stu-id="c9eb7-173">positiveInteger</span></span>|<span data-ttu-id="c9eb7-174">Decimal</span><span class="sxs-lookup"><span data-stu-id="c9eb7-174">Decimal</span></span>|  
|<span data-ttu-id="c9eb7-175">QName</span><span class="sxs-lookup"><span data-stu-id="c9eb7-175">QName</span></span>|<span data-ttu-id="c9eb7-176">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-176">String</span></span>|  
|<span data-ttu-id="c9eb7-177">Short</span><span class="sxs-lookup"><span data-stu-id="c9eb7-177">Short</span></span>|<span data-ttu-id="c9eb7-178">Int16</span><span class="sxs-lookup"><span data-stu-id="c9eb7-178">Int16</span></span>|  
|<span data-ttu-id="c9eb7-179">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-179">String</span></span>|<span data-ttu-id="c9eb7-180">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-180">String</span></span>|  
|<span data-ttu-id="c9eb7-181">Time</span><span class="sxs-lookup"><span data-stu-id="c9eb7-181">Time</span></span>|<span data-ttu-id="c9eb7-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="c9eb7-182">DateTime</span></span>|  
|<span data-ttu-id="c9eb7-183">Token</span><span class="sxs-lookup"><span data-stu-id="c9eb7-183">Token</span></span>|<span data-ttu-id="c9eb7-184">String</span><span class="sxs-lookup"><span data-stu-id="c9eb7-184">String</span></span>|  
|<span data-ttu-id="c9eb7-185">unsignedByte</span><span class="sxs-lookup"><span data-stu-id="c9eb7-185">unsignedByte</span></span>|<span data-ttu-id="c9eb7-186">Byte</span><span class="sxs-lookup"><span data-stu-id="c9eb7-186">Byte</span></span>|  
|<span data-ttu-id="c9eb7-187">unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c9eb7-187">unsignedInt</span></span>|<span data-ttu-id="c9eb7-188">UInt32</span><span class="sxs-lookup"><span data-stu-id="c9eb7-188">UInt32</span></span>|  
|<span data-ttu-id="c9eb7-189">unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c9eb7-189">unsignedShort</span></span>|<span data-ttu-id="c9eb7-190">UInt16</span><span class="sxs-lookup"><span data-stu-id="c9eb7-190">UInt16</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c9eb7-191">Los tipos de datos XSD de base64Binary, duration, ENTITES, hexBinary, IDREFS, long, NMTOKENS y unsignedLong no se admiten para promoción.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-191">XSD Data Type of base64Binary, duration, ENTITES, hexBinary, IDREFS, long, NMTOKENS, and unsignedLong are not supported for promotion.</span></span>  
  
## <a name="limitations-for-promoting-properties"></a><span data-ttu-id="c9eb7-192">Limitaciones para promocionar propiedades</span><span class="sxs-lookup"><span data-stu-id="c9eb7-192">Limitations for Promoting Properties</span></span>  
 <span data-ttu-id="c9eb7-193">Al promocionar propiedades, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9eb7-193">When promoting properties, consider the following:</span></span>  
  
-   <span data-ttu-id="c9eb7-194">Las propiedades promocionadas no pueden poseer más de 256 caracteres de longitud, mientras que en las propiedades escritas no existe limitación.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-194">Promoted properties are limited to 256 characters in length while written properties have no length limitation.</span></span>  
  
-   <span data-ttu-id="c9eb7-195">Las propiedades promocionadas se utilizan en el enrutamiento de mensajes y poseen un tamaño limitado por motivos de eficacia en su comparación y almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-195">Promoted properties are used in message routing and are limited in size for reasons of efficiency in comparison and storage.</span></span> <span data-ttu-id="c9eb7-196">Aunque las propiedades escritas no poseen limitaciones en el tamaño, el empleo de valores excesivamente grandes en el contexto puede afectar al rendimiento, ya que pueden procesarse y transmitirse con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-196">While written properties have no hard limits on size, using excessively large values in the context will have an impact on performance, because those values must still be processed and passed with the message.</span></span> <span data-ttu-id="c9eb7-197">Los campos distintivos son los ejemplos de propiedades escritas.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-197">Distinguished Fields are the examples of written properties.</span></span>  
  
-   <span data-ttu-id="c9eb7-198">Los nodos registro nunca se pueden promocionar como **campos distintivos**.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-198">Record nodes can never be promoted as **Distinguished Fields**.</span></span>  
  
-   <span data-ttu-id="c9eb7-199">Las propiedades promocionadas se restringen a atributos o elementos que no son de repetición.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-199">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
-   <span data-ttu-id="c9eb7-200">No promocione a la misma propiedad campos que pertenezcan al mismo nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-200">Do not promote fields belonging to the same root node to the same property.</span></span> <span data-ttu-id="c9eb7-201">Dichas promociones producen errores de compilación o de implementación.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-201">Such promotions produce compilation or deployment errors.</span></span>  
  
-   <span data-ttu-id="c9eb7-202">En un contexto de mensaje, hay algunas propiedades que no están disponibles, ya que no se han promocionado.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-202">Within a message context, there are some properties that are not available since they are not promoted.</span></span>  <span data-ttu-id="c9eb7-203">La propiedad BTS.ReceiveLocationName es de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-203">The BTS.ReceiveLocationName property is one such property.</span></span> <span data-ttu-id="c9eb7-204">Si puede agregar un nuevo esquema de propiedad o un nuevo proyecto de BizTalk Server al desarrollo, es posible tener acceso a esa propiedad desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-204">If you can add a new property schema or a new BizTalk Server project to your development it is possible to access this property from within an orchestration.</span></span>  
  
     <span data-ttu-id="c9eb7-205">Los valores de propiedades se identifican mediante el espacio de nombres de destino de propiedad y el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-205">Property values are identified by the property target namespace and property name.</span></span>  <span data-ttu-id="c9eb7-206">En el ejemplo siguiente se muestra cómo obtener acceso a la ubicación de recepción en el código.</span><span class="sxs-lookup"><span data-stu-id="c9eb7-206">The following example shows how to access the receive location in code.</span></span>  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a><span data-ttu-id="c9eb7-207">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c9eb7-207">In This Section</span></span>  
  
-   [<span data-ttu-id="c9eb7-208">Cómo abrir el cuadro de diálogo de propiedades promocionar</span><span class="sxs-lookup"><span data-stu-id="c9eb7-208">How to Open the Promote Properties Dialog Box</span></span>](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [<span data-ttu-id="c9eb7-209">Cómo copiar los datos en el contexto del mensaje como campos distintivos</span><span class="sxs-lookup"><span data-stu-id="c9eb7-209">How to Copy Data to the Message Context as Distinguished Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [<span data-ttu-id="c9eb7-210">Cómo copiar los datos en el contexto del mensaje como campos de propiedades</span><span class="sxs-lookup"><span data-stu-id="c9eb7-210">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)