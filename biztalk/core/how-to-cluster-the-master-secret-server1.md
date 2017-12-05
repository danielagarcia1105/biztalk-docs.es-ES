---
title: "Cómo agrupar el Servidor1 de secreto maestro | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, second node
- Master Secret server, restoring
- clustering, Master Secret server
- Master Secret server, clustering
ms.assetid: ef817fa4-e43d-4e3d-8686-5bd675708001
caps.latest.revision: "47"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9740bb1c73dd5f416dda3c2f29bb15fbc7241a51
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-cluster-the-master-secret-server"></a><span data-ttu-id="191b4-102">Cómo agrupar el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="191b4-102">How to Cluster the Master Secret Server</span></span>
<span data-ttu-id="191b4-103">Se recomienda seguir las instrucciones contenidas en esta sección para agrupar el servicio de inicio de sesión único (SSO) empresarial correctamente en el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="191b4-103">We recommended that you follow the instructions in this section to cluster the Enterprise Single Sign-On (SSO) service on the master secret server successfully.</span></span>  
  
 <span data-ttu-id="191b4-104">Al organizar por clústeres el servidor secreto principal, los servidores de inicio de sesión único se comunican con la instancia agrupada activa del servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="191b4-104">When you cluster the master secret server, the Single Sign-On servers communicate with the active clustered instance of the master secret server.</span></span> <span data-ttu-id="191b4-105">De forma similar, la instancia agrupada activa del servidor secreto principal se comunica con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="191b4-105">Similarly, the active clustered instance of the master secret server communicates with the SSO database.</span></span>  
  
 <span data-ttu-id="191b4-106">Deberá ser administrador de SSO para realizar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="191b4-106">You must be an SSO administrator to perform this procedure.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="191b4-107">El servidor secreto principal no puede instalarse en un clúster de equilibrio de carga de red (NLB).</span><span class="sxs-lookup"><span data-stu-id="191b4-107">You cannot install the master secret server on a Network Load Balancing (NLB) cluster.</span></span>  
  
### <a name="to-install-and-configure-enterprise-sso-on-the-cluster-nodes"></a><span data-ttu-id="191b4-108">Para instalar y configurar SSO empresarial en los nodos de clúster</span><span class="sxs-lookup"><span data-stu-id="191b4-108">To install and configure Enterprise SSO on the cluster nodes</span></span>  
  
1.  <span data-ttu-id="191b4-109">Instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en cada nodo del clúster.</span><span class="sxs-lookup"><span data-stu-id="191b4-109">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on each cluster node.</span></span> <span data-ttu-id="191b4-110">En **instalación de componentes**, seleccione **Enterprise Single Sign-On módulo de administración de** y **Enterprise Single Sign-On servidor secreto principal**.</span><span class="sxs-lookup"><span data-stu-id="191b4-110">In **Component Installation**, select **Enterprise Single Sign-On Administration Module** and **Enterprise Single Sign-On Master Secret Server**.</span></span> <span data-ttu-id="191b4-111">Una vez haya finalizado correctamente la instalación, haga lo **no** ejecutar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración.</span><span class="sxs-lookup"><span data-stu-id="191b4-111">After installation has completed successfully, do **not** run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
2.  <span data-ttu-id="191b4-112">Crear **administradores de SSO** y **administradores afiliados de SSO** grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="191b4-112">Create **SSO Administrators** and **SSO Affiliate Administrators** domain groups.</span></span> <span data-ttu-id="191b4-113">Para crear una instancia en clúster del servicio SSO empresarial, debe crear estos grupos como grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="191b4-113">To create a clustered instance of the Enterprise SSO service, you must create these groups as domain groups.</span></span>  
  
