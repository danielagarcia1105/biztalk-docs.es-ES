---
title: Cómo administrar asignaciones de usuario para el Host de SSO iniciado por | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, host initiated SSO
- host initiated SSO, user maps
ms.assetid: 6b05249e-da35-475b-9c23-5eb556013d57
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad232bf81fff96e6cabf367e9c591d02d4296151
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006709"
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a><span data-ttu-id="2b2e2-102">Cómo administrar asignaciones de usuario para el Host de SSO iniciado por</span><span class="sxs-lookup"><span data-stu-id="2b2e2-102">How to Manage User Mappings for Host Initiated SSO</span></span>
<span data-ttu-id="2b2e2-103">Utilice los procedimientos siguientes para crear asignaciones, definir credenciales y habilitar o deshabilitar asignaciones.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-103">Use the following procedures to create mappings, set credentials, and enable or disable mapping.</span></span>  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="2b2e2-104">Para administrar asignaciones de usuarios para SSO iniciado por host utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="2b2e2-104">To manage user mappings for host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="2b2e2-105">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="2b2e2-106">En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="2b2e2-107">En el panel de ámbito, haga clic en **aplicaciones afiliadas**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="2b2e2-108">En el panel de detalles, haga clic con el botón secundario en la aplicación afiliada, y después seleccione la opción de menú apropiada, según la acción que desee llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-108">In the details pane, right-click the affiliate application, and then choose the appropriate menu item for your action.</span></span>  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="2b2e2-109">Crear asignaciones en SSO iniciado por host utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2b2e2-109">To create mappings in host initiated SSO using the command line</span></span>  
  
1. <span data-ttu-id="2b2e2-110">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-110">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="2b2e2-111">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="2b2e2-112">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b2e2-113">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="2b2e2-114">Tipo **ssomanage – createmappings \<archivo de asignación\>**, donde **archivo de asignación >** es el nombre del archivo xml.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-114">Type **ssomanage –createmappings \<mapping file\>**, where **mapping file>** is the name of the xml file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2b2e2-115">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
    <span data-ttu-id="2b2e2-116">A continuación se muestra un ejemplo de archivo de asignaciones:</span><span class="sxs-lookup"><span data-stu-id="2b2e2-116">A sample mapping file is shown below:</span></span>  
  
   ```  
   <SSO>  
     <mapping>  
       <windowsDomain>DomainName</windowsDomain>  
       <windowsUserId>UserA</windowsUserId>  
       <externalApplication>SSOApplication</externalApplication>  
   <externalUserId>ExternalUserID that corresponds to UserA</externalUserId>  
     </mapping>  
   </SSO>  
  
   ```  
  
   <span data-ttu-id="2b2e2-117">Cuando la característica Validar contraseña está habilitada en la aplicación afiliada, es necesario definir las credenciales tal como se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="2b2e2-117">When the Validate Password feature is enabled for the affiliate application, it is necessary to set credentials, as follows:</span></span>  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="2b2e2-118">Para definir las credenciales para aplicaciones afiliadas de tipo individual utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2b2e2-118">To set credentials for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="2b2e2-119">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-119">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b2e2-120">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-120">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b2e2-121">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-121">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b2e2-122">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-122">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b2e2-123">Tipo **ssomanage - setcredentials \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-123">Type **ssomanage -setcredentials \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b2e2-124">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="2b2e2-125">Para definir las credenciales para aplicaciones afiliadas de tipo grupo de hosts utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2b2e2-125">To set credentials for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="2b2e2-126">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-126">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b2e2-127">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-127">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b2e2-128">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b2e2-129">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-129">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b2e2-130">Tipo **ssomanage - setcredentials \<nombre de cuenta externa\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-130">Type **ssomanage -setcredentials \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b2e2-131">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="2b2e2-132">Para habilitar las asignaciones de las aplicaciones afiliadas de tipo individual mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2b2e2-132">To enable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="2b2e2-133">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b2e2-134">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-134">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b2e2-135">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-135">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b2e2-136">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-136">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b2e2-137">Tipo **ssomanage - enablemapping \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-137">Type **ssomanage -enablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b2e2-138">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-138">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="2b2e2-139">Para deshabilitar las asignaciones para aplicaciones afiliadas de tipo individual utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2b2e2-139">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="2b2e2-140">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-140">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b2e2-141">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-141">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b2e2-142">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-142">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b2e2-143">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-143">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b2e2-144">Tipo **ssomanage - disablemapping \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-144">Type **ssomanage -disablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b2e2-145">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-145">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="2b2e2-146">Para habilitar las asignaciones para aplicaciones afiliadas de tipo grupo de hosts utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2b2e2-146">To enable mappings for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="2b2e2-147">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-147">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b2e2-148">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-148">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b2e2-149">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-149">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b2e2-150">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-150">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b2e2-151">Tipo **ssomanage - enablemapping \<nombre de cuenta externa\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-151">Type **ssomanage -enablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b2e2-152">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-152">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="2b2e2-153">Para deshabilitar las asignaciones para aplicaciones afiliadas de tipo individual utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2b2e2-153">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="2b2e2-154">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-154">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b2e2-155">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-155">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b2e2-156">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-156">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b2e2-157">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-157">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b2e2-158">Tipo **ssomanage - disablemapping \<nombre de cuenta externa\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-158">Type **ssomanage -disablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b2e2-159">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="2b2e2-159">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2e2-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b2e2-160">See Also</span></span>  
 [<span data-ttu-id="2b2e2-161">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="2b2e2-161">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)