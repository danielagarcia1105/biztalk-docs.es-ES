---
title: Cómo realizar copias de seguridad de bases de datos personalizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ddab49315f7d4a194224eb0773a7ea1fa1a314
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998581"
---
# <a name="how-to-back-up-custom-databases"></a><span data-ttu-id="40210-102">Cómo realizar copias de seguridad de bases de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="40210-102">How to Back Up Custom Databases</span></span>
<span data-ttu-id="40210-103">Ya que las bases de datos personalizadas no se instalan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], no se incluyen en la lista predeterminada de bases de datos que deben marcarse y de las que el trabajo de copia de seguridad de BizTalk Server debe realizar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40210-103">Because your custom databases are not installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], they are not included in the default list of databases to be marked and backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="40210-104">Si desea que el trabajo de copia de seguridad de BizTalk realice una copia de seguridad de las bases de datos personalizadas, tendrá que agregar manualmente las bases de datos al trabajo mencionado.</span><span class="sxs-lookup"><span data-stu-id="40210-104">If you want the Backup BizTalk Server job to back up your custom databases, you must manually add the databases to the Backup BizTalk Server job.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40210-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="40210-105">Prerequisites</span></span>  
  
1. <span data-ttu-id="40210-106">SQL Server debe configurarse para usar el modelo de recuperación completa y garantizar la integridad de los datos en los conjuntos de copias de seguridad de bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40210-106">SQL Server must be configured to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  <span data-ttu-id="40210-107">Para obtener más información, consulte [del trasvase de registros](../core/log-shipping.md).</span><span class="sxs-lookup"><span data-stu-id="40210-107">For more information see [Log Shipping](../core/log-shipping.md).</span></span>  
  
2. <span data-ttu-id="40210-108">Para realizar una copia de seguridad de las bases de datos personalizadas, tendrá que haber iniciado sesión con una cuenta de usuario que tenga acceso a cada una de las bases de datos de las que se va a efectuar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40210-108">To back up your custom databases, you must be logged on with a user account that has access to each of the databases you are backing up.</span></span>  
  
    <span data-ttu-id="40210-109">BizTalk Server incluye una función de SQL Server denominada BTS_BACKUP_USERS para que la cuenta de usuario utilizada para realizar una copia de seguridad de las bases de datos no necesite permisos de administrador del sistema en SQL Server, a excepción del servidor principal que controla el proceso de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40210-109">BizTalk Server includes a SQL Server role named BTS_BACKUP_USERS so that the user account you use to back up your databases does not require System Administrator permissions within SQL Server, except for the primary server controlling the backup process.</span></span>  
  
    <span data-ttu-id="40210-110">Al configurar la cuenta de usuario utilizada para realizar la copia de seguridad de las bases de datos, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="40210-110">When setting up the user account that you are using to back up your databases, note the following:</span></span>  
  
   -   <span data-ttu-id="40210-111">Debe crear una cuenta de inicio de sesión de SQL Server para este usuario y asignar este último a la función BTS_BACKUP_USERS de BizTalk en cada uno de los servidores.</span><span class="sxs-lookup"><span data-stu-id="40210-111">You must create a SQL Server logon account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS role on each server.</span></span>  
  
   -   <span data-ttu-id="40210-112">Los trabajos de copia de seguridad de BizTalk Server pueden configurarse para ejecutarse bajo una cuenta de usuario diferente de la usada para el servicio Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40210-112">The BizTalk Server backup jobs can be configured to run under a user account that is different than the one used for the SQL Server Agent service.</span></span>  
  
   -   <span data-ttu-id="40210-113">Tendrá que configurar el servicio del Agente SQL Server para que se ejecute en una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="40210-113">You must configure the SQL Server Agent service to run under a domain account.</span></span> <span data-ttu-id="40210-114">Si todas las bases de datos se encuentran en el mismo equipo, podrá configurar el Agente SQL Server para que utilice una cuenta local.</span><span class="sxs-lookup"><span data-stu-id="40210-114">If all databases are on the same computer, you can configure SQL Server Agent to use a local account.</span></span>  
  
### <a name="to-back-up-custom-databases"></a><span data-ttu-id="40210-115">Para realizar una copia de seguridad de bases de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="40210-115">To back up custom databases</span></span>  
  
1. <span data-ttu-id="40210-116">Genere los objetos en la nueva base de datos:</span><span class="sxs-lookup"><span data-stu-id="40210-116">Build the objects in the new database:</span></span>  
  
   - <span data-ttu-id="40210-117">Desplácese al directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema y, a continuación, ejecute Backup_Setup_All_Procs.sql y Backup_Setup_All_Tables.sql en todas las bases de datos personalizadas de las que desee realizar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40210-117">Browse to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema directory, and then run Backup_Setup_All_Procs.sql and Backup_Setup_All_Tables.sql against all your custom databases that you want to back up.</span></span> <span data-ttu-id="40210-118">Con ello, se crean la función, la tabla y los procedimientos necesarios, además de efectuarse la asignación de permisos a los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="40210-118">This creates the necessary procedures, table, and role and assigns permissions to the stored procedures.</span></span>  
  
