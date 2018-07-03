---
title: Solución de problemas de actualización y migración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad7f575038257bc876e3fc822e624e91c93451ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994645"
---
# <a name="migration-and-upgrade-troubleshooting"></a><span data-ttu-id="25ed2-102">Solución de problemas de actualización y migración</span><span class="sxs-lookup"><span data-stu-id="25ed2-102">Migration and Upgrade Troubleshooting</span></span>
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a><span data-ttu-id="25ed2-103">Los ensamblados tienen que anular la implementación antes de una actualización</span><span class="sxs-lookup"><span data-stu-id="25ed2-103">Assemblies need to be undeployed before an upgrade</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="25ed2-104">Síntoma</span><span class="sxs-lookup"><span data-stu-id="25ed2-104">Symptom</span></span>  
 <span data-ttu-id="25ed2-105">Al intentar actualizar A4SWIFT, se produce un error en el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="25ed2-105">When you attempt to upgrade A4SWIFT, the upgrade process fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="25ed2-106">Causa posible</span><span class="sxs-lookup"><span data-stu-id="25ed2-106">Possible Cause</span></span>  
 <span data-ttu-id="25ed2-107">Los siguientes ensamblados de A4SWIFT todavía se implementan cuando se realiza la actualización: Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration, Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas, Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span><span class="sxs-lookup"><span data-stu-id="25ed2-107">The following A4SWIFT assemblies are still deployed when the upgrade is done:  Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration, Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas, Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25ed2-108">No es necesario volver a implementar Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.</span><span class="sxs-lookup"><span data-stu-id="25ed2-108">You do not have to redeploy Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.</span></span> <span data-ttu-id="25ed2-109">El programa de instalación vuelve a implementar ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="25ed2-109">The installation program redeploys that assembly.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="25ed2-110">Solución</span><span class="sxs-lookup"><span data-stu-id="25ed2-110">Solution</span></span>  
 <span data-ttu-id="25ed2-111">Anule manualmente la implementación de los ensamblados de A4SWIFT cuatro en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ed2-111">Manually undeploy the four A4SWIFT assemblies in the following order:</span></span>  
  
- <span data-ttu-id="25ed2-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span><span class="sxs-lookup"><span data-stu-id="25ed2-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span></span>  
  
- <span data-ttu-id="25ed2-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span><span class="sxs-lookup"><span data-stu-id="25ed2-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span></span>  
  
- <span data-ttu-id="25ed2-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span><span class="sxs-lookup"><span data-stu-id="25ed2-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
  <span data-ttu-id="25ed2-115">Después de haber actualizado, volver a implementar estos ensamblados (con **BTSTask.exe**) en el orden inverso.</span><span class="sxs-lookup"><span data-stu-id="25ed2-115">After you have upgraded, redeploy these assemblies (using **BTSTask.exe**) in the reverse order.</span></span>  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a><span data-ttu-id="25ed2-116">Una actualización quita los permisos de acceso para la carpeta del servicio</span><span class="sxs-lookup"><span data-stu-id="25ed2-116">An upgrade removes access permissions for the Service folder</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="25ed2-117">Síntoma</span><span class="sxs-lookup"><span data-stu-id="25ed2-117">Symptom</span></span>  
 <span data-ttu-id="25ed2-118">Después de actualizar a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], el permiso de acceso para el Acelerador de BizTalk para la carpeta SWIFT\Service %programfiles%\Microsoft es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="25ed2-118">After an upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the access permission for the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder is incorrect.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="25ed2-119">Causa posible</span><span class="sxs-lookup"><span data-stu-id="25ed2-119">Possible Cause</span></span>  
 <span data-ttu-id="25ed2-120">Cuando se actualiza a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], el proceso de actualización quita los permisos de acceso para los grupos Administradores de A4SWIFT y los usuarios de A4SWIFT el Acelerador de BizTalk para la carpeta SWIFT\Service %programfiles%\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25ed2-120">When you upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the upgrade process removes access permissions for the A4SWIFT Administrators and A4SWIFT Users groups from the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="25ed2-121">Solución</span><span class="sxs-lookup"><span data-stu-id="25ed2-121">Solution</span></span>  
 <span data-ttu-id="25ed2-122">Si se produce este problema, establezca manualmente los siguientes permisos de acceso para la carpeta del servicio:</span><span class="sxs-lookup"><span data-stu-id="25ed2-122">If you encounter this problem, manually set the following access permissions for the Service folder:</span></span>  
  