3.  <span data-ttu-id="191b4-114">Cree o designe una cuenta de dominio que sea miembro de la **administradores de SSO** grupo de dominio.</span><span class="sxs-lookup"><span data-stu-id="191b4-114">Create or designate a domain account that is a member of the **SSO Administrators** domain group.</span></span> <span data-ttu-id="191b4-115">El Servicio SSO empresarial de cada nodo está configurado para iniciar sesión como esta cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="191b4-115">The Enterprise SSO service on each node is configured to log on as this domain account.</span></span> <span data-ttu-id="191b4-116">Esta cuenta debe tener la **iniciar sesión como un servicio** en cada nodo del clúster.</span><span class="sxs-lookup"><span data-stu-id="191b4-116">This account must have the **Log on as a service** right on each node in the cluster.</span></span>  
  
4.  <span data-ttu-id="191b4-117">Agregue la cuenta que usas para iniciar sesión durante el proceso de configuración para el dominio **administradores de SSO** grupo.</span><span class="sxs-lookup"><span data-stu-id="191b4-117">Add the account that you are using to log on during the configuration process to the domain **SSO Administrators** group.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="191b4-118">Si no se completan los pasos 3 y 4, la configuración del servicio SSO empresarial no se lleva a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="191b4-118">Configuration of the Enterprise SSO service fails if steps 3 and 4 are not completed.</span></span>  
  
5.  <span data-ttu-id="191b4-119">Inicie la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="191b4-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
6.  <span data-ttu-id="191b4-120">Seleccione **configuración personalizada** opción y escriba el **el nombre del servidor de base de datos**, **nombre de usuario**, y **contraseña** valores.</span><span class="sxs-lookup"><span data-stu-id="191b4-120">Select **Custom Configuration** option and enter the **Database server name**, **User name**, and **Password** values.</span></span> <span data-ttu-id="191b4-121">Seleccione **configurar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="191b4-121">Select **Configure** to continue.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="191b4-122">Dado que solo se pueden configurar el servicio SSO empresarial en este momento, puede especificar simplemente la cuenta de dominio creada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="191b4-122">Since you are only be configuring the Enterprise SSO service at this time, you can just enter the domain account that you created earlier here.</span></span>  
  
7.  <span data-ttu-id="191b4-123">Seleccione el **SSO empresarial** opción en el panel izquierdo y defina las siguientes opciones para la característica SSO empresarial:</span><span class="sxs-lookup"><span data-stu-id="191b4-123">Select the **Enterprise SSO** option from the left pane and set the following options for the Enterprise SSO feature:</span></span>  
  
    1.  <span data-ttu-id="191b4-124">Seleccione el **habilitar Enterprise Single Sign-On en este equipo** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="191b4-124">Select the **Enable Enterprise Single Sign-On on this computer** check box.</span></span>  
  
    2.  <span data-ttu-id="191b4-125">Seleccione **crear un nuevo sistema SSO**.</span><span class="sxs-lookup"><span data-stu-id="191b4-125">Select **Create a new SSO system**.</span></span>  
  
    3.  <span data-ttu-id="191b4-126">Escriba el **almacenes de datos** para **nombre del servidor** y **nombre de base de datos** valores.</span><span class="sxs-lookup"><span data-stu-id="191b4-126">Enter the **Data stores** for **Server Name** and **Database Name** values.</span></span>  
  
    4.  <span data-ttu-id="191b4-127">Compruebe que la cuenta de dominio creada anteriormente es la cuenta asociada con el servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="191b4-127">Verify that the domain account that you created earlier is the account that is associated with the Enterprise SSO service.</span></span>  
  
    5.  <span data-ttu-id="191b4-128">Escriba el grupo Administradores de SSO de dominio creado anteriormente como el grupo asociado con el rol Administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="191b4-128">Enter the domain SSO Administrators group that you created earlier as the group associated with the SSO Administrator(s) role.</span></span>  
  
    6.  <span data-ttu-id="191b4-129">Escriba el grupo Administradores afiliados de SSO de dominio creado anteriormente como el grupo asociado con el rol Administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="191b4-129">Enter the domain SSO Affiliate Administrators group that you created earlier as the group associated with the SSO Affiliate Administrator(s) role.</span></span>  
  
