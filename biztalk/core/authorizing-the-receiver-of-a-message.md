---
title: "Autorización del receptor de un mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, messages
- messages, receive authorization
- receive authorization
- messages, security
ms.assetid: c0cdb3ef-ee8e-40a1-9362-13cd26495951
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7317cd9c54568edd2c49df026790ee7a1e70fb2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="authorizing-the-receiver-of-a-message"></a>Autorización del receptor de un mensaje
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite limitar los procesos y las entidades que autoriza a recibir mensajes.  
  
 La siguiente ilustración muestra las características de seguridad de BizTalk Server que usará para autorizar al receptor de un mensaje.  
  
 ![Características de seguridad autorizar el receptor del mensaje](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")  
Características de seguridad usadas por BizTalk Server para autorizar al receptor de un mensaje.  
  
 Puede utilizar los siguientes mecanismos de seguridad para establecer quién tiene permiso (autorización) para recibir los mensajes enviados por usted:  
  
-   **Descifrado.** Asegúrese de que las entidades que envían mensajes a BizTalk Server tienen el certificado de clave pública para cifrar esos mensajes. BizTalk Server utiliza el certificado de clave privada para descifrar el mensaje.  
  
-   **Autorización de recepción.** Puede utilizar este método para controlar qué hosts del entorno de BizTalk Server pueden recibir un mensaje dado.  
  
-   **Cifrado.** Si utiliza el certificado de clave pública de una entidad determinada cuando BizTalk cifra un mensaje, puede asegurarse de que sólo esa entidad pueda leerlo.  
  
## <a name="receive-authorization"></a>Autorización de recepción  
 La autorización de recepción es el método que puede utilizar para controlar los hosts que pueden recibir (suscribirse a) un mensaje específico. BizTalk Server utiliza la información del certificado como una propiedad de suscripción para que coincidan con predicados en el mensaje: la base de datos de cuadro de mensajes sólo enruta los mensajes marcados como de autorización necesario para los hosts que tienen el certificado de descifrado para ese mensaje. Para ilustrar el proceso, considere estos escenarios:  
  
-   **Enrutamiento de un mensaje no cifrado:** cuando BizTalk Server recibe un mensaje que el remitente no cifrado, no hay ninguna limitación de descifrado en cuanto a cómo BizTalk enrutará el mensaje. Cualquier host puede recibirlo, tenga o no certificados de autorización de recepción configurados.  
  
-   **Enrutamiento de un mensaje cifrado:** cuando llega un mensaje cifrado, la canalización de recepción debe contener un componente de descodificación que descifra el mensaje. Cuando enruta un mensaje tras descifrarlo, BizTalk Server utiliza la huella digital del certificado utilizada para descifrar el mensaje como prueba en el mecanismo de suscripción de la base de datos de cuadro de mensajes, y sólo los hosts configurados con ese certificado reciben el mensaje.  
  
 Si desea usar la autorización de recepción, debe proporcionar la huella digital del certificado de descifrado en las propiedades del host que desea autorizar a recibir el mensaje. Para obtener más información acerca de la autorización de recepción, consulte [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Autenticación de mensajes entrantes](../core/inbound-message-authentication.md)   
 [Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md)   
 [Protección de mensajes salientes](../core/outbound-message-protection.md)   
 [Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md)   
 [Planear la seguridad de mensaje](../core/planning-message-security.md)