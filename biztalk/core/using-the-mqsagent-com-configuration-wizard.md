---
title: Mediante el Asistente para configuración de MQSAgent COM + | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mqsagent.wizard
helpviewer_keywords:
- MQSeries adapters, MQSAgent COM+ Configuration Wizard
- configuring [MQSeries adapters], MQSAgent COM+ Configuration Wizard
- MQSAgent COM+ Configuration Wizard
ms.assetid: f106700a-7f57-4c83-9344-6525fc10544d
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6e8b625bcc3accbefda193c52459616691c265
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a><span data-ttu-id="cc85c-102">Mediante el Asistente para configuración de MQSAgent COM +</span><span class="sxs-lookup"><span data-stu-id="cc85c-102">Using the MQSAgent COM+ Configuration Wizard</span></span>
<span data-ttu-id="cc85c-103">El Asistente para configuración de MQSAgent COM+ permite configurar MQSAgent, la parte de aplicación COM+ (componente MQSeries) del adaptador.</span><span class="sxs-lookup"><span data-stu-id="cc85c-103">The MQSAgent COM+ Configuration Wizard configures the MQSAgent, the COM+ application (MQSeries component) part of the adapter.</span></span> <span data-ttu-id="cc85c-104">El asistente define la identidad de aplicación del componente, así como el nombre de función y los usuarios incluidos en dicha función.</span><span class="sxs-lookup"><span data-stu-id="cc85c-104">The wizard sets the application identity of the component, and the role name and users included in the role.</span></span> <span data-ttu-id="cc85c-105">El nombre del componente MQSAgent COM + creado con el Asistente de configuración de MQSAgent COM + es **MQSAgent2**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-105">The name of the MQSAgent COM+ component created with the MQSAgent COM+ Configuration Wizard is **MQSAgent2**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc85c-106">La aplicación MQSAgent COM+ se admite en un servidor de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="cc85c-106">The MQSAgent COM+ application is supported on a 64-bit Windows server.</span></span> <span data-ttu-id="cc85c-107">Se ejecutará como proceso de 32 bits en WOW64.</span><span class="sxs-lookup"><span data-stu-id="cc85c-107">It will run as a 32-bit process under WOW64.</span></span> <span data-ttu-id="cc85c-108">Un equipo basado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecute en una versión de 64 bits de Windows Server se puede comunicar con un equipo remoto de 32 bits que tenga instalado MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="cc85c-108">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-based computer that is running on a 64-bit version of Windows Server can communicate with a remote 32-bit computer that has the MQSAgent installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc85c-109">MQSeries Agent y el ejecutable del Asistente de configuración de MQSAgent COM + **MQSConfigWiz.exe** no se instalan si actualiza desde BizTalk Server 2009 a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cc85c-109">The MQSeries Agent and the MQSAgent COM+ Configuration Wizard executable **MQSConfigWiz.exe** are not installed if you upgrade from BizTalk Server 2009 to BizTalk Server.</span></span> <span data-ttu-id="cc85c-110">Después de actualizar a BizTalk Server de BizTalk Server 2009 vuelva a ejecutar el programa de instalación, seleccione la **modificar** opción y seleccione MQSeries Agent en Software adicional para instalar estos componentes.</span><span class="sxs-lookup"><span data-stu-id="cc85c-110">After upgrading to BizTalk Server from BizTalk Server 2009 re-run setup, select the **Modify** option, and select the MQSeries Agent under the Additional Software to install these components.</span></span>  
  
## <a name="to-set-the-application-identity"></a><span data-ttu-id="cc85c-111">Para definir la identidad de la aplicación</span><span class="sxs-lookup"><span data-stu-id="cc85c-111">To set the application identity</span></span>  
  
