---
title: "Cómo mover el servidor secreto principal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b35fae6551a95c1c2009ac9786aa791d189f338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-master-secret-server"></a><span data-ttu-id="c18f2-102">Cómo mover el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="c18f2-102">How to Move the Master Secret Server</span></span>
<span data-ttu-id="c18f2-103">En este tema se documentan los pasos que pueden seguirse para mover el secreto principal de un servidor a otro, así como para mover el secreto principal de un servidor a un clúster de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c18f2-103">This topic documents the steps you can follow to move the master secret from one server to another and the steps you can follow to move the master secret from one server to a Windows Server Cluster.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a><span data-ttu-id="c18f2-104">Para mover el secreto principal de un servidor a otro</span><span class="sxs-lookup"><span data-stu-id="c18f2-104">To move the master secret from one server to another server</span></span>  
  
1.  <span data-ttu-id="c18f2-105">Instale Microsoft Enterprise Single Sign-On (SSO) Server en el nuevo servidor secreto principal si aún no se ha instalado.</span><span class="sxs-lookup"><span data-stu-id="c18f2-105">Install Microsoft Enterprise Single Sign-On (SSO) Server on the new master secret server if it is not already installed.</span></span> <span data-ttu-id="c18f2-106">Inicie el programa de instalación de Microsoft Enterprise Single Sign-On Server desde \Platform\SSO\setup.exe en el CD de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c18f2-106">Launch Microsoft Enterprise Single Sign-On Server setup from \Platform\SSO\setup.exe on the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] CD.</span></span>  
  
2.  <span data-ttu-id="c18f2-107">Configure SSO empresarial en el nuevo servidor secreto principal si aún no se ha configurado.</span><span class="sxs-lookup"><span data-stu-id="c18f2-107">Configure Enterprise SSO on the new master secret server if it is not already configured.</span></span> <span data-ttu-id="c18f2-108">Siga los pasos que se detallan a continuación para configurar SSO empresarial:</span><span class="sxs-lookup"><span data-stu-id="c18f2-108">Follow these steps to configure Enterprise SSO:</span></span>  
  
    1.  <span data-ttu-id="c18f2-109">Abra la herramienta de configuración.</span><span class="sxs-lookup"><span data-stu-id="c18f2-109">Open the Configuration tool.</span></span> <span data-ttu-id="c18f2-110">De forma predeterminada, la herramienta de configuración se encuentra en \<unidad >: \Program Files\Common Files\Enterprise inicio de sesión único-On\Configuration.exe.</span><span class="sxs-lookup"><span data-stu-id="c18f2-110">By default, the configuration tool is located at \<drive>:\Program Files\Common Files\Enterprise Single Sign-On\Configuration.exe.</span></span>  
  
    2.  <span data-ttu-id="c18f2-111">Haga clic para seleccionar **SSO empresarial** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c18f2-111">Click to select **Enterprise SSO** in the left pane.</span></span>  
  
    3.  <span data-ttu-id="c18f2-112">Active la casilla situada junto a **habilitar Enterprise Single Sign-On en este equipo** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="c18f2-112">Select the check box next to **Enable Enterprise Single Sign-On on this computer** in the right pane.</span></span>  
  
    4.  <span data-ttu-id="c18f2-113">Haga clic en la opción de **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="c18f2-113">Click the option to **Join an existing SSO System**.</span></span>  
  
    5.  <span data-ttu-id="c18f2-114">Especifique el existente **nombre del servidor** y **nombre de base de datos** para el SSO opciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c18f2-114">Specify the existing **Server Name** and **Database Name** for the SSO database options.</span></span>  
  
    6.  <span data-ttu-id="c18f2-115">Especificar la cuenta de servicio SSO empresarial existente para la **Enterprise Single Sign-On Server para el servicio de Windows** opción.</span><span class="sxs-lookup"><span data-stu-id="c18f2-115">Specify the existing Enterprise SSO service account for the **Enterprise Single Sign-On Server for the Windows Service** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c18f2-116">Debe ser una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="c18f2-116">This must be a domain account.</span></span>  
  
    7.  <span data-ttu-id="c18f2-117">Haga clic en la opción de **aplicar configuración** y haga clic en **configurar** en el cuadro de diálogo del Asistente para configuración para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c18f2-117">Click the option to **Apply Configuration** and click **Configure** in the Configuration Wizard dialog box to complete the configuration.</span></span>  
  
    8.  <span data-ttu-id="c18f2-118">Haga clic en **finalizar** y cierre la herramienta de configuración.</span><span class="sxs-lookup"><span data-stu-id="c18f2-118">Click **Finish** and close the Configuration tool.</span></span>  
  
