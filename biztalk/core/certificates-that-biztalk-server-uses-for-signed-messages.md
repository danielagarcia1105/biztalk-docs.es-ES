---
title: Certificados que utiliza BizTalk Server para mensajes firman | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, signed messages
- messages, message flow [digital signatures]
- S/MIME messages
- signed messages
- digital signatures, message flow
- messages, certificates
ms.assetid: 0b521e11-73ef-424f-9e6a-4fb42dc263ff
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce82b634fffac4af0f75cdff26c7f512a132de9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="certificates-that-biztalk-server-uses-for-signed-messages"></a><span data-ttu-id="76fd1-102">Certificados que BizTalk Server usa para mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="76fd1-102">Certificates that BizTalk Server Uses for Signed Messages</span></span>
<span data-ttu-id="76fd1-103">BizTalk Server admite la firma de mensajes de salida y la comprobación de firmas de mensajes de entrada en formato de extensiones seguras multipropósito al correo de Internet (Secure Multipurpose Internet Mail Extensions, S/MIME).</span><span class="sxs-lookup"><span data-stu-id="76fd1-103">BizTalk Server supports signing outbound messages and signature verification for inbound Secure Multipurpose Internet Mail Extensions (S/MIME) messages.</span></span> <span data-ttu-id="76fd1-104">BizTalk Server usa S/MIME versiones 2 y 3 para firmar mensajes de salida y validar la firma de mensajes de entrada.</span><span class="sxs-lookup"><span data-stu-id="76fd1-104">BizTalk Server uses S/MIME versions 2 and 3 to sign outbound messages and to validate the signature of inbound messages.</span></span> <span data-ttu-id="76fd1-105">De forma parecida, se puede configurar BizTalk Server para que firme y a continuación cifre los mensajes que envía a sus socios.</span><span class="sxs-lookup"><span data-stu-id="76fd1-105">Similarly, you can configure BizTalk Server to sign and then encrypt the messages it sends to its partners.</span></span>  
  
-   <span data-ttu-id="76fd1-106">BizTalk Server admite los algoritmos de firma SHA-1 y MD5 para la comprobación de firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="76fd1-106">BizTalk Server supports the SHA-1 and MD5 signing algorithms for verifying digital signatures.</span></span> <span data-ttu-id="76fd1-107">BizTalk Server usa el algoritmo de firma SHA-1 para firmar mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="76fd1-107">BizTalk Server uses the SHA-1 signing algorithm to sign outbound messages.</span></span>  
  
-   <span data-ttu-id="76fd1-108">Los sistemas de intercambio de claves admitidos por BizTalk Server para claves de firma son los algoritmos Rivest-Shamir-Adleman (RSA) y el Estándar de firma digital (Digital Signature Standard, DSS).</span><span class="sxs-lookup"><span data-stu-id="76fd1-108">The key exchange systems supported by BizTalk Server for signature keys are the Rivest-Shamir-Adleman (RSA) algorithms and the Digital Signature Standard (DSS).</span></span> <span data-ttu-id="76fd1-109">BizTalk Server no admite el sistema de intercambio Estándar de cifrado avanzado (Advanced Encryption Standard, AES) para claves de firma.</span><span class="sxs-lookup"><span data-stu-id="76fd1-109">BizTalk Server does not support the Advanced Encryption Standard (AES) exchange system for signature keys.</span></span>  
  
-   <span data-ttu-id="76fd1-110">El certificado de firma admitido por BizTalk Server es x.509 versión 3.</span><span class="sxs-lookup"><span data-stu-id="76fd1-110">The signing certificate supported by BizTalk Server is x.509 version 3.</span></span>  
  
 <span data-ttu-id="76fd1-111">La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server recibe un mensaje firmado digitalmente y, opcionalmente, usa la firma para resolver la identidad del socio como una entidad del entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="76fd1-111">The following figure shows the message flow when BizTalk Server receives a digitally signed message and optionally uses the signature to resolve the partner identity to a party in the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="76fd1-112">![Flujo de mensajes al enviar un mensaje firmado](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")</span><span class="sxs-lookup"><span data-stu-id="76fd1-112">![Message flow when sending a signed message](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")</span></span>  
  
 <span data-ttu-id="76fd1-113">Este es el flujo de mensajes generado cuando BizTalk Server recibe un mensaje firmado digitalmente:</span><span class="sxs-lookup"><span data-stu-id="76fd1-113">The message flow when BizTalk Server receives a digitally signed message is as follows:</span></span>  
  
1.  <span data-ttu-id="76fd1-114">Un socio envía un mensaje a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="76fd1-114">A partner sends a message to BizTalk Server.</span></span> <span data-ttu-id="76fd1-115">El socio firma el mensaje con su certificado de clave privada.</span><span class="sxs-lookup"><span data-stu-id="76fd1-115">The partner signs the message with its private key certificate.</span></span>  
  
2.  <span data-ttu-id="76fd1-116">El mensaje es recibido por el controlador de recepción correspondiente de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="76fd1-116">The appropriate BizTalk Server receive handler receives the message.</span></span>  
  
3.  <span data-ttu-id="76fd1-117">Durante la ejecución de la canalización de recepción, el componente de canalización Descodificador de MIME/SMIME comprueba la firma digital mediante la clave pública del socio.</span><span class="sxs-lookup"><span data-stu-id="76fd1-117">During the execution of the receive pipeline, the MIME/SMIME Decoder pipeline component verifies the digital signature by using the partner's public key.</span></span>  
  
