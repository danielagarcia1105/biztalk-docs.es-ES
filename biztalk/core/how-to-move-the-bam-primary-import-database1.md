---
title: Cómo mover la base de datos1 de importación principal BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Primary Import database [BAM]
- Primary Import database [BAM], migrating
ms.assetid: fab13fea-5c35-4a9f-977d-cc45545c54b2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff5caa9120be64e919ab4b6050f8df0c62fa33a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010613"
---
# <a name="how-to-move-the-bam-primary-import-database"></a><span data-ttu-id="9e31d-102">Cómo mover la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="9e31d-102">How to Move the BAM Primary Import Database</span></span>
<span data-ttu-id="9e31d-103">Este procedimiento se puede utilizar para mover la base de datos de importación principal de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="9e31d-103">You can use this procedure to move the BAM Primary Import database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e31d-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e31d-104">Prerequisites</span></span>  
 <span data-ttu-id="9e31d-105">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9e31d-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-primary-import-database"></a><span data-ttu-id="9e31d-106">Para mover la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="9e31d-106">To move the BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="9e31d-107">Detenga todos los servicios de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e31d-107">Stop all BizTalk Server services.</span></span> <span data-ttu-id="9e31d-108">Para obtener más información, consulte [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="9e31d-108">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
2. <span data-ttu-id="9e31d-109">Detenga el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="9e31d-109">Stop the IIS service.</span></span>  
  
3. <span data-ttu-id="9e31d-110">Detenga el servicio de notificación para alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="9e31d-110">Stop the BAM Alerts Notification Service:</span></span>  
  
   1.  <span data-ttu-id="9e31d-111">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-111">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="9e31d-112">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9e31d-112">At the command prompt, type:</span></span>  
  
       ```  
       Net stop NS$BamAlerts  
       ```  
  
4. <span data-ttu-id="9e31d-113">Siga las instrucciones en Libros en pantalla de SQL Server para realizar copias de seguridad de la base de datos de importación principal de BAM del servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="9e31d-113">Follow the instructions in SQL Server Books Online to back up the BAM Primary Import database on the old server.</span></span>  
  
5. <span data-ttu-id="9e31d-114">Copie la base de datos de importación principal de BAM en el nuevo servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9e31d-114">Copy the BAM Primary Import database to the new SQL Server.</span></span>  
  
6. <span data-ttu-id="9e31d-115">Siga las instrucciones en Libros en pantalla de SQL Server para restaurar la base de datos de importación principal de BAM en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="9e31d-115">Follow the instructions in SQL Server Books Online to restore the BAM Primary Import database on the new server.</span></span>  
  
7. <span data-ttu-id="9e31d-116">En un equipo en el que se ejecute [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], desplácese hasta la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="9e31d-116">On a computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], browse to the following folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="9e31d-117">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="9e31d-117">Schema\Restore</span></span>  
  
8. <span data-ttu-id="9e31d-118">Haga clic en **SampleUpdateInfo.xml**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-118">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
9. <span data-ttu-id="9e31d-119">En la sección de la base de datos de importación principal del archivo, reemplace **"SourceServer"** con el nombre del sistema de origen y reemplace **"DestinationServer"** con el nombre del sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9e31d-119">In the Primary Import Database section of the file, replace **"SourceServer"** with the name of the source system, and then replace **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9e31d-120">Flanquee el nombre de los sistemas de origen y destino con comillas.</span><span class="sxs-lookup"><span data-stu-id="9e31d-120">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e31d-121">Si cambia el nombre de alguna de las bases de datos de BizTalk Server, también tendrá que actualizar los nombres de las bases de datos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="9e31d-121">If you renamed any of the BizTalk Server databases, you must also update the database names as appropriate.</span></span>  
  
10. <span data-ttu-id="9e31d-122">Elimine el comentario de las líneas siguientes del archivo XML:</span><span class="sxs-lookup"><span data-stu-id="9e31d-122">Uncomment the following lines in the xml file:</span></span>  
  
    ```  
    - <UpdateConfiguration>  
      <MessageBoxDB oldDBName="BizTalkMsgboxDb" oldDBServer="Server01" newDBName="BizTalkMsgboxDb" newDBServer="Server01" IsMaster="1" />   
      <TrackingDB oldDBName="BizTalkDTADb" oldDBServer="Server01" newDBName="BizTalkDTADb" newDBServer="Server01" />   
      <ManagementDB oldDBName="BizTalkMgmtDb" oldDBServer="Server01" newDBName="BizTalkMgmtDb" newDBServer="Server01" />   
    - <BAM>  
    - <DeploymentUnit Name="OldPrimaryImportDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="PrimaryImportDatabase">  
      <Property Name="ServerName">Server02</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="ArchivingDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMArchive</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="AnalysisDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMAnalysis</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="StarSchemaDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMStarSchema</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="Alert">  
      <Property Name="DBServer">Server01</Property>   
      <Property Name="InstanceDatabaseName">BAMAlerts</Property>   
      </DeploymentUnit>  
      </BAM>  
    - <OtherDatabases>  
      <Database Name="SSO" oldDBName="SSODB" oldDBServer="Server01" newDBName="SSODB" newDBServer="Server01" />   
      </OtherDatabases>  
      </UpdateConfiguration>  
    ```  
  
