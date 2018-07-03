---
title: Cómo configurar certificados con un adaptador de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20ee05c5-9cea-456d-bff6-49dd249f0ff4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0a709ab6b28796328677e7e8ae009e3273565a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012285"
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a><span data-ttu-id="78a6c-102">Cómo configurar certificados con un adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="78a6c-102">How to Configure Certificates with a SOAP Adapter</span></span>
<span data-ttu-id="78a6c-103">El adaptador de envío SOAP puede ayudar a proteger una conexión con servidores que admitan o requieran certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="78a6c-103">The SOAP send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="78a6c-104">Si se especifica un certificado de cliente, el adaptador de envío SOAP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="78a6c-104">If you specify a client certificate, the SOAP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="78a6c-105">Si no especifica un certificado de cliente y el servidor de destino requiere certificados de cliente, no se autentica el remitente y el envío de SOAP adaptador no puede enviar el mensaje y seguirá la lógica de reintentos estándar.</span><span class="sxs-lookup"><span data-stu-id="78a6c-105">If you do not specify a client certificate and the destination server requires client certificates, the sender is not authenticated and the SOAP send adapter fails to send the message and follows the standard retry logic.</span></span>  

 <span data-ttu-id="78a6c-106">El adaptador de envío SOAP utilizará el certificado de cliente ubicado en el almacén personal de la cuenta en la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78a6c-106">The SOAP send adapter uses the client certificate from the Personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="78a6c-107">El adaptador de SOAP especifica el certificado por su huella digital.</span><span class="sxs-lookup"><span data-stu-id="78a6c-107">The SOAP adapter specifies the certificate by its thumbprint.</span></span> <span data-ttu-id="78a6c-108">Si, por cualquier motivo, el adaptador de envío SOAP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.</span><span class="sxs-lookup"><span data-stu-id="78a6c-108">If the SOAP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  

 <span data-ttu-id="78a6c-109">Cuando se usa un adaptador de SOAP para enviar un mensaje firmado o cifrado, configurar la propiedad de transporte de SOAP de huella digital del certificado de cliente para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="78a6c-109">When using a SOAP adapter to send an encrypted or signed message, configure the Client Certificate Thumbprint SOAP transport property for the send port.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="78a6c-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="78a6c-110">Prerequisites</span></span>  
 <span data-ttu-id="78a6c-111">Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="78a6c-111">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a><span data-ttu-id="78a6c-112">Para configurar BizTalk Server para enviar mensajes a través de una conexión de SOAP</span><span class="sxs-lookup"><span data-stu-id="78a6c-112">To configure BizTalk Server to send messages over a SOAP connection</span></span>  

1. <span data-ttu-id="78a6c-113">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, cree un nuevo puerto de envío SOAP o abra las propiedades de puerto de envío de un SOAP existente.</span><span class="sxs-lookup"><span data-stu-id="78a6c-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new SOAP send port or open the properties for an existing SOAP send port.</span></span>  

2. <span data-ttu-id="78a6c-114">Haga clic en **configurar** en el **transporte** sección de la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="78a6c-114">Click **Configure** in the **Transport** section of the **Send Port Properties** dialog box.</span></span>  

3. <span data-ttu-id="78a6c-115">En el **General** ficha **tipo de autenticación**, seleccione **Anonymous**, **básica**, **Digest**, o **NTLM**.</span><span class="sxs-lookup"><span data-stu-id="78a6c-115">On the **General** tab, in **Authentication type**, select **Anonymous**, **Basic**, **Digest**, or **NTLM**.</span></span>  

4. <span data-ttu-id="78a6c-116">Si el tipo de autenticación es **básica** o **implícita**, seleccione **no use Single Sign-On** (en cuyo caso debe especificar el nombre de usuario y contraseña) o seleccione  **Usar inicio de sesión único** (en cuyo caso debe seleccionar la aplicación afiliada).</span><span class="sxs-lookup"><span data-stu-id="78a6c-116">If the authentication type is **Basic** or **Digest**, either select **Do not use Single Sign-On** (in which case you must specify the user name and password) or select **Use Single Sign-On** (in which case you must select the Affiliate Application).</span></span>  

5. <span data-ttu-id="78a6c-117">En **huella digital de certificado de cliente SSL**, escriba la huella digital adecuada.</span><span class="sxs-lookup"><span data-stu-id="78a6c-117">In **SSL client certificate thumbprint**, enter the appropriate thumbprint.</span></span>  

6. <span data-ttu-id="78a6c-118">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="78a6c-118">Click **OK**, and then click **OK** again.</span></span>
