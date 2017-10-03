---
title: "Cómo quitar un certificado de un puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5193b1b6003660aac0e0b427da0f0a338b56d8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="12b58-102">Cómo quitar un certificado de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="12b58-102">How to Remove a Certificate from a Send Port</span></span>
<span data-ttu-id="12b58-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para quitar un certificado de seguridad de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="12b58-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a send port.</span></span> <span data-ttu-id="12b58-104">Al hacerlo, el puerto de envío dejará de cifrar mensajes; los mensajes se enviarán en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="12b58-104">When you do this, the send port will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="12b58-105">Cuando se quita un certificado de un puerto de envío, no se quita del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="12b58-105">Removing a certificate from a send port does not remove it from the certificate store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12b58-106">El desarrollador de aplicaciones puede quitar un certificado de seguridad de un puerto de envío durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="12b58-106">The application developer can remove a security certificate from a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12b58-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="12b58-107">Prerequisites</span></span>  
 <span data-ttu-id="12b58-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="12b58-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="12b58-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="12b58-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="12b58-110">Para quitar un certificado de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="12b58-110">To remove a certificate from a send port</span></span>  
  
1.  <span data-ttu-id="12b58-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="12b58-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="12b58-112">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee quitar un certificado de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="12b58-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a send port.</span></span>  
  
3.  <span data-ttu-id="12b58-113">Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="12b58-113">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="12b58-114">Haga clic en **quitar certificado**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="12b58-114">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b58-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="12b58-115">See Also</span></span>  
 [<span data-ttu-id="12b58-116">Crear y configurar puertos de envío</span><span class="sxs-lookup"><span data-stu-id="12b58-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)