|<span data-ttu-id="25ed2-123">Nombre de usuario o grupo</span><span class="sxs-lookup"><span data-stu-id="25ed2-123">Group or User Name</span></span>|<span data-ttu-id="25ed2-124">Permiso</span><span class="sxs-lookup"><span data-stu-id="25ed2-124">Permission</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="25ed2-125">Administradores de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="25ed2-125">A4SWIFT Administrators</span></span>|<span data-ttu-id="25ed2-126">Control total</span><span class="sxs-lookup"><span data-stu-id="25ed2-126">Full Control</span></span>|  
|<span data-ttu-id="25ed2-127">Usuarios de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="25ed2-127">A4SWIFT Users</span></span>|<span data-ttu-id="25ed2-128">Leer y ejecutar</span><span class="sxs-lookup"><span data-stu-id="25ed2-128">Read & Execute</span></span>|  
  
 <span data-ttu-id="25ed2-129">Para establecer estos permisos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ed2-129">To set these permissions, proceed as follows:</span></span>  
  
 <span data-ttu-id="25ed2-130">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, desplácese a *% programfiles %* \Microsoft BizTalk Accelerator para SWIFT\Service.</span><span class="sxs-lookup"><span data-stu-id="25ed2-130">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service.</span></span>  
  
1.  <span data-ttu-id="25ed2-131">Haga clic en la carpeta del servicio, haga clic en **propiedades**y, a continuación, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="25ed2-131">Right-click the Service folder, click **Properties**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="25ed2-132">En el panel de nombres de usuario o grupo del cuadro de diálogo Propiedades del servicio, haga clic en **agregar**, escriba ***\<nombre del servidor\>* administradores \A4SWIFT**y, a continuación, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="25ed2-132">In the Group or user names pane of the Service Properties dialog box, click **Add**, enter ***\<server name\>*\A4SWIFT Administrators**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25ed2-133">Si el grupo de administradores de A4SWIFT es un grupo de dominio, escriba ***\<nombre de dominio\>* administradores \A4SWIFT**.</span><span class="sxs-lookup"><span data-stu-id="25ed2-133">If the A4SWIFT Administrators group is a domain group, enter ***\<domain name\>*\A4SWIFT Administrators**.</span></span>  
  
3.  <span data-ttu-id="25ed2-134">Repita el paso 2 para ***\<nombre del servidor\>* \A4SWIFT usuarios**, o  **\< *nombre de dominio*\>\A4SWIFT usuarios** si el Grupo de usuarios de A4SWIFT es un grupo de dominio.</span><span class="sxs-lookup"><span data-stu-id="25ed2-134">Repeat step 2 for ***\<server name\>*\A4SWIFT Users**, or **\<*domain name*\>\A4SWIFT Users** if the A4SWIFT Users group is a domain group.</span></span>  
  
4.  <span data-ttu-id="25ed2-135">En el panel de nombres de usuario o grupo, seleccione **A4SWIFT administradores**.</span><span class="sxs-lookup"><span data-stu-id="25ed2-135">In the Group or user names pane, select **A4SWIFT Administrators**.</span></span> <span data-ttu-id="25ed2-136">En el panel permisos, seleccione **permitir** para **Control total**.</span><span class="sxs-lookup"><span data-stu-id="25ed2-136">In the Permissions pane, select **Allow** for **Full Control**.</span></span>  
  
5.  <span data-ttu-id="25ed2-137">En el panel de nombres de usuario o grupo, seleccione **los usuarios de A4SWIFT**.</span><span class="sxs-lookup"><span data-stu-id="25ed2-137">In the Group or user names pane, select **A4SWIFT Users**.</span></span> <span data-ttu-id="25ed2-138">En el panel permisos, haga clic en **permitir** para **lectura y ejecución**, **mostrar contenido de carpetas**, y **lectura**.</span><span class="sxs-lookup"><span data-stu-id="25ed2-138">In the Permissions pane, click **Allow** for **Read & Execute**, **List Folder Contents**, and **Read**.</span></span>  
  
6.  <span data-ttu-id="25ed2-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25ed2-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ed2-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="25ed2-140">See Also</span></span>  
 [<span data-ttu-id="25ed2-141">Solución de problemas: problemas y soluciones</span><span class="sxs-lookup"><span data-stu-id="25ed2-141">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)