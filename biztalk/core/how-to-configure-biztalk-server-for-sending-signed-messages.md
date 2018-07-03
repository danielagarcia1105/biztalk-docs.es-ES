---
title: Cómo configurar BizTalk Server para enviar mensajes firmados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be86fbb3-de80-4d9f-bcf0-c61347704229
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53487a4f7f70a7f22a2f9fdae988159723266847
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966357"
---
# <a name="how-to-configure-biztalk-server-for-sending-signed-messages"></a><span data-ttu-id="db69e-102">Cómo configurar BizTalk Server para el envío de mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="db69e-102">How to Configure BizTalk Server for Sending Signed Messages</span></span>
<span data-ttu-id="db69e-103">El procedimiento siguiente indica los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que envíe mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="db69e-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send signed messages.</span></span>  
  
-   <span data-ttu-id="db69e-104">Para crear una canalización para enviar mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="db69e-104">To create a pipeline to send signed messages</span></span>  
  
-   <span data-ttu-id="db69e-105">Para configurar el puerto de envío para enviar mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="db69e-105">To configure the send port for sending signed messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="db69e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="db69e-106">Prerequisites</span></span>  
 <span data-ttu-id="db69e-107">Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para enviar mensajes firmados, debe realizar los pasos descritos en [cómo instalar los certificados para firmas digitales](../core/how-to-install-the-certificates-for-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="db69e-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for sending signed messages, you must perform the steps in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-send-signed-messages"></a><span data-ttu-id="db69e-108">Para crear una canalización para enviar mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="db69e-108">To create a pipeline to send signed messages</span></span>  
  
1. <span data-ttu-id="db69e-109">En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.</span><span class="sxs-lookup"><span data-stu-id="db69e-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="db69e-110">En el **archivo** menú, haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="db69e-110">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="db69e-111">En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de envío** plantilla.</span><span class="sxs-lookup"><span data-stu-id="db69e-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Send Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="db69e-112">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="db69e-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="db69e-113">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="db69e-113">Click **Add**.</span></span>  
  
        <span data-ttu-id="db69e-114">La nueva canalización aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="db69e-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="db69e-115">Arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="db69e-115">Drag the MIME/SMIME Encoder pipeline component into the Encode stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="db69e-116">![MIME&#47;componente de canalización de codificador SMIME](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span><span class="sxs-lookup"><span data-stu-id="db69e-116">![MIME&#47;SMIME Encoder pipeline component](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span></span>  
  
3. <span data-ttu-id="db69e-117">En la ventana Propiedades, configure el componente de canalización de codificador de MIME/SMIME **tipo de firma** propiedad **ClearSign**o **BlobSign**.</span><span class="sxs-lookup"><span data-stu-id="db69e-117">In the Properties window, configure the MIME/SMIME Encoder pipeline component **Signature type** property to **ClearSign**or **BlobSign**.</span></span> <span data-ttu-id="db69e-118">Para obtener más información sobre la **habilitar el cifrado** propiedad, vea [cómo configurar el componente de canalización de codificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="db69e-118">For more information about the **Enable encryption** property, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="db69e-119">Si también usa cifrado, sólo se puede seleccionar **BlobSign**.</span><span class="sxs-lookup"><span data-stu-id="db69e-119">If you are also using encryption, you can only select **BlobSign**.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="db69e-120">Puede configurar las propiedades del componente de canalización de envío mediante la Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], una vez que la canalización se haya implementado en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="db69e-120">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="db69e-121">Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para un puerto de envío](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="db69e-121">For more information, see [How to Configure Per-Instance Pipeline Properties for a Send Port](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="db69e-122">El componente de canalización de codificador de MIME/SMIME realiza tanto el cifrado como la firma digital (cuando se configura para que realice las dos funciones).</span><span class="sxs-lookup"><span data-stu-id="db69e-122">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="db69e-123">Por lo tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados y firmados, puede usar la misma canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="db69e-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="db69e-124">Es decir, no es necesario crear canalizaciones diferentes para el cifrado y la firma digital.</span><span class="sxs-lookup"><span data-stu-id="db69e-124">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
4. <span data-ttu-id="db69e-125">Genere e implemente la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="db69e-125">Build and deploy the send pipeline.</span></span>  
  
### <a name="to-configure-the-send-port-for-sending-signed-messages"></a><span data-ttu-id="db69e-126">Para configurar el puerto de envío para enviar mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="db69e-126">To configure the send port for sending signed messages</span></span>  
  
1.  <span data-ttu-id="db69e-127">Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidas las ubicaciones de recepción para enviar mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="db69e-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to sending signed messages.</span></span> <span data-ttu-id="db69e-128">Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="db69e-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="db69e-129">Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="db69e-129">Configure the send port in the BizTalk Application with the send pipeline that you created in previous procedure.</span></span> <span data-ttu-id="db69e-130">Para obtener más información acerca de cómo configurar puertos de envío, consulte [crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md).</span><span class="sxs-lookup"><span data-stu-id="db69e-130">For more information about how to configure send ports, see [Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md).</span></span>  
  
3.  <span data-ttu-id="db69e-131">Configurar el grupo de BizTalk con el certificado de firma que instaló en [cómo instalar los certificados para firmas digitales](../core/how-to-install-the-certificates-for-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="db69e-131">Configure the BizTalk group with the signing certificate that you installed in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span> <span data-ttu-id="db69e-132">Para obtener más información acerca de cómo configurar un grupo de BizTalk, consulte [cómo modificar las propiedades de grupo](../core/how-to-modify-group-properties.md).</span><span class="sxs-lookup"><span data-stu-id="db69e-132">For more information how to configure a BizTalk group, see [How to Modify Group Properties](../core/how-to-modify-group-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db69e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="db69e-133">See Also</span></span>  
 <span data-ttu-id="db69e-134">[Cómo configurar BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="db69e-134">[How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span></span>  
 <span data-ttu-id="db69e-135">[Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="db69e-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="db69e-136">Envío y recepción de mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="db69e-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)