4.  <span data-ttu-id="76fd1-118">Si el componente de resolución de entidades está configurado, se usa el certificado de clave pública del socio para identificar la entidad en el sistema de BizTalk Server durante la ejecución del componente de resolución de entidades de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="76fd1-118">If party resolution component is configured, the partner's public key certificate is used to identify the party in the BizTalk Server system during the execution of the receive pipeline party resolution component.</span></span>  
  
5.  <span data-ttu-id="76fd1-119">Se produce un procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="76fd1-119">Additional processing occurs.</span></span>  
  
 <span data-ttu-id="76fd1-120">La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server envía un mensaje firmado digitalmente.</span><span class="sxs-lookup"><span data-stu-id="76fd1-120">The following figure shows the message flow when BizTalk Server sends a digitally signed message.</span></span>  
  
 ![](../core/media/bts-bpi-sp-msgsec-outboundsigning-r2c.gif "bts_BPI_SP_MSGSEC_OutboundSigning_R2c")  
  
 <span data-ttu-id="76fd1-121">Este es el flujo de mensajes generado cuando BizTalk Server envía un mensaje firmado digitalmente a un socio:</span><span class="sxs-lookup"><span data-stu-id="76fd1-121">The message flow when BizTalk Server sends a digitally signed message to a partner is as follows:</span></span>  
  
1.  <span data-ttu-id="76fd1-122">El mensaje es enviado al socio por el controlador de envío correspondiente de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="76fd1-122">The appropriate BizTalk Server send handler sends a message to the partner.</span></span>  
  
2.  <span data-ttu-id="76fd1-123">Durante la ejecución de la canalización de envío el componente de canalización Descodificador de MIME/SMIME comprueba la firma digital mediante la clave pública del socio.</span><span class="sxs-lookup"><span data-stu-id="76fd1-123">During the execution of the send pipeline, the MIME/SMIME Encoder pipeline component signs the message by using the BizTalk Server private key.</span></span>  
  
3.  <span data-ttu-id="76fd1-124">El socio recibe el mensaje de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="76fd1-124">The partner receives the message from BizTalk Server.</span></span> <span data-ttu-id="76fd1-125">El socio usa la clave pública de BizTalk Server para comprobar la firma digital.</span><span class="sxs-lookup"><span data-stu-id="76fd1-125">The partner uses the BizTalk Server public key to verify the digital signature.</span></span>  
  
 <span data-ttu-id="76fd1-126">Para comprobar la validez de los certificados asociados con los mensajes firmados de entrada, BizTalk Server valida la cadena de confianza de la entidad de certificación para el certificado en cuestión y comprueba que éste no ha expirado</span><span class="sxs-lookup"><span data-stu-id="76fd1-126">BizTalk Server verifies the validity of the certificates associated with the incoming signed messages by validating the certification authority (CA) trust chain for the certificate and by verifying that the certificate has not expired.</span></span> <span data-ttu-id="76fd1-127">El proceso de validación de la cadena de confianza de la entidad de certificación conlleva recorrer dicha cadena hasta alcanzar una entidad de certificación raíz.</span><span class="sxs-lookup"><span data-stu-id="76fd1-127">The process of validating the CA trust chain involves traversing the chain of trust on certificates until a root certification authority is reached.</span></span> <span data-ttu-id="76fd1-128">De esta forma, se valida que el certificado usado para firmar un mensaje procede realmente de la entidad identificada.</span><span class="sxs-lookup"><span data-stu-id="76fd1-128">This validates that the certificate used to sign a message is indeed from the identified party.</span></span> <span data-ttu-id="76fd1-129">Esta validación se produce en tiempo de ejecución para cada uno de los mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="76fd1-129">This validation occurs at runtime for each and every signed message.</span></span>  
  
 <span data-ttu-id="76fd1-130">Además, BizTalk Server puede comprobar que la entidad de certificación no ha revocado el certificado usado para firmar o cifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="76fd1-130">In addition, BizTalk Server can verify that the certification authority has not revoked the certificate used to sign or encrypt the message.</span></span> <span data-ttu-id="76fd1-131">Para ello, debe descargar la lista de revocación de certificados (CRL) desde la entidad de certificación e instalarla mediante el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="76fd1-131">To do this, you must download the certificate revocation list (CRL) from the certification authority and install it using Windows Explorer.</span></span> <span data-ttu-id="76fd1-132">Para obtener más información sobre cómo validar un certificado, consulte [cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="76fd1-132">For more information about how to validate a certificate, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76fd1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="76fd1-133">See Also</span></span>  
 <span data-ttu-id="76fd1-134">[Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="76fd1-134">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="76fd1-135">[Almacenes de certificados que utiliza BizTalk Server](../core/certificate-stores-that-biztalk-server-uses.md) </span><span class="sxs-lookup"><span data-stu-id="76fd1-135">[Certificate Stores that BizTalk Server Uses](../core/certificate-stores-that-biztalk-server-uses.md) </span></span>  
 <span data-ttu-id="76fd1-136">[Cifrado y certificados de firma](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="76fd1-136">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="76fd1-137">Enviar y recibir mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="76fd1-137">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)