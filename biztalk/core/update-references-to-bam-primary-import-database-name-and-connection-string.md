---
title: Actualizar la cadena de conexión y nombre de base de datos de importación principal BAM | Microsoft Docs
ms.custom: ''
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846aa3b08ce6cce9b2334da72440cf5ba918e5d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003141"
---
# <a name="update-references-to-the-bam-primary-import-database-name-and-connection-string"></a><span data-ttu-id="9e90e-102">Actualizar las referencias a la cadena de conexión y el nombre de base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="9e90e-102">Update References to the BAM Primary Import Database Name and Connection String</span></span>
<span data-ttu-id="9e90e-103">Si ha realizado una copia de seguridad de la base de datos BAMPrimaryImport, en el caso de que se produzca un error de datos o del sistema podrá restaurar la copia de seguridad en un equipo distinto y cambiar el nombre a esa copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9e90e-103">If you backed up your BAMPrimaryImport database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="9e90e-104">El servicio de bus de eventos BAM mueve los datos de eventos desde la base de datos de cuadro de mensajes a la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="9e90e-104">The BAM Event Bus service moves event data from the MessageBox database to the BAMPrimaryImport database.</span></span> <span data-ttu-id="9e90e-105">El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos.</span><span class="sxs-lookup"><span data-stu-id="9e90e-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="9e90e-106">Para obtener más información sobre el servicio de Bus de eventos BAM, consulte [administrar el servicio de Bus de eventos BAM](../core/managing-the-bam-event-bus-service.md).</span><span class="sxs-lookup"><span data-stu-id="9e90e-106">For more information about the BAM Event Bus service, see [Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md).</span></span>  
  
 <span data-ttu-id="9e90e-107">Para restaurar la base de datos BAMPrimaryImport, siga los pasos descritos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9e90e-107">To restore the BAMPrimaryImport database, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="9e90e-108">Además, tendrá que realizar estos pasos generales, a los que sigue un procedimiento que describe los pasos de forma detallada:</span><span class="sxs-lookup"><span data-stu-id="9e90e-108">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="9e90e-109">Actualice la conexión 1 de SQL en todos los paquetes DTS de SAE para hacer referencia al nuevo nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e90e-109">Update the SQL Connection 1 in all BAM DTS packages to refer to the new database name.</span></span>  
  
-   <span data-ttu-id="9e90e-110">Actualice el archivo web.config con el nuevo nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e90e-110">Update the web.config file with the new database name.</span></span>  
  
-   <span data-ttu-id="9e90e-111">Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM.</span><span class="sxs-lookup"><span data-stu-id="9e90e-111">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e90e-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e90e-112">Prerequisites</span></span>  
<span data-ttu-id="9e90e-113">Inicie sesión como miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e90e-113">Sign in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-references"></a><span data-ttu-id="9e90e-114">Actualizar las referencias</span><span class="sxs-lookup"><span data-stu-id="9e90e-114">Update the references</span></span>  
  
1. <span data-ttu-id="9e90e-115">Detenga todos los paquetes de Servicios de transformación de datos (DTS) de mantenimiento de datos y de actualización de cubos de BAM, o impida su ejecución hasta que se haya restaurado la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="9e90e-115">Stop any BAM cube update and data maintenance Data Transformation Services (DTS) packages, or prevent them from running until you have restored the BAMPrimaryImport database.</span></span>  
  
2. <span data-ttu-id="9e90e-116">Detenga el servicio de aplicaciones de BizTalk (que incluye el servicio de bus de eventos de SAE) para que no intente importar más datos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e90e-116">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
   1.  <span data-ttu-id="9e90e-117">Desde el **iniciar** menú, escriba **services.msc**y abra **servicios**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-117">From the **Start** menu, type **services.msc**, and open **Services**.</span></span>  
  
   2.  <span data-ttu-id="9e90e-118">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** servicio y, a continuación, **detener**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-118">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service, and then **Stop**.</span></span>  
  
3. <span data-ttu-id="9e90e-119">Restaurar la base de datos BAMPrimaryImport (pasos de [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)).</span><span class="sxs-lookup"><span data-stu-id="9e90e-119">Restore the BAMPrimaryImport database (steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md)).</span></span>  
  