3.  <span data-ttu-id="c18f2-119">Copia de seguridad del secreto principal siguiendo los pasos descritos en [cómo volver la seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="c18f2-119">Back up the existing master secret following the steps in [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
4.  <span data-ttu-id="c18f2-120">Cambie el nombre del servidor secreto principal en la base de datos de SSO para hacer referencia al nuevo servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="c18f2-120">Change the master secret server name in the SSO database to reference the new master secret server.</span></span> <span data-ttu-id="c18f2-121">Por ejemplo, puede ser el nombre del nuevo servidor secreto maestro **NewMSSServer**.</span><span class="sxs-lookup"><span data-stu-id="c18f2-121">For example, the name of the new master secret server may be **NewMSSServer**.</span></span> <span data-ttu-id="c18f2-122">Para ello, siga estos pasos en el servidor secreto principal original:</span><span class="sxs-lookup"><span data-stu-id="c18f2-122">To do this, follow these steps on the original master secret server:</span></span>  
  
    1.  <span data-ttu-id="c18f2-123">Pegue el siguiente código en un editor de texto, como notepad.exe:</span><span class="sxs-lookup"><span data-stu-id="c18f2-123">Paste the following code in a text editor such as notepad.exe:</span></span>  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  <span data-ttu-id="c18f2-124">Guarde el archivo como archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="c18f2-124">Save the file as .xml file.</span></span> <span data-ttu-id="c18f2-125">Por ejemplo, guarde el archivo como **NewMSSServer.xml**.</span><span class="sxs-lookup"><span data-stu-id="c18f2-125">For example, save the file as **NewMSSServer.xml**.</span></span>  
  
    3.  <span data-ttu-id="c18f2-126">En el símbolo del sistema, desplácese a la carpeta de instalación de SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="c18f2-126">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="c18f2-127">De forma predeterminada, es la carpeta de instalación \<unidad >: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="c18f2-127">By default, the installation folder is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="c18f2-128">Tipo de **ssomanage - updatedb** *XMLFile* para actualizar el nombre de servidor secreto principal en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c18f2-128">Type **ssomanage -updatedb** *XMLFile* to update the master secret server name in the database.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c18f2-129">Reemplace *XMLFile* con el nombre del archivo .xml que guardó.</span><span class="sxs-lookup"><span data-stu-id="c18f2-129">Replace *XMLFile* with the name of the .xml file that you saved.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c18f2-130">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c18f2-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="c18f2-131">Reinicie el servicio de inicio de sesión único empresarial en el nuevo servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="c18f2-131">Restart the Enterprise Single Sign-On service on the new master secret server.</span></span>  
  
6.  <span data-ttu-id="c18f2-132">Restaurar el secreto principal de copia de seguridad en el nuevo servidor secreto principal siguiendo los pasos descritos en [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md) en el nuevo servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="c18f2-132">Restore the backed-up master secret onto the new master secret server by following the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on the new master secret server.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a><span data-ttu-id="c18f2-133">Para mover el secreto principal de un servidor a un clúster de Windows Server</span><span class="sxs-lookup"><span data-stu-id="c18f2-133">To move the master secret from one server to a Windows Server Cluster</span></span>  
  
1.  <span data-ttu-id="c18f2-134">Instalar y configurar el servicio SSO empresarial en un clúster de Windows Server siguiendo los pasos descritos en [cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md).</span><span class="sxs-lookup"><span data-stu-id="c18f2-134">Install and configure the Enterprise SSO service on a Windows Server cluster by following the steps in [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span> <span data-ttu-id="c18f2-135">Complete cada uno de los pasos descritos en este tema, a excepción de los pasos descritos en la **restaurar el secreto principal en el segundo nodo de clúster** sección.</span><span class="sxs-lookup"><span data-stu-id="c18f2-135">Complete all of the steps in this topic except for the steps described in the **Restore the master secret on the second cluster node** section.</span></span> <span data-ttu-id="c18f2-136">Puesto que va a mover el servidor secreto principal existente en el clúster no elija la opción de **crear un nuevo sistema SSO** al configurar SSO empresarial en los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="c18f2-136">Since you will be moving the existing master secret server to the cluster do not choose the option to **Create a new SSO system** when configuring Enterprise SSO on the cluster nodes.</span></span> <span data-ttu-id="c18f2-137">Al configurar cada uno de los nodos del clúster, defina las opciones siguientes para la característica de SSO empresarial en el programa de configuración de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="c18f2-137">When configuring each cluster node, set the following options for the Enterprise SSO feature in the BizTalk Server Configuration program:</span></span>  
  
    1.  <span data-ttu-id="c18f2-138">Active la casilla junto a **habilitar Enterprise Single Sign-On en este equipo**.</span><span class="sxs-lookup"><span data-stu-id="c18f2-138">Check the box next to **Enable Enterprise Single Sign-On on this computer**.</span></span>  
  
    2.  <span data-ttu-id="c18f2-139">Haga clic en la opción de **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="c18f2-139">Click the option to **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="c18f2-140">Especifique valores para el nombre de la base de datos y del servidor de la base de datos de SSO existentes.</span><span class="sxs-lookup"><span data-stu-id="c18f2-140">Enter values for the existing SSO Database Server Name and Database Name.</span></span>  
  
    4.  <span data-ttu-id="c18f2-141">Indique la cuenta de servicio SSO existente al especificar la cuenta que se va a utilizar para el servicio de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="c18f2-141">Enter the existing SSO Service account when specifying the account to use for the Enterprise Single Sign-On Service.</span></span>  
  
2.  <span data-ttu-id="c18f2-142">Copie el archivo de copia de seguridad del secreto principal existente en la carpeta \Enterprise Single Sign-On en cada uno de los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="c18f2-142">Copy the existing master secret backup file to the \Enterprise Single Sign-On folder on each cluster node.</span></span>  
  
3.  <span data-ttu-id="c18f2-143">Si este clúster de Windows Server va a alojar uno o varios hosts de BizTalk agrupados, establezca el nombre de servidor de SSO para todos los usuarios como el servidor secreto maestro agrupado con la utilidad de línea de comandos ssomanage.</span><span class="sxs-lookup"><span data-stu-id="c18f2-143">If this Windows Server Cluster will host one or more clustered BizTalk hosts, set the SSO Server name for all users to the clustered master secret server with the ssomanage command line utility.</span></span> <span data-ttu-id="c18f2-144">Este comando debe ejecutarse desde la carpeta de instalación de SSO empresarial en cada servidor BizTalk Server en el grupo.</span><span class="sxs-lookup"><span data-stu-id="c18f2-144">This command should be run from the Enterprise SSO installation folder on each BizTalk Server in the group.</span></span> <span data-ttu-id="c18f2-145">Por ejemplo, la siguiente línea de comandos establecerá el servidor secreto principal agrupado como el nombre del servidor de SSO para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c18f2-145">For example, the following command line will set the SSO Server name for all users to the clustered master secret server:</span></span>  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c18f2-146">*SSOCLUSTER* es un marcador de posición para la red real de nombre de recurso que se crea en el grupo de clúster que contiene el servidor secreto principal agrupado resourceIn este escenario, todos los hosts de BizTalk deben crearse como recursos de clúster en el mismo grupo de clústeres que el recurso del servicio SSO empresarial agrupado.</span><span class="sxs-lookup"><span data-stu-id="c18f2-146">*SSOCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group that contains the clustered master secret server resourceIn this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="c18f2-147">La ejecución de una instancia de host de BizTalk no agrupada en un nodo de clúster de Windows Server en el que está agrupado el servicio SSO empresarial no es una configuración admitida.</span><span class="sxs-lookup"><span data-stu-id="c18f2-147">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="c18f2-148">Esto se debe a que la instancia de host de BizTalk no agrupada no se llevará a cabo correctamente si el servicio SSO empresarial agrupado se ha conmutado por error a otro nodo debido a la dependencia de una instancia de host de BizTalk del servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="c18f2-148">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c18f2-149">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c18f2-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="c18f2-150">En el Administrador de clústeres, haga clic en el grupo de clúster que contiene el recurso del servicio SSO empresarial y haga clic en **poner en conexión** para iniciar todos los recursos del grupo de clústeres.</span><span class="sxs-lookup"><span data-stu-id="c18f2-150">In Cluster Administrator, right-click the cluster group that contains the clustered Enterprise SSO service resource, and click **Bring Online** to start all of the resources in the cluster group.</span></span>  
  
5.  <span data-ttu-id="c18f2-151">Si este clúster de Windows Server va a alojar uno o más hosts de BizTalk agrupados, actualice el nombre de servidor de SSO accesible en la **propiedades del grupo de BizTalk** página para hacer referencia el servidor secreto principal agrupado.</span><span class="sxs-lookup"><span data-stu-id="c18f2-151">If this Windows Server Cluster will host one or more clustered BizTalk hosts, update the SSO Server name accessible in the **BizTalk Group Properties** page to reference the clustered master secret server.</span></span> <span data-ttu-id="c18f2-152">Iniciar **administración de BizTalk Server**, haga clic en el grupo de BizTalk y seleccione el **propiedades** menú elemento, a continuación, actualice la entrada de **nombre del servidor de SSO** y haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c18f2-152">Launch **BizTalk Server Administration**, right-click the BizTalk Group and select the **Properties** menu item, then update the entry for **SSO Server name** and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c18f2-153">En este escenario, todos los hosts de BizTalk deben crearse como recursos de clúster en el mismo grupo de clúster como el recurso del servicio SSO empresarial agrupado.</span><span class="sxs-lookup"><span data-stu-id="c18f2-153">In this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="c18f2-154">La ejecución de una instancia de host de BizTalk no agrupada en un nodo de clúster de Windows Server en el que está agrupado el servicio SSO empresarial no es una configuración admitida.</span><span class="sxs-lookup"><span data-stu-id="c18f2-154">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="c18f2-155">Esto se debe a que la instancia de host de BizTalk no agrupada no se llevará a cabo correctamente si el servicio SSO empresarial agrupado se ha conmutado por error a otro nodo debido a la dependencia de una instancia de host de BizTalk del servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="c18f2-155">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
6.  <span data-ttu-id="c18f2-156">Haga clic en la instancia en clúster del servicio SSO empresarial y haga clic en **poner sin conexión**, a continuación, haga clic en la instancia en clúster del servicio SSO empresarial y haga clic en **poner en conexión**.</span><span class="sxs-lookup"><span data-stu-id="c18f2-156">Right-click the clustered instance of the Enterprise SSO service and click **Take Offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring Online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c18f2-157">Si no se completa este paso, puede que los intentos de restaurar el secreto principal resulten infructuosos.</span><span class="sxs-lookup"><span data-stu-id="c18f2-157">If this step is not completed, attempts to restore the master secret may not succeed.</span></span>  
  
7.  <span data-ttu-id="c18f2-158">Restaure el secreto principal del que se ha realizado una copia de seguridad en cada nodo del clúster de Windows que aloja el servidor secreto principal agrupado.</span><span class="sxs-lookup"><span data-stu-id="c18f2-158">Restore the backed-up master secret on each node of the Windows cluster that houses the clustered master secret server.</span></span> <span data-ttu-id="c18f2-159">Siga los pasos de [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md) en cada nodo del clúster de Windows que aloja el servidor secreto principal agrupado.</span><span class="sxs-lookup"><span data-stu-id="c18f2-159">Follow the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on each node of the Windows cluster that houses the clustered master secret server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18f2-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="c18f2-160">See Also</span></span>  
 [<span data-ttu-id="c18f2-161">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="c18f2-161">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)