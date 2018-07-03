---
title: Cómo configurar el sistema de destino del trasvase de registros | Microsoft Docs
ms.custom: ''
ms.date: 2015-12-03
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- system failures, preventing
- log shipping
- databases, backing up
- backing up, databases
- system failures, backing up
- backing up, system failures
ms.assetid: 7b4425f5-b105-4fb2-a503-94ca1e75ad55
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ee5c7a5d59ce60923fa4ad3ba015f60bc30a0c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971469"
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="934ac-102">Cómo configurar el sistema de destino para el envío de registros</span><span class="sxs-lookup"><span data-stu-id="934ac-102">How to Configure the Destination System for Log Shipping</span></span>
<span data-ttu-id="934ac-103">El trasvase de registros proporciona funciones de servidor en espera para reducir el tiempo de inactividad en caso de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="934ac-103">Log shipping provides standby server capabilities to reduce downtime in the event of a system failure.</span></span> <span data-ttu-id="934ac-104">El envío de registros permite enviar automáticamente registros de transacciones desde el sistema de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-104">Log shipping allows you to automatically send transaction logs from the source system to the destination system.</span></span> <span data-ttu-id="934ac-105">En el sistema de destino, los registros de transacciones se restauran en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos; mantienen estrechamente sincronizados con las bases de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="934ac-105">At the destination system, the transaction logs are restored to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases; keeping them closely synchronized with the source databases.</span></span>  
  
 <span data-ttu-id="934ac-106">El envío de registros funciona tanto en entornos de servidor distribuido como de un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="934ac-106">Log shipping works in both single server and distributed server environments.</span></span> <span data-ttu-id="934ac-107">El servidor o grupo de servidores que contiene datos activos se conoce como sistema de origen (o principal).</span><span class="sxs-lookup"><span data-stu-id="934ac-107">The server or group of servers that contain live data is known as the source (or primary) system.</span></span> <span data-ttu-id="934ac-108">El servidor o grupo de servidores que se usa para restaurar las copias de seguridad de base de datos que genera el sistema de origen (o principal) se conoce como sistema de destino (o secundario).</span><span class="sxs-lookup"><span data-stu-id="934ac-108">The server or group of servers that are used to restore the database backups produced by the source (or primary) system is known as the destination (or secondary) system.</span></span>  
  
 <span data-ttu-id="934ac-109">[Acerca del trasvase de registros](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server) en el código SQL documentación proporciona detalles específicos.</span><span class="sxs-lookup"><span data-stu-id="934ac-109">[About Log Shipping](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server) in the SQL documentation provides specific details.</span></span>  
  
 <span data-ttu-id="934ac-110">Puede seguir los siguientes pasos para crear un sistema de destino compuesto de un servidor para un sistema de origen único.</span><span class="sxs-lookup"><span data-stu-id="934ac-110">You can use the following steps to create a destination system that consists of one server for a single source system.</span></span> <span data-ttu-id="934ac-111">Si el sistema de destino contiene varios servidores, repita los pasos en cada uno de éstos.</span><span class="sxs-lookup"><span data-stu-id="934ac-111">If the destination system contains multiple servers, repeat the steps on each destination server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="934ac-112">Guarde siempre una copia de sus archivos de copia de seguridad en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="934ac-112">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="934ac-113">Aunque haya registrado copias de seguridad, no podrá restaurar las bases de datos sin los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="934ac-113">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="934ac-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="934ac-114">Prerequisites</span></span>  
* <span data-ttu-id="934ac-115">Inicie sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="934ac-115">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
* <span data-ttu-id="934ac-116">Utilice la misma versión de SQL Server en los sistemas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-116">Use the same version of SQL Server on the source and destination systems.</span></span> <span data-ttu-id="934ac-117">SQL Server debe instalarse en la misma ubicación relativa en los sistemas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-117">SQL Server must be installed in the same relative location on the source and destination systems.</span></span>  
  
* <span data-ttu-id="934ac-118">El directorio para el registro de transacciones SQL (archivos .LDF) del sistema de origen también debe existir en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-118">The directory for SQL transaction log (.LDF files) on the source system must also exist on the destination system.</span></span> <span data-ttu-id="934ac-119">Si este directorio no se encuentra en el sistema de destino, cree el directorio con el mismo nombre y con los mismos permisos del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="934ac-119">If this directory is not on the destination system, create the directory with the same name and permissions as on the source system.</span></span>  
  
### <a name="configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="934ac-120">Configurar el sistema de destino del trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="934ac-120">Configure the destination system for log shipping</span></span>  
  
1. <span data-ttu-id="934ac-121">En el sistema de destino, abra **SQL Server Management Studio**y conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="934ac-121">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span> <span data-ttu-id="934ac-122">Seleccione **maestro** de bases de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="934ac-122">Select **master** from Available Databases.</span></span>  
  
