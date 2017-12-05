---
title: "Cómo actualizar referencias a la cadena de conexión y el nombre de base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring [BAM], connection strings
- Primary Import database [BAM], updating references
- connection strings, restoring
- connection strings, BAM
- restoring, BAM
- restoring [BAM], Primary Import database
- restoring [BAM], updating references
- Primary Import database [BAM], restoring
- BAM, restoring
- restoring, connection strings
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23efa3df9c59732c8459018a886f7f499d268eff
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-references-to-the-bam-primary-import-database-name-and-connection-string"></a><span data-ttu-id="2fe2c-102">Cómo actualizar referencias a la cadena de conexión y al nombre de base de datos de importación principal de SAE</span><span class="sxs-lookup"><span data-stu-id="2fe2c-102">How to Update References to the BAM Primary Import Database Name and Connection String</span></span>
<span data-ttu-id="2fe2c-103">Si ha realizado una copia de seguridad de la base de datos BAMPrimaryImport, en el caso de que se produzca un error de datos o del sistema podrá restaurar la copia de seguridad en un equipo distinto y cambiar el nombre a esa copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-103">If you backed up your BAMPrimaryImport database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="2fe2c-104">El servicio de bus de eventos BAM mueve los datos de eventos desde la base de datos de cuadro de mensajes a la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-104">The BAM Event Bus service moves event data from the MessageBox database to the BAMPrimaryImport database.</span></span> <span data-ttu-id="2fe2c-105">El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="2fe2c-106">Para obtener más información sobre el servicio de Bus de sucesos SAE, vea [administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md).</span><span class="sxs-lookup"><span data-stu-id="2fe2c-106">For more information about the BAM Event Bus service, see [Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md).</span></span>  
  
 <span data-ttu-id="2fe2c-107">Para restaurar la base de datos BAMPrimaryImport, siga los pasos descritos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2fe2c-107">To restore the BAMPrimaryImport database, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="2fe2c-108">Además, tendrá que realizar estos pasos generales, a los que sigue un procedimiento que describe los pasos de forma detallada:</span><span class="sxs-lookup"><span data-stu-id="2fe2c-108">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="2fe2c-109">Actualice la conexión 1 de SQL en todos los paquetes DTS de SAE para hacer referencia al nuevo nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-109">Update the SQL Connection 1 in all BAM DTS packages to refer to the new database name.</span></span>  
  
-   <span data-ttu-id="2fe2c-110">Actualice el archivo web.config con el nuevo nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-110">Update the web.config file with the new database name.</span></span>  
  
-   <span data-ttu-id="2fe2c-111">Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-111">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2fe2c-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2fe2c-112">Prerequisites</span></span>  
 <span data-ttu-id="2fe2c-113">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-113">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bamprimaryimport-database-name-and-connection-string"></a><span data-ttu-id="2fe2c-114">Para actualizar referencias a la cadena de conexión y al nombre de base de datos BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="2fe2c-114">To update references to the BAMPrimaryImport database name and connection string</span></span>  
  
1.  <span data-ttu-id="2fe2c-115">Detenga todos los paquetes de Servicios de transformación de datos (DTS) de mantenimiento de datos y de actualización de cubos de BAM, o impida su ejecución hasta que se haya restaurado la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-115">Stop any BAM cube update and data maintenance Data Transformation Services (DTS) packages, or prevent them from running until you have restored the BAMPrimaryImport database.</span></span>  
  
2.  <span data-ttu-id="2fe2c-116">Detenga el servicio de aplicaciones de BizTalk (que incluye el servicio de bus de eventos de SAE) para que no intente importar más datos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-116">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
    1.  <span data-ttu-id="2fe2c-117">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-117">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="2fe2c-118">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-118">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="2fe2c-119">Restaurar la base de datos BAMPrimaryImport, realice los pasos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2fe2c-119">Restore the BAMPrimaryImport database, performing the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span>  
  
4.  <span data-ttu-id="2fe2c-120">Actualice los siguientes archivos Web.Config:</span><span class="sxs-lookup"><span data-stu-id="2fe2c-120">Update the following Web.Config files:</span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="2fe2c-121">BAMPortal\BamManagementService\Web.Config.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-121">BAMPortal\BamManagementService\Web.Config.</span></span>  
  
         <span data-ttu-id="2fe2c-122">Reemplace el  *\<ServerName\>*  de cadena con el nuevo nombre del servidor y  *\<DatabaseName\>*  con el nuevo nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-122">Replace the *\<ServerName\>* string with the new server name and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="2fe2c-123">Actualice las cadenas de conexión siguientes:</span><span class="sxs-lookup"><span data-stu-id="2fe2c-123">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="2fe2c-124">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-124">\<appSettings\></span></span>  
  
         <span data-ttu-id="2fe2c-125">< Agregar clave = "BamServer" value = "*\<ServerName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-125"><add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
         <span data-ttu-id="2fe2c-126">< Agregar clave = "BamDatabase" value = "*\<DatabaseName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-126"><add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
         <span data-ttu-id="2fe2c-127">\<Agregar clave = "MaxResultRows" value = "2000" /\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-127">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
         <span data-ttu-id="2fe2c-128">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-128">\</appSettings\></span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="2fe2c-129">BAMPortal\BamQueryService\Web.Config.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-129">BAMPortal\BamQueryService\Web.Config.</span></span>  
  
         <span data-ttu-id="2fe2c-130">Reemplace el  *\<ServerName\>*  de cadena con el nuevo nombre del servidor y  *\<DatabaseName\>*  con el nuevo nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-130">Replace the *\<ServerName\>* string with the new server name and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="2fe2c-131">Actualice las cadenas de conexión siguientes:</span><span class="sxs-lookup"><span data-stu-id="2fe2c-131">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="2fe2c-132">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-132">\<appSettings\></span></span>  
  
         <span data-ttu-id="2fe2c-133">\<Agregar clave = "BamServer" value = "*\<ServerName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-133">\<add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
         <span data-ttu-id="2fe2c-134">\<Agregar clave = "BamDatabase" value = "*\<DatabaseName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-134">\<add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
         <span data-ttu-id="2fe2c-135">\<Agregar clave = "MaxResultRows" value = "2000" /\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-135">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
         <span data-ttu-id="2fe2c-136">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="2fe2c-136">\</appSettings\></span></span>  
  
