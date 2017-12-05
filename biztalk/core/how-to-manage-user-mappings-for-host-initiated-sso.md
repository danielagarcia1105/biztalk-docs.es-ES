---
title: "Cómo administrar las asignaciones de usuario para el Host para SSO iniciado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, host initiated SSO
- host initiated SSO, user maps
ms.assetid: 6b05249e-da35-475b-9c23-5eb556013d57
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bf65bdb3de30d5b701946215b5c7ae7d40d828
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a><span data-ttu-id="aeddf-102">Cómo administrar las asignaciones de usuario para el Host para SSO iniciado</span><span class="sxs-lookup"><span data-stu-id="aeddf-102">How to Manage User Mappings for Host Initiated SSO</span></span>
<span data-ttu-id="aeddf-103">Utilice los procedimientos siguientes para crear asignaciones, definir credenciales y habilitar o deshabilitar asignaciones.</span><span class="sxs-lookup"><span data-stu-id="aeddf-103">Use the following procedures to create mappings, set credentials, and enable or disable mapping.</span></span>  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="aeddf-104">Para administrar asignaciones de usuarios para SSO iniciado por host utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="aeddf-104">To manage user mappings for host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="aeddf-105">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="aeddf-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="aeddf-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="aeddf-107">En el panel de ámbito, haga clic en **aplicaciones afiliadas**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="aeddf-108">En el panel de detalles, haga clic con el botón secundario en la aplicación afiliada, y después seleccione la opción de menú apropiada, según la acción que desee llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="aeddf-108">In the details pane, right-click the affiliate application, and then choose the appropriate menu item for your action.</span></span>  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="aeddf-109">Crear asignaciones en SSO iniciado por host utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="aeddf-109">To create mappings in host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="aeddf-110">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="aeddf-111">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="aeddf-112">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aeddf-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aeddf-113">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aeddf-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="aeddf-114">Tipo de **ssomanage – createmappings \<archivo de asignación\>**, donde **archivo de asignación >** es el nombre del archivo xml.</span><span class="sxs-lookup"><span data-stu-id="aeddf-114">Type **ssomanage –createmappings \<mapping file\>**, where **mapping file>** is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aeddf-115">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeddf-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="aeddf-116">A continuación se muestra un ejemplo de archivo de asignaciones:</span><span class="sxs-lookup"><span data-stu-id="aeddf-116">A sample mapping file is shown below:</span></span>  
  
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
  
 <span data-ttu-id="aeddf-117">Cuando la característica Validar contraseña está habilitada en la aplicación afiliada, es necesario definir las credenciales tal como se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="aeddf-117">When the Validate Password feature is enabled for the affiliate application, it is necessary to set credentials, as follows:</span></span>  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="aeddf-118">Para definir las credenciales para aplicaciones afiliadas de tipo individual utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="aeddf-118">To set credentials for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="aeddf-119">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-119">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="aeddf-120">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-120">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="aeddf-121">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aeddf-121">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aeddf-122">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aeddf-122">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="aeddf-123">Tipo de **ssomanage - setcredentials \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-123">Type **ssomanage -setcredentials \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aeddf-124">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeddf-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="aeddf-125">Para definir las credenciales para aplicaciones afiliadas de tipo grupo de hosts utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="aeddf-125">To set credentials for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="aeddf-126">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-126">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="aeddf-127">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-127">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="aeddf-128">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aeddf-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aeddf-129">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aeddf-129">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="aeddf-130">Tipo de **ssomanage - setcredentials \<nombre de cuenta externa\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-130">Type **ssomanage -setcredentials \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aeddf-131">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeddf-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="aeddf-132">Para habilitar las asignaciones de las aplicaciones afiliadas de tipo individual mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="aeddf-132">To enable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="aeddf-133">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="aeddf-134">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-134">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="aeddf-135">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aeddf-135">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aeddf-136">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aeddf-136">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="aeddf-137">Tipo de **ssomanage - enablemapping \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-137">Type **ssomanage -enablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aeddf-138">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeddf-138">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="aeddf-139">Para deshabilitar las asignaciones para aplicaciones afiliadas de tipo individual utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="aeddf-139">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="aeddf-140">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-140">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="aeddf-141">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-141">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="aeddf-142">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aeddf-142">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aeddf-143">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aeddf-143">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="aeddf-144">Tipo de **ssomanage - disablemapping \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-144">Type **ssomanage -disablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aeddf-145">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeddf-145">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="aeddf-146">Para habilitar las asignaciones para aplicaciones afiliadas de tipo grupo de hosts utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="aeddf-146">To enable mappings for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="aeddf-147">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-147">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="aeddf-148">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-148">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="aeddf-149">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aeddf-149">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aeddf-150">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aeddf-150">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="aeddf-151">Tipo de **ssomanage - enablemapping \<nombre de cuenta externa\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-151">Type **ssomanage -enablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aeddf-152">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeddf-152">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="aeddf-153">Para deshabilitar las asignaciones para aplicaciones afiliadas de tipo individual utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="aeddf-153">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="aeddf-154">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-154">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="aeddf-155">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-155">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="aeddf-156">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aeddf-156">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aeddf-157">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aeddf-157">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="aeddf-158">Tipo de **ssomanage - disablemapping \<nombre de cuenta externa\> \<nombre de la aplicación\>**.</span><span class="sxs-lookup"><span data-stu-id="aeddf-158">Type **ssomanage -disablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aeddf-159">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeddf-159">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeddf-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="aeddf-160">See Also</span></span>  
 [<span data-ttu-id="aeddf-161">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="aeddf-161">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)