-   <span data-ttu-id="cc85c-112">Use la **identidad de aplicación** página del Asistente configuración de MQSAgent COM + para configurar la identidad de aplicación para MQSAgent como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="cc85c-112">Use the **Application Identity** page of the MQSAgent COM+ Configuration Wizard to set the application identity for the MQSAgent as follows:</span></span>  
  
    |<span data-ttu-id="cc85c-113">Use</span><span class="sxs-lookup"><span data-stu-id="cc85c-113">Use this</span></span>|<span data-ttu-id="cc85c-114">Para</span><span class="sxs-lookup"><span data-stu-id="cc85c-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cc85c-115">**Usuario interactivo**</span><span class="sxs-lookup"><span data-stu-id="cc85c-115">**Interactive User**</span></span>|<span data-ttu-id="cc85c-116">Utilizar la cuenta de inicio de sesión actual como identidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc85c-116">Select this option to use the current logon account for the application identity.</span></span>|  
    |<span data-ttu-id="cc85c-117">**Servicio local**</span><span class="sxs-lookup"><span data-stu-id="cc85c-117">**Local Service**</span></span>|<span data-ttu-id="cc85c-118">Definir la identidad de la aplicación con una cuenta de servicio integrada.</span><span class="sxs-lookup"><span data-stu-id="cc85c-118">Set the application identity to a built-in service account.</span></span>|  
    |<span data-ttu-id="cc85c-119">**Servicio de red**</span><span class="sxs-lookup"><span data-stu-id="cc85c-119">**Network Service**</span></span>|<span data-ttu-id="cc85c-120">Definir la identidad de la aplicación con una cuenta de servicio integrada con acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="cc85c-120">Set the application identity to a built-in account with network access.</span></span>|  
    |<span data-ttu-id="cc85c-121">**Este usuario**</span><span class="sxs-lookup"><span data-stu-id="cc85c-121">**This user**</span></span>|<span data-ttu-id="cc85c-122">Definir la identidad de aplicación con el nombre de usuario indicado.</span><span class="sxs-lookup"><span data-stu-id="cc85c-122">Set the application identity to the indicated user name.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="cc85c-123">Se recomienda no utilizar cuentas con permisos administrativos para definir la identidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc85c-123">It is not recommended that you use an account with administrative permissions for the application identity.</span></span> <span data-ttu-id="cc85c-124">La cuenta deberá tener el mínimo de permisos necesarios: permisos de lectura y escritura para las colas de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="cc85c-124">The account must have the minimal rights required: read and write permission for the MQSeries queues.</span></span>  
  
## <a name="to-name-the-role-and-add-users-to-it"></a><span data-ttu-id="cc85c-125">Para dar un nombre a la función y agregarle usuarios</span><span class="sxs-lookup"><span data-stu-id="cc85c-125">To name the role and add users to it</span></span>  
  
-   <span data-ttu-id="cc85c-126">Use la **nombre de la función** página del Asistente configuración de MQSAgent COM + para asignar un nombre y los usuarios a la función, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="cc85c-126">Use the **Name of Role** page of the MQSAgent COM+ Configuration Wizard  to assign a name and users to the role as follows:</span></span>  
  
    |<span data-ttu-id="cc85c-127">Use</span><span class="sxs-lookup"><span data-stu-id="cc85c-127">Use this</span></span>|<span data-ttu-id="cc85c-128">Para</span><span class="sxs-lookup"><span data-stu-id="cc85c-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cc85c-129">**Nombre de rol**</span><span class="sxs-lookup"><span data-stu-id="cc85c-129">**Name of role**</span></span>|<span data-ttu-id="cc85c-130">Escriba el nombre del rol.</span><span class="sxs-lookup"><span data-stu-id="cc85c-130">Type the name of the role.</span></span>|  
    |<span data-ttu-id="cc85c-131">**Usuarios**</span><span class="sxs-lookup"><span data-stu-id="cc85c-131">**Users**</span></span>|<span data-ttu-id="cc85c-132">Ver los usuarios que pertenecen a la función.</span><span class="sxs-lookup"><span data-stu-id="cc85c-132">Display the users that belong to the role.</span></span>|  
    |<span data-ttu-id="cc85c-133">**Agregar**</span><span class="sxs-lookup"><span data-stu-id="cc85c-133">**Add**</span></span>|<span data-ttu-id="cc85c-134">Agregar usuarios a la función.</span><span class="sxs-lookup"><span data-stu-id="cc85c-134">Add users to the role.</span></span> <span data-ttu-id="cc85c-135">Se trata de cuentas de servicio de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que usan el adaptador.</span><span class="sxs-lookup"><span data-stu-id="cc85c-135">These are the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service accounts using the adapter.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="cc85c-136">Agregue a la función sólo las cuentas que necesitan tener acceso al adaptador.</span><span class="sxs-lookup"><span data-stu-id="cc85c-136">Add to the role only accounts requiring access to the adapter.</span></span>  
  
## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a><span data-ttu-id="cc85c-137">Para definir la configuración de seguridad de MSDTC del equipo de Windows Server 2008 como No se requiere autenticación</span><span class="sxs-lookup"><span data-stu-id="cc85c-137">To set the MSDTC Security configuration on the Windows Server 2008 computer to No Authentication Required</span></span>  
 <span data-ttu-id="cc85c-138">Si la aplicación MQSAgent COM + está instalada en un [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] equipo y el adaptador de MQSeries (que se instala con BizTalk Server) se instala en un [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] equipo, la configuración de seguridad de MSDTC en el [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] equipo debe establecerse en **No se requiere autenticación**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-138">If the MQSAgent COM+ application is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computer and the MQSeries Adapter (which is installed with BizTalk Server) is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer, the MSDTC Security configuration on the [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer must be set to **No Authentication Required**.</span></span> <span data-ttu-id="cc85c-139">Siga estos pasos para establecer la configuración de seguridad de MSDTC como No se requiere autenticación:</span><span class="sxs-lookup"><span data-stu-id="cc85c-139">Follow these steps to set the MSDTC security configuration to No Authentication Required:</span></span>  
  
