---
title: Cómo especificar administradores de SSO y los administradores afiliados de cuentas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- enabling, SSO
- SSO, enabling
- disabling, SSO
- SSO, disabling
- managing [SSO], configuring administrator accounts
- managing [SSO], enabling
- managing [SSO], disabling
- SSO, administrator accounts
ms.assetid: 6c300e09-b781-45de-b2da-b1083164a1c0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab6a40db19ae42f0ba4007fd8044d7d7aa086adb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968245"
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a><span data-ttu-id="6390c-102">Cómo especificar administradores de SSO y los administradores afiliados de cuentas</span><span class="sxs-lookup"><span data-stu-id="6390c-102">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>
<span data-ttu-id="6390c-103">Las cuentas de administradores de inicio de sesión único (SSO) empresarial y las cuentas de administradores afiliados pueden ser individuales o de grupo de hosts.</span><span class="sxs-lookup"><span data-stu-id="6390c-103">The Enterprise Single Sign-On (SSO) Administrators and Affiliate Administrators accounts can be host group or individual accounts.</span></span> <span data-ttu-id="6390c-104">Debe crear estas cuentas antes de configurar el sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="6390c-104">You must create these accounts before you configure the SSO system.</span></span>  
  
 <span data-ttu-id="6390c-105">Cuando utilice cuentas de dominio, deberá crear cuentas de administradores de SSO y cuentas de administradores afiliados como grupos de seguridad de dominio globales en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="6390c-105">When using domain accounts, you must create the SSO Administrators and SSO Affiliate Administrators accounts as a domain global security groups in the domain controller.</span></span> <span data-ttu-id="6390c-106">Es el administrador de dominio quien debe crear estas cuentas.</span><span class="sxs-lookup"><span data-stu-id="6390c-106">The domain administrator must create these accounts.</span></span>  
  
 <span data-ttu-id="6390c-107">Debe especificar las cuentas de administradores de SSO y las cuentas de administradores afiliados en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="6390c-107">You must specify the Single Sign-On Administrators and Affiliate Administrators accounts in the SSO database.</span></span> <span data-ttu-id="6390c-108">Deberá deshabilitar el sistema de SSO antes de actualizar la base de datos SSO con el grupo de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="6390c-108">You must disable the Single Sign-On system before you update the SSO database with the SSO Administrators group.</span></span>  
  
 <span data-ttu-id="6390c-109">El código XML siguiente muestra un ejemplo de XML para actualizar la base de datos de SSO:</span><span class="sxs-lookup"><span data-stu-id="6390c-109">The following XML code shows a sample XML for updating the SSO database:</span></span>  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  <span data-ttu-id="6390c-110">El Asistente para configuración especifica el grupo de administradores de SSO y el grupo de administradores afiliados en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="6390c-110">The Configuration Wizard automatically specifies the SSO administrator and SSO affiliate administrator groups in the SSO database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6390c-111">Si SSO no se configura, los usuarios deben comprobar si las cuentas de dominio local se van a usar en un dominio de modo combinado.</span><span class="sxs-lookup"><span data-stu-id="6390c-111">If SSO does not configure, users should check whether Domain Local Accounts are being used in a mixed-mode domain.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="6390c-112">Para deshabilitar el sistema de inicio de sesión único empresarial utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="6390c-112">To disable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="6390c-113">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="6390c-113">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="6390c-114">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="6390c-114">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="6390c-115">Haga clic en **sistema**y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="6390c-115">Right-click **System**, and then click **Disable**.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="6390c-116">Para deshabilitar el sistema de inicio de sesión único empresarial utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6390c-116">To disable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="6390c-117">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="6390c-117">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="6390c-118">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="6390c-118">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6390c-119">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="6390c-119">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="6390c-120">Tipo **ssomanage** –**disablesso**.</span><span class="sxs-lookup"><span data-stu-id="6390c-120">Type **ssomanage** –**disablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6390c-121">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6390c-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a><span data-ttu-id="6390c-122">Para actualizar la base de datos de SSO utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="6390c-122">To update the SSO database using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="6390c-123">En el **iniciar** menú, haga clic en **todos los programas**, **Microsoft Enterprise Single Sign-On**y, a continuación, **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="6390c-123">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="6390c-124">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="6390c-124">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="6390c-125">Haga clic en **sistema**y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="6390c-125">Right-click **System**, and then click **Update**.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a><span data-ttu-id="6390c-126">Para actualizar la base de datos de SSO utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6390c-126">To update the SSO database using the command line</span></span>  
  
1. <span data-ttu-id="6390c-127">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="6390c-127">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="6390c-128">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="6390c-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6390c-129">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="6390c-129">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="6390c-130">Tipo ** ssomanage – updatedb *\<archivo de actualización\>**<em>, donde *\<archivo de actualización\></em>  es la ruta de acceso y nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="6390c-130">Type **ssomanage –updatedb *\<update file\>**<em>, where *\<update file\></em> is the path and name of the XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6390c-131">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6390c-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="6390c-132">Para habilitar el sistema de inicio de sesión único empresarial utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="6390c-132">To enable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="6390c-133">En el **iniciar** menú, haga clic en **todos los programas**, **Microsoft Enterprise Single Sign-On**y, a continuación, **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="6390c-133">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="6390c-134">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="6390c-134">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="6390c-135">Haga clic en **sistema**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="6390c-135">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="6390c-136">Para habilitar el sistema de inicio de sesión único empresarial utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6390c-136">To enable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="6390c-137">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="6390c-137">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="6390c-138">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="6390c-138">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6390c-139">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="6390c-139">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="6390c-140">Tipo **ssomanage – enablesso**.</span><span class="sxs-lookup"><span data-stu-id="6390c-140">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6390c-141">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6390c-141">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6390c-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="6390c-142">See Also</span></span>  
 [<span data-ttu-id="6390c-143">Grupos de usuarios de SSO</span><span class="sxs-lookup"><span data-stu-id="6390c-143">SSO User Groups</span></span>](../core/sso-user-groups.md)