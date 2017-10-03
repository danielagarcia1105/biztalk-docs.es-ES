---
title: "Cómo habilitar la validación automática de archivos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 258fcb96bbb9bbb045aeb3f48c2b324502d44940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-automatic-archive-validation"></a><span data-ttu-id="68fe2-102">Cómo habilitar la validación automática de archivos</span><span class="sxs-lookup"><span data-stu-id="68fe2-102">How to Enable Automatic Archive Validation</span></span>
<span data-ttu-id="68fe2-103">La validación de archivos permite validar los archivos a medida que se crean.</span><span class="sxs-lookup"><span data-stu-id="68fe2-103">Archive validation enables you to validate the archives as they are created.</span></span> <span data-ttu-id="68fe2-104">Antes de poder habilitar la validación de archivos automática, tendrá que configurar un servidor de base de datos secundario, también denominado servidor de validación.</span><span class="sxs-lookup"><span data-stu-id="68fe2-104">Before you can enable automatic archive validation, you must set up a secondary database server, also called a validation server.</span></span> <span data-ttu-id="68fe2-105">Ya que el proceso de archivo es una simple copia de seguridad, es posible que se pueda dañar la imagen real almacenada en el disco debido a un problema de hardware.</span><span class="sxs-lookup"><span data-stu-id="68fe2-105">Because the archiving process is a simple backup, it is possible that the actual image stored on the disk can be corrupted due to a hardware issue.</span></span>  
  
 <span data-ttu-id="68fe2-106">Cuando utiliza la función de validación de archivos, se puede asegurar de que el archivo (copia de seguridad) era correcto y de que se puede restaurar.</span><span class="sxs-lookup"><span data-stu-id="68fe2-106">Using the archive validation feature, you can ensure the archive (backup) was successful and can be restored.</span></span> <span data-ttu-id="68fe2-107">Después de crear un archivo, se notifica al servidor de validación que se ha creado un archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="68fe2-107">After an archive is created, the validation server is notified that a new archive has been created.</span></span> <span data-ttu-id="68fe2-108">El servidor de validación intenta restaurar el archivo.</span><span class="sxs-lookup"><span data-stu-id="68fe2-108">The validation server attempts to restore the archive.</span></span> <span data-ttu-id="68fe2-109">Un servidor de validación debe ser otra instancia de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] distinta a aquella en la que se ejecuta el trabajo.</span><span class="sxs-lookup"><span data-stu-id="68fe2-109">A validation server must be another instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] different from the one in which the job is running.</span></span> <span data-ttu-id="68fe2-110">La versión de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en el servidor de validación debe ser la misma que usó [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para hospedar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="68fe2-110">The version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] on the validation server must be the same version as the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] used to host the databases.</span></span>  
  
 <span data-ttu-id="68fe2-111">Si la restauración es correcta, el servidor de validación comunica esta información a la base de datos seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="68fe2-111">If the restore is successful, the validation server communicates this information back to the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="68fe2-112">Hasta que no se complete una restauración correcta, el trabajo de purga no purgará ningún dato más.</span><span class="sxs-lookup"><span data-stu-id="68fe2-112">Until a successful restore is completed, the purge job will not purge any more data.</span></span>  
  
 <span data-ttu-id="68fe2-113">Si la restauración no es correcta, el servidor de validación comunica esta información a la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="68fe2-113">If the restore is not successful, the validation server communicates this information back to the BizTalk Tracking database.</span></span> <span data-ttu-id="68fe2-114">El trabajo de purga crea otro archivo y espera la validación del archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="68fe2-114">The purge job creates another archive and awaits validation of the new archive.</span></span> <span data-ttu-id="68fe2-115">Esto impide que un archivo dañado pueda producir una pérdida de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="68fe2-115">This prevents the possibility of a corrupted archive causing you to lose tracking data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="68fe2-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="68fe2-116">Prerequisites</span></span>  
 <span data-ttu-id="68fe2-117">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68fe2-117">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-enable-automatic-archive-validation"></a><span data-ttu-id="68fe2-118">Para habilitar la validación automática del archivado</span><span class="sxs-lookup"><span data-stu-id="68fe2-118">To enable automatic archive validation</span></span>  
  