1.  <span data-ttu-id="cc85c-140">Haga clic en **iniciar** y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-140">Click **Start** and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="cc85c-141">Haga doble clic en **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-141">Double-click **Administrative Tools**.</span></span>  
  
3.  <span data-ttu-id="cc85c-142">Haga doble clic en **servicios de componentes** para iniciar el **servicios de componentes** interfaz de administración.</span><span class="sxs-lookup"><span data-stu-id="cc85c-142">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  
  
4.  <span data-ttu-id="cc85c-143">Expanda **servicios de componentes**, expanda **equipos**y, a continuación, expanda **Mi PC**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-143">Expand **Component Services**, expand **Computers**, and then expand **My Computer**.</span></span>  
  
5.  <span data-ttu-id="cc85c-144">Haga clic en **Mi PC** y haga clic en el **propiedades** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="cc85c-144">Right-click **My Computer** and click the **Properties** menu item.</span></span>  
  
6.  <span data-ttu-id="cc85c-145">En el **Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha y, a continuación, haga clic en **configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-145">In the **My Computer** dialog box, click the **MSDTC** tab and then click **Security Configuration**.</span></span>  
  
7.  <span data-ttu-id="cc85c-146">En el **configuración de seguridad** cuadro de diálogo, en la **comunicación con el Administrador de transacciones** sección, seleccione **No se requiere autenticación**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-146">In the **Security Configuration** dialog box, in the **Transaction Manager Communication** section, select **No Authentication Required**.</span></span> <span data-ttu-id="cc85c-147">Si aparece un cuadro de diálogo, haga clic en **Sí** reiniciar el Service DTC MS.</span><span class="sxs-lookup"><span data-stu-id="cc85c-147">If you are prompted with a dialog box, click **Yes** to restart the MS DTC Service.</span></span>  
  
8.  <span data-ttu-id="cc85c-148">Una vez reiniciado el servicio MS DTC, haga clic en **Aceptar** y haga clic en **Aceptar** otra vez para cerrar el **Mi PC** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cc85c-148">After the MS DTC service has restarted, click **OK** and click **OK** again to close the **My Computer** dialog box.</span></span>  
  
9. <span data-ttu-id="cc85c-149">Cerrar la **servicios de componentes** interfaz de administración.</span><span class="sxs-lookup"><span data-stu-id="cc85c-149">Close the **Component Services** management interface.</span></span>  
  
## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a><span data-ttu-id="cc85c-150">Para configurar los componentes de tiempo de ejecución de MQSAgent para ejecutarlos en un conjunto de credenciales alternativas</span><span class="sxs-lookup"><span data-stu-id="cc85c-150">To configure the MQSAgent runtime components to run under an alternative set of credentials</span></span>  
 <span data-ttu-id="cc85c-151">La aplicación MQSAgent COM+ incluye componentes tanto para la administración, como para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cc85c-151">The MQSAgent COM+ application includes components for both administration and runtime.</span></span> <span data-ttu-id="cc85c-152">Si desea separar esta funcionalidad en diferentes aplicaciones COM+ por motivos de seguridad, siga estos pasos en el equipo en el que se ha instalado la aplicación MQSAgent COM+:</span><span class="sxs-lookup"><span data-stu-id="cc85c-152">If you want to separate this functionality into different COM+ applications for security purposes, follow these steps on the computer that the MQSAgent COM+ application is installed on:</span></span>  
  
