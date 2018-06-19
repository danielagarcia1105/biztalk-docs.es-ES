---
title: Cómo configurar el servidor BizTalk Server para enviar mensajes MIME/SMIME de cifrado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f67152-5f80-4040-a9d6-0819fab7fcb5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83b5f28ac3716376aa93cff22f933363825615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297612"
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a><span data-ttu-id="5f555-102">Cómo configurar BizTalk Server para enviar mensajes cifrados de MIME/SMIME</span><span class="sxs-lookup"><span data-stu-id="5f555-102">How to Configure BizTalk Server to Send Encrypted MIME/SMIME Messages</span></span>
<span data-ttu-id="5f555-103">En este tema se describe cómo configurar BizTalk Server que utilicen certificados para enviar mensajes cifrados de MIME/SMIME.</span><span class="sxs-lookup"><span data-stu-id="5f555-103">This topic describes how to configure BizTalk Server to use certificates to send encrypted MIME/SMIME messages.</span></span> <span data-ttu-id="5f555-104">El procedimiento siguiente también se aplica a la configuración de enviar mensajes cifrados a través de transporte AS2.</span><span class="sxs-lookup"><span data-stu-id="5f555-104">The procedure below also applies to configuring the sending of encrypted messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5f555-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5f555-105">Prerequisites</span></span>  
 <span data-ttu-id="5f555-106">Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5f555-106">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a><span data-ttu-id="5f555-107">Para configurar BizTalk Server para enviar mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="5f555-107">To configure BizTalk Server to send encrypted messages</span></span>  
  
1.  <span data-ttu-id="5f555-108">Crear una canalización para enviar mensajes cifrados, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="5f555-108">Create a pipeline to send encrypted messages, as follows:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f555-109">Este paso no es necesario al configurar el transporte de AS2 para enviar mensajes cifrados, ya que la AS2Send y AS2EdiSend canalizaciones que se incluyen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servir esta función.</span><span class="sxs-lookup"><span data-stu-id="5f555-109">This step is not necessary when configuring AS2 transport for sending encrypted messages because the AS2Send and AS2EdiSend pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
    1.  <span data-ttu-id="5f555-110">Crear una canalización de envío y, a continuación, arrastre el componente de canalización de codificador de MIME/SMIME en la fase de codificación de la canalización.</span><span class="sxs-lookup"><span data-stu-id="5f555-110">Create a send pipeline and then drag the MIME/SMIME Encoder pipeline component into the Encode stage of the pipeline.</span></span>  
  
    2.  <span data-ttu-id="5f555-111">En el **propiedades** ventana, configure la propiedad de cifrado codificador de MIME/SMIME habilitar de componente de canalización para **True**.</span><span class="sxs-lookup"><span data-stu-id="5f555-111">In the **Properties** window, configure the MIME/SMIME Encoder pipeline component Enable encryption property to **True**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5f555-112">Puede configurar las propiedades del componente de canalización de envío mediante la consola de administración de servidor BizTalk Server una vez que la canalización se haya implementado en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5f555-112">You can configure the send pipeline component properties using the BizTalk Server Administration console after the pipeline has been deployed into a BizTalk group.</span></span>  
  
    3.  <span data-ttu-id="5f555-113">Genere e implemente la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="5f555-113">Build and deploy the send pipeline.</span></span>  
  
2.  <span data-ttu-id="5f555-114">Configurar el puerto de envío para enviar mensajes cifrados, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="5f555-114">Configure the send port for sending encrypted messages, as follows:</span></span>  
  
    1.  <span data-ttu-id="5f555-115">Agregue el ensamblado de BizTalk que ha creado que contiene la canalización de envío a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes cifrados.</span><span class="sxs-lookup"><span data-stu-id="5f555-115">Add the BizTalk assembly that you created containing the send pipeline to the BizTalk application including the receive locations to receive encrypted messages.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5f555-116">Este paso no es necesario al configurar el transporte de AS2 para enviar mensajes cifrados, puesto que las canalizaciones AS2Send y AS2EdiSend se incluyen en la aplicación EDI de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5f555-116">This step is not necessary when configuring AS2 transport for sending encrypted messages because the AS2Send and AS2EdiSend pipelines are included in the BizTalk EDI Application.</span></span>  
  
    2.  <span data-ttu-id="5f555-117">Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="5f555-117">Configure the send port in the BizTalk Application with the send pipeline that you created in the previous procedure.</span></span>  
  
    3.  <span data-ttu-id="5f555-118">Asigne el certificado de cifrado que instaló haciendo clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificado**.</span><span class="sxs-lookup"><span data-stu-id="5f555-118">Assign the encryption certificate that you installed by right-clicking the send port, clicking **Properties**, and then clicking **Certificate**.</span></span> <span data-ttu-id="5f555-119">Haga clic en **examinar**, busque el certificado que desea asignar a este puerto de envío y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5f555-119">Click **Browse**, browse to the certificate that you want to assign to this send port, and then click **OK**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5f555-120">Si el certificado no existe en el equipo local, en la **huella digital** , escriba o pegue la huella digital del certificado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5f555-120">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="5f555-121">La huella digital de certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="5f555-121">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>