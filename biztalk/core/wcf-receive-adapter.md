---
title: Adaptador de recepción WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- receive adapters, Web service headers
- SOAP messages, extracting information
- SOAP messages, WCF adapters
- WCF adapters, receive adapters
- messages, SOAP
- receive adapters, WCF adapters
- Web services, headers
- headers [messages]
- SOAP messages, receive adapters
ms.assetid: 6b3d5df1-5d9d-4240-a98f-ea29c3272e38
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c30d858c08da8a0f8d71d56397e43d591b3d773
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965837"
---
# <a name="wcf-receive-adapter"></a><span data-ttu-id="d3633-102">Adaptador de recepción WCF</span><span class="sxs-lookup"><span data-stu-id="d3633-102">WCF Receive Adapter</span></span>
<span data-ttu-id="d3633-103">El adaptador de recepción WCF permite recibir solicitudes del Servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d3633-103">The WCF receive adapter enables you to receive WCF service requests.</span></span>  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a><span data-ttu-id="d3633-104">Extraer el cuerpo del mensaje de BizTalk del mensaje SOAP</span><span class="sxs-lookup"><span data-stu-id="d3633-104">Extracting the BizTalk Message Body from the SOAP Message</span></span>  
 <span data-ttu-id="d3633-105">El cuerpo del mensaje de BizTalk entrante se puede extraer del mensaje SOAP a través de una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d3633-105">The inbound BizTalk message body can be extracted from the SOAP message by using one of the following options:</span></span>  
  
- <span data-ttu-id="d3633-106">Extraer el contenido del elemento Body de SOAP</span><span class="sxs-lookup"><span data-stu-id="d3633-106">Extract the content of the SOAP Body element</span></span>  
  
- <span data-ttu-id="d3633-107">Extraer el sobre SOAP completo</span><span class="sxs-lookup"><span data-stu-id="d3633-107">Extract the entire SOAP envelope</span></span>  
  
- <span data-ttu-id="d3633-108">Extraer el contenido del elemento del sobre SOAP mediante una expresión XPath</span><span class="sxs-lookup"><span data-stu-id="d3633-108">Extract the content of the element inside the SOAP envelope by using an XPath expression</span></span>  
  
  <span data-ttu-id="d3633-109">Puede configurar estas opciones en el cuadro de diálogo de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="d3633-109">You can configure these options in the transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a><span data-ttu-id="d3633-110">Extraiga el contenido del elemento Body SOAP</span><span class="sxs-lookup"><span data-stu-id="d3633-110">Extract the Content of the SOAP Body Element</span></span>  
 <span data-ttu-id="d3633-111">Cuando se selecciona esta opción, el contenido interno del elemento Body de SOAP se lee en el mensaje SOAP y se coloca en la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d3633-111">When this option is selected, the inner content of the SOAP Body element is read from the SOAP message and placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-entire-soap-envelope"></a><span data-ttu-id="d3633-112">Extraer la envoltura SOAP completo</span><span class="sxs-lookup"><span data-stu-id="d3633-112">Extract the Entire SOAP Envelope</span></span>  
 <span data-ttu-id="d3633-113">Cuando se selecciona esta opción, el sobre SOAP completo incluida la etiqueta se coloca en la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d3633-113">When this option is selected, the entire SOAP envelope including the tag is placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a><span data-ttu-id="d3633-114">Extraer el contenido del elemento mediante una expresión XPath</span><span class="sxs-lookup"><span data-stu-id="d3633-114">Extract the Content of the Element by Using an XPath Expression</span></span>  
 <span data-ttu-id="d3633-115">Cuando se selecciona esta opción, el contenido interno del elemento que se encuentra dentro del elemento Body de SOAP localizado por la expresión XPath se coloca en la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d3633-115">When this option is selected, the inner content of the element inside the SOAP Body element that is located by the XPath expression is placed into the body part of the BizTalk message.</span></span> <span data-ttu-id="d3633-116">Se omiten los datos restantes del elemento Body.</span><span class="sxs-lookup"><span data-stu-id="d3633-116">The rest of the data in the Body element is ignored.</span></span> <span data-ttu-id="d3633-117">También deberá especificar la codificación de nodo, para la codificación de Base64, Hex o cadena XML, de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d3633-117">You also need to specify the node encoding—for example, XML, Base64, Hex, or String encoding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3633-118">Si se selecciona la codificación XML, el contenido externo del elemento se localiza mediante la expresión XPath y se coloca en la parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="d3633-118">When the XML encoding is selected, the outer content of the element is located by the XPath expression and placed into the body part.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="d3633-119">Controlar encabezados de servicios Web</span><span class="sxs-lookup"><span data-stu-id="d3633-119">Handling Web Services Headers</span></span>  
 <span data-ttu-id="d3633-120">El adaptador de recepción promueve un subconjunto de encabezados de servicios Web estándar en el contexto del mensaje de BizTalk para habilitar el acceso sencillo y el enrutamiento basado en los valores de dichos encabezados.</span><span class="sxs-lookup"><span data-stu-id="d3633-120">The receive adapter promotes a subset of the standard Web services headers onto the BizTalk message context to enable easy access and routing based on values of those headers.</span></span> <span data-ttu-id="d3633-121">En la siguiente tabla se enumeran las propiedades que se guardarán en el contexto del mensaje mediante el adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="d3633-121">The following table lists the properties that will be saved onto the message context by the receive adapter.</span></span> <span data-ttu-id="d3633-122">Las propiedades se definen en los espacios de nombres siguientes: http://www.w3.org/2005/addressing y http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties.</span><span class="sxs-lookup"><span data-stu-id="d3633-122">The properties are defined under the following namespaces: http://www.w3.org/2005/addressing and http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties.</span></span>  
  