1.  <span data-ttu-id="cc85c-153">Habilite los cambios para el componente MQSAgent COM+.</span><span class="sxs-lookup"><span data-stu-id="cc85c-153">Enable changes for the MQSAgent COM+ component.</span></span>  
  
    -   <span data-ttu-id="cc85c-154">Haga clic en **iniciar** y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-154">Click **Start** and then click **Control Panel**.</span></span>  
  
    -   <span data-ttu-id="cc85c-155">Haga doble clic en **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-155">Double-click **Administrative Tools**.</span></span>  
  
    -   <span data-ttu-id="cc85c-156">Haga doble clic en **servicios de componentes** para iniciar el **servicios de componentes** interfaz de administración.</span><span class="sxs-lookup"><span data-stu-id="cc85c-156">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  
  
    -   <span data-ttu-id="cc85c-157">Expanda **servicios de componentes**, expanda **Mi PC**, expanda **aplicaciones COM +**, haga clic en el **MQSAgent2** aplicación COM + y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-157">Expand **Component Services**, expand **My Computer**, expand **COM+ Applications**, right-click the **MQSAgent2** COM+ application and then click **Properties**.</span></span>  
  
    -   <span data-ttu-id="cc85c-158">Haga clic en el **avanzadas** pestaña y desactive la opción **Deshabilitar cambios**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-158">Click the **Advanced** tab and uncheck **Disable changes**.</span></span>  
  
    -   <span data-ttu-id="cc85c-159">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-159">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="cc85c-160">Cree una nueva aplicación COM+ para los componentes de tiempo de ejecución de MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="cc85c-160">Create a new COM+ application for the MQSAgent runtime components.</span></span>  
  
    -   <span data-ttu-id="cc85c-161">Haga clic en **aplicaciones COM +**, haga clic en **New**, **aplicación** para mostrar la **Asistente para instalación de aplicación COM +** y haga clic en  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-161">Right-click **COM+ Applications**, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="cc85c-162">Haga clic en **crear una aplicación vacía**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-162">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="cc85c-163">Escriba el nombre **MQSAgent2RunTime**, deje la opción predeterminada para **aplicación de servidor** habilitado y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-163">Enter the name **MQSAgent2RunTime**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="cc85c-164">Seleccione la opción de **este usuario**, escriba la información de cuenta correspondiente y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-164">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cc85c-165">Esta cuenta debe tener **conectar** y **colocar** o **obtener** permisos en IBM WebSphere MQ adecuado para las colas de Windows.</span><span class="sxs-lookup"><span data-stu-id="cc85c-165">This account should have **connect** and **put** and/or **get** permissions on the appropriate IBM WebSphere MQ for Windows queues.</span></span> <span data-ttu-id="cc85c-166">Puede establecer los permisos adecuados para esta cuenta con la **setmqaut** comando disponible con IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="cc85c-166">You can set the appropriate permissions for this account with the **setmqaut** command available with the IBM WebSphere MQ.</span></span> <span data-ttu-id="cc85c-167">Para obtener más información sobre la **setmqaut** comando consulte la documentación de IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="cc85c-167">For more information about the **setmqaut** command see the IBM WebSphere MQ documentation.</span></span>  
  
    -   <span data-ttu-id="cc85c-168">Haga clic en **siguiente** en el **agregar funciones de aplicación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cc85c-168">Click **Next** on the **Add Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="cc85c-169">Haga clic en **siguiente** en el **agregar usuarios a funciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cc85c-169">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="cc85c-170">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-170">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="cc85c-171">Mueva los componentes de ejecución a la nueva aplicación COM+</span><span class="sxs-lookup"><span data-stu-id="cc85c-171">Move the runtime components to the new COM+ application</span></span>  
  
    -   <span data-ttu-id="cc85c-172">Expanda el **MQSAgent2** aplicación COM +.</span><span class="sxs-lookup"><span data-stu-id="cc85c-172">Expand the **MQSAgent2** COM+ application.</span></span>  
  
    -   <span data-ttu-id="cc85c-173">Expanda **componentes**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-173">Expand **Components**.</span></span>  
  
    -   <span data-ttu-id="cc85c-174">Haga clic en el **MQSAgent2.MQSAgent.1** componente y haga clic en **mover** para mostrar la **mover componentes (s)** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cc85c-174">Right-click the **MQSAgent2.MQSAgent.1** component and click **Move** to display the **Move components(s)** dialog box.</span></span>  
  
    -   <span data-ttu-id="cc85c-175">Seleccione **MQSAgent2RunTime** en **seleccione un destino** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cc85c-175">Select **MQSAgent2RunTime** under **Please select a destination** and click **OK**.</span></span>  
  
    -   <span data-ttu-id="cc85c-176">Repita estos pasos para la **MQSAgent2.MQSBroker.1** y **MQSAgent2.MQSProxy.1** componentes.</span><span class="sxs-lookup"><span data-stu-id="cc85c-176">Repeat these steps for the **MQSAgent2.MQSBroker.1** and **MQSAgent2.MQSProxy.1** components.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc85c-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc85c-177">See Also</span></span>  
 <span data-ttu-id="cc85c-178">[Controladores de recepción y envío de cómo configurar el adaptador de MQSeries](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="cc85c-178">[How to Configure MQSeries Adapter Send and Receive Handlers](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span></span>  
 [<span data-ttu-id="cc85c-179">Configuración del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="cc85c-179">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)