---
title: Cómo eliminar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec290d38-0220-4bf2-b596-2d6453e51c8d
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: d0632f7e4217cb9bbccd2ee604688f22eb6de348
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250984"
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="fe747-102">Cómo eliminar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="fe747-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="fe747-103">Use el complemento MMC o la **deleteapps** comando para eliminar la aplicación afiliada especificada de la base de datos de credenciales.</span><span class="sxs-lookup"><span data-stu-id="fe747-103">Use the MMC Snap-In or the **deleteapps** command to delete the specified affiliate application from the Credential database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe747-104">Cuando se elimina una aplicación afiliada, el sistema SSO elimina automáticamente todas las asignaciones asociadas a dicha aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe747-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe747-105">Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.</span><span class="sxs-lookup"><span data-stu-id="fe747-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="fe747-106">Para eliminar una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="fe747-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="fe747-107">Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="fe747-107">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="fe747-108">En el panel de ámbito del complemento de MMC, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="fe747-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="fe747-109">Haga clic en la aplicación afiliada y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fe747-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="fe747-110">Para eliminar una aplicación afiliada con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="fe747-110">To delete an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="fe747-111">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fe747-111">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="fe747-112">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="fe747-112">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="fe747-113">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="fe747-113">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fe747-114">Tipo de `ssomanage –deleteapp <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea quitar de la base de datos de credenciales.</span><span class="sxs-lookup"><span data-stu-id="fe747-114">Type `ssomanage –deleteapp <application name>`, where *\<application name>* is the name of the affiliate application you want to remove from the Credential database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe747-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe747-115">See Also</span></span>  
 <span data-ttu-id="fe747-116">[Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fe747-116">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="fe747-117">[Cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="fe747-117">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="fe747-118">[Administrar asignaciones de usuario](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="fe747-118">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="fe747-119">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="fe747-119">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)