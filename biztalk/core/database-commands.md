---
title: Comandos de la base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7ec623c49c90fc0fddcbab7b6ee9b4e7ea0ef58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="database-commands"></a><span data-ttu-id="aa5c7-102">Comandos de base de datos</span><span class="sxs-lookup"><span data-stu-id="aa5c7-102">Database Commands</span></span>
<span data-ttu-id="aa5c7-103">Los comandos de base de datos de la utilidad de administración de BAM le permiten trabajar con las bases de datos de BAM:</span><span class="sxs-lookup"><span data-stu-id="aa5c7-103">The BAM Management utility database commands allow you to work with the BAM databases:</span></span>  
  
-   <span data-ttu-id="aa5c7-104">las bases de datos de programa de instalación: crea las bases de datos específicas de BAM.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-104">setup-databases: Creates the BAM-specific databases.</span></span>  
  
-   <span data-ttu-id="aa5c7-105">migrar de sql: migra las bases de datos BAM desde:</span><span class="sxs-lookup"><span data-stu-id="aa5c7-105">migrate-sql: Migrates your BAM databases from:</span></span>  
  
    -   <span data-ttu-id="aa5c7-106">Microsoft SQL Server 2000 a Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="aa5c7-106">Microsoft SQL Server 2000 to Microsoft SQL Server 2008</span></span>  
  
    -   <span data-ttu-id="aa5c7-107">Microsoft SQL Server 2005 a Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="aa5c7-107">Microsoft SQL Server 2005 to Microsoft SQL Server 2008</span></span>  
  
-   <span data-ttu-id="aa5c7-108">Enable-reference: permite una referencia a una base de datos de importación principal de BAM distribuida.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-108">enable-reference: Enables a reference to a distributed BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="aa5c7-109">Get-references: Obtiene una lista de referencias a bases de datos de importación principal de BAM distribuidas.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-109">get-references: Gets a list of references to distributed BAM Primary Import databases.</span></span>  
  
-   <span data-ttu-id="aa5c7-110">Disable-reference: deshabilita una referencia a una base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-110">disable-reference: Disables a reference to a BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa5c7-111">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-111">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="aa5c7-112">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-112">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="aa5c7-113">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-113">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa5c7-114">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="setup-databases-command"></a><span data-ttu-id="aa5c7-115">setup-databases (comando)</span><span class="sxs-lookup"><span data-stu-id="aa5c7-115">setup-databases Command</span></span>  
 <span data-ttu-id="aa5c7-116">**Uso**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-116">**Usage**</span></span>  
  
 <span data-ttu-id="aa5c7-117">**el programa de instalación de bm.exe-databases-ConfigFile:\<archivo de configuración > [- NSUser:\<nombre de usuario del servicio de notificaciones >] [- NSUserPassword:\<contraseña de usuario del servicio de notificaciones >]**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-117">**bm.exe setup-databases-ConfigFile:\<configuration file>[ -NSUser:\<notifications service user name> ][ -NSUserPassword:\<notifications service user password> ]**</span></span>  
  
 <span data-ttu-id="aa5c7-118">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-118">**Parameters**</span></span>  
  
