---
title: Autenticación del remitente de un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parties, authenticating
- authenticating, authentication required
- messages, authenticating
- security, authenticating
- digital signatures, authenticating
- security, messages
- MessageBox database, authenticating
- authenticating, authentication trust
- messages, message flow
- authenticating, security
- authenticating, party resolution
- authenticating, digital signatures
- authenticating, messages
ms.assetid: 813a2fb9-0346-4129-9cc5-1713f72a491e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52b0e69a2799bf5b119093e4ac82773014e979b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019090"
---
# <a name="authenticating-the-sender-of-a-message"></a>Autenticación del remitente de un mensaje
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa diferentes mecanismos para comprobar si una entidad o un proceso son quienes dicen ser. Además, el usuario puede especificar si el proceso puede retransmitir a BizTalk Server quién es el remitente original del mensaje y si BizTalk Server reconoce a esa entidad como socio.  
  
 La siguiente ilustración muestra las características de seguridad de BizTalk Server que le permiten autenticar y autorizar al remitente de un mensaje.  
  
 ![Características de seguridad para mensajes seguros](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
Las características de seguridad que BizTalk Server utiliza para autenticar y autorizar el envío de un mensaje  
  
 Estas son las características que le permiten autenticar al remitente de un mensaje:  
  
- **Validación de firma digital.** Si el mensaje tiene una firma digital, BizTalk Server la utiliza para comprobar la identidad del remitente. Para obtener más información sobre cómo configurar la validación de firmas digitales, vea [cómo configurar BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).  
  
- **Resolución de entidades.** Todos los mensajes insertados en la base de datos de cuadro de mensajes, procedan o no de BizTalk Server, llevan un Id. de entidad (PID) que se determina mediante la asignación de un certificado digital o de una cuenta de Windows a un PID. Para obtener más información sobre cómo configurar el componente de resolución de entidades, vea [mediante certificados para la resolución de entidades](../core/using-certificates-for-party-resolution.md).  
  
- **Se requiere autenticación.** Si el puerto de recepción no puede determinar el remitente del mensaje, un host de BizTalk puede aceptarlo como un mensaje "de invitado" o simplemente ignorarlo. Esta característica le permite proteger su sistema de ataques de denegación de servicio, ya que los mensajes de entidades desconocidas no se procesarán ni se almacenarán en la base de datos de seguimiento. Para obtener más información sobre las opciones de autenticación para puertos de recepción, vea [cómo configurar las opciones de autenticación para un puerto de recepción](../core/how-to-configure-authentication-options-for-a-receive-port.md).  
  
- **Autenticación de confianza.** Si la base de datos de cuadro de mensajes recibe un mensaje de un host que no se ha identificado como con autenticación de confianza, dicha base de datos sobrescribirá el PID con el Id. de invitado y el SSID con la cuenta de servicio en la que se ejecuta la instancia del host. BizTalk Server permite que un host identificado como con autenticación de confianza indique que el remitente de un mensaje que dicho host está agregando a la cola de la base de datos de cuadro de mensajes es una entidad distinta del host de confianza mismo. Los fines principales de la autenticación de confianza son permitir que las canalizaciones resuelvan en un PID y pasen éste a servicios de consumo para su uso en la autorización y la resolución de entidades salientes, y permitir la transmisión del Id. de seguridad de Windows del remitente (SSID) a los servicios de consumo para su uso en la autorización de acciones de orquestación. Para obtener más información acerca de los host de confianza de autenticación, consulte [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md). Para obtener más información acerca de cómo utilizar orquestaciones de BizTalk Server junto con la resolución de entidades, vea [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md).  
  
  Puede utilizar algunas de las características mostradas en la ilustración o todas ellas, dependiendo de si necesita saber quién le envió el mensaje, cuál es su remitente original, o quién es el destinatario o el lector de su mensaje.  
  
  Si sus socios necesitan saber con seguridad que los mensajes proceden de usted y que nadie más puede leerlos mientras se encuentran en tránsito, le convendrá usar las siguientes técnicas para garantizar que sólo los destinatarios especificados y las aplicaciones especificadas reciben los mensajes:  
  
- Utilice firmas digitales para mensajes salientes a fin de que su socio pueda comprobar que usted es el remitente.  
  
- Cifre los mensajes salientes para garantizar que ninguna persona no autorizada pueda verlos mientras están en tránsito.  
  
  Si es importante determinar quién envió un mensaje a su empresa y garantizar que nadie más pueda leerlo mientras se encuentra en tránsito, le convendrá usar las siguientes técnicas para garantizar que sólo los destinatarios especificados y las aplicaciones especificadas reciben los mensajes:  
  
- Asegúrese de que BizTalk Server sólo acepta mensajes con firma digital para saber quién envió el mensaje.  
  
- Asegúrese de enviar a sus socios el certificado de clave pública para que cifren los mensajes que envían a BizTalk Server. Con el cifrado puede garantizar que ninguna persona no autorizada vea el mensaje mientras se encuentra en tránsito.  
  
- Use la propiedad de autenticación necesaria en el puerto de recepción para asegurarse de que el mensaje es de una entidad conocida.  
  
  Si el mensaje es procesado por más de un host, puede haber dudas sobre su remitente original. Cuando se necesita conocer la identidad del remitente original, por ejemplo al conceder acceso para enviar o recibir un mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un mecanismo de seguridad para propagar la identidad del remitente original a muchos hosts a fin de validar el acceso a los hosts de nivel inferior mediante esa identidad. En BizTalk Server este proceso se llama Autenticación de confianza. Para obtener más información, consulte [autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Autenticación de mensajes de entrada](../core/inbound-message-authentication.md)  
  
-   [Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md)  
  
-   [Protección de mensajes de salida](../core/outbound-message-protection.md)