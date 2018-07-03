---
title: Usar confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, publishing
- messages, acknowledgements
- BTS.AckSendPortID property
- BTS.AckSendPortName property
- BTS.AckType property
- BTS.AckFailureCode property
- BTS.AckID property
- acknowledgements, positive
- SOAP fault
- BTS.AckReceivePortID property
- BTS.AckReceivePortName property
- BTS.AckInboundTransportLocation property
- BTS.AckOutboundTransportLocation property
- messages, successful transmission
- BTS.AckDescription property
- orchestrations, messages
- acknowledgements, negative
- BTS.CorrelationToken property
- BTS.AckFailureCategory property
- positive acknowledgements (ACK)
- BTS.AckOwnerID property
ms.assetid: 2e5986d4-9633-4b7b-8ff3-fa3da93c5400
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe568185bde471bea9396786e58c31ced960d23
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968189"
---
# <a name="using-acknowledgments"></a><span data-ttu-id="91f94-102">Usar confirmaciones</span><span class="sxs-lookup"><span data-stu-id="91f94-102">Using Acknowledgments</span></span>
<span data-ttu-id="91f94-103">El motor de mensajería de BizTalk genera confirmaciones positivas (ACK) y confirmaciones negativas (NACK) en respuesta a situaciones que ocurren durante el procesamiento de un mensaje a través de un puerto.</span><span class="sxs-lookup"><span data-stu-id="91f94-103">The BizTalk Messaging Engine generates positive acknowledgments (ACK) and negative acknowledgments (NACK) in response to conditions encountered during the processing of a message through a port.</span></span> <span data-ttu-id="91f94-104">BizTalk Server publica una confirmación positiva para indicar que un mensaje se ha transmitido correctamente y una confirmación negativa para señalar que ha habido un error de transmisión y que se ha suspendido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="91f94-104">BizTalk Server publishes a positive acknowledgment to indicate successful transmission of a message and a negative acknowledgment to indicate transmission failure and suspension of a message.</span></span>  
  
## <a name="why-use-acknowledgments"></a><span data-ttu-id="91f94-105">¿Por qué se utilizan las confirmaciones?</span><span class="sxs-lookup"><span data-stu-id="91f94-105">Why Use Acknowledgments?</span></span>  
 <span data-ttu-id="91f94-106">Las confirmaciones positivas y negativas proporcionan información eficaz que permite determinar si un mensaje ha llegado al destino o si se ha producido algún problema en el proceso.</span><span class="sxs-lookup"><span data-stu-id="91f94-106">Positive and negative acknowledgments provide strong feedback that you can use to determine if a message arrived at its destination or encountered one or more problems along the way.</span></span> <span data-ttu-id="91f94-107">Por ejemplo, las confirmaciones son útiles si:</span><span class="sxs-lookup"><span data-stu-id="91f94-107">For example, acknowledgments are useful when:</span></span>  
  
- <span data-ttu-id="91f94-108">Desea supervisar un puerto de recepción para un nuevo socio comercial con fines de validación de esquemas y otros errores.</span><span class="sxs-lookup"><span data-stu-id="91f94-108">You want to monitor a receive port for a new trading partner for schema validation and other errors.</span></span>  
  