8.  <span data-ttu-id="191b4-130">Seleccione el **copia de seguridad de secreto de SSO de Enterprise** opción en el panel izquierdo y proporcione los parámetros adecuados para realizar una copia de seguridad del secreto de SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="191b4-130">Select the **Enterprise SSO Secret Backup** option from the left pane and provide the appropriate parameters for backing up the Enterprise SSO secret.</span></span> <span data-ttu-id="191b4-131">De forma predeterminada, el secreto de SSO empresarial es copia de seguridad  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On\\*SSOxxxx*bak.</span><span class="sxs-lookup"><span data-stu-id="191b4-131">By default, the Enterprise SSO secret is backed up to *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On\\*SSOxxxx*.bak.</span></span>  
  
9. <span data-ttu-id="191b4-132">Haga clic en el **aplicar configuración** y revise el resumen.</span><span class="sxs-lookup"><span data-stu-id="191b4-132">Click the **Apply Configuration** and review the Summary.</span></span>  
  
10. <span data-ttu-id="191b4-133">Haga clic en **siguiente** para aplicar la configuración.</span><span class="sxs-lookup"><span data-stu-id="191b4-133">Click **Next** to apply the configuration.</span></span>  
  
11. <span data-ttu-id="191b4-134">Haga clic en **finalizar** para cerrar el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="191b4-134">Click **Finish** to close the Configuration wizard.</span></span>  
  
12. <span data-ttu-id="191b4-135">Cierre la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="191b4-135">Close the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration.</span></span>  
  
13. <span data-ttu-id="191b4-136">Inicie sesión en el nodo de clúster pasivo e inicie la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="191b4-136">Log on to the passive cluster node and start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
14. <span data-ttu-id="191b4-137">Elija la **configuración personalizada** opción y especifique los mismos valores para la **el nombre del servidor de base de datos**, **nombre de usuario**, y **contraseña** que especificó al configurar el primer nodo del clúster.</span><span class="sxs-lookup"><span data-stu-id="191b4-137">Choose the **Custom Configuration** option and enter the same values for the **Database server name**, **User name**, and **Password** that you entered when configuring the first cluster node.</span></span> <span data-ttu-id="191b4-138">Después de escribir estos valores, haga clic en **configurar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="191b4-138">After entering these values, click **Configure** to continue.</span></span>  
  
15. <span data-ttu-id="191b4-139">Seleccione el **SSO empresarial** opción en el panel izquierdo y defina las siguientes opciones para la característica SSO empresarial:</span><span class="sxs-lookup"><span data-stu-id="191b4-139">Select the **Enterprise SSO** option from the left pane and set the following options for the Enterprise SSO feature:</span></span>  
  
    1.  <span data-ttu-id="191b4-140">Seleccione el **habilitar Enterprise Single Sign-On en este equipo** opción.</span><span class="sxs-lookup"><span data-stu-id="191b4-140">Select the **Enable Enterprise Single Sign-On on this computer** option.</span></span>  
  
    2.  <span data-ttu-id="191b4-141">Seleccione **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="191b4-141">Select **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="191b4-142">Especifique los mismos valores para la base de datos de SSO **nombre del servidor** y **nombre de base de datos** que especificó al configurar el primer nodo del clúster.</span><span class="sxs-lookup"><span data-stu-id="191b4-142">Enter the same values for the SSO Database **Server Name** and **Database Name** that you entered when configuring the first cluster node.</span></span>  
  
    4.  <span data-ttu-id="191b4-143">Especifique el mismo valor para la cuenta de dominio que el especificado al configurar el primer nodo de clúster.</span><span class="sxs-lookup"><span data-stu-id="191b4-143">Enter the same value for the domain account that you entered when configuring the first cluster node.</span></span>  
  
16. <span data-ttu-id="191b4-144">Seleccione **aplicar configuración** para mostrar el resumen.</span><span class="sxs-lookup"><span data-stu-id="191b4-144">Select **Apply Configuration** to display the Summary.</span></span>  
  
17. <span data-ttu-id="191b4-145">Seleccione **siguiente** para aplicar la configuración.</span><span class="sxs-lookup"><span data-stu-id="191b4-145">Select **Next** to apply the configuration.</span></span>  
  
18. <span data-ttu-id="191b4-146">Seleccione **finalizar** para cerrar el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="191b4-146">Select **Finish** to close the Configuration wizard.</span></span>  
  
