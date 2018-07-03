---
title: Cómo actualizar referencias a la notificación de BAM de servicios de bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM], restoring
- Notification Services Application database [BAM], updating references
- restoring, BAM
- NS$instance_name service Notification Services Application database [BAM], NS$instance_name service
- restoring [BAM], updating references
- BAM, restoring
- restoring [BAM], Notification Services Application database
- restoring [BAM], NS$instance_name service
ms.assetid: b007fdc2-2e74-4eef-b4c3-43689e9f2180
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 712e43b5220b6836d80d49953e159c878f40ca79
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978285"
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a><span data-ttu-id="6e4fa-102">Cómo actualizar referencias a las bases de datos de servicios de notificación de SAE</span><span class="sxs-lookup"><span data-stu-id="6e4fa-102">How to Update References to the BAM Notification Services Databases</span></span>
<span data-ttu-id="6e4fa-103">Después de llevar a cabo los pasos necesarios para restaurar las bases de datos de los servicios de notificación de supervisión de la actividad económica (BAM) en el sistema de destino, tendrá que volver a registrar el Servicio de notificación en todos los equipos del grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en los que se ejecutan los Servicios de notificación (NSservice.exe).</span><span class="sxs-lookup"><span data-stu-id="6e4fa-103">After you perform the steps necessary to restore the Business Activity Monitoring (BAM) Notification Services databases to the destination system, you must re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="6e4fa-104">Con ello, se permite que los servicios de notificación se conecten a las bases de datos en su nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-104">This enables Notification Services to connect to the databases in their new location.</span></span>  
  
 <span data-ttu-id="6e4fa-105">Al registrar una instancia de los servicios de notificación, se crea el servicio NS$instance_name, se crean contadores de rendimiento en el servidor local y se agrega información al Registro.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-105">Registering an instance of Notification Services creates the NS$instance_name service, creates performance counters on the local server, and adds information to the registry.</span></span> <span data-ttu-id="6e4fa-106">Debe registrar la instancia en cada uno de los servidores siguientes.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-106">You must register the instance on the following servers:</span></span>  
  
- <span data-ttu-id="6e4fa-107">Todos los servidores en los que se ejecute el servicio NS$instance_name.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-107">Each server that runs the NS$instance_name service.</span></span> <span data-ttu-id="6e4fa-108">El servicio ejecuta los componentes de distribuidor, generador y host de proveedor de sucesos.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-108">The service runs the event provider host, generator, and distributor components.</span></span> <span data-ttu-id="6e4fa-109">En el caso de las configuraciones escaladas de forma horizontal, el servicio se ejecuta en varios servidores.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-109">For scaled-out configurations, the service runs on multiple servers.</span></span>  
  
- <span data-ttu-id="6e4fa-110">Todos los servidores en los que se ejecute una aplicación de administración de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-110">Each server that runs a subscription management application.</span></span> <span data-ttu-id="6e4fa-111">Si la aplicación de administración de suscripciones se ejecuta en su propio servidor, no cree el servicio NS$instance_name al registrar la instancia.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-111">If the subscription management application runs on its own server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
- <span data-ttu-id="6e4fa-112">Todos los servidores en los que se ejecuta un proveedor de sucesos independiente.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-112">Each server that runs an independent event provider.</span></span> <span data-ttu-id="6e4fa-113">Si el proveedor de sucesos independiente se ejecuta en su propio servidor o en el servidor de la base de datos, no cree el servicio NS$instance_name al registrar la instancia.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-113">If the independent event provider runs on its own server or the database server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
  <span data-ttu-id="6e4fa-114">Si el servidor de la base de datos no ejecuta, además, los componentes de cliente o la instancia de servicios de notificación, no registre la instancia en este servidor.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-114">If the database server does not also run the Notification Services instance or the client components, do not register the instance on this server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6e4fa-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6e4fa-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="6e4fa-116">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-116">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
-   <span data-ttu-id="6e4fa-117">El Proveedor de alertas de Supervisión de la actividad económica (BAM) para los servicios de notificación de SQL debe estar instalado en el equipo en el que se estén restaurando las bases de datos de los servicios de notificación de BAM.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-117">The Business Activity Monitoring (BAM) Alert Provider for SQL Notification Services must be installed on the computer where you are restoring the BAM Notification Services databases.</span></span>  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a><span data-ttu-id="6e4fa-118">Para actualizar referencias a las bases de datos de servicios de notificación de BAM (SQL Server 2008 R2/SP1)</span><span class="sxs-lookup"><span data-stu-id="6e4fa-118">To update references to the BAM Notification Services databases (SQL Server 2008 R2/SP1)</span></span>  
  