4. <span data-ttu-id="9e90e-120">Actualice los siguientes archivos Web.Config:</span><span class="sxs-lookup"><span data-stu-id="9e90e-120">Update the following Web.Config files:</span></span>  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="9e90e-121">\BAMPortal\BamManagementService\Web.config.</span><span class="sxs-lookup"><span data-stu-id="9e90e-121">\BAMPortal\BamManagementService\Web.Config.</span></span>  
  
      <span data-ttu-id="9e90e-122">Reemplace el *\<ServerName\>* de cadena con el nuevo nombre del servidor y *\<DatabaseName\>* con el nuevo nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e90e-122">Replace the *\<ServerName\>* string with the new server name, and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="9e90e-123">Actualice las cadenas de conexión siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e90e-123">Update the following connection strings:</span></span>  
  
      <span data-ttu-id="9e90e-124">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="9e90e-124">\<appSettings\></span></span>  
  
      <span data-ttu-id="9e90e-125">< Agregar clave = "BamServer" value = "*\<ServerName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="9e90e-125"><add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
      <span data-ttu-id="9e90e-126">< Agregar clave = "BamDatabase" value = "*\<DatabaseName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="9e90e-126"><add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
      <span data-ttu-id="9e90e-127">\<Agregar clave = "MaxResultRows" value = "2000" /\></span><span class="sxs-lookup"><span data-stu-id="9e90e-127">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
      <span data-ttu-id="9e90e-128">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="9e90e-128">\</appSettings\></span></span>  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="9e90e-129">\BAMPortal\BamQueryService\Web.config.</span><span class="sxs-lookup"><span data-stu-id="9e90e-129">\BAMPortal\BamQueryService\Web.Config.</span></span>  
  
      <span data-ttu-id="9e90e-130">Reemplace el *\<ServerName\>* de cadena con el nuevo nombre del servidor y *\<DatabaseName\>* con el nuevo nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e90e-130">Replace the *\<ServerName\>* string with the new server name and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="9e90e-131">Actualice las cadenas de conexión siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e90e-131">Update the following connection strings:</span></span>  
  
      <span data-ttu-id="9e90e-132">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="9e90e-132">\<appSettings\></span></span>  
  
      <span data-ttu-id="9e90e-133">\<Agregar clave = "BamServer" value = "*\<ServerName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="9e90e-133">\<add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
      <span data-ttu-id="9e90e-134">\<Agregar clave = "BamDatabase" value = "*\<DatabaseName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="9e90e-134">\<add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
      <span data-ttu-id="9e90e-135">\<Agregar clave = "MaxResultRows" value = "2000" /\></span><span class="sxs-lookup"><span data-stu-id="9e90e-135">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
      <span data-ttu-id="9e90e-136">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="9e90e-136">\</appSettings\></span></span>  
  
5. <span data-ttu-id="9e90e-137">Abra un símbolo del sistema (menú Inicio > símbolo del sistema) y navegue hasta el siguiente directorio: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore.</span><span class="sxs-lookup"><span data-stu-id="9e90e-137">Open a command prompt (Start menu > Command Prompt), and navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore.</span></span>  
  
6. <span data-ttu-id="9e90e-138">Haga clic en **SampleUpdateInfo.xml**, y **editar**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-138">Right-click **SampleUpdateInfo.xml**, and **Edit**.</span></span>  
  
   1.  <span data-ttu-id="9e90e-139">En comentario todas las secciones de la base de datos, excepto el OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert.</span><span class="sxs-lookup"><span data-stu-id="9e90e-139">Comment out all of the database sections except for the  OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span> 
   2.  <span data-ttu-id="9e90e-140">OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert secciones, establezca el **SourceServer** y **servidor de destino** a la nombre del servidor donde residen las bases de datos existente.</span><span class="sxs-lookup"><span data-stu-id="9e90e-140">For the OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the **SourceServer** and **Destination Server** to the name of the existing server where those databases reside.</span></span>  
  
   3.  <span data-ttu-id="9e90e-141">Para PrimaryImportDatabase, establezca el **"SourceServer"** en el nombre del servidor donde se ha movido la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="9e90e-141">For PrimaryImportDatabase, set the **"SourceServer"** to the name of the server where you have moved the BAM Primary Import database.</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="9e90e-142">Flanquee el nombre de los sistemas de origen y destino con comillas.</span><span class="sxs-lookup"><span data-stu-id="9e90e-142">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="9e90e-143">Si cambió el nombre de cualquiera de las bases de datos de BizTalk Server, asegúrese de actualizar también los nombres de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e90e-143">If you renamed any of the BizTalk Server databases, be sure to also update the database names.</span></span>  
  
   4.  <span data-ttu-id="9e90e-144">Cuando termine de editar el archivo, guárdelo y salga.</span><span class="sxs-lookup"><span data-stu-id="9e90e-144">When you are finished editing the file, save it, and exit.</span></span>  
  
