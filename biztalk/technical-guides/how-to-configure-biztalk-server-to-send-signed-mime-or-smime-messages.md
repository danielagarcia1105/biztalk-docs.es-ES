---
title: Cómo configurar BizTalk Server para enviar firmados MIME o mensajes SMIME | Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba42463b-2c12-4329-919e-aca427d14eee
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e1f3e01179f26c825480bb3a7de8d13b8539129
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005469"
---
# <a name="how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages"></a><span data-ttu-id="67b02-102">Cómo configurar BizTalk Server envíe firmados MIME o mensajes SMIME</span><span class="sxs-lookup"><span data-stu-id="67b02-102">How to Configure BizTalk Server to Send Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="67b02-103">En este tema se describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utilizar certificados para enviar mensajes MIME/SMIME firmados.</span><span class="sxs-lookup"><span data-stu-id="67b02-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to send signed MIME/SMIME messages.</span></span> <span data-ttu-id="67b02-104">El procedimiento siguiente también se aplica a la configuración del envío de mensajes firmados mediante transporte AS2.</span><span class="sxs-lookup"><span data-stu-id="67b02-104">The procedure below also applies to configuring the sending of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="67b02-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="67b02-105">Prerequisites</span></span>  
 <span data-ttu-id="67b02-106">Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="67b02-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-signed-messages"></a><span data-ttu-id="67b02-107">Para configurar BizTalk Server para enviar mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="67b02-107">To configure BizTalk Server to send signed messages</span></span>  
  
1. <span data-ttu-id="67b02-108">Crear una canalización para enviar mensajes firmados, como sigue:</span><span class="sxs-lookup"><span data-stu-id="67b02-108">Create a pipeline to send signed messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="67b02-109">Este paso no es necesario al configurar el transporte AS2 para enviar mensajes firmados, porque el AS2Send y AS2EdiSend canalizaciones que se incluyen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] atender esta función.</span><span class="sxs-lookup"><span data-stu-id="67b02-109">This step is not necessary when configuring AS2 transport for sending signed messages because the AS2Send and AS2EdiSend pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
   1. <span data-ttu-id="67b02-110">Crear una canalización de envío y, a continuación, arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de la canalización.</span><span class="sxs-lookup"><span data-stu-id="67b02-110">Create a send pipeline and then drag the MIME/SMIME Encoder pipeline component into the Encode stage of the pipeline.</span></span>  
  
   2. <span data-ttu-id="67b02-111">En el **propiedades** ventana, configure la propiedad de tipo de firma de codificador de MIME/SMIME canalización componente ClearSign o BlobSign.</span><span class="sxs-lookup"><span data-stu-id="67b02-111">In the **Properties** window, configure the MIME/SMIME Encoder pipeline component Signature type property to ClearSign or BlobSign.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="67b02-112">Si también usa cifrado, solo se puede seleccionar BlobSign.</span><span class="sxs-lookup"><span data-stu-id="67b02-112">If you are also using encryption, you can only select BlobSign.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="67b02-113">Puede configurar las propiedades del componente de canalización de envío mediante la Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], una vez que la canalización se haya implementado en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="67b02-113">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="67b02-114">El componente de canalización de codificador de MIME/SMIME realiza tanto el cifrado como la firma digital (cuando se configura para que realice las dos funciones).</span><span class="sxs-lookup"><span data-stu-id="67b02-114">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="67b02-115">Por lo tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados y firmados, puede usar la misma canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="67b02-115">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="67b02-116">Es decir, no es necesario crear canalizaciones diferentes para el cifrado y la firma digital.</span><span class="sxs-lookup"><span data-stu-id="67b02-116">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
   3. <span data-ttu-id="67b02-117">Genere e implemente la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="67b02-117">Build and deploy the send pipeline.</span></span>  
  
2. <span data-ttu-id="67b02-118">Configurar el puerto de envío para enviar mensajes firmados, como sigue:</span><span class="sxs-lookup"><span data-stu-id="67b02-118">Configure the send port for sending signed messages, as follows:</span></span>  
  
   1. <span data-ttu-id="67b02-119">Agregue el ensamblado de BizTalk que creó que contiene la canalización de envío a la aplicación de BizTalk que incluye los puertos de envío para enviar mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="67b02-119">Add the BizTalk assembly that you created containing the send pipeline to the BizTalk application that includes the send ports to send signed messages.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="67b02-120">Este paso no es necesario al configurar el transporte AS2 para enviar mensajes firmados puesto que las canalizaciones AS2Send y AS2EdiSend se incluyen en la aplicación EDI de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b02-120">This step is not necessary when configuring AS2 transport for sending signed messages because the AS2Send and AS2EdiSend pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="67b02-121">Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="67b02-121">Configure the send port in the BizTalk application with the send pipeline that you created in the previous procedure.</span></span>  
  
3. <span data-ttu-id="67b02-122">Configure el grupo con un certificado para enviar mensajes firmados, como sigue:</span><span class="sxs-lookup"><span data-stu-id="67b02-122">Configure the group with a certificate for sending signed messages, as follows:</span></span>  
  
   1. <span data-ttu-id="67b02-123">Configurar el grupo de BizTalk con el certificado de firma que instaló expandiendo el grupo de BizTalk en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, hacer clic **grupo de BizTalk**y, a continuación, haga clic en  **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="67b02-123">Configure the BizTalk group with the signing certificate that you installed by expanding the BizTalk group in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-clicking **BizTalk Group**, and then clicking **Properties**.</span></span>  
  
   2. <span data-ttu-id="67b02-124">Haga clic en la ficha certificado, haga clic en **examinar**, seleccione el certificado adecuado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="67b02-124">Click the Certificate tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b02-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="67b02-125">See Also</span></span>  
 [<span data-ttu-id="67b02-126">Configurar certificados para MIME o mensajes SMIME</span><span class="sxs-lookup"><span data-stu-id="67b02-126">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)