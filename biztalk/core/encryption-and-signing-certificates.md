---
title: Cifrado y certificados de firma | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, security
- security, certificates
- security, messages
- certificates, encryption
- encryption certificates, messages
- messages, encryption
- messages, certificates
- security, encryption
ms.assetid: 3c3f9de5-4156-4133-8d5e-c30b142b6d61
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633484a6c5599b9323bfd7798f621b27a501ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241692"
---
# <a name="encryption-and-signing-certificates"></a><span data-ttu-id="f4243-102">Cifrado y certificados de firma</span><span class="sxs-lookup"><span data-stu-id="f4243-102">Encryption and Signing Certificates</span></span>
<span data-ttu-id="f4243-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se apoya en gran medida en la seguridad que ofrecen los certificados.</span><span class="sxs-lookup"><span data-stu-id="f4243-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] relies heavily on the security provided by certificates.</span></span> <span data-ttu-id="f4243-104">BizTalk Server usa certificados para el cifrado y la aplicación de firmas digitales, lo que le permite enviar y recibir datos fiables y garantizar que los datos procesados sean seguros.</span><span class="sxs-lookup"><span data-stu-id="f4243-104">By using certificates for encryption and digital signatures, BizTalk Server can send and receive data that can be trusted, and can help ensure that the data it processes is secure.</span></span> <span data-ttu-id="f4243-105">Tanto el cifrado como las firmas digitales utilizan un certificado de clave pública y un certificado de clave privada.</span><span class="sxs-lookup"><span data-stu-id="f4243-105">For both encryption and digital signatures, there is a public key certificate and a private key certificate.</span></span> <span data-ttu-id="f4243-106">En el caso del cifrado, el remitente del mensaje utiliza el certificado de clave pública del receptor para cifrar el mensaje, mientras que el receptor del mensaje (BizTalk Server) utiliza su clave privada para descifrarlo.</span><span class="sxs-lookup"><span data-stu-id="f4243-106">For encryption, the sender of the message uses the receiver's public key certificate to encrypt the message, while the receiver of the message (BizTalk Server) uses its private key to decrypt the message.</span></span> <span data-ttu-id="f4243-107">En el caso de las firmas digitales, el remitente del mensaje utiliza un certificado de clave privada para firmar el mensaje y el receptor del mensaje (BizTalk Server) utiliza el certificado de clave pública del remitente para comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="f4243-107">For digital signatures, the sender of the message uses a private key certificate to sign the message, and the receiver of the message (BizTalk Server) uses the public key certificate of the sender to verify the signature.</span></span>  
  
 <span data-ttu-id="f4243-108">BizTalk Server usa certificados de clave pública para comprobar las firmas digitales de los mensajes entrantes y para cifrar los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="f4243-108">BizTalk Server uses public key certificates to verify the digital signatures of inbound messages and for encrypting outbound messages.</span></span> <span data-ttu-id="f4243-109">BizTalk Server usa certificados de clave privada para descifrar los mensajes entrantes y para firmar los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="f4243-109">BizTalk Server uses private key certificates for decrypting inbound messages and signing outbound messages.</span></span>  
  
 <span data-ttu-id="f4243-110">El usuario configura los certificados que BizTalk Server usa en el Explorador de BizTalk y en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f4243-110">You configure the certificates BizTalk Server uses in BizTalk Explorer and in the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="f4243-111">Para obtener más información acerca de los certificados digitales, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508).</span><span class="sxs-lookup"><span data-stu-id="f4243-111">For more information about digital certificates, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4243-112">Mientras procesa mensajes de Extensiones seguras multipropósito de correo Internet (S/MIME), puede hacer que el motor de BizTalk Server compruebe la lista de revocación de certificados (CRL) para garantizar que un certificado no haya caducado y que se haya trazado su fiabilidad hasta una entidad emisora de certificados raíz.</span><span class="sxs-lookup"><span data-stu-id="f4243-112">While processing Secure Multipurpose Internet Mail Extensions (S/MIME) messages, you can choose to have the BizTalk Server engine check the Certificate Revocation List (CRL) to ensure that a certificate has not expired and that it is trusted down to a Root Certificate Authority (CA).</span></span> <span data-ttu-id="f4243-113">Esta comprobación se realiza en el componente descodificador de MIME/SMIME mientras la canalización procesa el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f4243-113">This verification occurs while the pipeline processes the message, in the MIME/SMIME decoder component.</span></span> <span data-ttu-id="f4243-114">Para obtener más información sobre cómo establecer **Comprobar lista de revocaciones** propiedad, vea [cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="f4243-114">For more information about how to set **Check Revocation List** property, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4243-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f4243-115">In This Section</span></span>  
  
-   [<span data-ttu-id="f4243-116">Almacenes de certificados que utiliza BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f4243-116">Certificate Stores that BizTalk Server Uses</span></span>](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [<span data-ttu-id="f4243-117">Certificados que utiliza BizTalk Server para mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="f4243-117">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [<span data-ttu-id="f4243-118">Certificados que utiliza BizTalk Server para los mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="f4243-118">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)