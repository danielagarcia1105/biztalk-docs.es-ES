---
title: Autorización del receptor de un mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- messages, receive authorization
- receive authorization
- messages, security
ms.assetid: c0cdb3ef-ee8e-40a1-9362-13cd26495951
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7317cd9c54568edd2c49df026790ee7a1e70fb2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230748"
---
# <a name="authorizing-the-receiver-of-a-message"></a><span data-ttu-id="3cebf-102">Autorización del receptor de un mensaje</span><span class="sxs-lookup"><span data-stu-id="3cebf-102">Authorizing the Receiver of a Message</span></span>
<span data-ttu-id="3cebf-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite limitar los procesos y las entidades que autoriza a recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="3cebf-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to limit the processes and parties that you authorize to receive messages.</span></span>  
  
 <span data-ttu-id="3cebf-104">La siguiente ilustración muestra las características de seguridad de BizTalk Server que usará para autorizar al receptor de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-104">The following figure shows the security features in BizTalk Server that you use to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="3cebf-105">![Características de seguridad autorizar el receptor del mensaje](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span><span class="sxs-lookup"><span data-stu-id="3cebf-105">![Security features authorizing the message receiver](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span></span>  
<span data-ttu-id="3cebf-106">Características de seguridad usadas por BizTalk Server para autorizar al receptor de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-106">Security features BizTalk Server uses to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="3cebf-107">Puede utilizar los siguientes mecanismos de seguridad para establecer quién tiene permiso (autorización) para recibir los mensajes enviados por usted:</span><span class="sxs-lookup"><span data-stu-id="3cebf-107">You can use the following security mechanisms to establish who has permission (authorization) to receive the messages that you send:</span></span>  
  
-   <span data-ttu-id="3cebf-108">**Descifrado.**</span><span class="sxs-lookup"><span data-stu-id="3cebf-108">**Decryption.**</span></span> <span data-ttu-id="3cebf-109">Asegúrese de que las entidades que envían mensajes a BizTalk Server tienen el certificado de clave pública para cifrar esos mensajes.</span><span class="sxs-lookup"><span data-stu-id="3cebf-109">Make sure the parties that send messages to BizTalk Server have the public key certificate for encrypting messages they send to BizTalk Server.</span></span> <span data-ttu-id="3cebf-110">BizTalk Server utiliza el certificado de clave privada para descifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-110">BizTalk Server uses the private key certificate to decrypt the message.</span></span>  
  
-   <span data-ttu-id="3cebf-111">**Autorización de recepción.**</span><span class="sxs-lookup"><span data-stu-id="3cebf-111">**Receive Authorization.**</span></span> <span data-ttu-id="3cebf-112">Puede utilizar este método para controlar qué hosts del entorno de BizTalk Server pueden recibir un mensaje dado.</span><span class="sxs-lookup"><span data-stu-id="3cebf-112">You can use this method to control which hosts within the BizTalk Server environment can receive a given message.</span></span>  
  
-   <span data-ttu-id="3cebf-113">**Cifrado.**</span><span class="sxs-lookup"><span data-stu-id="3cebf-113">**Encryption.**</span></span> <span data-ttu-id="3cebf-114">Si utiliza el certificado de clave pública de una entidad determinada cuando BizTalk cifra un mensaje, puede asegurarse de que sólo esa entidad pueda leerlo.</span><span class="sxs-lookup"><span data-stu-id="3cebf-114">By using the public key certificate from a given party when BizTalk encrypts a message, you can ensure that only the intended party is able to read the message.</span></span>  
  
## <a name="receive-authorization"></a><span data-ttu-id="3cebf-115">Autorización de recepción</span><span class="sxs-lookup"><span data-stu-id="3cebf-115">Receive Authorization</span></span>  
 <span data-ttu-id="3cebf-116">La autorización de recepción es el método que puede utilizar para controlar los hosts que pueden recibir (suscribirse a) un mensaje específico.</span><span class="sxs-lookup"><span data-stu-id="3cebf-116">Receive authorization is the method you can use to control which hosts can receive (subscribe for) a given message.</span></span> <span data-ttu-id="3cebf-117">BizTalk Server utiliza la información del certificado como una propiedad de suscripción para que coincidan con predicados en el mensaje: la base de datos de cuadro de mensajes sólo enruta los mensajes marcados como de autorización necesario para los hosts que tienen el certificado de descifrado para ese mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-117">BizTalk Server uses the certificate information as a subscription property to match predicates on the message: the MessageBox database only routes messages marked as authorization required to the hosts that have the decryption certificate for that message.</span></span> <span data-ttu-id="3cebf-118">Para ilustrar el proceso, considere estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="3cebf-118">To illustrate the process, consider the following scenarios:</span></span>  
  
-   <span data-ttu-id="3cebf-119">**Enrutamiento de un mensaje no cifrado:** cuando BizTalk Server recibe un mensaje que el remitente no cifrado, no hay ninguna limitación de descifrado en cuanto a cómo BizTalk enrutará el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-119">**Routing an un-encrypted message:** When BizTalk Server receives a message that the sender did not encrypt, there is no decryption limitation as to how BizTalk routes the message.</span></span> <span data-ttu-id="3cebf-120">Cualquier host puede recibirlo, tenga o no certificados de autorización de recepción configurados.</span><span class="sxs-lookup"><span data-stu-id="3cebf-120">Both hosts with and hosts without receive authorization certificates configured can receive the message.</span></span>  
  
-   <span data-ttu-id="3cebf-121">**Enrutamiento de un mensaje cifrado:** cuando llega un mensaje cifrado, la canalización de recepción debe contener un componente de descodificación que descifra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-121">**Routing an encrypted message:** When an encrypted message arrives, the receiving pipeline must contain a decoding component that decrypts the message.</span></span> <span data-ttu-id="3cebf-122">Cuando enruta un mensaje tras descifrarlo, BizTalk Server utiliza la huella digital del certificado utilizada para descifrar el mensaje como prueba en el mecanismo de suscripción de la base de datos de cuadro de mensajes, y sólo los hosts configurados con ese certificado reciben el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-122">When BizTalk Server routes a message after it is decrypted, BizTalk uses the certificate thumbprint used to decrypt the message as evidence in the MessageBox database subscription mechanism, and only those hosts configured with that certificate receive the message.</span></span>  
  
 <span data-ttu-id="3cebf-123">Si desea usar la autorización de recepción, debe proporcionar la huella digital del certificado de descifrado en las propiedades del host que desea autorizar a recibir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cebf-123">If you want to use receive authorization, you must provide the thumbprint of the decryption certificate in the properties of the host that you want to authorize to receive the message.</span></span> <span data-ttu-id="3cebf-124">Para obtener más información acerca de la autorización de recepción, consulte [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3cebf-124">For more information about receive authorization, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cebf-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cebf-125">See Also</span></span>  
 <span data-ttu-id="3cebf-126">[Autenticación de mensajes entrantes](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="3cebf-126">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="3cebf-127">[Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="3cebf-127">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="3cebf-128">[Protección de mensajes salientes](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="3cebf-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="3cebf-129">[Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="3cebf-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="3cebf-130">Planear la seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="3cebf-130">Planning Message Security</span></span>](../core/planning-message-security.md)