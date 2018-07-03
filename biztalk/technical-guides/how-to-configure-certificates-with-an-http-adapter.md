---
title: Cómo configurar certificados con un adaptador de HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2f454f-22b5-4113-9a23-e00a816d5e48
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520204a6c0f411f8f622838b846a3af41b6c60a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007101"
---
# <a name="how-to-configure-certificates-with-an-http-adapter"></a><span data-ttu-id="ce8a5-102">Cómo configurar certificados con un adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="ce8a5-102">How to Configure Certificates with an HTTP Adapter</span></span>
<span data-ttu-id="ce8a5-103">El adaptador de envío HTTP puede ayudar a proteger una conexión con servidores que admitan o requieran certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-103">The HTTP send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="ce8a5-104">Si se especifica un certificado de cliente, el adaptador de envío HTTP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-104">If a client certificate is specified, the HTTP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="ce8a5-105">Si no se especifica el certificado de cliente y el servidor de destino requiere certificados de cliente, el remitente no está autenticado y HTTP se produce un error de adaptador para enviar el mensaje de envío y sigue la lógica de reintentos estándar.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-105">If the client certificate is not specified and the destination server requires client certificates, the sender is not authenticated and the HTTP send adapter fails to send the message and follows the standard retry logic.</span></span>  

 <span data-ttu-id="ce8a5-106">El adaptador de envío HTTP usará el certificado de cliente ubicado en el almacén personal de la cuenta bajo la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce8a5-106">The HTTP send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="ce8a5-107">El certificado se especifica mediante la huella digital.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-107">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="ce8a5-108">Si, por cualquier motivo, el adaptador de envío HTTP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-108">If the HTTP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  

 <span data-ttu-id="ce8a5-109">Cuando se usa un adaptador de HTTP para enviar un mensaje firmado o cifrado, configurar la huella digital del certificado SSL propiedades de transporte HTTP para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-109">When using an HTTP adapter to send an encrypted or signed message, configure the SSL certificate thumbprint HTTP transport property for the send port.</span></span> <span data-ttu-id="ce8a5-110">En esta propiedad, especifique la huella digital del certificado que se usará para la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-110">In this property, specify the thumbprint of the certificate to use for message authentication.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="ce8a5-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ce8a5-111">Prerequisites</span></span>  
 <span data-ttu-id="ce8a5-112">Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-112">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-http-connection"></a><span data-ttu-id="ce8a5-113">Para configurar BizTalk Server para enviar mensajes a través de una conexión HTTP</span><span class="sxs-lookup"><span data-stu-id="ce8a5-113">To configure BizTalk Server to send messages over an HTTP connection</span></span>  

1. <span data-ttu-id="ce8a5-114">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, crear un puerto de envío HTTP nuevo o abra las propiedades de puerto de envío HTTP existente.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new HTTP send port or open the properties for an existing HTTP send port.</span></span>  

2. <span data-ttu-id="ce8a5-115">Haga clic en **configurar** en la sección de transporte de la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-115">Click **Configure** in the Transport section of the **Send Port Properties** dialog box.</span></span>  

3. <span data-ttu-id="ce8a5-116">Haga clic en **autenticación** en el **propiedades de transporte HTTP** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-116">Click **Authentication** in the **HTTP Transport Properties** dialog box.</span></span>  

4. <span data-ttu-id="ce8a5-117">En **tipo de autenticación**, seleccione **Anonymous**, **básica**, **Digest**, o **Kerberos**.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-117">In **Authentication type**, select **Anonymous**, **Basic**, **Digest**, or **Kerberos**.</span></span>  

5. <span data-ttu-id="ce8a5-118">Si el tipo de autenticación es **básica** o **implícita**, seleccione **no use Single Sign-On** (en cuyo caso debe especificar el nombre de usuario y contraseña) o seleccione  **Usar inicio de sesión único** (en cuyo caso debe seleccionar la aplicación afiliada).</span><span class="sxs-lookup"><span data-stu-id="ce8a5-118">If the authentication type is **Basic** or **Digest**, either select **Do not use Single Sign-On** (in which case you must specify the user name and password) or select **Use Single Sign-On** (in which case you must select the Affiliate Application).</span></span>  

6. <span data-ttu-id="ce8a5-119">En **huella digital de certificado de cliente SSL**, escriba la huella digital adecuada.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-119">In **SSL client certificate thumbprint**, enter the appropriate thumbprint.</span></span>  

7. <span data-ttu-id="ce8a5-120">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="ce8a5-120">Click **OK**, and then click **OK** again.</span></span>
