---
title: Cómo configurar BizTalk Server reciba firmados MIME o mensajes SMIME | Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2df073a27cb9e17851c9afec4b5531424d913fab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009189"
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a><span data-ttu-id="5fa72-102">Cómo configurar BizTalk Server reciba firmados MIME o mensajes SMIME</span><span class="sxs-lookup"><span data-stu-id="5fa72-102">How to Configure BizTalk Server to Receive Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="5fa72-103">En este tema se describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar certificados para recibir mensajes MIME/SMIME firmados.</span><span class="sxs-lookup"><span data-stu-id="5fa72-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive signed MIME/SMIME messages.</span></span> <span data-ttu-id="5fa72-104">El procedimiento siguiente también se aplica a la configuración de la recepción de mensajes firmados mediante transporte AS2.</span><span class="sxs-lookup"><span data-stu-id="5fa72-104">The procedure below also applies to configuring the receiving of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5fa72-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5fa72-105">Prerequisites</span></span>  
 <span data-ttu-id="5fa72-106">Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="5fa72-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a><span data-ttu-id="5fa72-107">Para configurar BizTalk Server para recibir mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="5fa72-107">To configure BizTalk Server to receive signed messages</span></span>  
  
1. <span data-ttu-id="5fa72-108">Crear una canalización para recibir mensajes firmados, como sigue:</span><span class="sxs-lookup"><span data-stu-id="5fa72-108">Create a pipeline to receive signed messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5fa72-109">Este paso no es necesario al configurar el transporte AS2 para recibir mensajes firmados, porque el AS2Receive y AS2EdiReceive canalizaciones que se incluyen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] atender esta función.</span><span class="sxs-lookup"><span data-stu-id="5fa72-109">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
   1. <span data-ttu-id="5fa72-110">Crear una canalización de recepción y, a continuación, arrastre el componente de canalización de descodificador de MIME/SMIME a la fase de descodificación de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="5fa72-110">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the receive pipeline.</span></span>  
  
   2. <span data-ttu-id="5fa72-111">En el **propiedades** ventana, configure las propiedades del componente de canalización de descodificador de MIME/SMIME.</span><span class="sxs-lookup"><span data-stu-id="5fa72-111">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="5fa72-112">Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fa72-112">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="5fa72-113">Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5fa72-113">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
   3. <span data-ttu-id="5fa72-114">Genere e implemente la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="5fa72-114">Build and deploy the receive pipeline.</span></span>  
  
2. <span data-ttu-id="5fa72-115">Configurar una ubicación de recepción para recibir mensajes firmados, como sigue:</span><span class="sxs-lookup"><span data-stu-id="5fa72-115">Configure a receive location for receiving signed messages, as follows:</span></span>  
  
   1. <span data-ttu-id="5fa72-116">Agregue el ensamblado de BizTalk que creó que contiene la canalización de recepción a la aplicación de BizTalk, incluidas las ubicaciones de recepción para recibir mensajes firmados.</span><span class="sxs-lookup"><span data-stu-id="5fa72-116">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive signed messages.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="5fa72-117">Este paso no es necesario al configurar el transporte AS2 para recibir mensajes firmados, puesto que las canalizaciones AS2Receive y AS2EdiReceive se incluyen en la aplicación EDI de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fa72-117">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="5fa72-118">Configurar las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="5fa72-118">Configure the receive locations in the BizTalk application with the receive pipeline that you created in previous procedure.</span></span>  
  
3. <span data-ttu-id="5fa72-119">Configure la entidad con un certificado para recibir mensajes firmados, como sigue:</span><span class="sxs-lookup"><span data-stu-id="5fa72-119">Configure the party with a certificate for receiving signed messages, as follows:</span></span>  
  
   -   <span data-ttu-id="5fa72-120">Abra el **las propiedades de entidad** cuadro de diálogo en la consola de administración de BizTalk Server, haga clic en el **certificado** , haga clic **examinar**, seleccione el certificado adecuado, y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fa72-120">Open the **Party Properties** dialog box in the BizTalk Server Administration Console, click the **Certificate** tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="5fa72-121">El certificado usado para comprobar una firma para una entidad debe ser único entre los certificados usados para comprobar las firmas de las demás entidades.</span><span class="sxs-lookup"><span data-stu-id="5fa72-121">The certificate used to verify a signature for a party must be unique from the certificates used to verify signatures for other parties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa72-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fa72-122">See Also</span></span>  
 [<span data-ttu-id="5fa72-123">Configurar certificados para MIME o mensajes SMIME</span><span class="sxs-lookup"><span data-stu-id="5fa72-123">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)