1.  <span data-ttu-id="68fe2-119">En el servidor de validación, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio** .</span><span class="sxs-lookup"><span data-stu-id="68fe2-119">On the validation server, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="68fe2-120">En el **conectar al servidor** diálogo cuadro, especifique el nombre de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] donde puede validar el archivo mediante la realización de una prueba del proceso de restauración y, a continuación, haga clic en **conectar** para conectarse a la servidor de SQL Server apropiado.</span><span class="sxs-lookup"><span data-stu-id="68fe2-120">In the **Connect to Server** dialog box, specify the name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] where you can validate the archive by performing a test of the restore process, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68fe2-121">Este servidor no debería ser otro servidor de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ya que reduce el rendimiento del sistema cuando valida el archivo.</span><span class="sxs-lookup"><span data-stu-id="68fe2-121">This server should not be another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database server as it reduces system performance when validating the archive.</span></span>  
  
3.  <span data-ttu-id="68fe2-122">En **Microsoft SQL Server Management Studio**, haga clic en **archivo**, haga clic en **abiertos**y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-122">In **Microsoft SQL Server Management Studio**, click **File**, click **Open**, and then click **File**.</span></span>  
  
4.  <span data-ttu-id="68fe2-123">En el **archivos abiertos** cuadro de diálogo, desplácese hasta el siguiente script SQL:</span><span class="sxs-lookup"><span data-stu-id="68fe2-123">In the **Open File** dialog box, browse to the following SQL script:</span></span>  
  
    ```  
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="68fe2-124">Es posible que se necesite copiar el script desde el equipo en el que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el servidor de validación.</span><span class="sxs-lookup"><span data-stu-id="68fe2-124">You might need to copy the script from the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the validation server.</span></span>  
  
5.  <span data-ttu-id="68fe2-125">Haga clic en el **consulta** menú y, a continuación, haga clic en **Execute**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-125">Click the **Query** menu, and then click **Execute**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68fe2-126">La secuencia de comandos BTS_Tracking_ValidateArchive.sql sólo funciona si la carpeta en la que se archiva la base de datos de seguimiento de BizTalk (BizTalkDTADb) es un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="68fe2-126">The BTS_Tracking_ValidateArchive.sql script only works if the folder where you are archiving your BizTalk Tracking (BizTalkDTADb) database is a network share.</span></span>  
  
     <span data-ttu-id="68fe2-127">La secuencia de comandos BTS_Tracking_ValidateArchive.sql crea un trabajo del Agente SQL Server que se denomina ValidateArchive.</span><span class="sxs-lookup"><span data-stu-id="68fe2-127">The BTS_Tracking_ValidateArchive.sql script creates a SQL Server Agent job called ValidateArchive.</span></span>  
  
6.  <span data-ttu-id="68fe2-128">El proceso de archivo y purgado potencialmente tiene acceso o actualiza las bases de datos en diferentes servidores de SQL Server, por lo que debe configurar servidores vinculados entre las instancias de SQL Server implicadas.</span><span class="sxs-lookup"><span data-stu-id="68fe2-128">The archiving and purging process potentially accesses and/or updates databases in different SQL Servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="68fe2-129">En **SQL Server Management Studio**, haga doble clic en **objetos Server**, haga clic en **servidores vinculados**y, a continuación, haga clic en **nuevo servidor vinculado**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-129">In **SQL Server Management Studio**, double-click **Server Objects**, right-click **Linked Servers**, and then click **New Linked Server**.</span></span>  
  
     <span data-ttu-id="68fe2-130">Debe configurar el servidor vinculado entre los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="68fe2-130">You must set up linked server between:</span></span>  
  
    -   <span data-ttu-id="68fe2-131">Cada una de las bases de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) y la base de datos de seguimiento de BizTalk (BizTalkDTADb), en el caso de que residan en servidores distintos.</span><span class="sxs-lookup"><span data-stu-id="68fe2-131">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database if they reside on different servers.</span></span>  
  
    -   <span data-ttu-id="68fe2-132">La base de datos de seguimiento de BizTalk (BizTalkDTADb) y el servidor de validación para la validación de archivos.</span><span class="sxs-lookup"><span data-stu-id="68fe2-132">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
    -   <span data-ttu-id="68fe2-133">Las cuentas de servicio del Agente SQL Server del equipo que aloja la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) deben contar con los permisos db_datareader y db_datawriter para la base de datos de seguimiento de BizTalk (BizTalkDTADb) del servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="68fe2-133">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68fe2-134">La cuenta utilizada para ejecutar el trabajo debe tener privilegios de operador de base de datos (DBO) en las dos bases de datos.</span><span class="sxs-lookup"><span data-stu-id="68fe2-134">The account used for running the job should have Database Operator (DBO) privileges on both the databases.</span></span>  
  
7.  <span data-ttu-id="68fe2-135">En el **nuevo servidor vinculado** cuadro de diálogo la **General** página **servidor vinculado**, escriba el nombre del servidor que desea vincularse.</span><span class="sxs-lookup"><span data-stu-id="68fe2-135">In the **New Linked Server** dialog box, on the **General** page, in **Linked server**, enter the name of the server you want to link to.</span></span>  
  
     <span data-ttu-id="68fe2-136">Por ejemplo, el servidor que aloja la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb), la base de datos de seguimiento de BizTalk (BizTalkDTADb) o el servidor de validación.</span><span class="sxs-lookup"><span data-stu-id="68fe2-136">For example, the server hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database, BizTalk Tracking (BizTalkDTADb) database, or the validation server.</span></span>  
  
8.  <span data-ttu-id="68fe2-137">En **tipo de servidor**, haga clic en **SQL Server**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-137">Under **Server type**, click **SQL Server**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="68fe2-138">En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-138">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
10. <span data-ttu-id="68fe2-139">En el **detalles del explorador de objetos** panel, haga clic en **ValidateArchive**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-139">In the **Object Explorer Details** pane, right-click **ValidateArchive**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="68fe2-140">En el **propiedades del trabajo - ValidateArchive** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-140">In the **Job Properties - ValidateArchive** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
12. <span data-ttu-id="68fe2-141">En el **lista de pasos de trabajo**, haga clic en **validar**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-141">In the **Job step list**, click **validate**, and then click **Edit**.</span></span>  
  
13. <span data-ttu-id="68fe2-142">En el **General** página, en la **comando** cuadro, en el comando **exec dtasp_ValidateArchive es null null**, sustituya null, null con el nombre del servidor que hospeda el BizTalk Seguimiento de la base de datos, entre comillas, seguidas del nombre de la base de seguimiento de BizTalk entrecomillado comillas simples y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68fe2-142">On the **General** page, in the **Command** box, in the command, **exec dtasp_ValidateArchive null, null**, replace null, null with the name of the server hosting the BizTalk Tracking database, surrounded by single quotes, followed by the name of the BizTalk Tracking database, surrounded by quotes, and then click **OK**.</span></span> <span data-ttu-id="68fe2-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68fe2-143">For example:</span></span>  
  
     <span data-ttu-id="68fe2-144">**exec dtasp_ValidateArchive '**  *\<TrackingServerName >* **','**  *\<TrackingDatabaseName >* **'**</span><span class="sxs-lookup"><span data-stu-id="68fe2-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName>* **', '** *\<TrackingDatabaseName>* **'**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68fe2-145">El trabajo ValidateArchive no tiene una programación y no se debería configurar una programación para él.</span><span class="sxs-lookup"><span data-stu-id="68fe2-145">The ValidateArchive job does not have a schedule and you should not configure a schedule for it.</span></span> <span data-ttu-id="68fe2-146">En su lugar, el trabajo DTA Purge and Archive (BizTalkDTADb) inicia este trabajo automáticamente cuando se crea un archivo.</span><span class="sxs-lookup"><span data-stu-id="68fe2-146">Instead, the DTA Purge and Archive (BizTalkDTADb) job starts this job automatically when an archive is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fe2-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="68fe2-147">See Also</span></span>  
 [<span data-ttu-id="68fe2-148">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="68fe2-148">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)