5.  <span data-ttu-id="2fe2c-137">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="2fe2c-138">Navegue hasta el siguiente directorio: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-138">Navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore.</span></span>  
  
7.  <span data-ttu-id="2fe2c-139">Haga clic en **SampleUpdateInfo.xml**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-139">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
    1.  <span data-ttu-id="2fe2c-140">Convierta en comentario todas las secciones de bases de datos, a excepción de BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-140">Comment out all of the database sections except for the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span>  
  
    2.  <span data-ttu-id="2fe2c-141">Para la BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert secciones, establezca el **"SourceServer"** y **"Servidor de destino"**  para el nombre del servidor existente donde residen las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-141">For the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the **"SourceServer"** and **"Destination Server"** to the name of the existing server where those databases reside.</span></span>  
  
    3.  <span data-ttu-id="2fe2c-142">En cuanto a PrimaryImportDatabase, establezca el **"SourceServer"** para el nombre del servidor donde se ha movido la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-142">For PrimaryImportDatabase, set the **"SourceServer"** to the name of the server where you have moved the BAM Primary Import database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="2fe2c-143">Flanquee el nombre de los sistemas de origen y destino con comillas.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-143">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2fe2c-144">Si cambia el nombre de alguna de las bases de datos de BizTalk Server, también tendrá que actualizar los nombres de las bases de datos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-144">If you renamed any of the BizTalk Server databases, you must also update the database names as appropriate.</span></span>  
  
    4.  <span data-ttu-id="2fe2c-145">Cuando haya terminado de editar el archivo, guárdelo y salga de él.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-145">When you are finished editing the file, save it and exit.</span></span>  
  
8.  <span data-ttu-id="2fe2c-146">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="2fe2c-146">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="2fe2c-147">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="2fe2c-147">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fe2c-148">Tan sólo tendrá que ejecutar UpdateDatabase.vbs una vez.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-148">You only need to run UpdateDatabase.vbs once.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fe2c-149">En los equipos de 64 bits, debe ejecutar UpdateDatabase.vbs desde un símbolo del sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-149">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span>  
  
9. <span data-ttu-id="2fe2c-150">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="2fe2c-150">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="2fe2c-151">Tracking</span><span class="sxs-lookup"><span data-stu-id="2fe2c-151">Tracking</span></span>  
  
10. <span data-ttu-id="2fe2c-152">En el símbolo del sistema, edite bm.exe.config, cambie el valor de key="DefaultServer" al nuevo nombre de servidor y, seguidamente, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-152">At the command prompt, edit bm.exe.config, change the value of key="DefaultServer" to the new server name, and then save the file.</span></span>  
  
11. <span data-ttu-id="2fe2c-153">Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-153">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="2fe2c-154">Para cada uno de los archivos:</span><span class="sxs-lookup"><span data-stu-id="2fe2c-154">For each file:</span></span>  
  
    1.  <span data-ttu-id="2fe2c-155">Abra el archivo de datos activos de Excel.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-155">Open the Excel live data file.</span></span> <span data-ttu-id="2fe2c-156">El nombre de archivo finaliza con _LiveData.xls.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-156">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="2fe2c-157">En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-157">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="2fe2c-158">En el **Seleccionar base de datos de BAM** cuadro de diálogo, escriba la base de datos de SQL Server y BAMPrimaryImport y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-158">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="2fe2c-159">En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-159">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="2fe2c-160">En el menú **Archivo** , haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-160">On the **File** menu, click **Save**.</span></span>  
  
12. <span data-ttu-id="2fe2c-161">Reinicie el servicio de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-161">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="2fe2c-162">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-162">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="2fe2c-163">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-163">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
13. <span data-ttu-id="2fe2c-164">Habilite todos los paquetes DTS de mantenimiento de datos y todas las actualizaciones de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="2fe2c-164">Enable any BAM cube update and data maintenance DTS packages.</span></span>  
  
14. <span data-ttu-id="2fe2c-165">Para resolver las instancias de seguimiento incompletas, vea [cómo resolver instancias de actividad incompletas](../core/how-to-resolve-incomplete-activity-instances.md).</span><span class="sxs-lookup"><span data-stu-id="2fe2c-165">To resolve any incomplete trace instances, see [How to Resolve Incomplete Activity Instances](../core/how-to-resolve-incomplete-activity-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe2c-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fe2c-166">See Also</span></span>  
 [<span data-ttu-id="2fe2c-167">Realizar una copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="2fe2c-167">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)