1. <span data-ttu-id="6e4fa-119">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-119">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="6e4fa-120">En el símbolo del sistema, desplácese al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-120">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="6e4fa-121">Tipo: **bm.exe get-config –filename:config.xml**</span><span class="sxs-lookup"><span data-stu-id="6e4fa-121">Type: **bm.exe get-config –filename:config.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6e4fa-122">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="6e4fa-123">Abra el archivo XML creado en el Paso 2 para obtener la lista de los equipos en los que debe volver a registrar los servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-123">Open the xml file created in step 2 to obtain the list of the computers on which you must re-register Notification Services.</span></span>  
  
    <span data-ttu-id="6e4fa-124">Los nombres de equipo se enumeran en la **\<nombre de la propiedad\= \>** parámetros en el **\<DeploymentUnit nombre = "Alert"\>** sección del archivo xml:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-124">The computer names are listed in the **\<Property Name\=\>** parameters in the **\<DeploymentUnit Name="Alert"\>** section of the xml file:</span></span>  
  
   ```  
   -<DeploymentUnit Name="Alert">  
   <Property Name="GeneratorServerName" />  
   <Property Name="ProviderServerName" />  
   <Property Name="DistributorServerName" />  
     </DeploymentUnit>  
   ```  
  
5. <span data-ttu-id="6e4fa-125">Detenga el servicio NS y, a continuación, elimine el registro de una instancia de los servicios de notificación en cada uno de los equipos que figuran en el archivo XML:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-125">On each computer listed in the xml file, stop the NS service and then unregister an instance of Notification Services:</span></span>  
  
   1.  <span data-ttu-id="6e4fa-126">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-126">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="6e4fa-127">En el símbolo del sistema, escriba: **net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="6e4fa-127">At the command prompt, type: **net stop NS$BamAlerts**</span></span>  
  
   3.  <span data-ttu-id="6e4fa-128">Escriba el siguiente comando para anular el registro de la instancia:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-128">Type the following command to unregister the instance:</span></span>  
  
        <span data-ttu-id="6e4fa-129">**NSControl unregister - name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="6e4fa-129">**nscontrol unregister  -name BamAlerts**</span></span>  
  
        <span data-ttu-id="6e4fa-130">Al eliminar el registro de una instancia, se quitan las entradas de aquél y el servicio NS$instance_name (en el caso de que esté presente), y, además, se eliminan los contadores de rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-130">Unregistering an instance removes the registry entries, removes the NS$instance_name service (if present), and deletes the performance counters for the service.</span></span>  
  
6. <span data-ttu-id="6e4fa-131">Vuelva a registrar el servicio de notificación:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-131">Re-register the Notification Service:</span></span>  
  
   1.  <span data-ttu-id="6e4fa-132">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-132">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="6e4fa-133">En el símbolo del sistema, escriba: **nscontrol register - name BamAlerts-server**  *\<ServerName\>***-service - serviceusername "*** \< ServiceUserName\>***"- servicepassword"***\<ServicePassword\>*** "**</span><span class="sxs-lookup"><span data-stu-id="6e4fa-133">At the command prompt, type: **nscontrol register -name BamAlerts -server** *\<ServerName\>***-service -serviceusername "***\<ServiceUserName\>***" -servicepassword "***\<ServicePassword\>***"**</span></span>  
  
        <span data-ttu-id="6e4fa-134">Esto permite que los servicios de notificación inicien sesión en la base de datos correcta (nscontrol mantiene esta información en el Registro del equipo de servicio).</span><span class="sxs-lookup"><span data-stu-id="6e4fa-134">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="6e4fa-135">Recuerde que debe usar el nuevo servidor de bases de datos de servicios de notificación en el **-server** opción al volver a registrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-135">Remember to use the new Notification Services databases server in the **-server** option when re-registering the service.</span></span> <span data-ttu-id="6e4fa-136">Además, el nombre de usuario que utilice en los nuevos servicios de notificación debería ser el mismo que el que utilizaba en los anteriores.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-136">In addition, you should use the same user name for the new Notification Services service as the old one.</span></span>  
  
7. <span data-ttu-id="6e4fa-137">En el equipo que hospeda el portal de BAM, haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**, haga clic en **deherramientasdeconfiguración**y, a continuación, haga clic en **línea de comandos de Notification Services**.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-137">On the computer that hosts the BAM portal, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
8. <span data-ttu-id="6e4fa-138">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-138">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="6e4fa-139">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="6e4fa-139">**net stop NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="6e4fa-140">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-140">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="6e4fa-141">**NSControl unregister - name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="6e4fa-141">**nscontrol unregister  -name BamAlerts**</span></span>  
  
10. <span data-ttu-id="6e4fa-142">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-142">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="6e4fa-143">**NSControl register - nombre***\<BamAlerts\>***-server**  *\<NotificationServicesDatabaseServer    \>*</span><span class="sxs-lookup"><span data-stu-id="6e4fa-143">**nscontrol register  -name**  *\<BamAlerts\>*  **-server** *\<NotificationServicesDatabaseServer\>*</span></span>  
  
11. <span data-ttu-id="6e4fa-144">En el símbolo del sistema, escriba: **net start NS$ BamAlerts**.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-144">At the command prompt, type: **net start NS$BamAlerts**.</span></span>  
  
12. <span data-ttu-id="6e4fa-145">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-145">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="6e4fa-146">En el símbolo del sistema, desplácese al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-146">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
14. <span data-ttu-id="6e4fa-147">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6e4fa-147">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="6e4fa-148">**bm.exe update-config –FileName:config.xml**</span><span class="sxs-lookup"><span data-stu-id="6e4fa-148">**bm.exe update-config –FileName:config.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e4fa-149">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6e4fa-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4fa-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e4fa-150">See Also</span></span>  
 [<span data-ttu-id="6e4fa-151">Realizar una copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="6e4fa-151">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)