---
title: Cómo deshabilitar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, applications
- managing [SSO applications], disabling
- applications [SSO], disabling
ms.assetid: febf1687-f0d0-4f87-b462-23535bbddf6d
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09efa7dd00f563b8b02469909d2105d443438e95
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-an-affiliate-application"></a><span data-ttu-id="9eab3-102">Cómo deshabilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="9eab3-102">How to Disable an Affiliate Application</span></span>
<span data-ttu-id="9eab3-103">Puede utilizar el Complemento MMC o la línea de comandos para deshabilitar la aplicación afiliada especificada.</span><span class="sxs-lookup"><span data-stu-id="9eab3-103">You can use the MMC Snap-In or the command line to disable the specified affiliate application.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="9eab3-104">Para deshabilitar una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="9eab3-104">To disable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="9eab3-105">En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="9eab3-105">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="9eab3-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="9eab3-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="9eab3-107">Haga clic en la aplicación afiliada y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="9eab3-107">Right-click the affiliate application, and then click **Disable**.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="9eab3-108">Para deshabilitar una aplicación afiliada desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9eab3-108">To disable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="9eab3-109">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9eab3-109">Click **Start**, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="9eab3-110">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="9eab3-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9eab3-111">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="9eab3-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="9eab3-112">Tipo **ssomanage-disableapp *\<nombre de la aplicación\>***, donde \<*nombre de la aplicación* \> es el nombre de la aplicación afiliada ¿desea deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="9eab3-112">Type **ssomanage –disableapp *\<application name\>***, where \<*application name*\> is the name of the affiliate application you want to disable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9eab3-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9eab3-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eab3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9eab3-114">See Also</span></span>  
 <span data-ttu-id="9eab3-115">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="9eab3-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="9eab3-116">[Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="9eab3-116">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="9eab3-117">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="9eab3-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="9eab3-118">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="9eab3-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)