---
title: Autorización del receptor de un mensaje | Microsoft Docs
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
ms.openlocfilehash: 612aa7cfca75e34248a094113258fc3c261ef14e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997237"
---
# <a name="authorizing-the-receiver-of-a-message"></a><span data-ttu-id="0fb81-102">Autorización del receptor de un mensaje</span><span class="sxs-lookup"><span data-stu-id="0fb81-102">Authorizing the Receiver of a Message</span></span>
<span data-ttu-id="0fb81-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite limitar los procesos y las entidades que autoriza a recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="0fb81-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to limit the processes and parties that you authorize to receive messages.</span></span>  
  
 <span data-ttu-id="0fb81-104">La siguiente ilustración muestra las características de seguridad de BizTalk Server que usará para autorizar al receptor de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-104">The following figure shows the security features in BizTalk Server that you use to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="0fb81-105">![Características de seguridad de autorización del receptor de mensaje](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span><span class="sxs-lookup"><span data-stu-id="0fb81-105">![Security features authorizing the message receiver](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span></span>  
<span data-ttu-id="0fb81-106">Características de seguridad usadas por BizTalk Server para autorizar al receptor de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-106">Security features BizTalk Server uses to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="0fb81-107">Puede utilizar los siguientes mecanismos de seguridad para establecer quién tiene permiso (autorización) para recibir los mensajes enviados por usted:</span><span class="sxs-lookup"><span data-stu-id="0fb81-107">You can use the following security mechanisms to establish who has permission (authorization) to receive the messages that you send:</span></span>  
  
-   <span data-ttu-id="0fb81-108">**Descifrado.**</span><span class="sxs-lookup"><span data-stu-id="0fb81-108">**Decryption.**</span></span> <span data-ttu-id="0fb81-109">Asegúrese de que las entidades que envían mensajes a BizTalk Server tienen el certificado de clave pública para cifrar esos mensajes.</span><span class="sxs-lookup"><span data-stu-id="0fb81-109">Make sure the parties that send messages to BizTalk Server have the public key certificate for encrypting messages they send to BizTalk Server.</span></span> <span data-ttu-id="0fb81-110">BizTalk Server utiliza el certificado de clave privada para descifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-110">BizTalk Server uses the private key certificate to decrypt the message.</span></span>  
  
-   <span data-ttu-id="0fb81-111">**Autorización de recepción.**</span><span class="sxs-lookup"><span data-stu-id="0fb81-111">**Receive Authorization.**</span></span> <span data-ttu-id="0fb81-112">Puede utilizar este método para controlar qué hosts del entorno de BizTalk Server pueden recibir un mensaje dado.</span><span class="sxs-lookup"><span data-stu-id="0fb81-112">You can use this method to control which hosts within the BizTalk Server environment can receive a given message.</span></span>  
  
-   <span data-ttu-id="0fb81-113">**Cifrado.**</span><span class="sxs-lookup"><span data-stu-id="0fb81-113">**Encryption.**</span></span> <span data-ttu-id="0fb81-114">Si utiliza el certificado de clave pública de una entidad determinada cuando BizTalk cifra un mensaje, puede asegurarse de que sólo esa entidad pueda leerlo.</span><span class="sxs-lookup"><span data-stu-id="0fb81-114">By using the public key certificate from a given party when BizTalk encrypts a message, you can ensure that only the intended party is able to read the message.</span></span>  
  
## <a name="receive-authorization"></a><span data-ttu-id="0fb81-115">Autorización de recepción</span><span class="sxs-lookup"><span data-stu-id="0fb81-115">Receive Authorization</span></span>  
 <span data-ttu-id="0fb81-116">La autorización de recepción es el método que puede utilizar para controlar los hosts que pueden recibir (suscribirse a) un mensaje específico.</span><span class="sxs-lookup"><span data-stu-id="0fb81-116">Receive authorization is the method you can use to control which hosts can receive (subscribe for) a given message.</span></span> <span data-ttu-id="0fb81-117">BizTalk Server utiliza la información del certificado como una propiedad de suscripción para que coincidan con predicados en el mensaje: la base de datos de cuadro de mensajes sólo enruta los mensajes marcados como de autorización necesaria a los hosts que tienen el certificado de descifrado para ese mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-117">BizTalk Server uses the certificate information as a subscription property to match predicates on the message: the MessageBox database only routes messages marked as authorization required to the hosts that have the decryption certificate for that message.</span></span> <span data-ttu-id="0fb81-118">Para ilustrar el proceso, considere estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="0fb81-118">To illustrate the process, consider the following scenarios:</span></span>  
  
- <span data-ttu-id="0fb81-119">**Enrutamiento de un mensaje sin cifrar:** cuando BizTalk Server recibe un mensaje que no cifró el remitente, no hay ninguna limitación de descifrado sobre cómo BizTalk enrutará el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-119">**Routing an un-encrypted message:** When BizTalk Server receives a message that the sender did not encrypt, there is no decryption limitation as to how BizTalk routes the message.</span></span> <span data-ttu-id="0fb81-120">Cualquier host puede recibirlo, tenga o no certificados de autorización de recepción configurados.</span><span class="sxs-lookup"><span data-stu-id="0fb81-120">Both hosts with and hosts without receive authorization certificates configured can receive the message.</span></span>  
  
- <span data-ttu-id="0fb81-121">**Enrutamiento de un mensaje cifrado:** cuando llega un mensaje cifrado, la canalización de recepción debe contener un componente de descodificación que descifra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-121">**Routing an encrypted message:** When an encrypted message arrives, the receiving pipeline must contain a decoding component that decrypts the message.</span></span> <span data-ttu-id="0fb81-122">Cuando enruta un mensaje tras descifrarlo, BizTalk Server utiliza la huella digital del certificado utilizada para descifrar el mensaje como prueba en el mecanismo de suscripción de la base de datos de cuadro de mensajes, y sólo los hosts configurados con ese certificado reciben el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-122">When BizTalk Server routes a message after it is decrypted, BizTalk uses the certificate thumbprint used to decrypt the message as evidence in the MessageBox database subscription mechanism, and only those hosts configured with that certificate receive the message.</span></span>  
  
  <span data-ttu-id="0fb81-123">Si desea usar la autorización de recepción, debe proporcionar la huella digital del certificado de descifrado en las propiedades del host que desea autorizar a recibir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb81-123">If you want to use receive authorization, you must provide the thumbprint of the decryption certificate in the properties of the host that you want to authorize to receive the message.</span></span> <span data-ttu-id="0fb81-124">Para obtener más información sobre la autorización de recepción, consulte [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0fb81-124">For more information about receive authorization, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb81-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fb81-125">See Also</span></span>  
 <span data-ttu-id="0fb81-126">[Autenticación de mensajes entrantes](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="0fb81-126">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="0fb81-127">[Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="0fb81-127">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="0fb81-128">[Protección de mensajes salientes](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="0fb81-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="0fb81-129">[Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="0fb81-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="0fb81-130">Planificación de la seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="0fb81-130">Planning Message Security</span></span>](../core/planning-message-security.md)