2. <span data-ttu-id="934ac-123">En el **archivo** menú, **abierto** el siguiente script SQL:</span><span class="sxs-lookup"><span data-stu-id="934ac-123">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
   ```  
  
3. <span data-ttu-id="934ac-124">En el **consulta** menú, seleccione **Execute**.</span><span class="sxs-lookup"><span data-stu-id="934ac-124">On the **Query** menu, select **Execute**.</span></span>  
  
    <span data-ttu-id="934ac-125">El *script LogShipping_Destination_Schema* quita y vuelve a crear las tablas utilizadas para restaurar las bases de datos de origen del sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-125">The *LogShipping_Destination_Schema* drops and recreates the tables used for restoring the source databases on the destination system.</span></span> <span data-ttu-id="934ac-126">Se incluyen las tablas para almacenar la lista de bases de datos que se están recuperando, copias del historial de copias de seguridad importado desde la base de datos BizTalkMgmtDb del sistema de origen e información acerca de los trabajos del Agente SQL Server que se configuraron para que se ejecutaran respecto a las bases de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="934ac-126">This includes tables to store the list of databases being recovered, copies of the backup history imported from the source system's BizTalkMgmtDb database, and information about SQL Server Agent jobs configured to run against the source databases.</span></span>  
  
4. <span data-ttu-id="934ac-127">En el **archivo** menú, **abierto** el siguiente script SQL:</span><span class="sxs-lookup"><span data-stu-id="934ac-127">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
   ```  
  
5. <span data-ttu-id="934ac-128">En el **consulta** menú, seleccione **Execute**.</span><span class="sxs-lookup"><span data-stu-id="934ac-128">On the **Query** menu, select **Execute**.</span></span>  
  
6. <span data-ttu-id="934ac-129">En el equipo o equipos identificados como sistemas de destino, abra **SQL Server Management Studio** y conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="934ac-129">On the computer or computers you have identified as the destination system, open **SQL Server Management Studio** and connect to the SQL Server.</span></span>  
  
7. <span data-ttu-id="934ac-130">Seleccione **nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="934ac-130">Select **New Query**.</span></span> <span data-ttu-id="934ac-131">Pegue el comando siguiente en la ventana de consulta:</span><span class="sxs-lookup"><span data-stu-id="934ac-131">In the query window, paste the following command:</span></span>  
  
   ```  
   exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
   @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
   @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
   @SourceServerName = null, -- null indicates that this destination server restores all databases  
   @fLinkServers = 1 -- 1 automatically links the server to the management database  
   ```  
  
    <span data-ttu-id="934ac-132">A continuación:</span><span class="sxs-lookup"><span data-stu-id="934ac-132">Then:</span></span>  
  
   1.  <span data-ttu-id="934ac-133">En el sistema de destino, habilite  **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**.</span><span class="sxs-lookup"><span data-stu-id="934ac-133">On the destination system, enable **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**.</span></span>  
  
   2.  <span data-ttu-id="934ac-134">En la ventana de consulta, reemplace *\<MyLogShippingSolution\>* con una descripción significativa entre comillas simples.</span><span class="sxs-lookup"><span data-stu-id="934ac-134">In the query window, replace *\<MyLogShippingSolution\>* with a meaningful description, surrounded by single quotes.</span></span>  
  
   3.  <span data-ttu-id="934ac-135">En la ventana de consulta, reemplace *\<BizTalkServerManagementDatabaseName\>* y *\<BizTalkServerManagementDatabaseServer\>* con el nombre y la ubicación de la base de datos de administración de BizTalk de origen, entrecomillado comillas simples.</span><span class="sxs-lookup"><span data-stu-id="934ac-135">In the query window, replace *\<BizTalkServerManagementDatabaseName\>* and *\<BizTalkServerManagementDatabaseServer\>* with the name and location of your source BizTalk Management database, surrounded by single quotes.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="934ac-136">Si tiene más de un servidor de origen, puede restaurar cada uno de ellos en su propio servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-136">If you have more than one source server, you can restore each source server to its own destination server.</span></span> <span data-ttu-id="934ac-137">En cada servidor de destino en el  **@SourceServerName = null** parámetro, reemplace *null* con el nombre del servidor de origen que corresponda, flanqueado por comillas (por ejemplo,  **@SourceServerName = 'Miservidordeorigen',**).</span><span class="sxs-lookup"><span data-stu-id="934ac-137">On each destination server, in the **@SourceServerName = null** parameter, replace *null* with the name of the appropriate source server, surrounded by single quotes (for example, **@SourceServerName = 'MySourceServer',**).</span></span>  
  
