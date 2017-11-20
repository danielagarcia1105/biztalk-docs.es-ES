---
title: "Tipo de datos de asignación para controladores de envío de TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bda336d149d373477b26efeb2e4b05de4aac7554
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a><span data-ttu-id="0ca18-102">Asignación de tipos de datos para controladores de envío de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0ca18-102">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="0ca18-103">La asignación de tipos de esquema XML a tipos TIBCO Rendezvous solo es posible si TIBCO Rendezvous proporciona información de tipos (xsi:type=).</span><span class="sxs-lookup"><span data-stu-id="0ca18-103">The mapping from XML schema types to TIBCO Rendezvous types is only possible if TIBCO Rendezvous provides type information (xsi:type=).</span></span> <span data-ttu-id="0ca18-104">Los tipos no compatibles se asignan a las cadenas si es posible.</span><span class="sxs-lookup"><span data-stu-id="0ca18-104">Any unsupported types are mapped to strings if it is possible.</span></span> <span data-ttu-id="0ca18-105">Si la asignación no es posible, o si la opción está deshabilitada en la configuración del puerto, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="0ca18-105">If mapping is not possible, or if the option is disabled in the port configuration, an error is generated.</span></span>  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a><span data-ttu-id="0ca18-106">Esquema XML para la asignación de tipos de datos de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0ca18-106">XML Schema to TIBCO Rendezvous Data Type Mapping</span></span>  
 <span data-ttu-id="0ca18-107">La siguiente tabla muestra la asignación posible desde tipos de esquema XML a tipos de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0ca18-107">The following table shows the possible mapping from XML schema types to TIBCO Rendezvous types.</span></span>  
  
