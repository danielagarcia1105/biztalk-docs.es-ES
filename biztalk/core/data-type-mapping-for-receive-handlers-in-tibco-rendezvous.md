---
title: "Asignación de tipos de datos para los controladores de recepción de TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data type mapping
- array types
- receive handlers, data type mapping
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8729a94fdcfc43ca17e498b10784cc163307badc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a><span data-ttu-id="0755d-102">Asignación de tipos de datos para controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0755d-102">Data Type Mapping for Receive Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="0755d-103">El Adaptador de Microsoft BizTalk para TIBCO Rendezvous asigna los tipos TIBCO RV a los tipos de esquemas XML según se especifica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="0755d-103">Microsoft BizTalk Adapter for TIBCO Rendezvous maps TIBCO RV types to XML Schema types as specified in the following table.</span></span>  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a><span data-ttu-id="0755d-104">TIBCO RV para asignación de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="0755d-104">TIBCO RV to XML Data Type Mapping</span></span>  
  
|<span data-ttu-id="0755d-105">Tipo TIBCO RV</span><span class="sxs-lookup"><span data-stu-id="0755d-105">TIBCO RV Type</span></span>|<span data-ttu-id="0755d-106">Tipo de esquema XML</span><span class="sxs-lookup"><span data-stu-id="0755d-106">XML Schema Type</span></span>|<span data-ttu-id="0755d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0755d-107">Comments</span></span>|  
|-------------------|---------------------|--------------|  
|<span data-ttu-id="0755d-108">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="0755d-108">TIBRVMSG_MSG</span></span>|<span data-ttu-id="0755d-109">tibrv:message</span><span class="sxs-lookup"><span data-stu-id="0755d-109">tibrv:message</span></span>|<span data-ttu-id="0755d-110">Completo documento XML construido a partir de todo el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0755d-110">Complete XML document constructed from entire message.</span></span>|  
|<span data-ttu-id="0755d-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="0755d-111">TIBRVMSG_XML</span></span>|<span data-ttu-id="0755d-112">tibrv:rawxml</span><span class="sxs-lookup"><span data-stu-id="0755d-112">tibrv:rawxml</span></span>|<span data-ttu-id="0755d-113">Documento XML construido a partir de la matriz de bytes (no interpreta por el adaptador).</span><span class="sxs-lookup"><span data-stu-id="0755d-113">XML Document constructed from the array of bytes (not interpreted by the adapter).</span></span>|  
|<span data-ttu-id="0755d-114">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="0755d-114">TIBRVMSG_DATETIME</span></span>|<span data-ttu-id="0755d-115">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="0755d-115">xsd:dateTime</span></span>|<span data-ttu-id="0755d-116">El adaptador usa la clase System.Xml.XmlConvert para convertir entre instancias de esquemas XML `dateTime` y `System.DateTime`.</span><span class="sxs-lookup"><span data-stu-id="0755d-116">The adapter uses the System.Xml.XmlConvert class to convert between XML Schema `dateTime` and `System.DateTime` instances.</span></span>|  
|<span data-ttu-id="0755d-117">TIBRVMSG_OPAQUE</span><span class="sxs-lookup"><span data-stu-id="0755d-117">TIBRVMSG_OPAQUE</span></span>|<span data-ttu-id="0755d-118">xsd:base64Binary</span><span class="sxs-lookup"><span data-stu-id="0755d-118">xsd:base64Binary</span></span>||  
|<span data-ttu-id="0755d-119">TIBRVMSG_STRING</span><span class="sxs-lookup"><span data-stu-id="0755d-119">TIBRVMSG_STRING</span></span>|<span data-ttu-id="0755d-120">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="0755d-120">xsd:string</span></span>||  
|<span data-ttu-id="0755d-121">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="0755d-121">TIBRVMSG_BOOL</span></span>|<span data-ttu-id="0755d-122">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="0755d-122">xsd:boolean</span></span>||  
|<span data-ttu-id="0755d-123">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="0755d-123">TIBRVMSG_I8</span></span>|<span data-ttu-id="0755d-124">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="0755d-124">xsd:byte</span></span>||  
|<span data-ttu-id="0755d-125">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="0755d-125">TIBRVMSG_I16</span></span>|<span data-ttu-id="0755d-126">xsd:short</span><span class="sxs-lookup"><span data-stu-id="0755d-126">xsd:short</span></span>||  
|<span data-ttu-id="0755d-127">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="0755d-127">TIBRVMSG_I32</span></span>|<span data-ttu-id="0755d-128">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0755d-128">xsd:int</span></span>||  
|<span data-ttu-id="0755d-129">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="0755d-129">TIBRVMSG_I64</span></span>|<span data-ttu-id="0755d-130">xsd:long</span><span class="sxs-lookup"><span data-stu-id="0755d-130">xsd:long</span></span>||  
|<span data-ttu-id="0755d-131">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="0755d-131">TIBRVMSG_U8</span></span>|<span data-ttu-id="0755d-132">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0755d-132">xsd:unsignedByte</span></span>||  
|<span data-ttu-id="0755d-133">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="0755d-133">TIBRVMSG_U16</span></span>|<span data-ttu-id="0755d-134">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="0755d-134">xsd:unsignedShort</span></span>||  
|<span data-ttu-id="0755d-135">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="0755d-135">TIBRVMSG_U32</span></span>|<span data-ttu-id="0755d-136">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0755d-136">xsd:unsignedInt</span></span>||  
|<span data-ttu-id="0755d-137">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="0755d-137">TIBRVMSG_U64</span></span>|<span data-ttu-id="0755d-138">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="0755d-138">xsd:unsignedLong</span></span>||  
|<span data-ttu-id="0755d-139">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="0755d-139">TIBRVMSG_F32</span></span>|<span data-ttu-id="0755d-140">xsd:float</span><span class="sxs-lookup"><span data-stu-id="0755d-140">xsd:float</span></span>||  
|<span data-ttu-id="0755d-141">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="0755d-141">TIBRVMSG_F64</span></span>|<span data-ttu-id="0755d-142">xsd:double</span><span class="sxs-lookup"><span data-stu-id="0755d-142">xsd:double</span></span>||  
|<span data-ttu-id="0755d-143">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="0755d-143">TIBRVMSG_IPADDR32</span></span>|<span data-ttu-id="0755d-144">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="0755d-144">tibrv:IPaddress</span></span>|<span data-ttu-id="0755d-145">`System.Net.IPAddress.ToString( )` se usa para generar la salida.</span><span class="sxs-lookup"><span data-stu-id="0755d-145">`System.Net.IPAddress.ToString( )` is used to generate the output.</span></span> <span data-ttu-id="0755d-146">El contenido está en el orden de bytes de la red.</span><span class="sxs-lookup"><span data-stu-id="0755d-146">Content is in network byte order.</span></span> <span data-ttu-id="0755d-147">ToString() se encarga de ello.</span><span class="sxs-lookup"><span data-stu-id="0755d-147">ToString() takes care of that.</span></span>|  
|<span data-ttu-id="0755d-148">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="0755d-148">TIBRVMSG_IPPORT16</span></span>|<span data-ttu-id="0755d-149">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="0755d-149">tibrv:IPport</span></span>|<span data-ttu-id="0755d-150">El contenido está en el orden de bytes de la red</span><span class="sxs-lookup"><span data-stu-id="0755d-150">Content is in network byte order</span></span>|  
|<span data-ttu-id="0755d-151">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-151">TIBRVMSG_I8ARRAY</span></span>|<span data-ttu-id="0755d-152">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="0755d-152">tibrv:arrayOfByte</span></span>|<span data-ttu-id="0755d-153">el espacio de nombres del esquema 'tibrv' se proporciona con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="0755d-153">'tibrv' schema namespace is provided with the adapter.</span></span>|  
|<span data-ttu-id="0755d-154">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-154">TIBRVMSG_I16ARRAY</span></span>|<span data-ttu-id="0755d-155">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="0755d-155">tibrv:arrayOfShort</span></span>||  
|<span data-ttu-id="0755d-156">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-156">TIBRVMSG_I32ARRAY</span></span>|<span data-ttu-id="0755d-157">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="0755d-157">tibrv:arrayOfInt</span></span>||  
|<span data-ttu-id="0755d-158">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-158">TIBRVMSG_I64ARRAY</span></span>|<span data-ttu-id="0755d-159">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="0755d-159">tibrv:arrayOfLong</span></span>||  
|<span data-ttu-id="0755d-160">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-160">TIBRVMSG_U8ARRAY</span></span>|<span data-ttu-id="0755d-161">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="0755d-161">tibrv:arrayOfUnsignedByte</span></span>||  
|<span data-ttu-id="0755d-162">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-162">TIBRVMSG_U16ARRAY</span></span>|<span data-ttu-id="0755d-163">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="0755d-163">tibrv:arrayOfUnsignedShort</span></span>||  
|<span data-ttu-id="0755d-164">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-164">TIBRVMSG_U32ARRAY</span></span>|<span data-ttu-id="0755d-165">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="0755d-165">tibrv:arrayOfUnsignedInt</span></span>||  
|<span data-ttu-id="0755d-166">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-166">TIBRVMSG_U64ARRAY</span></span>|<span data-ttu-id="0755d-167">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="0755d-167">tibrv:arrayOfUnsignedLong</span></span>||  
|<span data-ttu-id="0755d-168">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-168">TIBRVMSG_F32ARRAY</span></span>|<span data-ttu-id="0755d-169">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="0755d-169">tibrv:arrayOfFloat</span></span>||  
|<span data-ttu-id="0755d-170">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0755d-170">TIBRVMSG_F64ARRAY</span></span>|<span data-ttu-id="0755d-171">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="0755d-171">tibrv:arrayOfDouble</span></span>||  
  
 <span data-ttu-id="0755d-172">Las matrices de TIBCO Rendezvous difieren de una secuencia de campos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="0755d-172">TIBCO Rendezvous arrays differ from a sequence of fields with the same name.</span></span> <span data-ttu-id="0755d-173">Por ejemplo, en un mensaje de TIBCO Rendezvous, es válido tener una matriz con 70.000 elementos, pero no tener 70.000 campos.</span><span class="sxs-lookup"><span data-stu-id="0755d-173">For example, in a TIBCO Rendezvous message, it is valid to have an array with 70,000 elements, but it is not valid to have 70,000 fields.</span></span>  
  
 <span data-ttu-id="0755d-174">El esquema para los tipos de matriz de la tabla anterior es similar a éste:</span><span class="sxs-lookup"><span data-stu-id="0755d-174">The schema for the array types in the previous table looks like this:</span></span>  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="0755d-175">Un elemento de matriz de un mensaje tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0755d-175">An array element in a message looks like this:</span></span>  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 <span data-ttu-id="0755d-176">El esquema para la dirección IP tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0755d-176">The schema for the IPaddress looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 <span data-ttu-id="0755d-177">El esquema para el puerto IP tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0755d-177">The schema for the IPport looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0755d-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="0755d-178">See Also</span></span>  
 <span data-ttu-id="0755d-179">[Asignación de mensaje de TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="0755d-179">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="0755d-180">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0755d-180">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)