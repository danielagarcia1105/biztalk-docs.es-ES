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
# <a name="wcf-receive-adapter"></a>Adaptador de recepción WCF
El adaptador de recepción WCF permite recibir solicitudes del Servicio WCF.  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a>Extraer el cuerpo del mensaje de BizTalk del mensaje SOAP  
 El cuerpo del mensaje de BizTalk entrante se puede extraer del mensaje SOAP a través de una de las siguientes opciones:  
  
- Extraer el contenido del elemento Body de SOAP  
  
- Extraer el sobre SOAP completo  
  
- Extraer el contenido del elemento del sobre SOAP mediante una expresión XPath  
  
  Puede configurar estas opciones en el cuadro de diálogo de propiedades de transporte.  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a>Extraiga el contenido del elemento Body SOAP  
 Cuando se selecciona esta opción, el contenido interno del elemento Body de SOAP se lee en el mensaje SOAP y se coloca en la parte del cuerpo del mensaje de BizTalk.  
  
#### <a name="extract-the-entire-soap-envelope"></a>Extraer la envoltura SOAP completo  
 Cuando se selecciona esta opción, el sobre SOAP completo incluida la etiqueta se coloca en la parte del cuerpo del mensaje de BizTalk.  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a>Extraer el contenido del elemento mediante una expresión XPath  
 Cuando se selecciona esta opción, el contenido interno del elemento que se encuentra dentro del elemento Body de SOAP localizado por la expresión XPath se coloca en la parte del cuerpo del mensaje de BizTalk. Se omiten los datos restantes del elemento Body. También deberá especificar la codificación de nodo, para la codificación de Base64, Hex o cadena XML, de ejemplo.  
  
> [!NOTE]
>  Si se selecciona la codificación XML, el contenido externo del elemento se localiza mediante la expresión XPath y se coloca en la parte del cuerpo.  
  
## <a name="handling-web-services-headers"></a>Controlar encabezados de servicios Web  
 El adaptador de recepción promueve un subconjunto de encabezados de servicios Web estándar en el contexto del mensaje de BizTalk para habilitar el acceso sencillo y el enrutamiento basado en los valores de dichos encabezados. En la siguiente tabla se enumeran las propiedades que se guardarán en el contexto del mensaje mediante el adaptador de recepción. Las propiedades se definen en los espacios de nombres siguientes: http://www.w3.org/2005/addressing y http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties.  
  
|Encabezado|Nombre de la propiedad de BizTalk|¿Está promocionada?|  
|------------|---------------------------|------------------|  
|Acción|Acción|Sí|  
|MessageID|MessageID|no|  
|A|A|Sí|  
|ReplyTo/Address|ReplyTo|Sí|  
|From/Address|De|Sí|  
|Sequence/Identifier|SequenceId|Sí|  
|Sequence/MessageNumber|SequenceNumber|Sí|  
|Sequence/LastMessage|SequenceLastMessage|Sí|  
|\<Encabezado de SOAP:\>|InboundHeaders|no|  
  
## <a name="see-also"></a>Vea también  
 [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Adaptador de envío WCF](../core/wcf-send-adapter.md)   
 [¿Qué son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md)