2. <span data-ttu-id="40210-119">Lleve a cabo la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="40210-119">Perform the following configurations:</span></span>  
  
   -   <span data-ttu-id="40210-120">Vincule el servidor SQL Server que aloja la base de datos de administración de BizTalk con el servidor SQL Server que aloja la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="40210-120">Link the SQL server that is hosting the BizTalk Management database to the SQL server hosting the new database.</span></span> <span data-ttu-id="40210-121">La cuenta utilizada para ejecutar el servicio Agente SQL Server en el servidor SQL Server de administración debe ser una cuenta de dominio asignada a cada uno de los equipos que contiene una base de datos de la que se va a realizar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40210-121">The account used to run the SQL Server Agent service on the management SQL Server must be a domain account that is mapped to each computer holding a database to be backed up.</span></span> <span data-ttu-id="40210-122">Si las bases de datos se encuentran en el mismo equipo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="40210-122">If the databases are on the same computer you can skip this step.</span></span> <span data-ttu-id="40210-123">puesto que se lleva a cabo de forma automática.</span><span class="sxs-lookup"><span data-stu-id="40210-123">This is done automatically.</span></span>  
  
   -   <span data-ttu-id="40210-124">Agregue un inicio de sesión en el servidor SQL Server que aloja la nueva base de datos para la cuenta con la que se ejecuta el servicio Agente SQL Server en el servidor SQL Server de administración.</span><span class="sxs-lookup"><span data-stu-id="40210-124">Add a login on the SQL server hosting the new database for the account running the SQL Server Agent service on the Mgmt SQL Server.</span></span> <span data-ttu-id="40210-125">Si las bases de datos se encuentran en el mismo equipo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="40210-125">If the databases are on the same computer you can skip this step.</span></span>  
  
   -   <span data-ttu-id="40210-126">Agregue un usuario a la nueva base de datos para el inicio de sesión creado en el paso anterior y efectúe su agregación a la función BTS_BACKUP_USERS.</span><span class="sxs-lookup"><span data-stu-id="40210-126">Add a user in the new database for the login created in the previous step and add them to the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="40210-127">Las secuencias de comandos del Paso 1 crean esta función y conceden permisos de ejecución en los procedimientos necesarios.</span><span class="sxs-lookup"><span data-stu-id="40210-127">This role is created and granted Execute permissions on the necessary procedures by the scripts in step 1.</span></span>  
  
3. <span data-ttu-id="40210-128">Con el Administrador corporativo de SQL Server o SQL Server Management Studio, en la base de datos de administración de BizTalk (BizTalkMgmtDb), modifique la **adm_OtherBackupDatabases** tabla para incluir una fila para cada una de las bases de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="40210-128">Using SQL Server Enterprise Manager or SQL Server Management Studio, in the BizTalk Management (BizTalkMgmtDb) database, modify the **adm_OtherBackupDatabases** table to include a row for each of your custom databases.</span></span>  
  
4. <span data-ttu-id="40210-129">Escriba los nuevos nombres de base de datos y servidor en las columnas correspondientes, tal y como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="40210-129">Type the new server and database names in the corresponding columns, as shown in the following table.</span></span>  
  
   |<span data-ttu-id="40210-130">columna</span><span class="sxs-lookup"><span data-stu-id="40210-130">Column</span></span>|<span data-ttu-id="40210-131">Valor</span><span class="sxs-lookup"><span data-stu-id="40210-131">Value</span></span>|  
   |------------|-----------|  
   |<span data-ttu-id="40210-132">DefaultDatabaseName</span><span class="sxs-lookup"><span data-stu-id="40210-132">DefaultDatabaseName</span></span>|<span data-ttu-id="40210-133">Nombre descriptivo de la base de datos personalizada.</span><span class="sxs-lookup"><span data-stu-id="40210-133">The friendly name of your custom database.</span></span>|  
   |<span data-ttu-id="40210-134">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="40210-134">DatabaseName</span></span>|<span data-ttu-id="40210-135">Nombre de la base de datos personalizada.</span><span class="sxs-lookup"><span data-stu-id="40210-135">The name of your custom database.</span></span>|  
   |<span data-ttu-id="40210-136">ServerName</span><span class="sxs-lookup"><span data-stu-id="40210-136">ServerName</span></span>|<span data-ttu-id="40210-137">Nombre del equipo en el que se ejecuta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40210-137">The name of the computer running SQL Server.</span></span>|  
   |<span data-ttu-id="40210-138">BTSServerName</span><span class="sxs-lookup"><span data-stu-id="40210-138">BTSServerName</span></span>|<span data-ttu-id="40210-139">Nombre del servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="40210-139">The name of the BizTalk Server.</span></span> <span data-ttu-id="40210-140">Aunque no se utilice, debe contener un valor.</span><span class="sxs-lookup"><span data-stu-id="40210-140">This value is not used, but it must contain a value nonetheless.</span></span>|  
  
   <span data-ttu-id="40210-141">La próxima vez que ejecute el trabajo de copia de seguridad de BizTalk Server, éste realizará una copia de seguridad de las bases de datos personalizadas.</span><span class="sxs-lookup"><span data-stu-id="40210-141">The next time you run the Backup BizTalk Server job, it will back up your custom databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40210-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="40210-142">See Also</span></span>  
 <span data-ttu-id="40210-143">[Copia de seguridad y restaurar bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="40210-143">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="40210-144">Información avanzada sobre copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="40210-144">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)