19. <span data-ttu-id="191b4-147">Cerrar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración.</span><span class="sxs-lookup"><span data-stu-id="191b4-147">Close the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
### <a name="to-update-the-master-secret-server-name-in-the-sso-database"></a><span data-ttu-id="191b4-148">Para actualizar el nombre del servidor secreto principal en la base de datos de SSO</span><span class="sxs-lookup"><span data-stu-id="191b4-148">To update the master secret server name in the SSO database</span></span>  
  
1.  <span data-ttu-id="191b4-149">Escriba los comandos siguientes en un símbolo del sistema del nodo de clúster activo para detener y reiniciar el servicio SSO empresarial:</span><span class="sxs-lookup"><span data-stu-id="191b4-149">Type the following commands from a command prompt on the active cluster node to stop and restart the Enterprise SSO service:</span></span>  
  
    ```  
    net stop entsso  
    ```  
  
     <span data-ttu-id="191b4-150">y</span><span class="sxs-lookup"><span data-stu-id="191b4-150">and</span></span>  
  
    ```  
    net start entsso  
    ```  
  
2.  <span data-ttu-id="191b4-151">Cambie el nombre del servidor secreto principal en la base de datos de SSO al nombre de clúster mediante los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="191b4-151">Change the master secret server name in the SSO database to the cluster name by following these steps:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="191b4-152">El nombre de clúster es el nombre definido para el recurso de nombre de red creado en el grupo de clústeres o en la aplicación o servicio en clúster que contendrá el servicio SSO empresarial en clúster.</span><span class="sxs-lookup"><span data-stu-id="191b4-152">The cluster name is the name defined for the network name resource that you have created in the cluster group / clustered service or application that will contain the clustered Enterprise SSO service.</span></span> <span data-ttu-id="191b4-153">Por ejemplo, el nombre puede ser *BIZTALKCLUSTER*.</span><span class="sxs-lookup"><span data-stu-id="191b4-153">For example, the name may be *BIZTALKCLUSTER*.</span></span>  
  
    1.  <span data-ttu-id="191b4-154">Pegue el código siguiente en un editor de texto:</span><span class="sxs-lookup"><span data-stu-id="191b4-154">Paste the following code in a text editor:</span></span>  
  
        ```  
        <sso>  
          <globalInfo>  
            <secretServer>BIZTALKCLUSTER</secretServer>  
          </globalInfo>  
        </sso>  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="191b4-155">*BIZTALKCLUSTER* es un marcador de posición para el recurso de nombre de red real que se crea en el clúster o la aplicación o servicio en clúster grupo.</span><span class="sxs-lookup"><span data-stu-id="191b4-155">*BIZTALKCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group / clustered service or application.</span></span>  
  
    2.  <span data-ttu-id="191b4-156">Guarde el archivo con la extensión .xml.</span><span class="sxs-lookup"><span data-stu-id="191b4-156">Save the file as an .xml file.</span></span> <span data-ttu-id="191b4-157">Por ejemplo, puede guardar el archivo con el nombre SSOCLUSTER.xml.</span><span class="sxs-lookup"><span data-stu-id="191b4-157">For example, save the file as SSOCLUSTER.xml.</span></span>  
  
    3.  <span data-ttu-id="191b4-158">En el símbolo del sistema, desplácese a la carpeta de instalación de SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="191b4-158">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="191b4-159">De forma predeterminada, es la carpeta de instalación  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="191b4-159">By default, the installation folder is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="191b4-160">Escriba el comando siguiente en el símbolo del sistema para actualizar el servidor secreto principal en la base de datos:</span><span class="sxs-lookup"><span data-stu-id="191b4-160">Type the following command at the command prompt to update the master secret server name in the database:</span></span>  
  
        ```  
        ssomanage -updatedb XMLFile  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="191b4-161">*XMLFile* es un marcador de posición para el nombre del archivo .xml que guardó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="191b4-161">*XMLFile* is a placeholder for the name of the .xml file that you saved earlier.</span></span>  
  
