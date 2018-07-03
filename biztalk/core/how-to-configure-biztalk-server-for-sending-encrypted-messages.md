---
title: Cómo configurar BizTalk Server para enviar mensajes cifrados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb751d7c-49cd-46f0-9630-254cf06c497e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f7388e9f6b8e56397a3b6efdf466aec3383746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023906"
---
# <a name="how-to-configure-biztalk-server-for-sending-encrypted-messages"></a><span data-ttu-id="f570b-102">Cómo configurar BizTalk Server para el envío de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="f570b-102">How to Configure BizTalk Server for Sending Encrypted Messages</span></span>
<span data-ttu-id="f570b-103">En el siguiente procedimiento se enumeran los pasos que debe seguir para configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados.</span><span class="sxs-lookup"><span data-stu-id="f570b-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted messages.</span></span>  
  
-   <span data-ttu-id="f570b-104">Para crear una canalización para enviar mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="f570b-104">To create a pipeline to send encrypted messages</span></span>  
  
-   <span data-ttu-id="f570b-105">Para configurar el puerto de envío para enviar mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="f570b-105">To configure the send port for sending encrypted messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f570b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f570b-106">Prerequisites</span></span>  
 <span data-ttu-id="f570b-107">Antes de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s para enviar mensajes cifrados, debe realizar los pasos descritos en [cómo instalar los certificados para mensajes cifrados](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f570b-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for sending encrypted messages, you must perform the steps in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-send-encrypted-messages"></a><span data-ttu-id="f570b-108">Para crear una canalización para enviar mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="f570b-108">To create a pipeline to send encrypted messages</span></span>  
  
1. <span data-ttu-id="f570b-109">En el Explorador de soluciones de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione el proyecto en el que desea crear la canalización.</span><span class="sxs-lookup"><span data-stu-id="f570b-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="f570b-110">En el **archivo** menú, haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f570b-110">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="f570b-111">En el **Agregar nuevo elemento** diálogo cuadro, expanda elementos de proyecto de BizTalk, haga clic en **archivos de canalización**y, a continuación, haga clic en el **canalización de envío** plantilla.</span><span class="sxs-lookup"><span data-stu-id="f570b-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Send Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="f570b-112">En el **nombre** , escriba un nombre para la canalización.</span><span class="sxs-lookup"><span data-stu-id="f570b-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="f570b-113">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f570b-113">Click **Add**.</span></span>  
  
        <span data-ttu-id="f570b-114">La nueva canalización aparecerá en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="f570b-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="f570b-115">Arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="f570b-115">Drag the MIME/SMIME Encoder pipeline component into the Encode stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="f570b-116">![MIME&#47;componente de canalización de codificador SMIME](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span><span class="sxs-lookup"><span data-stu-id="f570b-116">![MIME&#47;SMIME Encoder pipeline component](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span></span>  
  
   -   <span data-ttu-id="f570b-117">En la ventana Propiedades, configure el componente de canalización de codificador de MIME/SMIME **habilitar el cifrado** propiedad `True`.</span><span class="sxs-lookup"><span data-stu-id="f570b-117">In the Properties window, configure the MIME/SMIME Encoder pipeline component **Enable encryption** property to `True`.</span></span> <span data-ttu-id="f570b-118">Para obtener más información sobre la **habilitar el cifrado** propiedad, vea [cómo configurar el componente de canalización de codificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="f570b-118">For more information about the **Enable encryption** property, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f570b-119">Puede configurar las propiedades del componente de canalización de envío mediante la Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], una vez que la canalización se haya implementado en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f570b-119">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="f570b-120">Para obtener más información, consulte [cómo configurar propiedades de canalización por instancia para un puerto de envío](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="f570b-120">For more information, see [How to Configure Per-Instance Pipeline Properties for a Send Port](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="f570b-121">El componente de canalización de codificador de MIME/SMIME realiza tanto el cifrado como la firma digital (cuando se configura para que realice las dos funciones).</span><span class="sxs-lookup"><span data-stu-id="f570b-121">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="f570b-122">Por lo tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados y firmados, puede usar la misma canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="f570b-122">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="f570b-123">Es decir, no es necesario crear canalizaciones diferentes para el cifrado y la firma digital.</span><span class="sxs-lookup"><span data-stu-id="f570b-123">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
3. <span data-ttu-id="f570b-124">Genere e implemente la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="f570b-124">Build and deploy the send pipeline.</span></span>  
  
### <a name="to-configure-the-send-port-for-sending-encrypted-messages"></a><span data-ttu-id="f570b-125">Para configurar el puerto de envío para enviar mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="f570b-125">To configure the send port for sending encrypted messages</span></span>  
  
1.  <span data-ttu-id="f570b-126">Agregue el ensamblado de BizTalk que creó en el procedimiento anterior a la aplicación de BizTalk incluidos los puertos de envío para enviar mensajes cifrados.</span><span class="sxs-lookup"><span data-stu-id="f570b-126">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the send ports to send encrypted messages.</span></span> <span data-ttu-id="f570b-127">Para obtener más información sobre cómo agregar ensamblados de BizTalk, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="f570b-127">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="f570b-128">Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior y, a continuación, asigne el certificado de cifrado que instaló en [cómo instalar los certificados para mensajes cifrados](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f570b-128">Configure the send port in the BizTalk Application with the send pipeline that you created in previous procedure, and then assign the encryption certificate that you installed in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span> <span data-ttu-id="f570b-129">Para obtener más información acerca de cómo configurar puertos de envío, consulte [cómo asignar un certificado a un puerto de envío](../core/how-to-assign-a-certificate-to-a-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="f570b-129">For more information about how to configure send ports, see [How to Assign a Certificate to a Send Port](../core/how-to-assign-a-certificate-to-a-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f570b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f570b-130">See Also</span></span>  
 <span data-ttu-id="f570b-131">[Cómo configurar BizTalk Server para recibir mensajes cifrados](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f570b-131">[How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md) </span></span>  
 <span data-ttu-id="f570b-132">[Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f570b-132">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="f570b-133">Envío y recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="f570b-133">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)