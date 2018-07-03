---
title: Cómo configurar BizTalk Server para recibir mensajes cifrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e7e4c-f80c-468e-aa86-7c18406feead
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765c47755e0d170473d92e755eba11e10a4dc3d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023578"
---
# <a name="how-to-configure-biztalk-server-for-receiving-encrypted-messages"></a><span data-ttu-id="9b9b6-102">Cómo configurar BizTalk Server para la recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="9b9b6-102">How to Configure BizTalk Server for Receiving Encrypted Messages</span></span>
<span data-ttu-id="9b9b6-103">En el siguiente procedimiento se enumeran los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted messages.</span></span>  
  
-   <span data-ttu-id="9b9b6-104">Para crear una canalización para recibir mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="9b9b6-104">To create a pipeline to receive encrypted messages</span></span>  
  
-   <span data-ttu-id="9b9b6-105">Para configurar la ubicación de recepción para recibir mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="9b9b6-105">To configure the receive location for receiving encrypted messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9b9b6-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9b9b6-106">Prerequisites</span></span>  
 <span data-ttu-id="9b9b6-107">Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para recibir mensajes cifrados, debe realizar los pasos descritos en [cómo instalar los certificados para mensajes cifrados](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for receiving encrypted messages, you must perform the steps in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-receive-encrypted-messages"></a><span data-ttu-id="9b9b6-108">Para crear una canalización para recibir mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="9b9b6-108">To create a pipeline to receive encrypted messages</span></span>  
  
1. <span data-ttu-id="9b9b6-109">En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="9b9b6-110">En el **archivo** menú, haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-110">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="9b9b6-111">En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de recepción** plantilla.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="9b9b6-112">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="9b9b6-113">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-113">Click **Add**.</span></span>  
  
        <span data-ttu-id="9b9b6-114">La nueva canalización aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="9b9b6-115">Arrastre el componente de canalización de descodificador de MIME/SMIME a la fase de descodificación de una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-115">Drag the MIME/SMIME Decoder pipeline component into the Decode stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="9b9b6-116">![MIME&#47;componente de canalización de descodificador de SMIME](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="9b9b6-116">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
   -   <span data-ttu-id="9b9b6-117">Configurar las propiedades del componente de canalización de descodificador de MIME/SMIME en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-117">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="9b9b6-118">Para obtener más información sobre el descodificador MIME/SMIME, vea [cómo configurar el componente de canalización de descodificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-118">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9b9b6-119">Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b9b6-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="9b9b6-120">Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="9b9b6-121">Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para una ubicación de recepción](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-121">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="9b9b6-122">El componente de canalización de descodificador de MIME/SMIME realiza tanto el descifrado como la validación de la firma digital (cuando se configura para que realice las dos funciones).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-122">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="9b9b6-123">Por tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados y firmados, puede usar la misma canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="9b9b6-124">Es decir, no tiene que crear canalizaciones diferentes para el descifrado y para la validación de la firma digital.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-124">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3. <span data-ttu-id="9b9b6-125">Genere e implemente la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-125">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-receiving-encrypted-messages"></a><span data-ttu-id="9b9b6-126">Para configurar la ubicación de recepción para recibir mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="9b9b6-126">To configure the receive location for receiving encrypted messages</span></span>  
  
1.  <span data-ttu-id="9b9b6-127">Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes cifrados.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive encrypted messages.</span></span> <span data-ttu-id="9b9b6-128">Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="9b9b6-129">Configure las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="9b9b6-129">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="9b9b6-130">Para obtener más información sobre cómo configurar las ubicaciones de recepción, vea [cómo editar las propiedades de una ubicación de recepción](../core/how-to-edit-the-properties-of-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-130">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
3.  <span data-ttu-id="9b9b6-131">Configurar el host usado como controlador de recepción para la ubicación de recepción con el certificado de descifrado que instaló en el procedimiento"para configurar hosts de BizTalk para recibir mensajes cifrados" en [cómo instalar los certificados de cifrado Mensajes](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-131">Configure the host used as receive handler for the receive location with the decryption certificate that you installed in the procedure," To configure BizTalk hosts for receiving encrypted messages" in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span> <span data-ttu-id="9b9b6-132">Para obtener más información acerca de cómo configurar propiedades de host, vea [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9b9b6-132">For more information how to configure host properties, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b9b6-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b9b6-133">See Also</span></span>  
 <span data-ttu-id="9b9b6-134">[Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9b9b6-134">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="9b9b6-135">[Cómo configurar BizTalk Server para enviar mensajes cifrados](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9b9b6-135">[How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="9b9b6-136">Envío y recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="9b9b6-136">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)