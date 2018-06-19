---
title: Comandos de administración de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16527acda7432b2eea35f0c87bb9d89fff632430
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974082"
---
# <a name="user-management-commands"></a><span data-ttu-id="919e7-102">Comandos de administración de usuario</span><span class="sxs-lookup"><span data-stu-id="919e7-102">User Management Commands</span></span>
<span data-ttu-id="919e7-103">Los comandos de administración de usuario de alertas de la utilidad de administración de BAM le permiten obtener, agregar y quitar usuarios.</span><span class="sxs-lookup"><span data-stu-id="919e7-103">The BAM Management utility alert user management commands allow you to get, add, and remove users.</span></span>  
  
-   <span data-ttu-id="919e7-104">Get-accounts: Obtiene una lista de todos los usuarios y grupos a los que pueden tener acceso a una vista especificada.</span><span class="sxs-lookup"><span data-stu-id="919e7-104">get-accounts: Gets a list of all users and groups that can access a specified view.</span></span>  
  
-   <span data-ttu-id="919e7-105">Agregar cuenta: concede derechos de acceso para el usuario o grupo especificado a la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="919e7-105">add-account: Grants access rights for the specified user or group to the specified view.</span></span>  
  
-   <span data-ttu-id="919e7-106">Remove-account: quita derechos de acceso para un usuario o grupo de una vista determinada.</span><span class="sxs-lookup"><span data-stu-id="919e7-106">remove-account: Removes access rights for a user or group from a specified view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="919e7-107">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="919e7-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="919e7-108">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="919e7-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="919e7-109">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="919e7-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="919e7-110">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="919e7-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-accounts-command"></a><span data-ttu-id="919e7-111">Comando get-accounts</span><span class="sxs-lookup"><span data-stu-id="919e7-111">get-accounts Command</span></span>  
 <span data-ttu-id="919e7-112">**Uso**</span><span class="sxs-lookup"><span data-stu-id="919e7-112">**Usage**</span></span>  
  
 <span data-ttu-id="919e7-113">**bm.exe get-accounts-View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="919e7-113">**bm.exe get-accounts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="919e7-114">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="919e7-114">**Parameters**</span></span>  
  
|<span data-ttu-id="919e7-115">Parámetro</span><span class="sxs-lookup"><span data-stu-id="919e7-115">Parameter</span></span>|<span data-ttu-id="919e7-116">Description</span><span class="sxs-lookup"><span data-stu-id="919e7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="919e7-117">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="919e7-117">View:\<view name\></span></span>|<span data-ttu-id="919e7-118">Nombre de la vista para la que se enumeran las cuentas.</span><span class="sxs-lookup"><span data-stu-id="919e7-118">The name of the view for which to list accounts.</span></span>|  
|<span data-ttu-id="919e7-119">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="919e7-119">Server:\<server\></span></span>|<span data-ttu-id="919e7-120">Opcional: El nombre del servidor desde el que se va a recuperar las cuentas.</span><span class="sxs-lookup"><span data-stu-id="919e7-120">Optional: The name of the server from which to retrieve the accounts.</span></span> <span data-ttu-id="919e7-121">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="919e7-121">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="919e7-122">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="919e7-122">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="919e7-123">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="919e7-123">Database:\<database\></span></span>|<span data-ttu-id="919e7-124">Opcional: El nombre de la base de datos que se va a recuperar las cuentas.</span><span class="sxs-lookup"><span data-stu-id="919e7-124">Optional: The name of the database from which to retrieve the accounts.</span></span> <span data-ttu-id="919e7-125">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="919e7-125">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="919e7-126">Enumera todos los usuarios y grupos que pueden tener acceso a la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="919e7-126">Lists all users and groups that can access the specified view.</span></span>  
  
 <span data-ttu-id="919e7-127">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="919e7-127">**Examples**</span></span>  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a><span data-ttu-id="919e7-128">Comando add-account</span><span class="sxs-lookup"><span data-stu-id="919e7-128">add-account Command</span></span>  
 <span data-ttu-id="919e7-129">**Uso**</span><span class="sxs-lookup"><span data-stu-id="919e7-129">**Usage**</span></span>  
  
 <span data-ttu-id="919e7-130">**bm.exe agregar-account - AccountName:\<nombre de la cuenta\> -View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="919e7-130">**bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="919e7-131">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="919e7-131">**Parameters**</span></span>  
  