|<span data-ttu-id="d3633-123">Encabezado</span><span class="sxs-lookup"><span data-stu-id="d3633-123">Header</span></span>|<span data-ttu-id="d3633-124">Nombre de la propiedad de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d3633-124">BizTalk property name</span></span>|<span data-ttu-id="d3633-125">¿Está promocionada?</span><span class="sxs-lookup"><span data-stu-id="d3633-125">Is promoted?</span></span>|  
|------------|---------------------------|------------------|  
|<span data-ttu-id="d3633-126">Acción</span><span class="sxs-lookup"><span data-stu-id="d3633-126">Action</span></span>|<span data-ttu-id="d3633-127">Acción</span><span class="sxs-lookup"><span data-stu-id="d3633-127">Action</span></span>|<span data-ttu-id="d3633-128">Sí</span><span class="sxs-lookup"><span data-stu-id="d3633-128">Yes</span></span>|  
|<span data-ttu-id="d3633-129">MessageID</span><span class="sxs-lookup"><span data-stu-id="d3633-129">MessageID</span></span>|<span data-ttu-id="d3633-130">MessageID</span><span class="sxs-lookup"><span data-stu-id="d3633-130">MessageID</span></span>|<span data-ttu-id="d3633-131">no</span><span class="sxs-lookup"><span data-stu-id="d3633-131">No</span></span>|  
|<span data-ttu-id="d3633-132">A</span><span class="sxs-lookup"><span data-stu-id="d3633-132">To</span></span>|<span data-ttu-id="d3633-133">A</span><span class="sxs-lookup"><span data-stu-id="d3633-133">To</span></span>|<span data-ttu-id="d3633-134">Sí</span><span class="sxs-lookup"><span data-stu-id="d3633-134">Yes</span></span>|  
|<span data-ttu-id="d3633-135">ReplyTo/Address</span><span class="sxs-lookup"><span data-stu-id="d3633-135">ReplyTo/Address</span></span>|<span data-ttu-id="d3633-136">ReplyTo</span><span class="sxs-lookup"><span data-stu-id="d3633-136">ReplyTo</span></span>|<span data-ttu-id="d3633-137">Sí</span><span class="sxs-lookup"><span data-stu-id="d3633-137">Yes</span></span>|  
|<span data-ttu-id="d3633-138">From/Address</span><span class="sxs-lookup"><span data-stu-id="d3633-138">From/Address</span></span>|<span data-ttu-id="d3633-139">De</span><span class="sxs-lookup"><span data-stu-id="d3633-139">From</span></span>|<span data-ttu-id="d3633-140">Sí</span><span class="sxs-lookup"><span data-stu-id="d3633-140">Yes</span></span>|  
|<span data-ttu-id="d3633-141">Sequence/Identifier</span><span class="sxs-lookup"><span data-stu-id="d3633-141">Sequence/Identifier</span></span>|<span data-ttu-id="d3633-142">SequenceId</span><span class="sxs-lookup"><span data-stu-id="d3633-142">SequenceId</span></span>|<span data-ttu-id="d3633-143">Sí</span><span class="sxs-lookup"><span data-stu-id="d3633-143">Yes</span></span>|  
|<span data-ttu-id="d3633-144">Sequence/MessageNumber</span><span class="sxs-lookup"><span data-stu-id="d3633-144">Sequence/MessageNumber</span></span>|<span data-ttu-id="d3633-145">SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="d3633-145">SequenceNumber</span></span>|<span data-ttu-id="d3633-146">Sí</span><span class="sxs-lookup"><span data-stu-id="d3633-146">Yes</span></span>|  
|<span data-ttu-id="d3633-147">Sequence/LastMessage</span><span class="sxs-lookup"><span data-stu-id="d3633-147">Sequence/LastMessage</span></span>|<span data-ttu-id="d3633-148">SequenceLastMessage</span><span class="sxs-lookup"><span data-stu-id="d3633-148">SequenceLastMessage</span></span>|<span data-ttu-id="d3633-149">Sí</span><span class="sxs-lookup"><span data-stu-id="d3633-149">Yes</span></span>|  
|<span data-ttu-id="d3633-150">\<Encabezado de SOAP:\></span><span class="sxs-lookup"><span data-stu-id="d3633-150">\<soap:Header\></span></span>|<span data-ttu-id="d3633-151">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="d3633-151">InboundHeaders</span></span>|<span data-ttu-id="d3633-152">no</span><span class="sxs-lookup"><span data-stu-id="d3633-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3633-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3633-153">See Also</span></span>  
 <span data-ttu-id="d3633-154">[Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="d3633-154">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="d3633-155">[Adaptador de envío WCF](../core/wcf-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d3633-155">[WCF Send Adapter](../core/wcf-send-adapter.md) </span></span>  
 [<span data-ttu-id="d3633-156">¿Qué son los adaptadores de WCF?</span><span class="sxs-lookup"><span data-stu-id="d3633-156">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)