|<span data-ttu-id="0ca18-108">Tipo XML</span><span class="sxs-lookup"><span data-stu-id="0ca18-108">XML Type</span></span>|<span data-ttu-id="0ca18-109">Tipo TIBCO RV</span><span class="sxs-lookup"><span data-stu-id="0ca18-109">TIBCO RV Type</span></span>|  
|--------------|-------------------|  
||<span data-ttu-id="0ca18-110">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="0ca18-110">TIBRVMSG_MSG</span></span>|  
||<span data-ttu-id="0ca18-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="0ca18-111">TIBRVMSG_XML</span></span>|  
|<span data-ttu-id="0ca18-112">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="0ca18-112">xsd:dateTime</span></span>|<span data-ttu-id="0ca18-113">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="0ca18-113">TIBRVMSG_DATETIME</span></span>|  
|<span data-ttu-id="0ca18-114">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="0ca18-114">xsd:boolean</span></span>|<span data-ttu-id="0ca18-115">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="0ca18-115">TIBRVMSG_BOOL</span></span>|  
|<span data-ttu-id="0ca18-116">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="0ca18-116">xsd:byte</span></span>|<span data-ttu-id="0ca18-117">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="0ca18-117">TIBRVMSG_I8</span></span>|  
|<span data-ttu-id="0ca18-118">xsd:short</span><span class="sxs-lookup"><span data-stu-id="0ca18-118">xsd:short</span></span>|<span data-ttu-id="0ca18-119">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="0ca18-119">TIBRVMSG_I16</span></span>|  
|<span data-ttu-id="0ca18-120">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0ca18-120">xsd:int</span></span>|<span data-ttu-id="0ca18-121">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="0ca18-121">TIBRVMSG_I32</span></span>|  
|<span data-ttu-id="0ca18-122">xsd:long</span><span class="sxs-lookup"><span data-stu-id="0ca18-122">xsd:long</span></span>|<span data-ttu-id="0ca18-123">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="0ca18-123">TIBRVMSG_I64</span></span>|  
|<span data-ttu-id="0ca18-124">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0ca18-124">xsd:unsignedByte</span></span>|<span data-ttu-id="0ca18-125">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="0ca18-125">TIBRVMSG_U8</span></span>|  
|<span data-ttu-id="0ca18-126">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="0ca18-126">xsd:unsignedShort</span></span>|<span data-ttu-id="0ca18-127">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="0ca18-127">TIBRVMSG_U16</span></span>|  
|<span data-ttu-id="0ca18-128">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0ca18-128">xsd:unsignedInt</span></span>|<span data-ttu-id="0ca18-129">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="0ca18-129">TIBRVMSG_U32</span></span>|  
|<span data-ttu-id="0ca18-130">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="0ca18-130">xsd:unsignedLong</span></span>|<span data-ttu-id="0ca18-131">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="0ca18-131">TIBRVMSG_U64</span></span>|  
|<span data-ttu-id="0ca18-132">xsd:float</span><span class="sxs-lookup"><span data-stu-id="0ca18-132">xsd:float</span></span>|<span data-ttu-id="0ca18-133">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="0ca18-133">TIBRVMSG_F32</span></span>|  
|<span data-ttu-id="0ca18-134">xsd:double</span><span class="sxs-lookup"><span data-stu-id="0ca18-134">xsd:double</span></span>|<span data-ttu-id="0ca18-135">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="0ca18-135">TIBRVMSG_F64</span></span>|  
|<span data-ttu-id="0ca18-136">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="0ca18-136">tibrv:IPaddress</span></span>|<span data-ttu-id="0ca18-137">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="0ca18-137">TIBRVMSG_IPADDR32</span></span>|  
|<span data-ttu-id="0ca18-138">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="0ca18-138">tibrv:IPport</span></span>|<span data-ttu-id="0ca18-139">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="0ca18-139">TIBRVMSG_IPPORT16</span></span>|  
|<span data-ttu-id="0ca18-140">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="0ca18-140">tibrv:arrayOfByte</span></span>|<span data-ttu-id="0ca18-141">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-141">TIBRVMSG_I8ARRAY</span></span>|  
|<span data-ttu-id="0ca18-142">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="0ca18-142">tibrv:arrayOfShort</span></span>|<span data-ttu-id="0ca18-143">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-143">TIBRVMSG_I16ARRAY</span></span>|  
|<span data-ttu-id="0ca18-144">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="0ca18-144">tibrv:arrayOfInt</span></span>|<span data-ttu-id="0ca18-145">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-145">TIBRVMSG_I32ARRAY</span></span>|  
|<span data-ttu-id="0ca18-146">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="0ca18-146">tibrv:arrayOfLong</span></span>|<span data-ttu-id="0ca18-147">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-147">TIBRVMSG_I64ARRAY</span></span>|  
|<span data-ttu-id="0ca18-148">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="0ca18-148">tibrv:arrayOfUnsignedByte</span></span>|<span data-ttu-id="0ca18-149">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-149">TIBRVMSG_U8ARRAY</span></span>|  
|<span data-ttu-id="0ca18-150">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="0ca18-150">tibrv:arrayOfUnsignedShort</span></span>|<span data-ttu-id="0ca18-151">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-151">TIBRVMSG_U16ARRAY</span></span>|  
|<span data-ttu-id="0ca18-152">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="0ca18-152">tibrv:arrayOfUnsignedInt</span></span>|<span data-ttu-id="0ca18-153">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-153">TIBRVMSG_U32ARRAY</span></span>|  
|<span data-ttu-id="0ca18-154">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="0ca18-154">tibrv:arrayOfUnsignedLong</span></span>|<span data-ttu-id="0ca18-155">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-155">TIBRVMSG_U64ARRAY</span></span>|  
|<span data-ttu-id="0ca18-156">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="0ca18-156">tibrv:arrayOfFloat</span></span>|<span data-ttu-id="0ca18-157">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-157">TIBRVMSG_F32ARRAY</span></span>|  
|<span data-ttu-id="0ca18-158">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="0ca18-158">tibrv:arrayOfDouble</span></span>|<span data-ttu-id="0ca18-159">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0ca18-159">TIBRVMSG_F64ARRAY</span></span>|  
|<span data-ttu-id="0ca18-160">Todo lo demás, con un mensaje de depuración</span><span class="sxs-lookup"><span data-stu-id="0ca18-160">Anything else - with a debug message</span></span>|<span data-ttu-id="0ca18-161">TIBRVMSG_STRING el registro.</span><span class="sxs-lookup"><span data-stu-id="0ca18-161">TIBRVMSG_STRING the log.</span></span>|  
  
 <span data-ttu-id="0ca18-162">Puesto que el adaptador de BizTalk para TIBCO Rendezvous no tiene acceso a un esquema, cuando se transmita de BizTalk Server a TIBCO Rendezvous, se debe proporcionar el atributo XML `xsi:type` para cualquier campo que no sea una cadena.</span><span class="sxs-lookup"><span data-stu-id="0ca18-162">Because BizTalk Adapter for TIBCO Rendezvous does not have access to a schema, when you transmit from BizTalk Server to TIBCO Rendezvous, you must provide the XML `xsi:type` attribute for any non-string field.</span></span> <span data-ttu-id="0ca18-163">El adaptador usa esa información para generar el tipo de campo de mensaje apropiado en el mensaje de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0ca18-163">The adapter uses that information to generate the appropriate message field type in the TIBCO Rendezvous message.</span></span>  
  