7. <span data-ttu-id="9e90e-145">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9e90e-145">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="9e90e-146">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="9e90e-146">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9e90e-147">Sólo ejecutar UpdateDatabase.vbs una vez.</span><span class="sxs-lookup"><span data-stu-id="9e90e-147">Only run UpdateDatabase.vbs once.</span></span>  
   > 
   >  <span data-ttu-id="9e90e-148">En equipos de 64 bits, ejecute UpdateDatabase.vbs desde un símbolo del sistema de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="9e90e-148">On 64-bit computers, run UpdateDatabase.vbs from a 64-bit command prompt.</span></span>  
  
8. <span data-ttu-id="9e90e-149">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e90e-149">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="9e90e-150">\Tracking</span><span class="sxs-lookup"><span data-stu-id="9e90e-150">\Tracking</span></span>  
  
9. <span data-ttu-id="9e90e-151">En el símbolo del sistema, edite bm.exe.config, cambie el valor de key="DefaultServer" al nuevo nombre de servidor y, seguidamente, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="9e90e-151">At the command prompt, edit bm.exe.config, change the value of key="DefaultServer" to the new server name, and then save the file.</span></span>  
  
10. <span data-ttu-id="9e90e-152">Actualice la referencia a la base de datos BAMPrimaryImport en todos los archivos Microsoft Excel de datos activos de BAM.</span><span class="sxs-lookup"><span data-stu-id="9e90e-152">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="9e90e-153">Para cada uno de los archivos:</span><span class="sxs-lookup"><span data-stu-id="9e90e-153">For each file:</span></span>  
  
    1.  <span data-ttu-id="9e90e-154">Abra el archivo de datos activos de Excel.</span><span class="sxs-lookup"><span data-stu-id="9e90e-154">Open the Excel live data file.</span></span> <span data-ttu-id="9e90e-155">El nombre de archivo finaliza con _LiveData.xls.</span><span class="sxs-lookup"><span data-stu-id="9e90e-155">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="9e90e-156">En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-156">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="9e90e-157">En el **Seleccionar base de datos de BAM** cuadro de diálogo, escriba la base de datos de SQL Server y BAMPrimaryImport y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-157">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="9e90e-158">En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-158">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="9e90e-159">En el menú **Archivo** , haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-159">On the **File** menu, click **Save**.</span></span>  
  
11. <span data-ttu-id="9e90e-160">Reinicie el servicio de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9e90e-160">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="9e90e-161">Abra **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-161">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="9e90e-162">Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** servicio y, a continuación, **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9e90e-162">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service, and then **Start**.</span></span>  
  
12. <span data-ttu-id="9e90e-163">Habilite todos los paquetes DTS de mantenimiento de datos y todas las actualizaciones de cubos de SAE.</span><span class="sxs-lookup"><span data-stu-id="9e90e-163">Enable any BAM cube update and data maintenance DTS packages.</span></span>  
  
13. <span data-ttu-id="9e90e-164">Para resolver todas las instancias de seguimiento incompletas, vea [resolver instancias de actividad incompletas](../core/how-to-resolve-incomplete-activity-instances.md).</span><span class="sxs-lookup"><span data-stu-id="9e90e-164">To resolve any incomplete trace instances, see [Resolve Incomplete Activity Instances](../core/how-to-resolve-incomplete-activity-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e90e-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e90e-165">See Also</span></span>  
 [<span data-ttu-id="9e90e-166">Realizar una copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="9e90e-166">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