8. <span data-ttu-id="934ac-138">En el **consulta** menú, seleccione **Execute**.</span><span class="sxs-lookup"><span data-stu-id="934ac-138">On the **Query** menu, select **Execute**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="934ac-139">Si la consulta produce un error, después de corregir el problema con la consulta, debe empezar desde el paso 1 de este procedimiento para volver a configurar el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-139">If the query fails, after you fix the problem with the query, you must start over from step 1 of this procedure to reconfigure the destination system.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="934ac-140">Los trabajos de restauración del sistema de destino intentan volver a crear los archivos de datos y registros para cada una de las bases de datos restauradas en la misma ubicación en la que existieron en el servidor de base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="934ac-140">The restore jobs on the destination system attempt to recreate the log and data files for each restored database in the same location as they existed on the source database server.</span></span>  
  
9. <span data-ttu-id="934ac-141">En el sistema de destino en **SQL Server Management Studio**, expanda **del Agente SQL Server**y expanda **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="934ac-141">On the destination system in **SQL Server Management Studio**, expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
     <span data-ttu-id="934ac-142">En el panel de detalles, hay tres trabajos nuevos:</span><span class="sxs-lookup"><span data-stu-id="934ac-142">In the details pane, there are three new jobs:</span></span>  
  
   - <span data-ttu-id="934ac-143">**Registro BTS-obtener historial de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="934ac-143">**BTS Log Shipping Get Backup History**</span></span>  
  
      <span data-ttu-id="934ac-144">Este trabajo de BizTalk mueve los registros de historial de copia de seguridad desde el origen al destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-144">This BizTalk job moves backup history records from the source to the destination.</span></span> <span data-ttu-id="934ac-145">De forma predeterminada, está programado para ejecutarse cada minuto.</span><span class="sxs-lookup"><span data-stu-id="934ac-145">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="934ac-146">Este trabajo se ejecuta con la mayor frecuencia posible para mover registros de historial del origen al destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-146">This job runs as frequently as possible in order to move history records from the source to the destination.</span></span> <span data-ttu-id="934ac-147">En el caso de que se produzca un error en el sistema de origen, el servidor identificado como el sistema de destino sigue procesando los registros de historial ya importados.</span><span class="sxs-lookup"><span data-stu-id="934ac-147">In the event of a system failure to the source system, the server that you identified as the destination system continues to process the history records that have already been imported.</span></span>  
  
   - <span data-ttu-id="934ac-148">**Servidor de registro BTS-Restaurar bases de datos**</span><span class="sxs-lookup"><span data-stu-id="934ac-148">**BTS Server Log Shipping Restore Databases**</span></span>  
  
      <span data-ttu-id="934ac-149">Este trabajo de BizTalk restaura los archivos de copia de seguridad para las bases de datos del origen en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-149">This BizTalk job restores backup files for the given databases for the source to the destination server.</span></span> <span data-ttu-id="934ac-150">De forma predeterminada, está programado para ejecutarse cada minuto.</span><span class="sxs-lookup"><span data-stu-id="934ac-150">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="934ac-151">Este trabajo se ejecuta de forma continua sin completarse siempre que haya archivos de copia de seguridad que restaurar.</span><span class="sxs-lookup"><span data-stu-id="934ac-151">This job runs continuously without completing as long as there are backup files to restore.</span></span> <span data-ttu-id="934ac-152">Como precaución adicional, puede ejecutar este trabajo una vez más para garantizar que está completo.</span><span class="sxs-lookup"><span data-stu-id="934ac-152">As an extra precaution, you can run this job an additional time to ensure that it is complete.</span></span>  
  
   - <span data-ttu-id="934ac-153">**Registro BTS-Restaurar en marca**</span><span class="sxs-lookup"><span data-stu-id="934ac-153">**BTS Log Shipping Restore To Mark**</span></span>  
  
      <span data-ttu-id="934ac-154">Este trabajo de BizTalk restaura todas las bases de datos a una marca en la última copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="934ac-154">This BizTalk job restores all of the databases to a mark in the last log backup.</span></span> <span data-ttu-id="934ac-155">Con ello, se garantiza que todas las bases de datos se encuentren en un estado transaccionalmente coherente.</span><span class="sxs-lookup"><span data-stu-id="934ac-155">This ensures that all of the databases are in a transactionally consistent state.</span></span> <span data-ttu-id="934ac-156">Además, este trabajo vuelve a crear todos los trabajos del Agente SQL Server que estuvieron en el sistema de origen en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-156">In addition, this job re-creates all of the SQL Server Agent jobs on the destination system that had been on the source system.</span></span>  
  
     > [!IMPORTANT]
     >  <span data-ttu-id="934ac-157">Debe supervisar estos trabajos para garantizar que no se produzcan errores en ellos.</span><span class="sxs-lookup"><span data-stu-id="934ac-157">You should monitor these jobs to ensure that they do not fail.</span></span>  
  
