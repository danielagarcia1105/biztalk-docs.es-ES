---
title: Certificados que utiliza BizTalk Server para mensajes cifran | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f2dbd51506da7b505f66b3001b8bdc6fa0a58ac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a><span data-ttu-id="2bbc4-102">Certificados que BizTalk Server usa para los mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="2bbc4-102">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2bbc4-103"> admite mediante clave pública el cifrado de mensajes salientes y el descifrado de mensajes entrantes según las extensiones seguras multipropósito de correo Internet (S/MIME).</span><span class="sxs-lookup"><span data-stu-id="2bbc4-103"> supports public key encryption of outbound messages and decryption of inbound messages based on Secure Multipurpose Internet Mail Extensions (S/MIME).</span></span> <span data-ttu-id="2bbc4-104">BizTalk Server utiliza S/MIME versión 3 para el cifrado de mensajes salientes, y S/MIME versiones 2 y 3 para el descifrado de mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-104">BizTalk Server uses S/MIME version 3 for encryption of outbound messages, and S/MIME versions 2 and 3 for decryption of inbound messages.</span></span>  
  
-   <span data-ttu-id="2bbc4-105">BizTalk Server admite certificados de cifrado RSA y Diffie Hellman.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-105">BizTalk Server supports RSA and Diffie Hellman encryption certificates.</span></span>  
  
-   <span data-ttu-id="2bbc4-106">BizTalk Server admite los algoritmos de cifrado Estándar de cifrado de datos (DES), 3DES y RC2.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-106">BizTalk Server supports Data Encryption Standard (DES), 3DES, and RC2 encryption algorithms.</span></span>  
  
 <span data-ttu-id="2bbc4-107">La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server recibe un mensaje cifrado.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-107">The following figure shows the message flow when BizTalk Server receives an encrypted message.</span></span>  
  
 <span data-ttu-id="2bbc4-108">![Flujo de mensajes al recibir un mensaje cifrado](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="2bbc4-108">![Message flow when receiving an encrypted message](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span></span>  
  
 <span data-ttu-id="2bbc4-109">El flujo de mensajes generado cuando BizTalk Server recibe un mensaje cifrado es como sigue:</span><span class="sxs-lookup"><span data-stu-id="2bbc4-109">The message flow when BizTalk Server receives an encrypted message is as follows:</span></span>  
  
1.  <span data-ttu-id="2bbc4-110">Un socio envía un mensaje a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-110">A partner sends a message to BizTalk Server.</span></span> <span data-ttu-id="2bbc4-111">El socio cifra el mensaje con la clave pública de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-111">The partner encrypts the message with the BizTalk Server public key.</span></span>  
  
2.  <span data-ttu-id="2bbc4-112">El mensaje es recibido por el controlador de recepción correspondiente de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-112">The appropriate BizTalk Server receive handler receives the message.</span></span>  
  
3.  <span data-ttu-id="2bbc4-113">Durante la ejecución de la canalización de recepción, el componente de canalización Descodificador de MIME/SMIME descifra el mensaje mediante la clave privada de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-113">During the receive pipeline execution, the MIME/SMIME Decoder pipeline component decrypts the message by using the BizTalk Server private key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bbc4-114">Para que el descifrado de canalización se complete correctamente en un equipo con IIS 7.0, asegúrese de que la cuenta para el grupo de aplicaciones de IIS y la cuenta utilizada por la instancia de host asociada con el controlador de recepción son los mismos y que esta cuenta es miembro de la \<machineName \>Grupo \IIS_WPG.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-114">For pipeline decryption to succeed on an IIS 7.0 computer, ensure that the account for the IIS application pool and the account used by the host instance associated with the receive handler are the same and that this account is a member of the \<machineName\>\IIS_WPG group.</span></span> <span data-ttu-id="2bbc4-115">Para obtener más información acerca de cómo configurar IIS procesar identidad para IIS 7.0, vea [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md).</span><span class="sxs-lookup"><span data-stu-id="2bbc4-115">For more information on setting IIS process identity for IIS 7.0 see [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md).</span></span> <span data-ttu-id="2bbc4-116">Estos procesos se deben ejecutar en la misma cuenta para comprobar que se carga el perfil de cuenta que, a su vez, carga las claves de registro necesarias para llevar a cabo el descifrado en la canalización.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-116">These processes must run under the same account to ensure that the account profile is loaded which in turns loads the registry keys required to perform decryption in the pipeline.</span></span> <span data-ttu-id="2bbc4-117">Por motivos de rendimiento, IIS 7.0 no carga el perfil de cuenta al iniciar el proceso w3wp.exe asociado, de modo que la instancia de host de BizTalk debe configurarse con la misma cuenta, para que BizTalk cargue el perfil de cuenta y las claves del Registro.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-117">For performance reasons, IIS 7.0 does not load the account profile when starting the associated w3wp.exe process so the BizTalk host instance must be configured with the same account so that BizTalk will load the account profile and registry keys.</span></span>  
  
4.  <span data-ttu-id="2bbc4-118">Se produce un procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-118">Additional processing occurs.</span></span>  
  
 <span data-ttu-id="2bbc4-119">La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server envía un mensaje cifrado.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-119">The following figure shows the message flow when BizTalk Server sends an encrypted message.</span></span>  
  
 <span data-ttu-id="2bbc4-120">![Flujo de mensajes al enviar un mensaje cifrado](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="2bbc4-120">![Message flow when sending an encrypted message](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span></span>  
  
 <span data-ttu-id="2bbc4-121">La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server envía un mensaje cifrado a un socio:</span><span class="sxs-lookup"><span data-stu-id="2bbc4-121">The message flow when BizTalk Server sends an encrypted message to a partner is as follows:</span></span>  
  
1.  <span data-ttu-id="2bbc4-122">El mensaje es enviado al socio por el controlador de envío correspondiente de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-122">The appropriate BizTalk Server send handler sends a message to the partner.</span></span>  
  
2.  <span data-ttu-id="2bbc4-123">Durante la ejecución de la canalización de envío, el componente de canalización Descodificador de MIME/SMIME cifra el mensaje mediante la clave pública del socio.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-123">During the send pipeline execution, the MIME/SMIME Encoder pipeline component encrypts the message by using the partner's public key.</span></span>  
  
3.  <span data-ttu-id="2bbc4-124">El socio recibe el mensaje de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-124">The partner receives the message from BizTalk Server.</span></span> <span data-ttu-id="2bbc4-125">El socio utiliza su clave privada para descifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2bbc4-125">The partner uses its private key to decrypt the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbc4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bbc4-126">See Also</span></span>  
 <span data-ttu-id="2bbc4-127">[Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="2bbc4-127">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="2bbc4-128">[Almacenes de certificados que utiliza BizTalk Server](../core/certificate-stores-that-biztalk-server-uses.md) </span><span class="sxs-lookup"><span data-stu-id="2bbc4-128">[Certificate Stores that BizTalk Server Uses](../core/certificate-stores-that-biztalk-server-uses.md) </span></span>  
 <span data-ttu-id="2bbc4-129">[Cifrado y certificados de firma](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="2bbc4-129">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="2bbc4-130">Envío y recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="2bbc4-130">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)