---
title: "Consideraciones al consumir servicios WCF con WCF adaptadores de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- best practices, WCF services
- WCF services, best practices
- consuming, best practices
- WCF services, consuming
ms.assetid: 8bbcfd99-3495-458d-bd7a-6d170a29dde2
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2bb1e512b8a13c3d91b87bbfc410c3d21f334fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-consuming-wcf-services-with-the-wcf-send-adapters"></a>Consideraciones al consumir servicios WCF con los adaptadores de envío WCF
Este tema proporciona información que es necesario tener en cuenta a la hora de consumir servicios WCF con los adaptadores de WCF.  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-solicit-messages"></a>Utilice la opción "Plantilla: contenido especificado por plantilla" al enviar contenido que no sea XML como mensajes de petición  
 Los adaptadores de WCF con **cuerpo--cuerpo de mensaje de respuesta de BizTalk** (el valor predeterminado) opción no permite el envío de mensajes no XML, como imágenes de mapa de bits y datos de caracteres. Puede usar el **plantilla--contenido especificado por plantilla** opción para los adaptadores de WCF enviar mensajes no XML. Para obtener más información acerca de cómo usar la plantilla, vea [consideraciones al publicar servicios WCF con los adaptadores de recepción de WCF](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md).  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-ports-always-ignore-the-proxy-if-the-service-address-begins-with-httplocalhost"></a>Los puertos de envío WCF-BasicHttp y WCF-WSHttp siempre omiten el proxy si la dirección del servicio comienza por http://localhost  
 El WCF-BasicHttp y WCF-WSHttp puertos de envío siempre omiten el proxy si la dirección de servicio comienza por http://localhost si el proxy está configurado en el **Proxy** ficha del puerto de envío o la **Proxy** ficha del controlador de envío. Debe utilizar el nombre de host (en lugar del de localhost) si desea que los clientes pasen a través de un proxy al hablar con servicios del mismo equipo.  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-adapters-suspend-the-messages-if-the-proxy-setting-is-not-correctly-configured"></a>Los adaptadores de envío WCF-BasicHttp y WCF-WSHttp suspenden los mensajes si el proxy no está configurado correctamente  
 Puede especificar la configuración del proxy para el WCF-BasicHttp y WCF-WSHttp adaptadores de envío el **Proxy** ficha del puerto de envío o la **Proxy** ficha del controlador de envío. Si el proxy no está configurado correctamente, los adaptadores de envío suspenden los mensajes y recibirá el mensaje de error "No había ningún extremo a la escucha que pudiera aceptar el mensaje" en el registro de eventos.  
  
## <a name="setting-up-the-permissions-for-a-wcf-send-port-with-the-wcf-netmsmq-adapter"></a>Configurar los permisos para un puerto de envío WCF con el adaptador de WCF-NetMsmq  
 Cuando un puerto de envío WCF con el adaptador de WCF-NetMsmq envía un mensaje a un Servicio WCF publicado con NetMsmqBinding, dirige el mensaje a la cola de destino, que es la cola administrada por el administrador de colas del servicio. El administrador de colas del cliente envía el mensaje a una cola de transmisión (o saliente). La cola de transmisión es una cola situada en el administrador de colas del cliente que almacena mensajes para transmitirlos a la cola de destino.  
  
 El administrador de colas del servicio acepta los mensajes dirigidos a las colas de destino que le pertenecen y, además, almacena los mensajes. A continuación, el servicio realiza solicitudes para leer de la cola de destino y el administrador de colas entrega los mensajes al servicio. Por este motivo, la cuenta del servicio de la instancia de host de BizTalk que aloja el puerto de envío debería disponer de los permisos necesarios para escribir en la cola de transmisión.  
  
## <a name="use-an-empty-xpath-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>Utilizar una expresión XPath vacía para recibir un mensaje SOAP con datos de caracteres en el contenido del elemento Cuerpo de SOAP  
 Un puerto de petición-respuesta de WCF puede recibir un mensaje WCF como mensaje de respuesta. Para crear un mensaje de BizTalk de un mensaje de respuesta entrante con datos de caracteres en el contenido del mensaje SOAP **cuerpo** elemento tal como se muestra en el ejemplo siguiente, que debe conservarse el **expresión XPath** cuadro de texto vacío en la **mensaje** ficha en el cuadro de diálogo de propiedades de transporte WCF adaptador.  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 Si selecciona el **sobres** o **cuerpo** opción, el adaptador no crea el mensaje de BizTalk desde el mensaje entrante. El mensaje no se suspende porque los mensajes que producen error en el procesamiento del cálculo de referencia de SOAP entrante no se suspenden. Para obtener más información acerca de cómo utilizar la expresión XPath en el **mensaje** pestaña, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).  
  
> [!NOTE]
>  Puede usar la herramienta TraceViewer (SvcTraceViewer.exe) de Windows SDK mediante la configuración de BTSNTSvc.exe.config.file. Para obtener más información sobre el SDK de Windows, consulte "What's New in the Windows SDK" en [http://go.microsoft.com/fwlink/?LinkId=75219](http://go.microsoft.com/fwlink/?LinkId=75219). Para obtener más información acerca de la herramienta TraceViewer, vea "TraceViewer Tool (SvcTraceViewer.exe)" en [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218).  
  
## <a name="biztalk-server-does-not-use-multi-part-message-types-and-root-elements-describing-custom-soap-headers"></a>BizTalk Server no utiliza tipos de mensaje de varias partes y elementos raíz que describan los encabezados SOAP personalizados  
 Si ejecuta el Asistente de consumición del Servicio WCF de BizTalk en metadatos en los que se hayan definido encabezados SOAP personalizados, el asistente genera elementos raíz en los esquemas generados para representar los encabezados SOAP personalizados. El asistente también crea tipos de mensajes de varias partes en orquestaciones para los encabezados SOAP personalizados. Servidor BizTalk Server. Sin embargo, BizTalk Server no utiliza tipos de mensajes de varias partes ni elementos raíz para controlar los encabezados SOAP personalizados.  
  
 Para obtener acceso a los encabezados SOAP personalizados, debe usar el **InboundHeaders** propiedad. Para obtener más información acerca de la recepción de encabezados SOAP personalizados, consulte [encabezados SOAP con servicios de WCF publican](../core/soap-headers-with-published-wcf-services.md). Para utilizar encabezados SOAP personalizados, debe usar el **OutboundCustomHeaders** propiedad. Para obtener más información acerca de cómo enviar encabezados SOAP personalizados, consulte [encabezados SOAP con servicios de WCF consume](../core/soap-headers-with-consumed-wcf-services.md).  
  
## <a name="create-separate-host-instances-for-send-ports-that-use-different-proxy-addresses-andor-proxy-credentials"></a>Crear instancias de host independientes para los puertos de envío que utilicen direcciones de proxy o credenciales de proxy distintas.  
 Para obtener el máximo rendimiento de los adaptadores de envío de WCF, recomendamos que cree instancias de host independientes para los puertos de envío que utilicen direcciones de proxy o credenciales de proxy distintas. Esto evita la contención en la configuración del proxy.  
  
## <a name="see-also"></a>Vea también  
 [Archivo BTSNTSvc.exe.config](../core/btsntsvc-exe-config-file.md)