11. <span data-ttu-id="9e31d-123">Cuando haya terminado de editar el archivo, guárdelo y salga de él.</span><span class="sxs-lookup"><span data-stu-id="9e31d-123">When you are finished editing the file, save it and exit.</span></span>  
  
12. <span data-ttu-id="9e31d-124">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-124">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="9e31d-125">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e31d-125">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="9e31d-126">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="9e31d-126">Schema\Restore</span></span>  
  
14. <span data-ttu-id="9e31d-127">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9e31d-127">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="9e31d-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="9e31d-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
15. <span data-ttu-id="9e31d-129">Actualice la referencia a la base de datos de importación principal de SAE en todos los archivos Microsoft Excel de datos activos de SAE.</span><span class="sxs-lookup"><span data-stu-id="9e31d-129">Update the reference to BAM Primary Import Database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="9e31d-130">Para cada uno de los archivos:</span><span class="sxs-lookup"><span data-stu-id="9e31d-130">For each file:</span></span>  
  
    1.  <span data-ttu-id="9e31d-131">Abra el archivo de datos activos de Excel.</span><span class="sxs-lookup"><span data-stu-id="9e31d-131">Open the Excel live data file.</span></span> <span data-ttu-id="9e31d-132">El nombre de archivo finaliza con _LiveData.xls.</span><span class="sxs-lookup"><span data-stu-id="9e31d-132">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="9e31d-133">En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-133">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="9e31d-134">En el **Seleccionar base de datos de BAM** cuadro de diálogo, escriba la base de datos de SQL Server y BAMPrimaryImport y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-134">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="9e31d-135">En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-135">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="9e31d-136">En el menú **Archivo** , haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-136">On the **File** menu, click **Save**.</span></span>  
  
16. <span data-ttu-id="9e31d-137">Actualice los nombres de servidor y base de datos en todos los paquetes DTS de análisis de BAM, a los que se agrega el prefijo "BAM_AN_" o "BAM_DM_" mediante los pasos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="9e31d-137">Update the server and database names in all BAM analysis DTS packages, which are prefixed with "BAM_AN_" or "BAM_DM_" by following these steps:</span></span>  
  
    1.  <span data-ttu-id="9e31d-138">En el servidor que aloja SAE, abra el Administrador corporativo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9e31d-138">On the server hosting BAM, open SQL Server Enterprise Manager.</span></span>  
  
    2.  <span data-ttu-id="9e31d-139">Abra el **Data Transformation Services** carpeta.</span><span class="sxs-lookup"><span data-stu-id="9e31d-139">Open the **Data Transformation Services** folder.</span></span>  
  
    3.  <span data-ttu-id="9e31d-140">Abra el **paquetes locales** carpeta y, a continuación, abra los paquetes DTS.</span><span class="sxs-lookup"><span data-stu-id="9e31d-140">Open the **Local Packages** folder, and then open the DTS packages.</span></span>  
  
    4.  <span data-ttu-id="9e31d-141">En el **paquete** menú, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-141">On the **Package** menu, click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="9e31d-142">En el **Variables globales** pestaña, actualice los valores para el servidor de importación principal y la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e31d-142">On the **Global Variables** tab, update the values for the primary import server and database.</span></span>  
  
    6.  <span data-ttu-id="9e31d-143">Cambie las líneas siguientes para que coincidan con el nuevo servidor y la nueva base de datos:</span><span class="sxs-lookup"><span data-stu-id="9e31d-143">Change the following lines to match your new server and database:</span></span>  
  
         <span data-ttu-id="9e31d-144">PrimaryImportServer = "*\<ServerName\>*"</span><span class="sxs-lookup"><span data-stu-id="9e31d-144">PrimaryImportServer= "*\<ServerName\>*"</span></span>  
  
         <span data-ttu-id="9e31d-145">PrimaryImportDatabase = "*\<DatabaseName\>*"</span><span class="sxs-lookup"><span data-stu-id="9e31d-145">PrimaryImportDatabase = "*\<DatabaseName\>*"</span></span>  
  
17. <span data-ttu-id="9e31d-146">Inicie todos los servicios de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e31d-146">Start all BizTalk Server services.</span></span> <span data-ttu-id="9e31d-147">Para obtener más información, consulte [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="9e31d-147">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
18. <span data-ttu-id="9e31d-148">Inicia el servicio IIS.</span><span class="sxs-lookup"><span data-stu-id="9e31d-148">Start the IIS service.</span></span>  
  
19. <span data-ttu-id="9e31d-149">Inicie el servicio de notificación para alertas de BAM:</span><span class="sxs-lookup"><span data-stu-id="9e31d-149">Start the BAM Alerts Notification Service:</span></span>  
  
    1.  <span data-ttu-id="9e31d-150">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e31d-150">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="9e31d-151">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9e31d-151">At the command prompt, type:</span></span>  
  
        ```  
        Net start NS$BamAlerts  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="9e31d-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e31d-152">See Also</span></span>  
 [<span data-ttu-id="9e31d-153">Mover bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9e31d-153">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)