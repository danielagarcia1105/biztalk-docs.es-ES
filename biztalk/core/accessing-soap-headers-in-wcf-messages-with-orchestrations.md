---
title: Obtener acceso a los encabezados SOAP en mensajes WCF con orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- orchestrations, WCF services
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: fe02fb02-18d6-4fc6-89e0-b06bdbfa5cb4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bfd1dd4e09071c3d7bcccf28878f19e13acad8a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a>Obtener acceso a encabezados SOAP en mensajes WCF con orquestaciones
Para obtener acceso a los valores del encabezado SOAP de mensajes entrantes de WCF en orquestaciones, use la propiedad de contexto **WCF. InboundHeaders**. Los adaptadores WCF copian encabezados SOAP personalizados y encabezados SOAP estándar en los mensajes entrantes en el **WCF. InboundHeaders** propiedad. Además, los adaptadores de WCF permiten seleccionar las propiedades que desee promocionar o escribir en las propiedades de contexto mediante programación. Vea [encabezados SOAP con servicios de WCF publican](../core/soap-headers-with-published-wcf-services.md) para obtener más detalles.  
  
 El valor contenido en la propiedad de contexto es una cadena que contiene los datos XML con la \< **encabezados** \> elemento raíz y los encabezados SOAP entrantes se copian como elementos secundarios de la \< **encabezados** \> elemento. La manera más sencilla de obtener acceso a estos datos consiste en usar el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma, carga la cadena en un **XmlDocument**y usar Consultas de XPath para tener acceso a campos específicos. Para obtener más información acerca de cómo crear documentos XML en el Editor de expresiones de BizTalk, consulte [lenguaje XLANG s](../core/xlang-s-language.md).  
  
 En el ejemplo de código siguiente se obtiene el encabezado SOAP de solicitud un **asignación de mensajes** o **expresión** forma para el **WCF. InboundHeaders** propiedad:  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 Las propiedades de contexto están asociadas con un mensaje concreto. El motor de mensajería no asigna automáticamente los valores de los encabezados SOAP desde el mensaje de solicitud al mensaje de respuesta. Al crear el mensaje de respuesta para un servicio WCF, debe definir específicamente los valores del encabezado SOAP a través de la **WCF. OutboundCustomHeaders** propiedad. El comando siguiente es el método más sencillo de establecer una propiedad de contexto del encabezado SOAP:  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 También puede establecer la propiedad de contexto mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto.  
  
 Para obtener más información acerca de cómo los encabezados SOAP de acceso con los adaptadores de WCF, consulte el ejemplo SDK "Usando Custom SOAP encabezados con los adaptadores de WCF" en [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).  
  
## <a name="see-also"></a>Vea también  
 [Obtener acceso a los encabezados SOAP en mensajes WCF con componentes de canalización](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)   
 [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)   
 [Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md)