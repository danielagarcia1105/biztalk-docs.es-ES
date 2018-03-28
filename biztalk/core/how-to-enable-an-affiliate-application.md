---
title: Cómo habilitar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], enabling
- managing [SSO applications], enabling
- enabling, applications [SSO]
ms.assetid: 81c94e1b-cd3d-482e-9a78-9b1476af9e5f
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a0e4776b60b81256552552c60aa1abb8abdcde8
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="0c990-102">Cómo habilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="0c990-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="0c990-103">Utilice el Complemento MMC o la línea de comandos para habilitar la aplicación afiliada especificada.</span><span class="sxs-lookup"><span data-stu-id="0c990-103">You can use the MMC Snap-In or the command line to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="0c990-104">Para habilitar una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="0c990-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="0c990-105">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="0c990-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="0c990-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="0c990-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="0c990-107">Haga clic en la aplicación afiliada y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="0c990-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="0c990-108">Para habilitar una aplicación afiliada desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="0c990-108">To enable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="0c990-109">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="0c990-109">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="0c990-110">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="0c990-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0c990-111">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="0c990-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="0c990-112">Tipo **ssomanage-enableapp *\<nombre de la aplicación\>***, donde \<*nombre de la aplicación* \> es el nombre de la aplicación afiliada que desee Para habilitar.</span><span class="sxs-lookup"><span data-stu-id="0c990-112">Type **ssomanage –enableapp *\<application name\>***, where \<*application name*\> is the name of the affiliate application you want to enable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c990-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="0c990-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c990-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c990-114">See Also</span></span>  
 <span data-ttu-id="0c990-115">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0c990-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="0c990-116">[Cómo crear una aplicación afiliada](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="0c990-116">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="0c990-117">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="0c990-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="0c990-118">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="0c990-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)