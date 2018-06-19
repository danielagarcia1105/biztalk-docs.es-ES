---
title: Cómo configurar certificados con un adaptador SOAP | Documentos de Microsoft
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
ms.openlocfilehash: 8e382fa9084fd728e04efa29900fb0222d8b05ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298284"
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a><span data-ttu-id="32903-102">Cómo configurar certificados con un adaptador SOAP</span><span class="sxs-lookup"><span data-stu-id="32903-102">How to Configure Certificates with a SOAP Adapter</span></span>
<span data-ttu-id="32903-103">El adaptador de envío SOAP puede ayudar a proteger una conexión con servidores que admitan o requieran certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="32903-103">The SOAP send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="32903-104">Si se especifica un certificado de cliente, el adaptador de envío SOAP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="32903-104">If you specify a client certificate, the SOAP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="32903-105">Si no especifica un certificado de cliente y el servidor de destino requiere certificados de cliente, no se autentica el remitente y el envío de SOAP adaptador no puede enviar el mensaje y seguirá la lógica de reintentos estándar.</span><span class="sxs-lookup"><span data-stu-id="32903-105">If you do not specify a client certificate and the destination server requires client certificates, the sender is not authenticated and the SOAP send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="32903-106">El adaptador de envío SOAP utilizará el certificado de cliente ubicado en el almacén personal de la cuenta en la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32903-106">The SOAP send adapter uses the client certificate from the Personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="32903-107">El adaptador de SOAP especifica el certificado por su huella digital.</span><span class="sxs-lookup"><span data-stu-id="32903-107">The SOAP adapter specifies the certificate by its thumbprint.</span></span> <span data-ttu-id="32903-108">Si, por cualquier motivo, el adaptador de envío SOAP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.</span><span class="sxs-lookup"><span data-stu-id="32903-108">If the SOAP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
 <span data-ttu-id="32903-109">Cuando se usa un adaptador SOAP para enviar un mensaje firmado o cifrado, configurar la propiedad de transporte de SOAP de huella digital de certificado de cliente para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="32903-109">When using a SOAP adapter to send an encrypted or signed message, configure the Client Certificate Thumbprint SOAP transport property for the send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32903-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="32903-110">Prerequisites</span></span>  
 <span data-ttu-id="32903-111">Para llevar a cabo el procedimiento de este tema, debe iniciar sesión como un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="32903-111">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a><span data-ttu-id="32903-112">Para configurar BizTalk Server para enviar mensajes a través de una conexión de SOAP</span><span class="sxs-lookup"><span data-stu-id="32903-112">To configure BizTalk Server to send messages over a SOAP connection</span></span>  
  
1.  <span data-ttu-id="32903-113">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, cree un nuevo puerto de envío SOAP o abra las propiedades de puerto de envío de un SOAP existente.</span><span class="sxs-lookup"><span data-stu-id="32903-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new SOAP send port or open the properties for an existing SOAP send port.</span></span>  
  
2.  <span data-ttu-id="32903-114">Haga clic en **configurar** en el **transporte** sección de la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="32903-114">Click **Configure** in the **Transport** section of the **Send Port Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="32903-115">En el **General** ficha **tipo de autenticación**, seleccione **Anonymous**, **básica**, **implícita**, o **NTLM**.</span><span class="sxs-lookup"><span data-stu-id="32903-115">On the **General** tab, in **Authentication type**, select **Anonymous**, **Basic**, **Digest**, or **NTLM**.</span></span>  
  
4.  <span data-ttu-id="32903-116">Si el tipo de autenticación es **básica** o **implícita**, seleccionar una opción **no use Single Sign-On** (en cuyo caso debe especificar el nombre de usuario y contraseña) o seleccione  **Use Single Sign-On** (en cuyo caso debe seleccionar la aplicación afiliada).</span><span class="sxs-lookup"><span data-stu-id="32903-116">If the authentication type is **Basic** or **Digest**, either select **Do not use Single Sign-On** (in which case you must specify the user name and password) or select **Use Single Sign-On** (in which case you must select the Affiliate Application).</span></span>  
  
5.  <span data-ttu-id="32903-117">En **huella digital de certificado de cliente SSL**, especifique la huella digital adecuada.</span><span class="sxs-lookup"><span data-stu-id="32903-117">In **SSL client certificate thumbprint**, enter the appropriate thumbprint.</span></span>  
  
6.  <span data-ttu-id="32903-118">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="32903-118">Click **OK**, and then click **OK** again.</span></span>