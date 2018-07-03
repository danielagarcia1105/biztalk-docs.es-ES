---
title: Cómo instalar los certificados para mensajes cifrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e11fdb81-041c-4ba6-849d-d511ead0e8be
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24cd9c34fef3c7d984874cc72da13030b167d0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994101"
---
# <a name="how-to-install-the-certificates-for-encrypted-messages"></a><span data-ttu-id="a327a-102">Cómo instalar los certificados para mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="a327a-102">How to Install the Certificates for Encrypted Messages</span></span>
<span data-ttu-id="a327a-103">En el siguiente procedimiento se enumeran los pasos de nivel superior que debe seguir para instalar los certificados que le permitirán recibir y enviar mensajes cifrados.</span><span class="sxs-lookup"><span data-stu-id="a327a-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending encrypted messages.</span></span>  
  
-   <span data-ttu-id="a327a-104">Para instalar certificados en el almacén de certificados para descifrado</span><span class="sxs-lookup"><span data-stu-id="a327a-104">To install certificates in the certificates store for decryption</span></span>  
  
-   <span data-ttu-id="a327a-105">Para instalar certificados en el almacén de certificados para cifrado</span><span class="sxs-lookup"><span data-stu-id="a327a-105">To install certificates in the certificates store for encryption</span></span>  
  
-   <span data-ttu-id="a327a-106">Para configurar hosts de BizTalk para la recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="a327a-106">To configure BizTalk hosts for receiving encrypted messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a327a-107">Puede usar un mismo certificado para las operaciones de firma y descifrado, o bien usar un certificado para cada función.</span><span class="sxs-lookup"><span data-stu-id="a327a-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
  
### <a name="to-install-the-decryption-certificates-in-the-certificates-store"></a><span data-ttu-id="a327a-108">Para instalar los certificados de descifrado en el almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="a327a-108">To install the decryption certificates in the certificates store</span></span>  
  
1. <span data-ttu-id="a327a-109">Un administrador de su organización solicita un par de claves pública y privada para cifrado a la entidad emisora de certificados (CA) para su uso por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a327a-109">An administrator in your organization requests a private-public key pair for encryption from the certification authority (CA) for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2. <span data-ttu-id="a327a-110">El administrador envía la clave pública para el cifrado al socio comercial A.</span><span class="sxs-lookup"><span data-stu-id="a327a-110">The administrator sends the public key for encryption to Partner A.</span></span>  
  
3. <span data-ttu-id="a327a-111">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como la cuenta de servicio de la instancia de host que está ejecutando el controlador que recibirá mensajes del socio comercial A. Instale el certificado de clave privada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el descifrado de mensajes en el almacén personal de la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="a327a-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as the service account for the host instance running the handler that will receive messages from Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for decrypting messages in the personal store for the service account.</span></span> <span data-ttu-id="a327a-112">En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.</span><span class="sxs-lookup"><span data-stu-id="a327a-112">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="a327a-113">![Los certificados necesarios para recibir mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="a327a-113">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4. <span data-ttu-id="a327a-114">En el socio comercial A, instale el certificado de clave pública de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el cifrado de mensajes enviados al socio comercial A en el almacén adecuado.</span><span class="sxs-lookup"><span data-stu-id="a327a-114">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for encrypting messages sent to Partner A in the appropriate store.</span></span> <span data-ttu-id="a327a-115">(Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave pública en el almacén de otras personas.)</span><span class="sxs-lookup"><span data-stu-id="a327a-115">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other People store.)</span></span>  
  
### <a name="to-install-the-encryption-certificates-in-the-certificates-store"></a><span data-ttu-id="a327a-116">Para instalar los certificados de cifrado en el almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="a327a-116">To install the encryption certificates in the certificates store</span></span>  
  
1. <span data-ttu-id="a327a-117">El socio comercial A solicita un par de claves pública y privada para cifrado a la entidad emisora de certificados (CA).</span><span class="sxs-lookup"><span data-stu-id="a327a-117">Partner A requests a private-public key pair for encryption from the CA.</span></span>  
  
2. <span data-ttu-id="a327a-118">El socio comercial A instala el certificado de clave privada para el descifrado de los mensajes en el almacén correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a327a-118">Partner A installs the private key certificate for decrypting the messages in the appropriate store.</span></span> <span data-ttu-id="a327a-119">(Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave privada en el almacén de certificados personales.)</span><span class="sxs-lookup"><span data-stu-id="a327a-119">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal certificate store.)</span></span>  
  
3. <span data-ttu-id="a327a-120">El socio comercial A le envía su clave pública para el cifrado de los mensajes enviados a él.</span><span class="sxs-lookup"><span data-stu-id="a327a-120">Partner A sends you its public key for encrypting messages sent to Partner A.</span></span>  
  
4. <span data-ttu-id="a327a-121">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que enviará mensajes al socio comercial A. Instale el certificado de clave pública del socio comercial A para el cifrado de los mensajes enviados a éste en el almacén Otras personas.</span><span class="sxs-lookup"><span data-stu-id="a327a-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will send messages to Partner A. Install the Partner A public key certificate for encrypting messages sent to Partner A in the Other People store.</span></span> <span data-ttu-id="a327a-122">En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.</span><span class="sxs-lookup"><span data-stu-id="a327a-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="a327a-123">![Los certificados necesarios para enviar mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="a327a-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
### <a name="to-configure-biztalk-hosts-for-receiving-encrypted-messages"></a><span data-ttu-id="a327a-124">Para configurar hosts de BizTalk para la recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="a327a-124">To configure BizTalk hosts for receiving encrypted messages</span></span>  
  
1. <span data-ttu-id="a327a-125">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a327a-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a327a-126">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **configuración de plataforma**, expanda **Hosts**.</span><span class="sxs-lookup"><span data-stu-id="a327a-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Platform Settings**, expand **Hosts**.</span></span>  
  
   1.  <span data-ttu-id="a327a-127">En el panel derecho, haga clic en un host de BizTalk es el controlador para recibir los mensajes cifrados y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a327a-127">On the right pane, right-click a BizTalk host that is the handler for receiving the encrypted messages, and then click **Properties**.</span></span>  
  
   2.  <span data-ttu-id="a327a-128">En el **propiedades de Host** cuadro de diálogo, haga clic en **certificado**, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="a327a-128">On the **Host Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
   3.  <span data-ttu-id="a327a-129">En el **Seleccionar certificado** cuadro de diálogo, seleccione el certificado de descifrado que instaló y, a continuación, cierre todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a327a-129">On the **Select Certificate** dialog box, select the decryption certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="a327a-130">Para obtener más información, consulte [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a327a-130">For more information, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a327a-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a327a-131">Next Steps</span></span>  
 <span data-ttu-id="a327a-132">Crear una canalización para recibir mensajes cifrados, consulte [cómo configurar BizTalk Server para recibir mensajes cifrados](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="a327a-132">You create a pipeline to receive encrypted messages in [How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)</span></span>  
  
 <span data-ttu-id="a327a-133">Crear una canalización para enviar mensajes cifrados [cómo configurar BizTalk Server para enviar mensajes cifrados](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="a327a-133">You create a pipeline to send encrypted messages in [How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a327a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a327a-134">See Also</span></span>  
 <span data-ttu-id="a327a-135">[Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a327a-135">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="a327a-136">Envío y recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="a327a-136">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)