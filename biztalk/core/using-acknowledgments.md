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
# <a name="using-acknowledgments"></a>Usar confirmaciones
El motor de mensajería de BizTalk genera confirmaciones positivas (ACK) y confirmaciones negativas (NACK) en respuesta a situaciones que ocurren durante el procesamiento de un mensaje a través de un puerto. BizTalk Server publica una confirmación positiva para indicar que un mensaje se ha transmitido correctamente y una confirmación negativa para señalar que ha habido un error de transmisión y que se ha suspendido el mensaje.  
  
## <a name="why-use-acknowledgments"></a>¿Por qué se utilizan las confirmaciones?  
 Las confirmaciones positivas y negativas proporcionan información eficaz que permite determinar si un mensaje ha llegado al destino o si se ha producido algún problema en el proceso. Por ejemplo, las confirmaciones son útiles si:  
  
- Desea supervisar un puerto de recepción para un nuevo socio comercial con fines de validación de esquemas y otros errores.  
  
- Desea marcar el estado de una solicitud de préstamo enviada para aprobación como "en curso" si ésta se envía correctamente a un socio comercial para aprobación o como "con errores" si hay errores en la transmisión (por ejemplo, si el servidor del socio comercial está inactivo).  
  
- Procesa intercambios que contienen varios pedidos y desea realizar un seguimiento del número de pedidos transmitidos y no trasmitidos.  
  
  Puede realizar las acciones descritas en los escenarios anteriores si utiliza confirmaciones y enrutamiento basado en contenido que use filtros.  
  
## <a name="routing-acknowledgments"></a>Enrutar confirmaciones  
 Cuando se publica una confirmación ACK o NACK, todas las propiedades de contexto del mensaje que causó la generación de una confirmación ACK o NACK se degradan. Cualquier propiedad promocionada no pasa al flujo de confirmación. Para enrutar una confirmación, cree un filtro con las siguientes propiedades desde el **BTS** espacio de nombres:  
  
|Nombre de propiedad|Tipo de datos|Descripción|  
|-------------------|---------------|-----------------|  
|BTS.AckFailureCategory|xs:int|Identifica el **ErrorCategory**, que indica la ubicación y el motivo de la suspensión.|  
|BTS.AckFailureCode|xs:string|Identifica el **ErrorCode**, que indica la ubicación y el motivo de la suspensión.|  
|BTS.AckType|xs:string|El valor es ACK para una confirmación positiva y NACK en el caso de una confirmación negativa.|  
|BTS.AckID|xs:string|Identifica el **MessageID** del mensaje original.|  
|BTS.AckOwnerID|xs:string|Identifica el Id. de instancia del mensaje original.|  
|BTS.CorrelationToken|xs:string|Identifica el token de correlación del mensaje original, si hay alguno presente.|  
|BTS.AckDescription|xs:string|Identifica el **ErrorDescription**, que indica la ubicación y el motivo de la suspensión.|  
|BTS.AckSendPortID|xs:string|Identifica el **SendPortID** del mensaje original.|  
|BTS.AckSendPortName|xs:string|Identifica el **SendPortName** del mensaje original.|  
|BTS.AckOutboundTransportLocation|xs:string|Identifica el **OutboundTransportLocation** del mensaje original.|  
|BTS.AckReceivePortID|xs:string|Identifica el **ReceivePortID** del mensaje original.|  
|BTS.AckReceivePortName|xs:string|Identifica el **ReceivePortName** del mensaje original.|  
|BTS.AckInboundTransportLocation|xs:string|Identifica el **InboundTransportLocation** del mensaje original.|  
  
> [!NOTE]
>  Las propiedades que contienen información de errores no se incluyen en las confirmaciones ACK, ya que estas confirmaciones indican que la entrega se ha realizado.  
  
## <a name="negative-acknowledgment-message-body"></a>Cuerpo del mensaje de una confirmación negativa  
 Gran parte de la información importante acerca de una confirmación positiva o negativa se incluye en las propiedades de contexto. Además de las propiedades de contexto, las confirmaciones NACK contienen una sección denominada cuerpo del mensaje que incluye un error de SOAP. El formato del error de SOAP es el siguiente:  
  
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
  
 El mensaje de excepción generado por el adaptador se encuentra en la sección de detalles de SOAP del elemento ErrorDescription.  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a>Tener acceso al cuerpo del mensaje desde una orquestación  
 Si tiene un puerto de orquestación que requiere notificación de entrega, el elemento DeliveryFailureException generado como resultado de un error de transmisión se deserializa desde el error de SOAP incluido en el cuerpo del mensaje NACK. Para tener acceso a la cadena del mensaje de excepción desde la orquestación, convierta el elemento DeliveryFailureException en un elemento SoapException y, a continuación, obtenga acceso a InnerXml como se muestra en el siguiente código:  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 El ejemplo de código anterior devuelve un fragmento XML similar al siguiente:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a>¿Cuándo se publica una confirmación?  
 Las confirmaciones positivas (ACK) y negativas (NACK) se publican en la base de datos del cuadro de mensajes en el momento en que se produce el error si al menos una suscripción coincide. Por ejemplo, si BizTalk Server no encuentra un esquema coincidente para un mensaje leído desde un puerto de recepción y no hay suscripciones NACK, suspenderá el mensaje (si no se ha habilitado el enrutamiento de mensajes con errores) y no publicará un mensaje NACK.  
  
## <a name="see-also"></a>Vea también  
 [Control de errores](../core/error-handling.md)   
 [Uso del enrutamiento de mensajes con errores](../core/using-failed-message-routing.md)