|<span data-ttu-id="aa5c7-119">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aa5c7-119">Parameter</span></span>|<span data-ttu-id="aa5c7-120">Description</span><span class="sxs-lookup"><span data-stu-id="aa5c7-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa5c7-121">ConfigFile:\<archivo de configuración ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-121">ConfigFile:\<configuration file></span></span>|<span data-ttu-id="aa5c7-122">El archivo de configuración de BAM desde el que se va a crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-122">The BAM configuration file from which to create the database.</span></span>|  
|<span data-ttu-id="aa5c7-123">NSUser:\<nombre de usuario del servicio de notificaciones ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-123">NSUser:\<notifications service user name></span></span>|<span data-ttu-id="aa5c7-124">Opcional: El identificador de usuario de un usuario de servicios de notificaciones con permisos para crear bases de datos.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-124">Optional: The user ID of a notifications services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="aa5c7-125">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="aa5c7-125">NSUserPassword</span></span>|<span data-ttu-id="aa5c7-126">Opcional: La contraseña para el usuario de servicios de notificaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-126">Optional: The password for the specified notifications services user.</span></span>|  
  
 <span data-ttu-id="aa5c7-127">Crea las bases de datos descritas en el archivo de configuración (importación principal de BAM, esquema de estrella de BAM, análisis de BAM y alertas) si todavía no existen.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-127">Creates the databases described in the configuration file (BAM Primary Import, BAM Star Schema, BAM Archive, BAM Analysis, and alerts) if they do not already exist.</span></span> <span data-ttu-id="aa5c7-128">Una vez que se cree las bases de datos, el comando crea las tablas de metadatos de BAM asociadas y los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-128">Once the databases are created, the command creates the associated BAM metadata tables and stored procedures.</span></span>  
  
 <span data-ttu-id="aa5c7-129">Los parámetros NSUser y NSUserPassword son necesarios si está configurando alertas BAM.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-129">The NSUser and NSUserPassword parameters are required if you are setting up BAM alerts.</span></span> <span data-ttu-id="aa5c7-130">Si no se especifica el NSUserPassword en la línea de comandos, bm.exe le pide la contraseña.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-130">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa5c7-131">Después de completar el comando, puede tener una excepción del AlertModule en el registro de seguimiento en cuenta:</span><span class="sxs-lookup"><span data-stu-id="aa5c7-131">After the completion of the command, you may note an exception from the AlertModule in the trace log:</span></span>  
