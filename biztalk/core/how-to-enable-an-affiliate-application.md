---
title: Cómo habilitar una aplicación afiliada | Microsoft Docs
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb36c7c8d083cb72cd92cc90c088c7d8a35a9731
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004197"
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="a5dbc-102">Cómo habilitar una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="a5dbc-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="a5dbc-103">Utilice el Complemento MMC o la línea de comandos para habilitar la aplicación afiliada especificada.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-103">You can use the MMC Snap-In or the command line to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="a5dbc-104">Para habilitar una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="a5dbc-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="a5dbc-105">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="a5dbc-106">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="a5dbc-107">Haga clic en la aplicación afiliada y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="a5dbc-108">Para habilitar una aplicación afiliada desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="a5dbc-108">To enable an affiliate application using the command line</span></span>  
  
1. <span data-ttu-id="a5dbc-109">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-109">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="a5dbc-110">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a5dbc-111">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="a5dbc-112">Tipo <strong>ssomanage-enableapp  *\<nombre de la aplicación\></strong><em>, donde \<</em> nombre de la aplicación* \> es el nombre de la aplicación afiliada que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-112">Type <strong>ssomanage –enableapp *\<application name\></strong><em>, where \<</em>application name*\> is the name of the affiliate application you want to enable.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a5dbc-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dbc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5dbc-114">See Also</span></span>  
 <span data-ttu-id="a5dbc-115">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a5dbc-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="a5dbc-116">[Cómo crear una aplicación afiliada](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="a5dbc-116">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="a5dbc-117">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="a5dbc-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="a5dbc-118">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="a5dbc-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)