10. <span data-ttu-id="934ac-158">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], vaya a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="934ac-158">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], go to the following folder:</span></span>  
  
     <span data-ttu-id="934ac-159">equipo de 32 bits: %SystemDrive%\Program Files\Microsoft BizTalk Server \<versión\>\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="934ac-159">32-bit computer: %SystemDrive%\Program Files\Microsoft BizTalk Server \<version\>\Schema\Restore</span></span>  
  
     <span data-ttu-id="934ac-160">equipo de 64 bits: %SystemDrive%\Program Files (x86) \Microsoft BizTalk Server \<versión\>\Bins32\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="934ac-160">64-bit computer: %SystemDrive%\Program Files (x86)\Microsoft BizTalk Server \<version\>\Bins32\Schema\Restore</span></span>  
  
11. <span data-ttu-id="934ac-161">Haga clic en **SampleUpdateInfo.xml**y seleccione **editar**.</span><span class="sxs-lookup"><span data-stu-id="934ac-161">Right-click **SampleUpdateInfo.xml**, and select **Edit**.</span></span> <span data-ttu-id="934ac-162">Realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="934ac-162">Do the following:</span></span>  
  
    -   <span data-ttu-id="934ac-163">Reemplace todas las instancias de **"SourceServer"** con el nombre del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="934ac-163">Replace all instances of **"SourceServer"** with the name of the source system.</span></span>  
  
    -   <span data-ttu-id="934ac-164">Reemplace todas las instancias de **"DestinationServer"** con el nombre del sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="934ac-164">Replace all instances of **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="934ac-165">Flanquee el nombre de los sistemas de origen y destino con comillas.</span><span class="sxs-lookup"><span data-stu-id="934ac-165">Include the quotation marks around the name of the source and destination systems.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="934ac-166">Si cambió el nombre de cualquier base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe actualizar los nombres de la base de datos en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="934ac-166">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names within the XML file.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="934ac-167">Si ha configurado BAM, debe agregar las siguientes líneas en el **OtherDatabases** sección de la **SampleUpdateInfo.xml** archivo para las bases de datos BAMAlertsApplication y BAMAlertsNSMain:</span><span class="sxs-lookup"><span data-stu-id="934ac-167">If you have configured BAM, you must add the following lines in the **OtherDatabases** section of the **SampleUpdateInfo.xml** file for the BAMAlertsApplication and BAMAlertsNSMain databases:</span></span>   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    > 
    >  <span data-ttu-id="934ac-168">Si ha cambiado el nombre predeterminado para estas dos bases de datos, use los nombres reales correspondientes.</span><span class="sxs-lookup"><span data-stu-id="934ac-168">If you changed the default name for these two databases, please use the actual database names.</span></span>  
  
12. <span data-ttu-id="934ac-169">Si tiene más de una base de datos de cuadro de mensajes en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system, agregue otra línea MessageBoxDB a la lista y, a continuación, establezca **IsMaster = "0"** para las bases de datos no principales.</span><span class="sxs-lookup"><span data-stu-id="934ac-169">If you have more than one MessageBox database in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system, add another MessageBoxDB line to the list, and then set **IsMaster="0"** for the non-master databases.</span></span>  
  
13. <span data-ttu-id="934ac-170">Si usa BAM o el motor de reglas, quite los comentarios de estas líneas según corresponda.</span><span class="sxs-lookup"><span data-stu-id="934ac-170">If you are using BAM or the Rules Engine, uncomment these lines as appropriate.</span></span>  
  
14. <span data-ttu-id="934ac-171">Si dispone de las bases de datos personalizados, agregarlos en el **\<OtherDatabases\>** sección.</span><span class="sxs-lookup"><span data-stu-id="934ac-171">If you have any custom databases, add them under the **\<OtherDatabases\>** section.</span></span> <span data-ttu-id="934ac-172">Consulte [cómo realizar copias de seguridad de bases de datos personalizadas](../core/how-to-back-up-custom-databases.md).</span><span class="sxs-lookup"><span data-stu-id="934ac-172">See [How to Back Up Custom Databases](../core/how-to-back-up-custom-databases.md).</span></span>  
  
15. <span data-ttu-id="934ac-173">Cuando termine de editar el archivo, guárdelo y salga.</span><span class="sxs-lookup"><span data-stu-id="934ac-173">When you are finished editing the file, save it, and exit.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="934ac-174">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="934ac-174">Next Steps</span></span>  
 [<span data-ttu-id="934ac-175">Cómo restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="934ac-175">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="934ac-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="934ac-176">See Also</span></span>  
 <span data-ttu-id="934ac-177">[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="934ac-177">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="934ac-178">[Cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="934ac-178">[How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="934ac-179">Cómo realizar copias de seguridad de bases de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="934ac-179">How to Back Up Custom Databases</span></span>](../core/how-to-back-up-custom-databases.md)