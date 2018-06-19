---
title: Cómo habilitar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 051bc35f-55e6-4811-9559-b1bb66a570ce
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 53dcd9886bc808f84b112146971a6f9519c404e2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250936"
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="59a01-102">Cómo habilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="59a01-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="59a01-103">Puede usar el complemento MMC o la **enableapp** comando para habilitar la aplicación afiliada especificada.</span><span class="sxs-lookup"><span data-stu-id="59a01-103">You can use the MMC Snap-In or the **enableapp** command to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="59a01-104">Para habilitar una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="59a01-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="59a01-105">Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="59a01-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="59a01-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="59a01-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="59a01-107">Haga clic en la aplicación afiliada y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="59a01-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="59a01-108">Para habilitar una aplicación afiliada desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="59a01-108">To enable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="59a01-109">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="59a01-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="59a01-110">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="59a01-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="59a01-111">El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="59a01-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="59a01-112">Tipo de `ssomanage –enableapp <application name>`, donde \< *nombre de la aplicación*> es el nombre de la aplicación afiliada que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="59a01-112">Type `ssomanage –enableapp <application name>`, where \<*application name*> is the name of the affiliate application you want to enable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a01-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="59a01-113">See Also</span></span>  
 <span data-ttu-id="59a01-114">[Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="59a01-114">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="59a01-115">[Cómo crear una aplicación afiliada](../esso/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="59a01-115">[How to Create an Affiliate Application](../esso/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="59a01-116">[Administrar asignaciones de usuario](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="59a01-116">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="59a01-117">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="59a01-117">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)