### <a name="to-create-the-clustered-enterprise-sso-resource"></a><span data-ttu-id="191b4-162">Para crear el recurso SSO empresarial agrupado</span><span class="sxs-lookup"><span data-stu-id="191b4-162">To create the clustered Enterprise SSO resource</span></span>  
  
1.  <span data-ttu-id="191b4-163">Si el clúster no está configurado con un recurso Coordinador de transacciones distribuidas (MSDTC) agrupado, a continuación, siga los pasos descritos en las notas del producto "Mejorar el error tolerancia en BizTalk Server por mediante un servidor clúster Windows" en [http:// ¿go.Microsoft.com/fwlink/? LinkId = 69207](http://go.microsoft.com/fwlink/?LinkId=69207) para crear un recurso MSDTC agrupado.</span><span class="sxs-lookup"><span data-stu-id="191b4-163">If the cluster is not configured with a clustered Distributed Transaction Coordinator (MSDTC) resource then follow the steps in the "Improving Fault Tolerance in BizTalk Server by Using a Windows Server Cluster" white paper at [http://go.microsoft.com/fwlink/?LinkId=69207](http://go.microsoft.com/fwlink/?LinkId=69207) to create a clustered MSDTC resource.</span></span>  
  
2.  <span data-ttu-id="191b4-164">Haga clic en **iniciar**, **programas**, **herramientas administrativas**y, a continuación, **administración de clúster de conmutación por error** para iniciar el clúster de conmutación por error Programa de administración.</span><span class="sxs-lookup"><span data-stu-id="191b4-164">Click **Start**, **Programs**, **Administrative Tools**, and then **Failover Cluster Management** to start the Failover Cluster Management program.</span></span>  
  
3.  <span data-ttu-id="191b4-165">En el panel izquierdo, haga clic en **administración de clúster de conmutación por error** y haga clic en **administrar un clúster**.</span><span class="sxs-lookup"><span data-stu-id="191b4-165">In the left hand pane, right-click **Failover Cluster Management** and click **Manage a Cluster**.</span></span>  
  
4.  <span data-ttu-id="191b4-166">En el **seleccionar un clúster para administrar** diálogo cuadro, escriba el clúster para administrar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="191b4-166">On the **Select a cluster to manage** dialog box, enter the cluster to be managed and click **OK**.</span></span>  
  
5.  <span data-ttu-id="191b4-167">En el panel izquierdo, haga clic para seleccionar un servicio o aplicación en clúster que contenga un recurso de dirección IP y nombre de red.</span><span class="sxs-lookup"><span data-stu-id="191b4-167">In the left hand pane click to select a clustered service or application that contains an IP Address and Network Name resource.</span></span> <span data-ttu-id="191b4-168">Siga los pasos de [cómo crear un grupo de clústeres con un disco, una dirección IP y un recurso de nombre de](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md) para crear un grupo con un recurso de dirección IP y nombre de red si no existe.</span><span class="sxs-lookup"><span data-stu-id="191b4-168">Follow the steps in [How to Create a Cluster Group with a Disk, IP Address, and Name Resource](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md) to create a group with an IP Address and Network Name resource if one does not already exist.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="191b4-169">Un servicio SSO empresarial en clúster no necesita de forma explícita el uso de un recurso de disco físico en clúster en el mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="191b4-169">A clustered Enterprise SSO service does not explicitly require the use of a clustered Physical Disk resource in the same group.</span></span>  
  
6.  <span data-ttu-id="191b4-170">Haga clic en la aplicación o servicio en clúster, seleccione **agregar un recurso**y haga clic en **servicio genérico** para mostrar la **Asistente para nuevo recurso** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="191b4-170">Right-click the clustered service or application, point to **Add a resource**, and click **Generic Service** to display the **New Resource Wizard** dialog.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="191b4-171">En el **parámetros de servicio genérico** cuadro de diálogo, si no hace clic para seleccionar la **usar el nombre de red como nombre del equipo** casilla de verificación, los equipos de cliente SSO generarán un error similar al siguiente cuando se intente ponerse en contacto con esta instancia en clúster del servicio SSO empresarial:</span><span class="sxs-lookup"><span data-stu-id="191b4-171">In the **Generic Service Parameters** dialog box, if you do not click to select the **Use Network Name for computer name** check box, SSO client computers will generate an error similar to the following when they try to contact this clustered instance of the Enterprise SSO service:</span></span>  
    >   
    >  <span data-ttu-id="191b4-172">No se pudieron recuperar los secretos principales.</span><span class="sxs-lookup"><span data-stu-id="191b4-172">Failed to retrieve master secrets.</span></span>  
    >   
    >  <span data-ttu-id="191b4-173">Compruebe que el nombre del servidor secreto principal es correcto y está disponible.</span><span class="sxs-lookup"><span data-stu-id="191b4-173">Verify that the master secret server name is correct and that it is available.</span></span> <span data-ttu-id="191b4-174">Nombre del servidor secreto: ENTSSO Código de error: 0x800706D9. No hay más extremos disponibles desde el asignador de extremos.</span><span class="sxs-lookup"><span data-stu-id="191b4-174">Secret Server Name: ENTSSO Error Code: 0x800706D9, there are no more endpoints available from the endpoint mapper.</span></span>  
  
7.  <span data-ttu-id="191b4-175">En el **Seleccionar servicio** página de la **Asistente para nuevo recurso**, haga clic para seleccionar **Enterprise Single Sign-On Service** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="191b4-175">On the **Select Service** page of the **New Resource Wizard**, click to select **Enterprise Single Sign-On Service** and click **Next**.</span></span>  
  
8.  <span data-ttu-id="191b4-176">En el **confirmación** página haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="191b4-176">On the **Confirmation** page click **Next**.</span></span>  
  
9. <span data-ttu-id="191b4-177">En el **resumen** página haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="191b4-177">On the **Summary** page click **Finish**.</span></span> <span data-ttu-id="191b4-178">Aparecerá una instancia agrupada del servicio de inicio de sesión único de empresa en **otros recursos** en el panel central de la **administración de clúster de conmutación por error** interfaz.</span><span class="sxs-lookup"><span data-stu-id="191b4-178">A clustered instance of the Enterprise Single Sign-On Service will appear under **Other Resources** in the center pane of the **Failover Cluster Management** interface.</span></span>  
  
10. <span data-ttu-id="191b4-179">Haga clic en la instancia en clúster del servicio de inicio de sesión único de empresa y seleccione **propiedades** para mostrar la **Enterprise Single Sign-On propiedades del servicio** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="191b4-179">Right-click the clustered instance of the Enterprise Single Sign-On Service and select **Properties** to display the **Enterprise Single Sign-On Service Properties** dialog box.</span></span>  
  
11. <span data-ttu-id="191b4-180">Haga clic en el **dependencias** ficha del cuadro de diálogo de propiedades y haga clic en **insertar**.</span><span class="sxs-lookup"><span data-stu-id="191b4-180">Click the **Dependencies** tab of the properties dialog box and click **Insert**.</span></span>  
  
12. <span data-ttu-id="191b4-181">Haga clic en el cuadro de lista desplegable en **recursos**, seleccione la **nombre:** recurso y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="191b4-181">Click the drop down box under **Resource**, select the **Name:** resource and click **OK**.</span></span>  
  
### <a name="to-restore-the-master-secret-on-the-second-cluster-node"></a><span data-ttu-id="191b4-182">Para restaurar el secreto principal en el segundo nodo de clúster</span><span class="sxs-lookup"><span data-stu-id="191b4-182">To restore the master secret on the second cluster node</span></span>  
  
1.  <span data-ttu-id="191b4-183">En administración de clúster de conmutación por error, haga clic en el servicio en clúster o la aplicación que contiene el servicio de inicio de sesión único empresarial en clúster y, a continuación, haga clic en **conectar este servicio o aplicación** para iniciar todos los recursos en el servicio clúster o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="191b4-183">In Failover Cluster Management, right click the clustered service or application that contains the clustered Enterprise Single Sign-On service and then click **Bring this service or application online** to start all of the resources in the clustered service or application.</span></span>  
  
2.  <span data-ttu-id="191b4-184">Haga clic en la aplicación o servicio en clúster, seleccione **mover este servicio o aplicación a otro nodo**y haga clic en el segundo nodo.</span><span class="sxs-lookup"><span data-stu-id="191b4-184">Right-click the clustered service or application, point to **Move this service or application to another node**, and click the second node.</span></span> <span data-ttu-id="191b4-185">Este paso mueve el servicio o la aplicación en clúster que contiene el servicio Inicio de sesión único empresarial en clúster del primer nodo al segundo.</span><span class="sxs-lookup"><span data-stu-id="191b4-185">This step moves the clustered service or application that contains the clustered Enterprise Single Sign-On service from the first node to the second node.</span></span>  
  
3.  <span data-ttu-id="191b4-186">Haga clic en el servicio de Enterprise Single Sign-On en clúster y haga clic en **dejar este servicio o aplicación sin conexión**, a continuación, haga clic en la instancia en clúster del servicio SSO empresarial y haga clic en **poner este servicio o aplicación en línea**.</span><span class="sxs-lookup"><span data-stu-id="191b4-186">Right-click the clustered Enterprise Single Sign-On service and click **Take this service or application offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring this service or application online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="191b4-187">Si no se completa este paso, es posible que el intento de restaurar el secreto principal resulte infructuoso.</span><span class="sxs-lookup"><span data-stu-id="191b4-187">If this step is not completed the attempt to restore the master secret may not succeed.</span></span>  
  
4.  <span data-ttu-id="191b4-188">Copie el archivo de copia de seguridad del secreto principal del primer nodo a la carpeta de instalación \Enterprise Single Sign-On del segundo nodo.</span><span class="sxs-lookup"><span data-stu-id="191b4-188">Copy the master secret backup file from the first node to the \Enterprise Single Sign-On installation folder on the second node.</span></span> <span data-ttu-id="191b4-189">De forma predeterminada, es la carpeta de instalación  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="191b4-189">By default, the installation folder is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5.  <span data-ttu-id="191b4-190">Inicie sesión en el segundo nodo y, en un símbolo del sistema, cambie a la carpeta de instalación de SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="191b4-190">Log on to the second node and at a command prompt, change to the Enterprise SSO installation folder.</span></span>  
  
6.  <span data-ttu-id="191b4-191">Para restaurar el secreto principal en el segundo nodo, escriba el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="191b4-191">Type the following command from the command prompt to restore the master secret to the second node:</span></span>  
  
    ```  
    ssoconfig -restoresecret RestoreFile  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="191b4-192">Reemplace *RestoreFile* con la ruta de acceso y el nombre del archivo de copia de seguridad que contiene el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="191b4-192">Replace *RestoreFile* with the path of and the name of the backup file that contains the master secret.</span></span>  
  
     <span data-ttu-id="191b4-193">El secreto principal se almacena en el Registro en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="191b4-193">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="191b4-194">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span><span class="sxs-lookup"><span data-stu-id="191b4-194">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span></span>  
  
7.  <span data-ttu-id="191b4-195">Mueva la aplicación o servicio en clúster que contiene el servicio de inicio de sesión único empresarial en clúster de este nodo de clúster a otro nodo de clúster para garantizar la funcionalidad de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="191b4-195">Move the clustered service or application that contains the clustered Enterprise Single Sign-On service from this cluster node to other cluster node to ensure failover functionality.</span></span> <span data-ttu-id="191b4-196">A continuación, mueva el grupo de clúster en el sentido contrario para comprobar la funcionalidad de conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="191b4-196">Then move the cluster group back to verify fail-back functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191b4-197">Vea también</span><span class="sxs-lookup"><span data-stu-id="191b4-197">See Also</span></span>  
 [<span data-ttu-id="191b4-198">Cómo crear un grupo de clústeres con un disco, una dirección IP y un recurso de nombre</span><span class="sxs-lookup"><span data-stu-id="191b4-198">How to Create a Cluster Group with a Disk, IP Address, and Name Resource</span></span>](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)
