---
title: Cómo instalar los certificados para firmas digitales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b924cbd0ddbbeada7e70dd178c979cb53872124e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000117"
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a><span data-ttu-id="cbed5-102">Cómo instalar los certificados para firmas digitales</span><span class="sxs-lookup"><span data-stu-id="cbed5-102">How to install the Certificates for Digital Signatures</span></span>
<span data-ttu-id="cbed5-103">En el siguiente procedimiento se enumeran los pasos de nivel superior que debe seguir para instalar los certificados que le permitirán recibir y enviar mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="cbed5-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending signed messages.</span></span>  
  
-   <span data-ttu-id="cbed5-104">Para instalar los certificados en el almacén de certificados y que reciban mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="cbed5-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="cbed5-105">Para instalar los certificados de firma para el envío de mensajes firmados al almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="cbed5-105">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
-   <span data-ttu-id="cbed5-106">Para configurar el grupo de BizTalk para el envío de mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="cbed5-106">To configure the BizTalk Group for sending signed messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbed5-107">Puede usar un mismo certificado para las operaciones de firma y descifrado, o bien usar un certificado para cada función.</span><span class="sxs-lookup"><span data-stu-id="cbed5-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="cbed5-108">Únicamente puede especificar un certificado de firma con el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] firma todos los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="cbed5-108">You can only specify one signing certificate with which [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] signs all outbound messages.</span></span> <span data-ttu-id="cbed5-109">En otras palabras, no puede usar diferentes certificados de firma en función de a quién le envíe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cbed5-109">In other words, you cannot use different signing certificates depending on who you are sending the message to.</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="cbed5-110">Para instalar los certificados en el almacén de certificados y que reciban mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="cbed5-110">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1. <span data-ttu-id="cbed5-111">El socio comercial A solicita un par de claves pública y privada para las firmas digitales de la entidad emisora de certificados (CA).</span><span class="sxs-lookup"><span data-stu-id="cbed5-111">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2. <span data-ttu-id="cbed5-112">El socio comercial A le envía la clave pública para las firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="cbed5-112">Partner A sends you its public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="cbed5-113">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión en el servidor que tiene una instancia de host que ejecuta un controlador que recibirá mensajes del socio comercial A. Instale el certificado de clave pública del socio comercial A para comprobar la firma en el almacén Otras personas.</span><span class="sxs-lookup"><span data-stu-id="cbed5-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="cbed5-114">En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.</span><span class="sxs-lookup"><span data-stu-id="cbed5-114">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="cbed5-115">![Los certificados necesarios para recibir mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="cbed5-115">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4. <span data-ttu-id="cbed5-116">En el socio comercial A, instale el certificado de clave privada del socio comercial A para firmar los mensajes en el almacén adecuado.</span><span class="sxs-lookup"><span data-stu-id="cbed5-116">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="cbed5-117">(Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave privada en el almacén personal para la cuenta que firmará los mensajes enviados a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="cbed5-117">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a><span data-ttu-id="cbed5-118">Para instalar los certificados de firma para el envío de mensajes firmados al almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="cbed5-118">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
1. <span data-ttu-id="cbed5-119">Un administrador de su organización solicita un par de claves pública y privada para firmas digitales a la CA para que las use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbed5-119">An administrator in your organization requests a private-public key pair for digital signatures from the CA for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2. <span data-ttu-id="cbed5-120">El administrador envía al socio comercial A (y al resto de socios comerciales) la clave pública para firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="cbed5-120">The administrator sends Partner A (and all other partners) the public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="cbed5-121">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], inicie sesión como cuenta de servicio de la instancia de host que está ejecutando el controlador que enviará mensajes al socio comercial A. Instale el certificado de clave privada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para firmar mensajes en el almacén personal de la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="cbed5-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as service account for the host instance running the handler that will send messages to Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for signing messages in the personal store for the service account.</span></span> <span data-ttu-id="cbed5-122">En la siguiente ilustración, se muestra el almacén de certificados donde se instala el certificado.</span><span class="sxs-lookup"><span data-stu-id="cbed5-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="cbed5-123">![Los certificados necesarios para enviar mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="cbed5-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
4. <span data-ttu-id="cbed5-124">En el socio comercial A, instale el certificado de clave pública de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para comprobar la firma digital del almacén adecuado.</span><span class="sxs-lookup"><span data-stu-id="cbed5-124">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for verifying its digital signature in the appropriate store.</span></span> <span data-ttu-id="cbed5-125">(Si el socio comercial A usa [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale la clave pública en el almacén de Otras personas.)</span><span class="sxs-lookup"><span data-stu-id="cbed5-125">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other people store.)</span></span>  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a><span data-ttu-id="cbed5-126">Para configurar el grupo de BizTalk para el envío de mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="cbed5-126">To configure the BizTalk Group for sending signed messages</span></span>  
  
1. <span data-ttu-id="cbed5-127">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="cbed5-127">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cbed5-128">Haga clic en **grupo de BizTalk**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cbed5-128">Right-click **BizTalk Group**, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="cbed5-129">En el **propiedades del grupo** cuadro de diálogo, haga clic en **certificado**, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="cbed5-129">On the **Group Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
4. <span data-ttu-id="cbed5-130">En el **Seleccionar certificado** cuadro de diálogo, seleccione el certificado de firma que instaló y, a continuación, cierre todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cbed5-130">On the **Select Certificate** dialog box, select the signing certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cbed5-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cbed5-131">Next Steps</span></span>  
 <span data-ttu-id="cbed5-132">Crear una canalización para recibir mensajes firmados en [cómo configurar BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="cbed5-132">You create a pipeline to receive signed messages in [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>  
  
 <span data-ttu-id="cbed5-133">Crear una canalización para enviar mensajes firmados [cómo configurar BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="cbed5-133">You create a pipeline to send signed messages in [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbed5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbed5-134">See Also</span></span>  
 <span data-ttu-id="cbed5-135">[Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="cbed5-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="cbed5-136">Envío y recepción de mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="cbed5-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)