---
title: Adaptador de envío de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- serializing, SOAP messages
- WCF adapters, extracting information
- messages, extracting information
- SOAP messages, serializing
- WCF adapters, message bodies
- send adapters, WCF adapters
- Web services, headers
- WCF adapters, send adapters
ms.assetid: 226a020a-2e12-41fe-a4a2-6683d9e98219
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70604fbc15f5f15b0a7ff2325debdc28ac3a97c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288764"
---
# <a name="wcf-send-adapter"></a>Adaptador de envío WCF
El adaptador de envío WCF le permite llamar a un Servicio WCF a través del contrato sin tipo.  
  
## <a name="specifying-the-wcf-message-body"></a>Especificar el cuerpo de mensaje WCF  
 El cuerpo de mensaje que necesita enviar al servidor BizTalk Server puede insertarse en el mensaje SOAP mediante la utilización de una de las siguientes opciones:  
  
-   Extraer el contenido del cuerpo del mensaje de BizTalk  
  
-   Especificar el contenido mediante la plantilla  
  
 Puede configurar estas opciones en el cuadro de diálogo de propiedades de transporte de puerto de envío.  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a>Extraer el contenido del cuerpo de mensaje de BizTalk  
 Cuando se selecciona esta opción, se inserta el contenido del cuerpo de mensaje de BizTalk en el elemento de Cuerpo de SOAP para el cuerpo de mensaje de salida de WCF.  
  
#### <a name="specify-the-content-by-using-the-template"></a>Especificar el contenido utilizando la plantilla  
 Cuando se selecciona esta opción, se sitúa del cuerpo de mensaje de BizTalk en el elemento de cuerpo de SOAP para la plantilla XML para el cuerpo de mensaje de salida de WCF.  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a>Serializar el mensaje de BizTalk en un mensaje SOAP  
 El adaptador de envío serializa el mensaje de BizTalk en un mensaje SOPA antes de enviarlo. Las siguientes reglas se aplican durante la serialización del mensaje:  
  
-   Si el mensaje de BizTalk es un mensaje de varias partes, sólo se usa la parte del cuerpo.  
  
-   Si el mensaje de BizTalk contiene el sobre de SOAP completo, se envuelve un otro sobre SOAP.  
  
-   Si el mensaje de BizTalk contiene datos XML arbitrarios, el mensaje de BizTalk se coloca en el elemento Cuerpo de SOAP.  
  
## <a name="handling-web-services-headers"></a>Controlar encabezados de servicios Web  
 Durante las operaciones de envío, BizTaklk Server no tiene control sobre los encabezados estándar de servicios Web. WCF establece y procesa los encabezados. El único encabezado estándar que se puede modificar mediante la aplicación de BizTalk Server es el **un: acción** encabezado. Si la propiedad de contexto **acción** se especifica en el espacio de nombres de adaptador, el adaptador de envío WCF utilizará el valor de la propiedad para establecer el **acción** en el mensaje SOAP.  
  
> [!NOTE]
>  Para dinámicas de puertos de envío, si **acción** se especifica en el **OutboundHeaders**, la propiedad de contexto establecido para el **WCF. Acción** se pasará por alto.  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a>Especificar la propiedad de contexto BTS.IsDynamicSend  
 El adaptador de envío WCF almacena la configuración para los puertos de envío. Si el **BTS. IsDynamicSend** propiedad está establecida en true, el envío WCF adaptador no usa la configuración almacenada en caché, sino que lee toda la información de configuración desde el mensaje de propiedades de contexto de los mensajes salientes. En un puerto de envío estático, WCF adaptador de envío utiliza **BTS. SPLastUpdatedTime**, que es el momento en que la configuración del puerto de envío estático se modificó por última vez, para detectar si hay cualquier configuración de puerto de envío de cambios en el método estático. De esta forma, el adaptador de envío WCF no necesita leer todas las configuraciones de todos los contextos de mensaje.  
  
 Si desea invalidar las propiedades de puerto de envío estático distinto de la **WCF. Acción** propiedad en una canalización de envío, debe establecer el **BTS. IsDynamicSend** no ha cambiado la propiedad en true para que el adaptador de envío WCF no usará la configuración almacenada en caché aunque la última marca de tiempo actualizada.  
  
## <a name="see-also"></a>Vea también  
 [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Adaptador de recepción de WCF](../core/wcf-receive-adapter.md)   
 [¿Cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md)   
 [Cómo utilizar propiedades de contexto de mensaje](../core/how-to-use-message-context-properties.md)