- <span data-ttu-id="91f94-109">Desea marcar el estado de una solicitud de préstamo enviada para aprobación como "en curso" si ésta se envía correctamente a un socio comercial para aprobación o como "con errores" si hay errores en la transmisión (por ejemplo, si el servidor del socio comercial está inactivo).</span><span class="sxs-lookup"><span data-stu-id="91f94-109">You want to mark the status of a loan request sent out for approval as "in process" if it is successfully sent to a partner for approval or "failed" if transmission fails (for example, if the partner's server is down).</span></span>  
  
- <span data-ttu-id="91f94-110">Procesa intercambios que contienen varios pedidos y desea realizar un seguimiento del número de pedidos transmitidos y no trasmitidos.</span><span class="sxs-lookup"><span data-stu-id="91f94-110">You process interchanges containing multiple purchase orders and want to track the number of orders that are transmitted or fail transmission.</span></span>  
  
  <span data-ttu-id="91f94-111">Puede realizar las acciones descritas en los escenarios anteriores si utiliza confirmaciones y enrutamiento basado en contenido que use filtros.</span><span class="sxs-lookup"><span data-stu-id="91f94-111">You can accomplish each of these scenarios by using acknowledgments and content-based routing that uses filters.</span></span>  
  
## <a name="routing-acknowledgments"></a><span data-ttu-id="91f94-112">Enrutar confirmaciones</span><span class="sxs-lookup"><span data-stu-id="91f94-112">Routing Acknowledgments</span></span>  
 <span data-ttu-id="91f94-113">Cuando se publica una confirmación ACK o NACK, todas las propiedades de contexto del mensaje que causó la generación de una confirmación ACK o NACK se degradan.</span><span class="sxs-lookup"><span data-stu-id="91f94-113">When an ACK or NACK is published, all of the message context properties from the message that caused the ACK/NACK are demoted.</span></span> <span data-ttu-id="91f94-114">Cualquier propiedad promocionada no pasa al flujo de confirmación.</span><span class="sxs-lookup"><span data-stu-id="91f94-114">Any properties that were promoted do not flow to the acknowledgment.</span></span> <span data-ttu-id="91f94-115">Para enrutar una confirmación, cree un filtro con las siguientes propiedades desde el **BTS** espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="91f94-115">To route an acknowledgment, build a filter using the following properties from the **BTS** namespace:</span></span>  
  
|<span data-ttu-id="91f94-116">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="91f94-116">Property name</span></span>|<span data-ttu-id="91f94-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="91f94-117">Data type</span></span>|<span data-ttu-id="91f94-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="91f94-118">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="91f94-119">BTS.AckFailureCategory</span><span class="sxs-lookup"><span data-stu-id="91f94-119">BTS.AckFailureCategory</span></span>|<span data-ttu-id="91f94-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="91f94-120">xs:int</span></span>|<span data-ttu-id="91f94-121">Identifica el **ErrorCategory**, que indica la ubicación y el motivo de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="91f94-121">Identifies the **ErrorCategory**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="91f94-122">BTS.AckFailureCode</span><span class="sxs-lookup"><span data-stu-id="91f94-122">BTS.AckFailureCode</span></span>|<span data-ttu-id="91f94-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-123">xs:string</span></span>|<span data-ttu-id="91f94-124">Identifica el **ErrorCode**, que indica la ubicación y el motivo de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="91f94-124">Identifies the **ErrorCode**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="91f94-125">BTS.AckType</span><span class="sxs-lookup"><span data-stu-id="91f94-125">BTS.AckType</span></span>|<span data-ttu-id="91f94-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-126">xs:string</span></span>|<span data-ttu-id="91f94-127">El valor es ACK para una confirmación positiva y NACK en el caso de una confirmación negativa.</span><span class="sxs-lookup"><span data-stu-id="91f94-127">Value is ACK for a positive acknowledgment and NACK for a negative acknowledgment.</span></span>|  
|<span data-ttu-id="91f94-128">BTS.AckID</span><span class="sxs-lookup"><span data-stu-id="91f94-128">BTS.AckID</span></span>|<span data-ttu-id="91f94-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-129">xs:string</span></span>|<span data-ttu-id="91f94-130">Identifica el **MessageID** del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-130">Identifies the **MessageID** of the original message.</span></span>|  
|<span data-ttu-id="91f94-131">BTS.AckOwnerID</span><span class="sxs-lookup"><span data-stu-id="91f94-131">BTS.AckOwnerID</span></span>|<span data-ttu-id="91f94-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-132">xs:string</span></span>|<span data-ttu-id="91f94-133">Identifica el Id. de instancia del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-133">Identifies the instance ID from the original message.</span></span>|  
|<span data-ttu-id="91f94-134">BTS.CorrelationToken</span><span class="sxs-lookup"><span data-stu-id="91f94-134">BTS.CorrelationToken</span></span>|<span data-ttu-id="91f94-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-135">xs:string</span></span>|<span data-ttu-id="91f94-136">Identifica el token de correlación del mensaje original, si hay alguno presente.</span><span class="sxs-lookup"><span data-stu-id="91f94-136">Identifies the correlation token from the original message if one is present.</span></span>|  
|<span data-ttu-id="91f94-137">BTS.AckDescription</span><span class="sxs-lookup"><span data-stu-id="91f94-137">BTS.AckDescription</span></span>|<span data-ttu-id="91f94-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-138">xs:string</span></span>|<span data-ttu-id="91f94-139">Identifica el **ErrorDescription**, que indica la ubicación y el motivo de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="91f94-139">Identifies the **ErrorDescription**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="91f94-140">BTS.AckSendPortID</span><span class="sxs-lookup"><span data-stu-id="91f94-140">BTS.AckSendPortID</span></span>|<span data-ttu-id="91f94-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-141">xs:string</span></span>|<span data-ttu-id="91f94-142">Identifica el **SendPortID** del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-142">Identifies the **SendPortID** from the original message.</span></span>|  
|<span data-ttu-id="91f94-143">BTS.AckSendPortName</span><span class="sxs-lookup"><span data-stu-id="91f94-143">BTS.AckSendPortName</span></span>|<span data-ttu-id="91f94-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-144">xs:string</span></span>|<span data-ttu-id="91f94-145">Identifica el **SendPortName** del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-145">Identifies the **SendPortName** from the original message.</span></span>|  
|<span data-ttu-id="91f94-146">BTS.AckOutboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="91f94-146">BTS.AckOutboundTransportLocation</span></span>|<span data-ttu-id="91f94-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-147">xs:string</span></span>|<span data-ttu-id="91f94-148">Identifica el **OutboundTransportLocation** del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-148">Identifies the **OutboundTransportLocation** from the original message.</span></span>|  
|<span data-ttu-id="91f94-149">BTS.AckReceivePortID</span><span class="sxs-lookup"><span data-stu-id="91f94-149">BTS.AckReceivePortID</span></span>|<span data-ttu-id="91f94-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-150">xs:string</span></span>|<span data-ttu-id="91f94-151">Identifica el **ReceivePortID** del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-151">Identifies the **ReceivePortID** from the original message.</span></span>|  
|<span data-ttu-id="91f94-152">BTS.AckReceivePortName</span><span class="sxs-lookup"><span data-stu-id="91f94-152">BTS.AckReceivePortName</span></span>|<span data-ttu-id="91f94-153">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-153">xs:string</span></span>|<span data-ttu-id="91f94-154">Identifica el **ReceivePortName** del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-154">Identifies the **ReceivePortName** from the original message.</span></span>|  
|<span data-ttu-id="91f94-155">BTS.AckInboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="91f94-155">BTS.AckInboundTransportLocation</span></span>|<span data-ttu-id="91f94-156">xs:string</span><span class="sxs-lookup"><span data-stu-id="91f94-156">xs:string</span></span>|<span data-ttu-id="91f94-157">Identifica el **InboundTransportLocation** del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="91f94-157">Identifies the **InboundTransportLocation** from the original message.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="91f94-158">Las propiedades que contienen información de errores no se incluyen en las confirmaciones ACK, ya que estas confirmaciones indican que la entrega se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="91f94-158">The properties that contain error information are not present in ACKs because they signal a positive delivery.</span></span>  
  
## <a name="negative-acknowledgment-message-body"></a><span data-ttu-id="91f94-159">Cuerpo del mensaje de una confirmación negativa</span><span class="sxs-lookup"><span data-stu-id="91f94-159">Negative Acknowledgment Message Body</span></span>  
 <span data-ttu-id="91f94-160">Gran parte de la información importante acerca de una confirmación positiva o negativa se incluye en las propiedades de contexto.</span><span class="sxs-lookup"><span data-stu-id="91f94-160">Much of the important information about a positive or negative acknowledgment is contained in the context properties.</span></span> <span data-ttu-id="91f94-161">Además de las propiedades de contexto, las confirmaciones NACK contienen una sección denominada cuerpo del mensaje que incluye un error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="91f94-161">In addition to the context properties, NACKs also contain a message body part containing a SOAP fault.</span></span> <span data-ttu-id="91f94-162">El formato del error de SOAP es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="91f94-162">The format of the SOAP fault is as follows:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<SOAP:Envelope xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" SOAP:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
  <SOAP:Body>  
    <SOAP:Fault>  
      <faultcode>Microsoft BizTalk Server Negative Acknowledgment </faultcode>  
      <faultstring>An error occurred while processing the message, refer to the details section for more information </faultstring>  
      <faultactor>C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml</faultactor>  
      <detail>  
        <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
          <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
          <ErrorCode>0xc0c01658</ErrorCode>  
          <ErrorCategory>0</ErrorCategory>  
          <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".  </ErrorDescription>  
        </ns0:NACK>  
      </detail>  
    </SOAP:Fault>  
  </SOAP:Body>  
</SOAP:Envelope>  
```  
  
 <span data-ttu-id="91f94-163">El mensaje de excepción generado por el adaptador se encuentra en la sección de detalles de SOAP del elemento ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="91f94-163">The exception message raised by the adapter is in the SOAP Detail section in the ErrorDescription element.</span></span>  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a><span data-ttu-id="91f94-164">Tener acceso al cuerpo del mensaje desde una orquestación</span><span class="sxs-lookup"><span data-stu-id="91f94-164">Accessing the Message Body from an Orchestration</span></span>  
 <span data-ttu-id="91f94-165">Si tiene un puerto de orquestación que requiere notificación de entrega, el elemento DeliveryFailureException generado como resultado de un error de transmisión se deserializa desde el error de SOAP incluido en el cuerpo del mensaje NACK.</span><span class="sxs-lookup"><span data-stu-id="91f94-165">If you have an orchestration port that requires delivery notification, the DeliveryFailureException that is thrown on a transmission failure is deserialized from the SOAP fault that is contained in the NACK message body.</span></span> <span data-ttu-id="91f94-166">Para tener acceso a la cadena del mensaje de excepción desde la orquestación, convierta el elemento DeliveryFailureException en un elemento SoapException y, a continuación, obtenga acceso a InnerXml como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="91f94-166">To access the exception message string from within your orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml as shown in the following code:</span></span>  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 <span data-ttu-id="91f94-167">El ejemplo de código anterior devuelve un fragmento XML similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="91f94-167">The preceding code sample returns an XML fragment similar to the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a><span data-ttu-id="91f94-168">¿Cuándo se publica una confirmación?</span><span class="sxs-lookup"><span data-stu-id="91f94-168">When Is an Acknowledgment Published?</span></span>  
 <span data-ttu-id="91f94-169">Las confirmaciones positivas (ACK) y negativas (NACK) se publican en la base de datos del cuadro de mensajes en el momento en que se produce el error si al menos una suscripción coincide.</span><span class="sxs-lookup"><span data-stu-id="91f94-169">Both positive (ACK) and negative (NACK) acknowledgments are published to the MessageBox database at the point of failure provided there is at least one matching subscription.</span></span> <span data-ttu-id="91f94-170">Por ejemplo, si BizTalk Server no encuentra un esquema coincidente para un mensaje leído desde un puerto de recepción y no hay suscripciones NACK, suspenderá el mensaje (si no se ha habilitado el enrutamiento de mensajes con errores) y no publicará un mensaje NACK.</span><span class="sxs-lookup"><span data-stu-id="91f94-170">For example, if BizTalk Server cannot find a matching schema for a message read from a receive port and there are no NACK subscriptions, it suspends the message (if failed message routing has not been enabled) and does not publish a NACK</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f94-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f94-171">See Also</span></span>  
 <span data-ttu-id="91f94-172">[Control de errores](../core/error-handling.md) </span><span class="sxs-lookup"><span data-stu-id="91f94-172">[Error Handling](../core/error-handling.md) </span></span>  
 [<span data-ttu-id="91f94-173">Uso del enrutamiento de mensajes con errores</span><span class="sxs-lookup"><span data-stu-id="91f94-173">Using Failed Message Routing</span></span>](../core/using-failed-message-routing.md)