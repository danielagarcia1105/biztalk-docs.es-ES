---
title: Cómo mover la notificación de BAM servicios Databases1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d0ae3e4b5af7304eb07973fd5e19efce2e68c99
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009805"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a><span data-ttu-id="6d625-102">Cómo mover las bases de datos de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="6d625-102">How to Move the BAM Notification Services Databases</span></span>
<span data-ttu-id="6d625-103">Puede usar este procedimiento para mover la base de datos de servicios de notificación de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="6d625-103">You can use this procedure to move the BAM Notification Services database to another server.</span></span>  <span data-ttu-id="6d625-104">Desde una perspectiva de escenario to-end, mover la base de datos de servicios de notificación de BAM consta de dos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="6d625-104">From an end-to-end scenario perspective, moving the BAM Notification Services database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="6d625-105">Mover la base de datos de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="6d625-105">Moving the BAM Notification Services Database</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [<span data-ttu-id="6d625-106">Actualizar las referencias a la nueva notificación de BAM de servicios de bases de datos</span><span class="sxs-lookup"><span data-stu-id="6d625-106">Updating References to the New BAM Notification Services Databases</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  <span data-ttu-id="6d625-107">Debe mover la base de datos de aplicación de servicios de notificación de BAM (BAMAlertsApplication) y la base de datos de instancia de servicios de notificación de BAM (BAMAlertsNSMain) conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="6d625-107">You must move the BAM Notification Services Application (BAMAlertsApplication) database and the BAM Notification Services Instance (BAMAlertsNSMain) database together.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6d625-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6d625-108">Prerequisites</span></span>  
 <span data-ttu-id="6d625-109">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d625-109">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_NotiMoveDB"></a><span data-ttu-id="6d625-110">Mover la base de datos de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="6d625-110">Moving the BAM Notification Services Database</span></span>  
 <span data-ttu-id="6d625-111">Realice los pasos en el siguiente procedimiento para mover la base de datos de servicios de notificación de BAM.</span><span class="sxs-lookup"><span data-stu-id="6d625-111">Perform the steps in the following procedure to move the BAM Notification Services database.</span></span>  
  
#### <a name="to-move-the-bam-notification-services-database"></a><span data-ttu-id="6d625-112">Para mover la base de datos de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="6d625-112">To move the BAM Notification Services database</span></span>  
  
1.  <span data-ttu-id="6d625-113">Detenga cualquier BAM cubo datos y actualización paquetes SSIS de mantenimiento, o impida su ejecución hasta que haya restaurado la base de datos de servicios de notificación de BAM.</span><span class="sxs-lookup"><span data-stu-id="6d625-113">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Notification Services database.</span></span>  
  
2.  <span data-ttu-id="6d625-114">Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d625-114">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="6d625-115">Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="6d625-115">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="6d625-116">Detenga el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="6d625-116">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="6d625-117">Detenga el servicio de notificación de alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="6d625-117">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="6d625-118">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d625-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="6d625-119">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6d625-119">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="6d625-120">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="6d625-120">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="6d625-121">Hacer copia de seguridad de la base de datos de servicios de notificación de BAM en el servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="6d625-121">Back up the BAM Notification Services database on the old server.</span></span> <span data-ttu-id="6d625-122">Para obtener instrucciones sobre la copia de seguridad de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo realizar copias de seguridad de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6d625-122">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6d625-123">Realice este paso para las bases de datos de BAMAlertsApplication y BAMAlertsNSMain.</span><span class="sxs-lookup"><span data-stu-id="6d625-123">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
6.  <span data-ttu-id="6d625-124">Copiar la base de datos de servicios de notificación de BAM en la nueva [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="6d625-124">Copy the BAM Notification Services database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="6d625-125">Restaure la base de datos de servicios de notificación de BAM en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="6d625-125">Restore the BAM Notification Services database on the new server.</span></span> <span data-ttu-id="6d625-126">Para obtener instrucciones acerca de cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6d625-126">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6d625-127">Realice este paso para las bases de datos de BAMAlertsApplication y BAMAlertsNSMain.</span><span class="sxs-lookup"><span data-stu-id="6d625-127">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
##  <a name="BKMK_NotiUpdate"></a><span data-ttu-id="6d625-128">Actualizar las referencias a la nueva notificación de BAM de servicios de bases de datos</span><span class="sxs-lookup"><span data-stu-id="6d625-128">Updating References to the New BAM Notification Services Databases</span></span>  
 <span data-ttu-id="6d625-129">Después de haber movido la base de datos, debe actualizar todas las referencias a las bases de datos de servicios de notificación de BAM.</span><span class="sxs-lookup"><span data-stu-id="6d625-129">After you have moved the database, you must update all the references to the new BAM Notification Services databases.</span></span> <span data-ttu-id="6d625-130">Deben actualizar las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d625-130">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="6d625-131">Actualizar la configuración de BAM con los nuevos nombres de base de datos y el servidor.</span><span class="sxs-lookup"><span data-stu-id="6d625-131">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="6d625-132">Vea [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig).</span><span class="sxs-lookup"><span data-stu-id="6d625-132">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="6d625-133">Volver a registrar el servicio de notificación en todos los equipos en los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.</span><span class="sxs-lookup"><span data-stu-id="6d625-133">Re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="6d625-134">Vea [registrar Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister).</span><span class="sxs-lookup"><span data-stu-id="6d625-134">See [Register the Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister).</span></span>  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a><span data-ttu-id="6d625-135">Para actualizar la configuración de BAM</span><span class="sxs-lookup"><span data-stu-id="6d625-135">To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="6d625-136">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="6d625-136">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="6d625-137">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d625-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="6d625-138">En un equipo que ejecuta BizTalk Server, vaya a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="6d625-138">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="6d625-139">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="6d625-139">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="6d625-140">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="6d625-140">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="6d625-141">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="6d625-141">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="6d625-142">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="6d625-142">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="6d625-143">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6d625-143">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="6d625-144">**Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -base de datos:\<base de datos\>**</span><span class="sxs-lookup"><span data-stu-id="6d625-144">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6d625-145">Cuando se ejecuta este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración de <servername> y sustituya el nombre real de la base de datos que se va a obtener la información de configuración de <database>.</span><span class="sxs-lookup"><span data-stu-id="6d625-145">When running this command, substitute the actual name of the server from which to get the configuration information for <servername> and substitute the actual name of the database from which to get the configuration information for <database>.</span></span> <span data-ttu-id="6d625-146">Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="6d625-146">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="6d625-147">Edite el archivo BAMConfiguration.xml y cambie la **DBServer** propiedades en la `<DeploymentUnit Name="Alert">` sección para el nuevo nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="6d625-147">Edit the BAMConfiguration.xml file and change the **DBServer** properties in the `<DeploymentUnit Name="Alert">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="6d625-148">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="6d625-148">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="6d625-149">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d625-149">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6d625-150">En un equipo que ejecuta BizTalk Server, vaya a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="6d625-150">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="6d625-151">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="6d625-151">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="6d625-152">**% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="6d625-152">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="6d625-153">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="6d625-153">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="6d625-154">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="6d625-154">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="6d625-155">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6d625-155">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="6d625-156">**bm.exe update-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="6d625-156">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_NotiRegister"></a><span data-ttu-id="6d625-157">Registrar los servicios de notificación</span><span class="sxs-lookup"><span data-stu-id="6d625-157">Register the Notification Services</span></span>  
 <span data-ttu-id="6d625-158">Después de haber movido la base de datos de servicios de notificación de BAM, debe volver a registrar el servicio de notificación en todos los equipos del grupo de BizTalk Server que se ejecutan los servicios de notificación (NSservice.exe).</span><span class="sxs-lookup"><span data-stu-id="6d625-158">After you have moved the BAM Notification Services database, you must re-register the Notification Service on all computers in the BizTalk Server group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="6d625-159">Con ello, se permite que los servicios de notificación se conecten a las bases de datos en su nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="6d625-159">This enables Notification Services to connect to the databases in their new location.</span></span> <span data-ttu-id="6d625-160">Para obtener instrucciones sobre cómo registrar los servicios de notificación, siga los pasos 5 al 11 en [cómo actualizar referencias a las bases de datos de servicios de notificación de BAM](http://go.microsoft.com/fwlink/?LinkId=156684) (http://go.microsoft.com/fwlink/?LinkId=156684) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="6d625-160">For instructions on how to register the Notification Services, follow steps 5 through 11 at [How to Update References to the BAM Notification Services Databases](http://go.microsoft.com/fwlink/?LinkId=156684) (http://go.microsoft.com/fwlink/?LinkId=156684) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="6d625-161">Tenga en cuenta lo siguiente cuando realice los pasos mencionados en el vínculo anterior:</span><span class="sxs-lookup"><span data-stu-id="6d625-161">Note the following while performing steps mentioned in the preceding link:</span></span>  
  
-   <span data-ttu-id="6d625-162">Los pasos 5 y 6 en el vínculo anterior deben realizarse en los servidores enumerados en el XML de configuración de BAM para las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d625-162">Steps 5 and 6 in the preceding link must be performed on the servers listed in the BAM configuration XML for the following properties:</span></span>  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   <span data-ttu-id="6d625-163">Paso 7 a 11 debe realizarse en el equipo que aloja el portal BAM.</span><span class="sxs-lookup"><span data-stu-id="6d625-163">Step 7 through 11 must be performed on the computer that hosts the BAM portal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d625-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d625-164">See Also</span></span>  
 [<span data-ttu-id="6d625-165">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="6d625-165">Moving Databases</span></span>](../technical-guides/moving-databases.md)