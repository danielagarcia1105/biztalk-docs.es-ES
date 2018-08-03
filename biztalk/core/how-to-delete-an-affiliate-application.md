---
title: Cómo eliminar una aplicación afiliada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97315d21e3793ec6a282deb5f8cdd69d79ab7491
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003325"
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="22c6d-102">Cómo eliminar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="22c6d-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="22c6d-103">Puede utilizar el Complemento MMC o la línea de comandos para eliminar la aplicación afiliada de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="22c6d-103">You can use the MMC Snap-In or the command line to delete the specified affiliate application from the SSO database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22c6d-104">Cuando se elimina una aplicación afiliada, el sistema SSO elimina automáticamente todas las asignaciones asociadas a dicha aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c6d-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22c6d-105">Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.</span><span class="sxs-lookup"><span data-stu-id="22c6d-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="22c6d-106">Para eliminar una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="22c6d-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="22c6d-107">En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="22c6d-107">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="22c6d-108">En el panel de ámbito del complemento de MMC, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="22c6d-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="22c6d-109">Haga clic en la aplicación afiliada y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="22c6d-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="22c6d-110">Para eliminar una aplicación afiliada con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="22c6d-110">To delete an affiliate application using the command line</span></span>  
  
1. <span data-ttu-id="22c6d-111">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="22c6d-111">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="22c6d-112">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="22c6d-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="22c6d-113">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="22c6d-113">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="22c6d-114">Tipo ** ssomanage-deleteapp *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea quitar de la Base de datos SSO.</span><span class="sxs-lookup"><span data-stu-id="22c6d-114">Type **ssomanage –deleteapp *\<application name\>**<em>, where *\<application name\></em> is the name of the affiliate application you want to remove from the SSO database.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="22c6d-115">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="22c6d-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c6d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="22c6d-116">See Also</span></span>  
 <span data-ttu-id="22c6d-117">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="22c6d-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="22c6d-118">[Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="22c6d-118">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="22c6d-119">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="22c6d-119">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="22c6d-120">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="22c6d-120">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)