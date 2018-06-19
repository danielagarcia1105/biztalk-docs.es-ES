---
title: Planear la seguridad de mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826db8480d378342ee30993f67bbd60e27751d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264292"
---
# <a name="planning-message-security"></a><span data-ttu-id="a5a4b-102">Planear la seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="a5a4b-102">Planning Message Security</span></span>
<span data-ttu-id="a5a4b-103">Dependiendo de las directivas de seguridad de su empresa, puede serle útil considerar las preguntas de la tabla siguiente para determinar el nivel de seguridad que debe implementar en su entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a5a4b-103">Based on the security policies in your company, you may want to consider the questions in the following table to determine the level of security that you must implement in your BizTalk Server environment.</span></span> <span data-ttu-id="a5a4b-104">Las respuestas a estas preguntas determinarán las características de seguridad que necesita para la mensajería.</span><span class="sxs-lookup"><span data-stu-id="a5a4b-104">The answers to these questions will determine the security features that you need for messaging.</span></span>  
  
|<span data-ttu-id="a5a4b-105">Pregunta</span><span class="sxs-lookup"><span data-stu-id="a5a4b-105">Question</span></span>|<span data-ttu-id="a5a4b-106">Característica de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a5a4b-106">BizTalk Server Security Feature</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="a5a4b-107">**Al recibir un mensaje:**</span><span class="sxs-lookup"><span data-stu-id="a5a4b-107">**When receiving a message:**</span></span>||  
|<span data-ttu-id="a5a4b-108">¿Cómo determina la identidad del remitente del mensaje?</span><span class="sxs-lookup"><span data-stu-id="a5a4b-108">How do you determine the identity of the sender of the message?</span></span>|<span data-ttu-id="a5a4b-109">Puede identificar con certeza al remitente de un mensaje mediante el componente de resolución de entidades de la canalización de BizTalk y el certificado de firma, o el Id. de seguridad de Windows (SID).</span><span class="sxs-lookup"><span data-stu-id="a5a4b-109">You can use the party resolution component in the BizTalk pipeline and the signing certificate or Windows Security ID (SID) to identify the sender of a message positively.</span></span> <span data-ttu-id="a5a4b-110">Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a5a4b-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="a5a4b-111">¿Sabe qué entidad le envió el mensaje?</span><span class="sxs-lookup"><span data-stu-id="a5a4b-111">Do you know the party that sent you the message?</span></span>|<span data-ttu-id="a5a4b-112">Puede determinar si la entidad que le envió el mensaje ya es un socio comercial de su sistema mediante el componente de resolución de entidades de la canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a5a4b-112">You can use the party resolution component in the BizTalk pipeline to determine whether the party that sent you the message is a trading partner already in your system.</span></span> <span data-ttu-id="a5a4b-113">Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a5a4b-113">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="a5a4b-114">¿Desea no recibir mensajes de entidades que no conoce?</span><span class="sxs-lookup"><span data-stu-id="a5a4b-114">Do you want to avoid receiving messages from parties you do not know?</span></span>|<span data-ttu-id="a5a4b-115">Puede usar la función de autenticación necesaria en el puerto para requerir que BizTalk Server sólo procese los mensajes de entidades conocidas.</span><span class="sxs-lookup"><span data-stu-id="a5a4b-115">You can use the authentication required feature in the port to require that BizTalk server processes only the messages from parties that you know.</span></span> <span data-ttu-id="a5a4b-116">Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a5a4b-116">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="a5a4b-117">**Al enviar un mensaje:**</span><span class="sxs-lookup"><span data-stu-id="a5a4b-117">**When sending a message:**</span></span>||  
|<span data-ttu-id="a5a4b-118">¿Cómo garantiza la privacidad de los mensajes salientes?</span><span class="sxs-lookup"><span data-stu-id="a5a4b-118">How do you ensure the privacy of outgoing messages?</span></span>|<span data-ttu-id="a5a4b-119">Puede cifrar el mensaje para asegurarse de que sólo lo pueda leer la entidad deseada.</span><span class="sxs-lookup"><span data-stu-id="a5a4b-119">You can encrypt the message to ensure that only the intended party can read the message.</span></span> <span data-ttu-id="a5a4b-120">Para obtener más información, consulte [protección de mensaje saliente](../core/outbound-message-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a5a4b-120">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
|<span data-ttu-id="a5a4b-121">¿Cómo impide que usuarios malintencionados manipulen el mensaje durante la transmisión?</span><span class="sxs-lookup"><span data-stu-id="a5a4b-121">How do you prevent malicious users from tampering with the message during transmission?</span></span>|<span data-ttu-id="a5a4b-122">Puede utilizar firmas digitales para garantizar la integridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a5a4b-122">You can use digital signatures to ensure the integrity of the message.</span></span> <span data-ttu-id="a5a4b-123">Para obtener más información, consulte [protección de mensaje saliente](../core/outbound-message-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a5a4b-123">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="a5a4b-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a5a4b-124">In This Section</span></span>  
  
-   [<span data-ttu-id="a5a4b-125">Seguridad para enviar y recibir mensajes</span><span class="sxs-lookup"><span data-stu-id="a5a4b-125">Security for Sending and Receiving Messages</span></span>](../core/security-for-sending-and-receiving-messages.md)  
  
-   [<span data-ttu-id="a5a4b-126">Cifrado y certificados de firma</span><span class="sxs-lookup"><span data-stu-id="a5a4b-126">Encryption and Signing Certificates</span></span>](../core/encryption-and-signing-certificates.md)  
  
-   [<span data-ttu-id="a5a4b-127">Autenticación del remitente de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a5a4b-127">Authenticating the Sender of a Message</span></span>](../core/authenticating-the-sender-of-a-message.md)  
  
-   [<span data-ttu-id="a5a4b-128">Autorización del receptor de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a5a4b-128">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)