---
title: Cómo quitar un certificado de un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4efc52ba5531bac17fa244edfbf7e197fa0028ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980997"
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="9e0cc-102">Cómo quitar un certificado de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="9e0cc-102">How to Remove a Certificate from a Send Port</span></span>
<span data-ttu-id="9e0cc-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para quitar un certificado de seguridad de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a send port.</span></span> <span data-ttu-id="9e0cc-104">Al hacerlo, el puerto de envío dejará de cifrar mensajes; los mensajes se enviarán en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-104">When you do this, the send port will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="9e0cc-105">Cuando se quita un certificado de un puerto de envío, no se quita del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-105">Removing a certificate from a send port does not remove it from the certificate store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e0cc-106">El desarrollador de aplicaciones puede quitar un certificado de seguridad de un puerto de envío durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-106">The application developer can remove a security certificate from a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e0cc-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e0cc-107">Prerequisites</span></span>  
 <span data-ttu-id="9e0cc-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9e0cc-109">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="9e0cc-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="9e0cc-110">Para quitar un certificado de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="9e0cc-110">To remove a certificate from a send port</span></span>  
  
1. <span data-ttu-id="9e0cc-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9e0cc-112">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee quitar un certificado de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a send port.</span></span>  
  
3. <span data-ttu-id="9e0cc-113">Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-113">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificates**.</span></span>  
  
4. <span data-ttu-id="9e0cc-114">Haga clic en **quitar certificado**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e0cc-114">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0cc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e0cc-115">See Also</span></span>  
 [<span data-ttu-id="9e0cc-116">Creación y configuración de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="9e0cc-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)