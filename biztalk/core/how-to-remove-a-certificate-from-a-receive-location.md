---
title: Cómo quitar un certificado desde una ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 717d41bf-4260-4df4-9d0a-07243bb9b12c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e70cd846c364d52544bf8504d42132dd35fe65d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254540"
---
# <a name="how-to-remove-a-certificate-from-a-receive-location"></a><span data-ttu-id="50bf2-102">Cómo quitar un certificado de una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="50bf2-102">How to Remove a Certificate from a Receive Location</span></span>
<span data-ttu-id="50bf2-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para quitar un certificado de seguridad de una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="50bf2-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a receive location.</span></span> <span data-ttu-id="50bf2-104">Al hacerlo, la ubicación de recepción dejará de cifrar mensajes; los mensajes se enviarán en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="50bf2-104">When you do this, the receive location will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="50bf2-105">Cuando se quita un certificado de una ubicación de recepción, no se quita del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="50bf2-105">Removing a certificate from a receive location does not remove it from the certificate store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="50bf2-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="50bf2-106">Prerequisites</span></span>  
 <span data-ttu-id="50bf2-107">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="50bf2-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="50bf2-108">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="50bf2-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-receive-location"></a><span data-ttu-id="50bf2-109">Para quitar un certificado de una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="50bf2-109">To remove a certificate from a receive location</span></span>  
  
1.  <span data-ttu-id="50bf2-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="50bf2-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="50bf2-111">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee quitar un certificado de una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="50bf2-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a receive location.</span></span>  
  
3.  <span data-ttu-id="50bf2-112">Expanda **ubicaciones de recepción**, haga clic en la ubicación de recepción, haga clic en **propiedades**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="50bf2-112">Expand **Receive Locations**, right-click the receive location, click **Properties**, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="50bf2-113">Haga clic en **quitar certificado**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="50bf2-113">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bf2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="50bf2-114">See Also</span></span>  
 [<span data-ttu-id="50bf2-115">Administrar ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="50bf2-115">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)