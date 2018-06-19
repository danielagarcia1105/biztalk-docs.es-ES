---
title: Protección de mensajes salientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, outbound messages
- outbound messages
- security, messages
- authenticating, warnings
- messages, outbound
ms.assetid: 839d3b44-bb44-454b-817c-67b7c8cd74c9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7adbbae776edee8a4f563e2cd48ee035acc3fd7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264628"
---
# <a name="outbound-message-protection"></a>Protección de mensajes salientes
La siguiente ilustración muestra las características de seguridad de BizTalk Server que puede usar para impedir que sus mensajes salientes sean leídos por personas no autorizadas.  
  
 ![Características de seguridad que protegen los mensajes salientes](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")  
Características de seguridad usadas por BizTalk Server para proteger los mensajes salientes.  
  
 Al enviar un mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza los pasos siguientes para asegurarse de que lo hace de forma segura y de que la entidad receptora puede determinar su remitente:  
  
1.  Si la canalización de envío contiene un componente de codificación (como S/MIME) configurado para firmar todos los mensajes salientes, el certificado de firma del grupo de BizTalk se recupera del almacén de certificados personales de la cuenta de servicio de la instancia de host en que se está ejecutando la canalización, y el mensaje se firma mediante la clave privada asociada con el certificado.  
  
2.  Si la canalización de envío contiene un componente de codificación (como S/MIME) configurado para cifrar todos los mensajes salientes, se utiliza la huella digital del certificado de cifrado para recuperar el certificado de clave pública del almacén de certificados Otras personas, y el mensaje se cifra mediante ese certificado.  
  
> [!IMPORTANT]
>  Aunque use un solo certificado de firma para todas las canalizaciones de envío de su entorno de BizTalk, debe asegurarse de que ese certificado está disponible en el almacén de certificados de la cuenta de servicio de cada instancia de host de los hosts en que se estén ejecutando canalizaciones de envío.  
  
 Para obtener más información acerca de cómo enviar mensajes firmados, vea [cómo configurar BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).  
  
## <a name="see-also"></a>Vea también  
 [Autenticación de mensajes entrantes](../core/inbound-message-authentication.md)   
 [Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md)   
 [Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md)   
 [Autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md)   
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)