|<span data-ttu-id="919e7-132">Parámetro</span><span class="sxs-lookup"><span data-stu-id="919e7-132">Parameter</span></span>|<span data-ttu-id="919e7-133">Description</span><span class="sxs-lookup"><span data-stu-id="919e7-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="919e7-134">AccountName:<nombre de cuenta</span><span class="sxs-lookup"><span data-stu-id="919e7-134">AccountName:<account name</span></span>|<span data-ttu-id="919e7-135">Nombre de la cuenta a la que se conceden derechos.</span><span class="sxs-lookup"><span data-stu-id="919e7-135">The name of the account to which rights are granted.</span></span>|  
|<span data-ttu-id="919e7-136">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="919e7-136">View:\<view name\></span></span>|<span data-ttu-id="919e7-137">Nombre de la vista a la que se conceden derechos.</span><span class="sxs-lookup"><span data-stu-id="919e7-137">The name of the view to which rights are granted.</span></span>|  
|<span data-ttu-id="919e7-138">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="919e7-138">Server:\<server\></span></span>|<span data-ttu-id="919e7-139">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="919e7-139">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="919e7-140">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="919e7-140">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="919e7-141">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="919e7-141">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="919e7-142">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="919e7-142">Database:\<database\></span></span>|<span data-ttu-id="919e7-143">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="919e7-143">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="919e7-144">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="919e7-144">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="919e7-145">Otorga los derechos de acceso a la vista especificada al usuario o grupo de usuarios especificado.</span><span class="sxs-lookup"><span data-stu-id="919e7-145">Grants the specified user or group access rights to the specified view.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="919e7-146">Si usas agregaciones en tiempo Real (ATR), los usuarios agregados con **Agregar cuenta** comando no se conceden automáticamente derechos de inicio de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="919e7-146">If you are using Real Time Aggregations (RTAs), users added with **add-account** command are not automatically granted logon rights to SQL Server.</span></span> <span data-ttu-id="919e7-147">Si está utilizando ATR, considere la posibilidad de establecer un grupo de usuarios de Windows que contenga todos los usuarios que necesitan tener acceso a las vistas de las ATR.</span><span class="sxs-lookup"><span data-stu-id="919e7-147">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="919e7-148">Conceda a ese grupo derechos explícitos de inicio de sesión en el servidor SQL Server en el que residan las bases de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="919e7-148">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import databases.</span></span>  
  
 <span data-ttu-id="919e7-149">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="919e7-149">**Examples**</span></span>  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a><span data-ttu-id="919e7-150">Comando remove-account</span><span class="sxs-lookup"><span data-stu-id="919e7-150">remove-account Command</span></span>  
 <span data-ttu-id="919e7-151">**Uso**</span><span class="sxs-lookup"><span data-stu-id="919e7-151">**Usage**</span></span>  
  
 <span data-ttu-id="919e7-152">**bm.exe remove-account - AccountName:\<nombre de la cuenta\> -View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="919e7-152">**bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="919e7-153">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="919e7-153">**Parameters**</span></span>  
  
|<span data-ttu-id="919e7-154">Parámetro</span><span class="sxs-lookup"><span data-stu-id="919e7-154">Parameter</span></span>|<span data-ttu-id="919e7-155">Description</span><span class="sxs-lookup"><span data-stu-id="919e7-155">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="919e7-156">AccountName:\<nombre de cuenta\></span><span class="sxs-lookup"><span data-stu-id="919e7-156">AccountName:\<account name\></span></span>|<span data-ttu-id="919e7-157">Nombre de la cuenta desde la que se van a quitar derechos de la vista.</span><span class="sxs-lookup"><span data-stu-id="919e7-157">The name of the account from which to remove rights to the view.</span></span>|  
|<span data-ttu-id="919e7-158">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="919e7-158">View:\<view name\></span></span>|<span data-ttu-id="919e7-159">Nombre de la vista a la que se quitan derechos.</span><span class="sxs-lookup"><span data-stu-id="919e7-159">The name of the view to which rights are removed.</span></span>|  
|<span data-ttu-id="919e7-160">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="919e7-160">Server:\<server\></span></span>|<span data-ttu-id="919e7-161">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="919e7-161">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="919e7-162">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="919e7-162">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="919e7-163">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="919e7-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="919e7-164">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="919e7-164">Database:\<database\></span></span>|<span data-ttu-id="919e7-165">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="919e7-165">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="919e7-166">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="919e7-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="919e7-167">Quita los derechos de acceso de un usuario o un grupo desde una vista especificada</span><span class="sxs-lookup"><span data-stu-id="919e7-167">Removes access rights for a user or group from a specified view.</span></span> <span data-ttu-id="919e7-168">Al quitar una cuenta de una vista, se quita esa cuenta y todos sus miembros de las alertas definidas para la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="919e7-168">Removing an account from a view removes that account and all of its members from alerts defined for the specified view.</span></span> <span data-ttu-id="919e7-169">Si esa cuenta es el único propietario de un alerta, el usuario actual (admin) se convierte en el nuevo propietario de la alerta.</span><span class="sxs-lookup"><span data-stu-id="919e7-169">If that account is the sole owner of an alert, the current user (admin) becomes the new owner of the alert.</span></span>  
  
 <span data-ttu-id="919e7-170">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="919e7-170">**Examples**</span></span>  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="919e7-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="919e7-171">See Also</span></span>  
 [<span data-ttu-id="919e7-172">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="919e7-172">BAM Management Utility</span></span>](../core/bam-management-utility.md)