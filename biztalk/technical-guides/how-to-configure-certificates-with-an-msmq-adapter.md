---
title: Cómo configurar certificados con un adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 922a171d-705f-4465-acda-212aa3797c57
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f36e3d13920982f79fe693a306a8123f089c76e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297916"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a><span data-ttu-id="47c6b-102">Cómo configurar certificados con un adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="47c6b-102">How to Configure Certificates with an MSMQ Adapter</span></span>
<span data-ttu-id="47c6b-103">El adaptador de envío MSMQ puede ayudar a proteger una conexión con servidores que admitan o requieran certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="47c6b-103">The MSMQ send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="47c6b-104">Si se especifica un certificado de cliente, el adaptador de envío MSMQ utiliza el certificado al conectarse a los servidores que requieran o admitan certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="47c6b-104">If a client certificate is specified, the MSMQ send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="47c6b-105">Si no se especifica el certificado de cliente y el servidor de destino requiere certificados de cliente, no se autentica el remitente y el MSMQ para enviar el adaptador no puede enviar el mensaje y sigue la lógica de reintentos estándar.</span><span class="sxs-lookup"><span data-stu-id="47c6b-105">If the client certificate is not specified and the destination server requires client certificates, the sender is not authenticated and the MSMQ send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="47c6b-106">El MSMQ para el adaptador de envío utiliza el certificado de cliente desde el almacén personal de la cuenta bajo la que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="47c6b-106">The MSMQ send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="47c6b-107">El certificado se especifica mediante la huella digital.</span><span class="sxs-lookup"><span data-stu-id="47c6b-107">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="47c6b-108">Si se produce un error en el adaptador de envío MSMQ cargar el certificado por cualquier motivo, se suspende el mensaje que se intentaba enviar.</span><span class="sxs-lookup"><span data-stu-id="47c6b-108">If the MSMQ send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
 <span data-ttu-id="47c6b-109">Cuando se usa un adaptador MSMQ para enviar un mensaje firmado o cifrado, configurar la propiedad de transporte de MSMQ de huella digital de certificado para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="47c6b-109">When using an MSMQ adapter to send an encrypted or signed message, configure the Certificate Thumbprint MSMQ transport property for the send port.</span></span> <span data-ttu-id="47c6b-110">En esta propiedad, especifique la huella digital del certificado que se utilizará para la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="47c6b-110">In this property, specify the thumbprint of the certificate to use for message authentication.</span></span> <span data-ttu-id="47c6b-111">Utilizar esta propiedad en combinación con la propiedad Utilizar autenticación para comprobar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="47c6b-111">Use this property in combination with the Use Authentication property to verify the message.</span></span> <span data-ttu-id="47c6b-112">Utilizar las propiedades Nombre de usuario y Contraseña para obtener acceso a las colas.</span><span class="sxs-lookup"><span data-stu-id="47c6b-112">Use the User Name and Password properties to gain access to queues.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="47c6b-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="47c6b-113">Prerequisites</span></span>  
 <span data-ttu-id="47c6b-114">Para llevar a cabo el procedimiento de este tema, debe iniciar sesión como un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="47c6b-114">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a><span data-ttu-id="47c6b-115">Para configurar BizTalk Server para enviar mensajes a través de una conexión de MSMQ</span><span class="sxs-lookup"><span data-stu-id="47c6b-115">To configure BizTalk Server to send messages over an MSMQ connection</span></span>  
  
1.  <span data-ttu-id="47c6b-116">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, cree un nuevo puerto de envío MSMQ o abra las propiedades de puerto de envío MSMQ existente.</span><span class="sxs-lookup"><span data-stu-id="47c6b-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new MSMQ send port or open the properties for an existing MSMQ send port.</span></span>  
  
2.  <span data-ttu-id="47c6b-117">Haga clic en **configurar** en el **transporte** sección de la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="47c6b-117">Click **Configure** in the **Transport** section of the **Send Port Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="47c6b-118">En el **propiedades de transporte de MSMQ** cuadro de diálogo para **autenticación**, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="47c6b-118">In the **MSMQ Transport Properties** dialog box, for **Authentication**, select **True**.</span></span>  
  
4.  <span data-ttu-id="47c6b-119">Para **huella digital del certificado**, especifique la huella digital adecuada.</span><span class="sxs-lookup"><span data-stu-id="47c6b-119">For **Certificate thumbprint**, enter the appropriate thumbprint.</span></span>  
  
5.  <span data-ttu-id="47c6b-120">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="47c6b-120">Click **OK**, and then click **OK** again.</span></span>