>   
>  <span data-ttu-id="aa5c7-132">"La cuenta especificada es el propietario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-132">"The specified account is the Database Owner.</span></span> <span data-ttu-id="aa5c7-133">El propietario de la base de datos tiene siempre acceso a la vista y no se puede agregar ni quitar de la vista."</span><span class="sxs-lookup"><span data-stu-id="aa5c7-133">The Database owner always has access to the view and cannot be added to or removed from the view."</span></span>  
>   
>  <span data-ttu-id="aa5c7-134">Asimismo, es posible que vea una advertencia en el evento de NotificationServices#19001.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-134">In addition, you may see a warning in the event from NotificationServices #19001.</span></span>  
>   
>  <span data-ttu-id="aa5c7-135">Si no se informó de ningún error durante la ejecución del comando, puede pasar estos avisos por alto con seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-135">If no errors were reported during the execution of the command, you can safely disregard these notices.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aa5c7-136">Si ejecuta un comando setup-database mediante un archivo de configuración de BAM que no contiene una sección de alertas y si ya ha configurado alertas BAM, bm.exe sobrescribirá la configuración de tal manera que ya no funcionarán las alertas.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-136">If you execute a setup-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="aa5c7-137">Para configurar las bases de datos de BAM, deberá tener permisos de administrador en el servidor Microsoft SQL Server en que residen las bases de datos BAMPrimaryImport, BAMStarSchema y BAMArchive.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-137">To set up the BAM databases you must have administrator permissions on the Microsoft SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span> <span data-ttu-id="aa5c7-138">Para configurar las bases de datos de servicios de notificación de SQL, deberá tener permisos de administrador y ser miembro del grupo local de administradores, así como ser miembro de otros grupos adicionales de administradores que se hayan configurado, como el grupo de administradores de BTS.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-138">To set up SQL Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
 <span data-ttu-id="aa5c7-139">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-139">**Examples**</span></span>  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a><span data-ttu-id="aa5c7-140">migrate-sql (comando)</span><span class="sxs-lookup"><span data-stu-id="aa5c7-140">migrate-sql Command</span></span>  
 <span data-ttu-id="aa5c7-141">**Uso**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-141">**Usage**</span></span>  
  
 <span data-ttu-id="aa5c7-142">**bm.exe migrar t-SQL-de: sql2000-a: sql2008 [- NSUser:\<nombre de usuario del servicio de notificaciones >] [- NSUserPassword:\<contraseña de usuario del servicio de notificaciones >] [-Server:\<servidor >] [-base de datos:\< base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-142">**bm.exe migrate-sql -From:sql2000 -To:sql2008 [ -NSUser:\<notifications service user name> ][ -NSUserPassword:\<notifications service user password> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="aa5c7-143">\-O bien -</span><span class="sxs-lookup"><span data-stu-id="aa5c7-143">\- Or -</span></span>  
  
 <span data-ttu-id="aa5c7-144">**bm.exe migrar t-SQL-de: sql2005-a: sql2008 [- NSUser:\<nombre de usuario del servicio de notificaciones >] [- NSUserPassword:\<contraseña de usuario del servicio de notificaciones >] [-Server:\<servidor >] [-base de datos:\< base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-144">**bm.exe migrate-sql -From:sql2005 -To:sql2008 [ -NSUser:\<notifications service user name> ][ -NSUserPassword:\<notifications service user password> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="aa5c7-145">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-145">**Parameters**</span></span>  
  
|<span data-ttu-id="aa5c7-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aa5c7-146">Parameter</span></span>|<span data-ttu-id="aa5c7-147">Description</span><span class="sxs-lookup"><span data-stu-id="aa5c7-147">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa5c7-148">Desde: sql2000</span><span class="sxs-lookup"><span data-stu-id="aa5c7-148">From: sql2000</span></span>|<span data-ttu-id="aa5c7-149">Especifica que está convirtiendo desde una base de datos de Microsoft SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-149">Specifies that you are converting from a Microsoft SQL Server 2000 database.</span></span>|  
|<span data-ttu-id="aa5c7-150">To:sql2008</span><span class="sxs-lookup"><span data-stu-id="aa5c7-150">To:sql2008</span></span>|<span data-ttu-id="aa5c7-151">Especifica que va a convertir en una base de datos de Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-151">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="aa5c7-152">Desde: sql2005</span><span class="sxs-lookup"><span data-stu-id="aa5c7-152">From: sql2005</span></span>|<span data-ttu-id="aa5c7-153">Especifica que está convirtiendo desde una base de datos de Microsoft SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-153">Specifies that you are converting from a Microsoft SQL Server 2005 database.</span></span>|  
|<span data-ttu-id="aa5c7-154">To:sql2008</span><span class="sxs-lookup"><span data-stu-id="aa5c7-154">To:sql2008</span></span>|<span data-ttu-id="aa5c7-155">Especifica que va a convertir en una base de datos de Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-155">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="aa5c7-156">NSUser:\<nombre de usuario del servicio de notificaciones ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-156">NSUser:\<notifications service user name></span></span>|<span data-ttu-id="aa5c7-157">Opcional: El identificador de usuario de un usuario de servicios de notificación con permisos para crear bases de datos.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-157">Optional: The user ID of a Notifications Services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="aa5c7-158">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="aa5c7-158">NSUserPassword</span></span>|<span data-ttu-id="aa5c7-159">Opcional: La contraseña para el usuario de servicios de notificación especificado.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-159">Optional: The password for the specified Notifications Services user.</span></span>|  
|<span data-ttu-id="aa5c7-160">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-160">Server:\<server></span></span>|<span data-ttu-id="aa5c7-161">Opcional: El nombre del servidor en el que residirá la base de datos convertida.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-161">Optional: The name of the server on which the converted database will reside.</span></span> <span data-ttu-id="aa5c7-162">El servidor debe estar en el mismo dominio que el equipo que hospeda la base de datos de Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-162">The server must be in the same domain as the computer hosting the Microsoft SQL Server 2008 database.</span></span> <span data-ttu-id="aa5c7-163">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="aa5c7-164">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-164">Database:\<database></span></span>|<span data-ttu-id="aa5c7-165">Opcional: El nombre de la base de datos convertida.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-165">Optional: Then name of the converted database.</span></span> <span data-ttu-id="aa5c7-166">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="aa5c7-167">Migra la infraestructura BAM desde Microsoft SQL Server 2000 o Microsoft SQL Server 2005 a Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-167">Migrates the BAM infrastructure from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span> <span data-ttu-id="aa5c7-168">Utilice este comando después de actualizar el servidor de base de datos y el servidor de análisis de Microsoft SQL Server 2000 o Microsoft SQL Server 2005 a Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-168">Use this command after you upgrade your database server and Analysis server from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span>  
  
 <span data-ttu-id="aa5c7-169">Los parámetros NSUser y NSUserPassword son necesarios si ha configurado alertas BAM.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-169">The NSUser and NSUserPassword parameters are required if BAM alerts are configured.</span></span> <span data-ttu-id="aa5c7-170">Si no se especifica el NSUserPassword en la línea de comandos, bm.exe le pide la contraseña.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-170">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
 <span data-ttu-id="aa5c7-171">Para migrar las bases de datos de servicios de notificación de SQL Server, deberá tener permisos de administrador y ser miembro del grupo local de administradores, así como ser miembro de otros grupos adicionales de administradores que se hayan configurado, como el grupo de administradores de BTS.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-171">To migrate the SQL Server Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa5c7-172">Si recibe el mensaje de error "ERROR: no se puede iniciar el servicio NS$ BAMAlerts en equipo '\<nombre del equipo >'.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-172">If you receive the error message "ERROR: Cannot start service NS$BAMAlerts on computer '\<computer name>'.</span></span> <span data-ttu-id="aa5c7-173">El servicio no respondió a tiempo a la solicitud de inicio o de control.", intente reiniciar el servicio de forma manual.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-173">The service did not respond to the start or control request in a timely fashion.", try restarting the service manually.</span></span> <span data-ttu-id="aa5c7-174">Si SQL Server está muy ocupado durante una migración, es posible que no se reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-174">If the SQL Server is extremely busy during a migration, the service may not restart.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa5c7-175">Para ejecutar el comando migrate-sql en el equipo en el que se encuentran instalados los servicios de notificación, tendrá que ser miembro del grupo local de administradores de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-175">To run the migrate-sql command on the computer where Notification Services is installed, you must belong to the Local Administrators group on that computer.</span></span>  
  
 <span data-ttu-id="aa5c7-176">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-176">**Examples**</span></span>  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a><span data-ttu-id="aa5c7-177">enable-reference (comando)</span><span class="sxs-lookup"><span data-stu-id="aa5c7-177">enable-reference Command</span></span>  
 <span data-ttu-id="aa5c7-178">**Uso**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-178">**Usage**</span></span>  
  
 <span data-ttu-id="aa5c7-179">**bm.exe enable-reference - TargetServer:\<servidor de destino > - TargetDatabase:\<base de datos de destino > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-179">**bm.exe enable-reference -TargetServer:\<target server> -TargetDatabase:\<target database>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="aa5c7-180">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-180">**Parameters**</span></span>  
  
|<span data-ttu-id="aa5c7-181">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aa5c7-181">Parameter</span></span>|<span data-ttu-id="aa5c7-182">Description</span><span class="sxs-lookup"><span data-stu-id="aa5c7-182">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa5c7-183">TargetServer:\<servidor de destino ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-183">TargetServer:\<target server></span></span>|<span data-ttu-id="aa5c7-184">Nombre del servidor para el que se habilita la referencia.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-184">The name of the server to which the reference is enabled.</span></span> <span data-ttu-id="aa5c7-185">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="aa5c7-186">TargetDatabase:\<base de datos de destino ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-186">TargetDatabase:\<target database></span></span>|<span data-ttu-id="aa5c7-187">Nombre de la base de datos para la que se habilita la referencia.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-187">The name of the database to which the reference is enabled.</span></span>|  
|<span data-ttu-id="aa5c7-188">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-188">Server:\<server></span></span>|<span data-ttu-id="aa5c7-189">Opcional: El nombre del servidor que tendrá una referencia habilitada para el servidor de destino y la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-189">Optional: The name of the server which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="aa5c7-190">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-190">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="aa5c7-191">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-191">Database:\<database></span></span>|<span data-ttu-id="aa5c7-192">Opcional: El nombre de la base de datos que tiene una referencia habilitada para el servidor de destino y la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-192">Optional: The name of the database which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="aa5c7-193">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-193">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="aa5c7-194">Habilita una referencia a otra base de datos distribuida de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-194">Enables a reference to another distributed BAM Primary Import database.</span></span> <span data-ttu-id="aa5c7-195">Permite suscripciones desde la base de datos actual a los metadatos de la actividad y vista en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-195">This allows subscriptions from the current database to the view and activity metadata on the target BAM Primary Import database.</span></span> <span data-ttu-id="aa5c7-196">Se utiliza para habilitar la exploración de las actividades distribuidas.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-196">You use this to enable navigation of the distributed activities.</span></span>  
  
 <span data-ttu-id="aa5c7-197">Puede especificar el servidor de destino como una instancia de SQL Server, por ejemplo 'mymachine2\myinstance'.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-197">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="aa5c7-198">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-198">**Examples**</span></span>  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a><span data-ttu-id="aa5c7-199">get-references (comando)</span><span class="sxs-lookup"><span data-stu-id="aa5c7-199">get-references Command</span></span>  
 <span data-ttu-id="aa5c7-200">**Uso**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-200">**Usage**</span></span>  
  
 <span data-ttu-id="aa5c7-201">**bm.exe get-references [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-201">**bm.exe get-references [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="aa5c7-202">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-202">**Parameters**</span></span>  
  
|<span data-ttu-id="aa5c7-203">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aa5c7-203">Parameter</span></span>|<span data-ttu-id="aa5c7-204">Description</span><span class="sxs-lookup"><span data-stu-id="aa5c7-204">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa5c7-205">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-205">Server:\<server></span></span>|<span data-ttu-id="aa5c7-206">Opcional: El nombre del servidor en el que se va a obtener una lista de referencias.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-206">Optional: The name of the server on which to get a list of references.</span></span> <span data-ttu-id="aa5c7-207">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-207">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="aa5c7-208">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-208">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="aa5c7-209">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-209">Database:\<database></span></span>|<span data-ttu-id="aa5c7-210">Opcional: El nombre de la base de datos que se va a obtener una lista de referencias.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-210">Optional: The name of the database on which to get a list of references.</span></span> <span data-ttu-id="aa5c7-211">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-211">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="aa5c7-212">Enumera las referencias habilitadas en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-212">Lists the references enabled on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="aa5c7-213">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-213">**Examples**</span></span>  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a><span data-ttu-id="aa5c7-214">Comando disable-reference</span><span class="sxs-lookup"><span data-stu-id="aa5c7-214">disable-reference Command</span></span>  
 <span data-ttu-id="aa5c7-215">**Uso**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-215">**Usage**</span></span>  
  
 <span data-ttu-id="aa5c7-216">**bm.exe disable-reference - TargetServer:\<servidor de destino > - TargetDatabase:\<base de datos de destino > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-216">**bm.exe disable-reference -TargetServer:\<target server> -TargetDatabase:\<target database>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="aa5c7-217">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-217">**Parameters**</span></span>  
  
|<span data-ttu-id="aa5c7-218">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aa5c7-218">Parameter</span></span>|<span data-ttu-id="aa5c7-219">Description</span><span class="sxs-lookup"><span data-stu-id="aa5c7-219">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa5c7-220">TargetServer:\<servidor de destino ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-220">TargetServer:\<target server></span></span>|<span data-ttu-id="aa5c7-221">Nombre del servidor desde el que se deshabilitan las referencias.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-221">The name of the server on which to disable the references.</span></span> <span data-ttu-id="aa5c7-222">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-222">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="aa5c7-223">TargetDatabase:\<base de datos de destino ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-223">TargetDatabase:\<target database></span></span>|<span data-ttu-id="aa5c7-224">Nombre de la base de datos desde la que se deshabilitan las referencias.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-224">The name of the database on which to disable the references.</span></span>|  
|<span data-ttu-id="aa5c7-225">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-225">Server:\<server></span></span>|<span data-ttu-id="aa5c7-226">Opcional: El nombre del servidor en que hace referencia al destino servidor y base de datos se va a deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-226">Optional: The name of the server on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="aa5c7-227">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-227">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="aa5c7-228">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-228">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="aa5c7-229">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="aa5c7-229">Database:\<database></span></span>|<span data-ttu-id="aa5c7-230">Opcional: El nombre de la base de datos en la que hace referencia al servidor de destino y la base de datos son va a deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-230">Optional: The name of the database on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="aa5c7-231">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-231">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="aa5c7-232">Deshabilita una referencia a otra base de datos de importación principal de BAM  distribuida en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-232">Disables a reference to another distributed BAM Primary Import database on the target server.</span></span>  
  
 <span data-ttu-id="aa5c7-233">Puede especificar el servidor de destino como una instancia de SQL Server, por ejemplo 'mymachine2\myinstance'.</span><span class="sxs-lookup"><span data-stu-id="aa5c7-233">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="aa5c7-234">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="aa5c7-234">**Examples**</span></span>  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa5c7-235">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa5c7-235">See Also</span></span>  
 [<span data-ttu-id="aa5c7-236">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="aa5c7-236">BAM Management Utility</span></span>](../core/bam-management-utility.md)