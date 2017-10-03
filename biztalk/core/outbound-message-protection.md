---
title: "Protección de mensajes salientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, outbound messages
- outbound messages
- security, messages
- authenticating, warnings
- messages, outbound
ms.assetid: 839d3b44-bb44-454b-817c-67b7c8cd74c9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7adbbae776edee8a4f563e2cd48ee035acc3fd7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="outbound-message-protection"></a><span data-ttu-id="c34be-102">Protección de mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="c34be-102">Outbound Message Protection</span></span>
<span data-ttu-id="c34be-103">La siguiente ilustración muestra las características de seguridad de BizTalk Server que puede usar para impedir que sus mensajes salientes sean leídos por personas no autorizadas.</span><span class="sxs-lookup"><span data-stu-id="c34be-103">The following figure shows the security features in BizTalk Server that you use to help protect outbound messages from being read by unauthorized parties.</span></span>  
  
 <span data-ttu-id="c34be-104">![Características de seguridad que protegen los mensajes salientes](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span><span class="sxs-lookup"><span data-stu-id="c34be-104">![Security features protecting outbound messages](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span></span>  
<span data-ttu-id="c34be-105">Características de seguridad usadas por BizTalk Server para proteger los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="c34be-105">Security features BizTalk Server uses to protect outbound messages.</span></span>  
  
 <span data-ttu-id="c34be-106">Al enviar un mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza los pasos siguientes para asegurarse de que lo hace de forma segura y de que la entidad receptora puede determinar su remitente:</span><span class="sxs-lookup"><span data-stu-id="c34be-106">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, it takes the following steps to help ensure that it sends the message securely, and that the receiving party can determine the message sender:</span></span>  
  
1.  <span data-ttu-id="c34be-107">Si la canalización de envío contiene un componente de codificación (como S/MIME) configurado para firmar todos los mensajes salientes, el certificado de firma del grupo de BizTalk se recupera del almacén de certificados personales de la cuenta de servicio de la instancia de host en que se está ejecutando la canalización, y el mensaje se firma mediante la clave privada asociada con el certificado.</span><span class="sxs-lookup"><span data-stu-id="c34be-107">If the send pipeline contains an encoding component (such as S/MIME) that is configured to sign all outbound messages, the signing certificate for the BizTalk group is retrieved from the personal certificate store for the host instance service account under which the pipeline is running, and the message is signed using the private key associated with the certificate.</span></span>  
  
2.  <span data-ttu-id="c34be-108">Si la canalización de envío contiene un componente de codificación (como S/MIME) configurado para cifrar todos los mensajes salientes, se utiliza la huella digital del certificado de cifrado para recuperar el certificado de clave pública del almacén de certificados Otras personas, y el mensaje se cifra mediante ese certificado.</span><span class="sxs-lookup"><span data-stu-id="c34be-108">If the send pipeline contains an encoding component (such as S/MIME) that is configured to encrypt all outbound messages, the encryption certificate thumbprint is used to retrieve the public key certificate from the Other People certificate store, and the message is encrypted using that certificate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c34be-109">Aunque use un solo certificado de firma para todas las canalizaciones de envío de su entorno de BizTalk, debe asegurarse de que ese certificado está disponible en el almacén de certificados de la cuenta de servicio de cada instancia de host de los hosts en que se estén ejecutando canalizaciones de envío.</span><span class="sxs-lookup"><span data-stu-id="c34be-109">Although you use one signing certificate for all the send pipelines in your BizTalk environment, you must ensure this signing certificate is available in the certificate store of the service account of each host instance of the hosts where the send pipelines are running.</span></span>  
  
 <span data-ttu-id="c34be-110">Para obtener más información acerca de cómo enviar mensajes firmados, vea [cómo configurar BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c34be-110">For more information about how to send signed messages, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34be-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c34be-111">See Also</span></span>  
 <span data-ttu-id="c34be-112">[Autenticación de mensajes entrantes](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="c34be-112">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="c34be-113">[Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="c34be-113">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="c34be-114">[Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="c34be-114">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 <span data-ttu-id="c34be-115">[Autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="c34be-115">[Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md) </span></span>  
 [<span data-ttu-id="c34be-116">Certificados que utiliza BizTalk Server para mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="c34be-116">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)