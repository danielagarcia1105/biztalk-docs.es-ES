---
title: "Asignación de tipo de datos para recibir desde TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb17ceac0c323bba7a6f25cff0d07473b6d7fa3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a><span data-ttu-id="4082e-102">Asignación de tipos de datos para controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="4082e-102">Data Type Mapping for Receive Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="4082e-103">El Adaptador de Microsoft BizTalk para TIBCO Rendezvous asigna los tipos TIBCO RV a los tipos de esquemas XML según se especifica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4082e-103">Microsoft BizTalk Adapter for TIBCO Rendezvous maps TIBCO RV types to XML Schema types as specified in the following table.</span></span>  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a><span data-ttu-id="4082e-104">TIBCO RV para asignación de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="4082e-104">TIBCO RV to XML Data Type Mapping</span></span>  
  
|<span data-ttu-id="4082e-105">Tipo TIBCO RV</span><span class="sxs-lookup"><span data-stu-id="4082e-105">TIBCO RV Type</span></span>|<span data-ttu-id="4082e-106">Tipo de esquema XML</span><span class="sxs-lookup"><span data-stu-id="4082e-106">XML Schema Type</span></span>|<span data-ttu-id="4082e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4082e-107">Comments</span></span>|  
|-------------------|---------------------|--------------|  
|<span data-ttu-id="4082e-108">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="4082e-108">TIBRVMSG_MSG</span></span>|<span data-ttu-id="4082e-109">tibrv:message</span><span class="sxs-lookup"><span data-stu-id="4082e-109">tibrv:message</span></span>|<span data-ttu-id="4082e-110">Completo documento XML construido a partir de todo el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4082e-110">Complete XML document constructed from entire message.</span></span>|  
|<span data-ttu-id="4082e-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="4082e-111">TIBRVMSG_XML</span></span>|<span data-ttu-id="4082e-112">tibrv:rawxml</span><span class="sxs-lookup"><span data-stu-id="4082e-112">tibrv:rawxml</span></span>|<span data-ttu-id="4082e-113">Documento XML construido a partir de la matriz de bytes (no interpreta por el adaptador).</span><span class="sxs-lookup"><span data-stu-id="4082e-113">XML Document constructed from the array of bytes (not interpreted by the adapter).</span></span>|  
|<span data-ttu-id="4082e-114">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="4082e-114">TIBRVMSG_DATETIME</span></span>|<span data-ttu-id="4082e-115">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="4082e-115">xsd:dateTime</span></span>|<span data-ttu-id="4082e-116">El adaptador usa la clase System.Xml.XmlConvert para convertir entre instancias de esquemas XML `dateTime` y `System.DateTime`.</span><span class="sxs-lookup"><span data-stu-id="4082e-116">The adapter uses the System.Xml.XmlConvert class to convert between XML Schema `dateTime` and `System.DateTime` instances.</span></span>|  
|<span data-ttu-id="4082e-117">TIBRVMSG_OPAQUE</span><span class="sxs-lookup"><span data-stu-id="4082e-117">TIBRVMSG_OPAQUE</span></span>|<span data-ttu-id="4082e-118">xsd:base64Binary</span><span class="sxs-lookup"><span data-stu-id="4082e-118">xsd:base64Binary</span></span>||  
|<span data-ttu-id="4082e-119">TIBRVMSG_STRING</span><span class="sxs-lookup"><span data-stu-id="4082e-119">TIBRVMSG_STRING</span></span>|<span data-ttu-id="4082e-120">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="4082e-120">xsd:string</span></span>||  
|<span data-ttu-id="4082e-121">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="4082e-121">TIBRVMSG_BOOL</span></span>|<span data-ttu-id="4082e-122">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="4082e-122">xsd:boolean</span></span>||  
|<span data-ttu-id="4082e-123">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="4082e-123">TIBRVMSG_I8</span></span>|<span data-ttu-id="4082e-124">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="4082e-124">xsd:byte</span></span>||  
|<span data-ttu-id="4082e-125">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="4082e-125">TIBRVMSG_I16</span></span>|<span data-ttu-id="4082e-126">xsd:short</span><span class="sxs-lookup"><span data-stu-id="4082e-126">xsd:short</span></span>||  
|<span data-ttu-id="4082e-127">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="4082e-127">TIBRVMSG_I32</span></span>|<span data-ttu-id="4082e-128">xsd:int</span><span class="sxs-lookup"><span data-stu-id="4082e-128">xsd:int</span></span>||  
|<span data-ttu-id="4082e-129">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="4082e-129">TIBRVMSG_I64</span></span>|<span data-ttu-id="4082e-130">xsd:long</span><span class="sxs-lookup"><span data-stu-id="4082e-130">xsd:long</span></span>||  
|<span data-ttu-id="4082e-131">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="4082e-131">TIBRVMSG_U8</span></span>|<span data-ttu-id="4082e-132">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="4082e-132">xsd:unsignedByte</span></span>||  
|<span data-ttu-id="4082e-133">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="4082e-133">TIBRVMSG_U16</span></span>|<span data-ttu-id="4082e-134">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="4082e-134">xsd:unsignedShort</span></span>||  
|<span data-ttu-id="4082e-135">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="4082e-135">TIBRVMSG_U32</span></span>|<span data-ttu-id="4082e-136">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4082e-136">xsd:unsignedInt</span></span>||  
|<span data-ttu-id="4082e-137">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="4082e-137">TIBRVMSG_U64</span></span>|<span data-ttu-id="4082e-138">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="4082e-138">xsd:unsignedLong</span></span>||  
|<span data-ttu-id="4082e-139">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="4082e-139">TIBRVMSG_F32</span></span>|<span data-ttu-id="4082e-140">xsd:float</span><span class="sxs-lookup"><span data-stu-id="4082e-140">xsd:float</span></span>||  
|<span data-ttu-id="4082e-141">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="4082e-141">TIBRVMSG_F64</span></span>|<span data-ttu-id="4082e-142">xsd:double</span><span class="sxs-lookup"><span data-stu-id="4082e-142">xsd:double</span></span>||  
|<span data-ttu-id="4082e-143">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="4082e-143">TIBRVMSG_IPADDR32</span></span>|<span data-ttu-id="4082e-144">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="4082e-144">tibrv:IPaddress</span></span>|<span data-ttu-id="4082e-145">`System.Net.IPAddress.ToString( )` se usa para generar la salida.</span><span class="sxs-lookup"><span data-stu-id="4082e-145">`System.Net.IPAddress.ToString( )` is used to generate the output.</span></span> <span data-ttu-id="4082e-146">El contenido está en el orden de bytes de la red.</span><span class="sxs-lookup"><span data-stu-id="4082e-146">Content is in network byte order.</span></span> <span data-ttu-id="4082e-147">ToString() se encarga de ello.</span><span class="sxs-lookup"><span data-stu-id="4082e-147">ToString() takes care of that.</span></span>|  
|<span data-ttu-id="4082e-148">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="4082e-148">TIBRVMSG_IPPORT16</span></span>|<span data-ttu-id="4082e-149">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="4082e-149">tibrv:IPport</span></span>|<span data-ttu-id="4082e-150">El contenido está en el orden de bytes de la red</span><span class="sxs-lookup"><span data-stu-id="4082e-150">Content is in network byte order</span></span>|  
|<span data-ttu-id="4082e-151">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-151">TIBRVMSG_I8ARRAY</span></span>|<span data-ttu-id="4082e-152">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="4082e-152">tibrv:arrayOfByte</span></span>|<span data-ttu-id="4082e-153">el espacio de nombres del esquema 'tibrv' se proporciona con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="4082e-153">'tibrv' schema namespace is provided with the adapter.</span></span>|  
|<span data-ttu-id="4082e-154">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-154">TIBRVMSG_I16ARRAY</span></span>|<span data-ttu-id="4082e-155">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="4082e-155">tibrv:arrayOfShort</span></span>||  
|<span data-ttu-id="4082e-156">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-156">TIBRVMSG_I32ARRAY</span></span>|<span data-ttu-id="4082e-157">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="4082e-157">tibrv:arrayOfInt</span></span>||  
|<span data-ttu-id="4082e-158">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-158">TIBRVMSG_I64ARRAY</span></span>|<span data-ttu-id="4082e-159">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="4082e-159">tibrv:arrayOfLong</span></span>||  
|<span data-ttu-id="4082e-160">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-160">TIBRVMSG_U8ARRAY</span></span>|<span data-ttu-id="4082e-161">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="4082e-161">tibrv:arrayOfUnsignedByte</span></span>||  
|<span data-ttu-id="4082e-162">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-162">TIBRVMSG_U16ARRAY</span></span>|<span data-ttu-id="4082e-163">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="4082e-163">tibrv:arrayOfUnsignedShort</span></span>||  
|<span data-ttu-id="4082e-164">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-164">TIBRVMSG_U32ARRAY</span></span>|<span data-ttu-id="4082e-165">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="4082e-165">tibrv:arrayOfUnsignedInt</span></span>||  
|<span data-ttu-id="4082e-166">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-166">TIBRVMSG_U64ARRAY</span></span>|<span data-ttu-id="4082e-167">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="4082e-167">tibrv:arrayOfUnsignedLong</span></span>||  
|<span data-ttu-id="4082e-168">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-168">TIBRVMSG_F32ARRAY</span></span>|<span data-ttu-id="4082e-169">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="4082e-169">tibrv:arrayOfFloat</span></span>||  
|<span data-ttu-id="4082e-170">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="4082e-170">TIBRVMSG_F64ARRAY</span></span>|<span data-ttu-id="4082e-171">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="4082e-171">tibrv:arrayOfDouble</span></span>||  
  
 <span data-ttu-id="4082e-172">Las matrices de TIBCO Rendezvous difieren de una secuencia de campos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="4082e-172">TIBCO Rendezvous arrays differ from a sequence of fields with the same name.</span></span> <span data-ttu-id="4082e-173">Por ejemplo, en un mensaje de TIBCO Rendezvous, es válido tener una matriz con 70.000 elementos, pero no tener 70.000 campos.</span><span class="sxs-lookup"><span data-stu-id="4082e-173">For example, in a TIBCO Rendezvous message, it is valid to have an array with 70,000 elements, but it is not valid to have 70,000 fields.</span></span>  
  
 <span data-ttu-id="4082e-174">El esquema para los tipos de matriz de la tabla anterior es similar a éste:</span><span class="sxs-lookup"><span data-stu-id="4082e-174">The schema for the array types in the previous table looks like this:</span></span>  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="4082e-175">Un elemento de matriz de un mensaje tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4082e-175">An array element in a message looks like this:</span></span>  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 <span data-ttu-id="4082e-176">El esquema para la dirección IP tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4082e-176">The schema for the IPaddress looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 <span data-ttu-id="4082e-177">El esquema para el puerto IP tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4082e-177">The schema for the IPport looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4082e-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="4082e-178">See Also</span></span>  
 <span data-ttu-id="4082e-179">[Asignación de mensaje de TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="4082e-179">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="4082e-180">Creación de controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="4082e-180">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)