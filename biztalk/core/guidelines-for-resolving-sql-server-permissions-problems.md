---
title: Directrices para solucionar problemas de permisos de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c24512-5f65-4363-b806-8dd52b22f179
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32561c19bf099b226dc5425edb35ebbaf0a8b3b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992389"
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a><span data-ttu-id="706cc-102">Directrices para solucionar problemas de permisos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="706cc-102">Guidelines for Resolving SQL Server Permissions Problems</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="706cc-103"> hace un gran uso de las bases de datos de Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para operaciones en tiempo de ejecución y, por tanto, es importante que los permisos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se establezcan correctamente.</span><span class="sxs-lookup"><span data-stu-id="706cc-103"> makes extensive use of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases for run-time operations and as such, it is important that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions are set correctly.</span></span> <span data-ttu-id="706cc-104">Este tema proporciona directrices generales para minimizar los problemas con los permisos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], así como los pasos que pueden seguirse para resolver los problemas de ese tipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que afecten a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="706cc-104">This topic provides some general guidelines for minimizing [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions problems and steps that you can follow to troubleshoot [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions problems that affect [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="706cc-105">Directrices generales</span><span class="sxs-lookup"><span data-stu-id="706cc-105">General Guidelines</span></span>  
  
- <span data-ttu-id="706cc-106">**Utilice los usuarios del dominio y grupos para una instalación de varios equipos de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="706cc-106">**Use domain users and groups for a multicomputer installation of BizTalk Server**</span></span>  
  
   <span data-ttu-id="706cc-107">Debe utilizar grupos y cuentas de usuario del dominio al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ejecutarlo en un escenario con varios equipos, por ejemplo, cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] están instalados en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="706cc-107">You must use domain user groups and accounts when configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to run in a multicomputer scenario, for example, where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on separate computers.</span></span> <span data-ttu-id="706cc-108">No intente configurar ni ejecutar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un *paso a través* escenario de autenticación mediante el cual se crean pares de nombres de usuario y contraseñas coincidentes en cada equipo para evitar el uso de cuentas y grupos de dominio.</span><span class="sxs-lookup"><span data-stu-id="706cc-108">Do not attempt to configure or run [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a *pass-through* authentication scenario whereby matching pairs of usernames and passwords are created on each computer to avoid using domain groups and accounts.</span></span> <span data-ttu-id="706cc-109">Aunque aparentemente ese escenario de paso a través funcione correctamente en algunas circunstancias, provocará que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no funcione en otras y no es una configuración admitida.</span><span class="sxs-lookup"><span data-stu-id="706cc-109">While such a pass-through scenario may appear to function correctly in some scenarios, this will cause [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to fail in other scenarios and is not a supported configuration.</span></span>  
  
   <span data-ttu-id="706cc-110">Para obtener más información sobre cómo instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una configuración de varios equipos, descargue la Guía de instalación en [instalación guías relacionadas con BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582).</span><span class="sxs-lookup"><span data-stu-id="706cc-110">For more information about installing and configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a multicomputer configuration, download the Installation Guide at [Installation Guides Related to BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582).</span></span>  
  
- <span data-ttu-id="706cc-111">**Asegúrese de que se definen los grupos y usuarios de Windows adecuada en las funciones adecuadas de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="706cc-111">**Ensure that the appropriate Windows users and groups are defined in the appropriate SQL Server roles**</span></span>  
  
   <span data-ttu-id="706cc-112">Compruebe la correcta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] pertenencia al rol como se muestra en la tabla en el tema [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="706cc-112">Verify correct [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role membership as listed in the table in the topic [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="706cc-113">**Usuario SQL Server Profiler para diagnosticar problemas de permisos**</span><span class="sxs-lookup"><span data-stu-id="706cc-113">**User SQL Server Profiler to diagnose permissions problems**</span></span>  
  
   <span data-ttu-id="706cc-114">Configurar un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] seguimiento de Profiler para supervisar el **evento Audit Login Failed** para recopilar información detallada acerca de los errores de permisos.</span><span class="sxs-lookup"><span data-stu-id="706cc-114">Set up a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler trace to monitor the **Audit Login Failed Event** to gather detailed information about permissions failures.</span></span> <span data-ttu-id="706cc-115">Para obtener información acerca del uso del generador de perfiles de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], vea la documentación de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="706cc-115">For information about how to use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler, see the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] documentation.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="706cc-116">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="706cc-116">Known Issues</span></span>  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a><span data-ttu-id="706cc-117">Los trabajos de SQL Server instalados con BizTalk Server no se pueden ejecutar.</span><span class="sxs-lookup"><span data-stu-id="706cc-117">The SQL Server jobs that are installed with BizTalk Server fail to execute</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="706cc-118">Problema</span><span class="sxs-lookup"><span data-stu-id="706cc-118">Problem</span></span>  
 <span data-ttu-id="706cc-119">Se producen errores en los trabajos de SQL Server instalados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y se generan errores parecidos a los siguientes en el registro de aplicaciones de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="706cc-119">The SQL Server jobs that are installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] fail and errors similar to the following are generated in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Application log:</span></span>  
  
 <span data-ttu-id="706cc-120">Tipo de evento: advertencia</span><span class="sxs-lookup"><span data-stu-id="706cc-120">Event Type: Warning</span></span>  
  
 <span data-ttu-id="706cc-121">Origen del evento: SQLSERVERAGENT</span><span class="sxs-lookup"><span data-stu-id="706cc-121">Event Source: SQLSERVERAGENT</span></span>  
  
 <span data-ttu-id="706cc-122">Categoría del evento: motor de trabajos</span><span class="sxs-lookup"><span data-stu-id="706cc-122">Event Category: Job Engine</span></span>  
  
 <span data-ttu-id="706cc-123">Id. de evento: 208</span><span class="sxs-lookup"><span data-stu-id="706cc-123">Event ID: 208</span></span>  
  
 <span data-ttu-id="706cc-124">Fecha: 6/29/2008</span><span class="sxs-lookup"><span data-stu-id="706cc-124">Date: 6/29/2008</span></span>  
  
 <span data-ttu-id="706cc-125">Hora: 4:45:01 p.m.</span><span class="sxs-lookup"><span data-stu-id="706cc-125">Time: 4:45:01 PM</span></span>  
  
 <span data-ttu-id="706cc-126">Usuario: N/D</span><span class="sxs-lookup"><span data-stu-id="706cc-126">User: N/A</span></span>  
  
 <span data-ttu-id="706cc-127">Equipo: *SQLServer*</span><span class="sxs-lookup"><span data-stu-id="706cc-127">Computer: *SQLServer*</span></span>  
  
 <span data-ttu-id="706cc-128">Descripción:</span><span class="sxs-lookup"><span data-stu-id="706cc-128">Description:</span></span>  
  
 <span data-ttu-id="706cc-129">Trabajo programado de SQL Server 'Copia de seguridad de BizTalk Server'</span><span class="sxs-lookup"><span data-stu-id="706cc-129">SQL Server Scheduled Job 'Backup BizTalk Server'</span></span>  
  
 <span data-ttu-id="706cc-130">(0x4AC7C44A48541443927A56C5C6699ECF) - Estado: Error - Invocado el: 2008-6-29 13:45:01 - Mensaje: Error en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="706cc-130">(0x4AC7C44A48541443927A56C5C6699ECF) - Status: Failed - Invoked on: 2008-6-29 13:45:01 - Message: The job failed.</span></span>  <span data-ttu-id="706cc-131">El trabajo fue invocado por Programación 305 (MarkAndBackupLogSched).</span><span class="sxs-lookup"><span data-stu-id="706cc-131">The Job was invoked by Schedule 305 (MarkAndBackupLogSched).</span></span> <span data-ttu-id="706cc-132">El último paso ejecutado fue el paso 1 (BackupFull).</span><span class="sxs-lookup"><span data-stu-id="706cc-132">The last step to run was step 1 (BackupFull).</span></span>  
  
 <span data-ttu-id="706cc-133">**- y -**</span><span class="sxs-lookup"><span data-stu-id="706cc-133">**- and -**</span></span>  
  
 <span data-ttu-id="706cc-134">Tipo de evento: información</span><span class="sxs-lookup"><span data-stu-id="706cc-134">Event Type: Information</span></span>  
  
 <span data-ttu-id="706cc-135">Origen del evento: MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="706cc-135">Event Source: MSSQLSERVER</span></span>  
  
 <span data-ttu-id="706cc-136">Categoría del evento: (4)</span><span class="sxs-lookup"><span data-stu-id="706cc-136">Event Category: (4)</span></span>  
  
 <span data-ttu-id="706cc-137">Id. de evento: 17055</span><span class="sxs-lookup"><span data-stu-id="706cc-137">Event ID: 17055</span></span>  
  
 <span data-ttu-id="706cc-138">Fecha: 6/29/2008</span><span class="sxs-lookup"><span data-stu-id="706cc-138">Date: 6/29/2008</span></span>  
  
 <span data-ttu-id="706cc-139">Hora: 4:45:01 p.m.</span><span class="sxs-lookup"><span data-stu-id="706cc-139">Time: 4:45:01 PM</span></span>  
  
 <span data-ttu-id="706cc-140">Usuario: N/D</span><span class="sxs-lookup"><span data-stu-id="706cc-140">User: N/A</span></span>  
  
 <span data-ttu-id="706cc-141">Equipo: *SQLServer*</span><span class="sxs-lookup"><span data-stu-id="706cc-141">Computer: *SQLServer*</span></span>  
  
 <span data-ttu-id="706cc-142">Descripción:</span><span class="sxs-lookup"><span data-stu-id="706cc-142">Description:</span></span>  
  
 <span data-ttu-id="706cc-143">18456: Error de inicio de sesión del usuario 'NT AUTHORITY\SYSTEM'.</span><span class="sxs-lookup"><span data-stu-id="706cc-143">18456: Login failed for user 'NT AUTHORITY\SYSTEM'.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="706cc-144">Causa</span><span class="sxs-lookup"><span data-stu-id="706cc-144">Cause</span></span>  
 <span data-ttu-id="706cc-145">Este error puede producirse si el inicio de sesión BUILTIN\Administrators se ha quitado de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="706cc-145">This error can occur if the BUILTIN\Administrators login has been removed from [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="706cc-146">Si se elimina el inicio de sesión BUILTIN\Administrators, sqlmaint.exe no podrá iniciar la sesión en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], lo que impedirá la ejecución de los trabajos de SQL.</span><span class="sxs-lookup"><span data-stu-id="706cc-146">If the BUILTIN\Administrators login is deleted, sqlmaint.exe will be unable to logon to [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] which will prevent SQL jobs from running.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="706cc-147">Solución</span><span class="sxs-lookup"><span data-stu-id="706cc-147">Resolution</span></span>  
 <span data-ttu-id="706cc-148">Para solucionar este problema, vuelva a crear el inicio de sesión BUILTIN\Administrators y agréguelo al rol db_owner de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y a la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="706cc-148">To resolve this issue, re-create the BUILTIN\Administrators Login and add it to the db_owner role for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and the Master database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="706cc-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="706cc-149">See Also</span></span>  
 <span data-ttu-id="706cc-150">[Solucionar problemas de SQL Server](../core/troubleshooting-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="706cc-150">[Troubleshooting SQL Server](../core/troubleshooting-sql-server.md) </span></span>  
 [<span data-ttu-id="706cc-151">Solucionar problemas de permisos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="706cc-151">Troubleshooting BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)