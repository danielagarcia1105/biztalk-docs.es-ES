---
title: Cómo deshabilitar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7df6e78-6d18-443d-82dc-4351c20a8c4e
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 6bae89d2a05ec34095e0fa2ac3feafc7b88b894e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-an-affiliate-application"></a><span data-ttu-id="a9e77-102">Cómo deshabilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="a9e77-102">How to Disable an Affiliate Application</span></span>
<span data-ttu-id="a9e77-103">Use el complemento MMC o la **disableapp** comando para deshabilitar la aplicación afiliada especificada.</span><span class="sxs-lookup"><span data-stu-id="a9e77-103">Use the MMC Snap-In or the **disableapp** command to disable the specified affiliate application.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="a9e77-104">Para deshabilitar una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="a9e77-104">To disable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="a9e77-105">Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="a9e77-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="a9e77-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="a9e77-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="a9e77-107">Haga clic en la aplicación afiliada y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="a9e77-107">Right-click the affiliate application, and then click **Disable**.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="a9e77-108">Para deshabilitar una aplicación afiliada desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="a9e77-108">To disable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="a9e77-109">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a9e77-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="a9e77-110">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="a9e77-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="a9e77-111">El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="a9e77-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a9e77-112">Tipo de `ssomanage –disableapp <application name>`, donde \< *nombre de la aplicación*> es el nombre de la aplicación afiliada que desea deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="a9e77-112">Type `ssomanage –disableapp <application name>`, where \<*application name*> is the name of the affiliate application you want to disable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e77-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9e77-113">See Also</span></span>  
 <span data-ttu-id="a9e77-114">[Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a9e77-114">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="a9e77-115">[Cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="a9e77-115">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="a9e77-116">[Administrar asignaciones de usuario](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="a9e77-116">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="a9e77-117">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="a9e77-117">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)