## <a name="message-mapping-example"></a><span data-ttu-id="0ca18-164">Ejemplo de asignación de mensaje</span><span class="sxs-lookup"><span data-stu-id="0ca18-164">Message Mapping Example</span></span>  
 <span data-ttu-id="0ca18-165">En el ejemplo siguiente se muestra la asignación de un mensaje desde BizTalk Server a TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0ca18-165">The following example demonstrates mapping a message from BizTalk Server to TIBCO Rendezvous.</span></span> <span data-ttu-id="0ca18-166">Consulte la tabla de asignación de tipos de datos para obtener información acerca de cómo se asignan los tipos.</span><span class="sxs-lookup"><span data-stu-id="0ca18-166">Refer to the data type mapping table for information about how types are mapped.</span></span>  
  
```  
<ns:QuoteUpdate xmlns:xsi http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd http://www.w3.org/2001/XMLSchema"  
xmlns:tibrv="http://schemas.microsoft.com/TibcoRendezvous/Types"  
xmlns:ns="some namespace for this message [value not important, unless the schema is also used for receive ports]">  
  
<ns:SymbolName id=1 xsi:type="xsd:string">MSFT</ns:SymbolName>  
  
<ns:LastTrade id=2 xsi:type="xsd:double">28.40</ns:LastTrade>   
<ns:DayLow id=3 xsi:type="xsd:double">28.25</ns:DayLow>  
  
```  
  
|||  
|-|-|  
|`<ns:DayHigh`|`id=4 xsi:type="xsd:double">28.40</ns:DayHigh>`|  
|`<ns:MarketCap`|`id=10>262575234981</ns:MarketCap>`|  
|`<ns:Bids`|`id=100 xsi:type="tibrv:message">`|  
  
```  
<ns:TopBids id=1 xsi:type="tibrv:arrayOfDouble">  
<item>28.40</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.38</item>  
  
</ns:TopBids>  
  
<ns:BidsSize id=2 xsi:type="tibrv:arrayOfLong">  
<item>500</item>  
<item>1000</item>  
<item>100</item>  
<item>100</item>  
<item>2000</item>  
  
</ns:BidsSize>  
</ns:Bids>  
</ns:QuoteUpdate>  
  
```  
  
 <span data-ttu-id="0ca18-167">Una vez generado el mensaje anterior como mensaje de TIBCO Rendezvous estructurado, sería una instancia TibcoMsg de nivel superior con seis campos.</span><span class="sxs-lookup"><span data-stu-id="0ca18-167">After the previous message is generated as a structured TIBCO Rendezvous message, it would be a top-level TibcoMsg instance with six fields.</span></span> <span data-ttu-id="0ca18-168">Los últimos campos son un mensaje secundario, compuesto por dos campos de tipos de matriz (los elementos "item" no se asignan a los campos de mensaje de TIBCO Rendezvous, sino a los elementos de un campo de mensaje de tipo `array`).</span><span class="sxs-lookup"><span data-stu-id="0ca18-168">The last fields are a sub-message, composed of two fields of array types (the 'item' elements are not mapped to TIBCO Rendezvous Message fields, but to elements in one Message Field of type `array`).</span></span> <span data-ttu-id="0ca18-169">El campo MarketCap, al no tener ninguna especificación de tipo, se enviaría como un campo de mensaje de cadena.</span><span class="sxs-lookup"><span data-stu-id="0ca18-169">The MarketCap field, having no type specification, would be sent as a string message field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca18-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ca18-170">See Also</span></span>  
 [<span data-ttu-id="0ca18-171">Creación de controladores de envío de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0ca18-171">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)