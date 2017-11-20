---
title: "Cómo configurar el servidor BizTalk Server para recibir mensajes firmados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48479532-24a9-41d9-a3b8-2a23f4e76457
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 814aa3f25866f18a1d7fe536bc47a996f286916d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-receiving-signed-messages"></a><span data-ttu-id="05260-102">Cómo configurar BizTalk Server para la recepción de mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="05260-102">How to Configure BizTalk Server for Receiving Signed Messages</span></span>
<span data-ttu-id="05260-103">En el siguiente procedimiento se enumeran los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados.</span><span class="sxs-lookup"><span data-stu-id="05260-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted messages.</span></span>  
  
-   <span data-ttu-id="05260-104">Para crear una canalización para recibir mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="05260-104">To create a pipeline to receive signed messages</span></span>  
  
-   <span data-ttu-id="05260-105">Para configurar la ubicación de recepción para recibir mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="05260-105">To configure the receive location for receiving signed messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="05260-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="05260-106">Prerequisites</span></span>  
 <span data-ttu-id="05260-107">Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para recibir mensajes firmados, debe realizar los pasos descritos en [cómo instalar los certificados para las firmas digitales](../core/how-to-install-the-certificates-for-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="05260-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for receiving signed messages, you must perform the steps in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-receive-signed-messages"></a><span data-ttu-id="05260-108">Para crear una canalización para recibir mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="05260-108">To create a pipeline to receive signed messages</span></span>  
  
1.  <span data-ttu-id="05260-109">En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.</span><span class="sxs-lookup"><span data-stu-id="05260-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="05260-110">En el **archivo** menú, haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="05260-110">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="05260-111">En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de recepción** plantilla.</span><span class="sxs-lookup"><span data-stu-id="05260-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="05260-112">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="05260-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="05260-113">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="05260-113">Click **Add**.</span></span>  
  
         <span data-ttu-id="05260-114">La nueva canalización aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="05260-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="05260-115">Arrastre el componente de canalización de descodificador de MIME/SMIME en el **Decode** fase de una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="05260-115">Drag the MIME/SMIME Decoder pipeline component into the **Decode** stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="05260-116">![MIME &#47; Componente de canalización de descodificador de SMIME](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="05260-116">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
    -   <span data-ttu-id="05260-117">Configurar las propiedades del componente de canalización de descodificador de MIME/SMIME en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="05260-117">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="05260-118">Para obtener más información sobre el descodificador MIME/SMIME, vea [cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="05260-118">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05260-119">Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05260-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="05260-120">Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="05260-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="05260-121">Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para una ubicación de recepción](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="05260-121">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05260-122">El componente de canalización de descodificador de MIME/SMIME realiza tanto el descifrado como la validación de la firma digital (cuando se configura para que realice las dos funciones).</span><span class="sxs-lookup"><span data-stu-id="05260-122">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="05260-123">Por tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados y firmados, puede usar la misma canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="05260-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="05260-124">Es decir, no tiene que crear canalizaciones diferentes para el descifrado y para la validación de la firma digital.</span><span class="sxs-lookup"><span data-stu-id="05260-124">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3.  <span data-ttu-id="05260-125">Genere e implemente la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="05260-125">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-receiving-signed-messages"></a><span data-ttu-id="05260-126">Para configurar la ubicación de recepción para recibir mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="05260-126">To configure the receive location for receiving signed messages</span></span>  
  
1.  <span data-ttu-id="05260-127">Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="05260-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive signed messages.</span></span> <span data-ttu-id="05260-128">Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="05260-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="05260-129">Configure las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="05260-129">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="05260-130">Para obtener más información sobre cómo configurar ubicaciones de recepción, consulte [cómo editar las propiedades de una ubicación de recepción](../core/how-to-edit-the-properties-of-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="05260-130">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05260-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="05260-131">See Also</span></span>  
 <span data-ttu-id="05260-132">[Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="05260-132">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="05260-133">[Cómo configurar el servidor BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="05260-133">[How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md) </span></span>  
 <span data-ttu-id="05260-134">[Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="05260-134">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="05260-135">Enviar y recibir mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="05260-135">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)