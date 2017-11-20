---
title: "Comandos de administración de la actividad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90c5f394ed32b68f4f9b747c580fac02e22a8ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="activity-management-commands"></a><span data-ttu-id="52fe1-102">Comandos de la administración de la actividad</span><span class="sxs-lookup"><span data-stu-id="52fe1-102">Activity Management Commands</span></span>
<span data-ttu-id="52fe1-103">Los comandos de administración de la actividad de la utilidad de administración de BAM permiten trabajar con actividades implementadas.</span><span class="sxs-lookup"><span data-stu-id="52fe1-103">The BAM Management utility activity management commands allow you to work with deployed activities.</span></span>  
  
-   <span data-ttu-id="52fe1-104">Get-activities: Obtiene una lista de actividades implementadas.</span><span class="sxs-lookup"><span data-stu-id="52fe1-104">get-activities: Gets a list of deployed activities.</span></span>  
  
-   <span data-ttu-id="52fe1-105">Remove-activity: quita una actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-105">remove-activity: Removes an activity.</span></span>  
  
-   <span data-ttu-id="52fe1-106">Get-activitywindow: Obtiene la duración de una actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-106">get-activitywindow: Gets the duration for an activity.</span></span>  
  
-   <span data-ttu-id="52fe1-107">Set-activitywindow: establece la duración de una actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-107">set-activitywindow: Sets the activity duration for an activity.</span></span>  
  
-   <span data-ttu-id="52fe1-108">Get-index: Obtiene la lista de índices.</span><span class="sxs-lookup"><span data-stu-id="52fe1-108">get-index: Gets the list of indexes.</span></span>  
  
-   <span data-ttu-id="52fe1-109">Crear índice: crea un nuevo índice.</span><span class="sxs-lookup"><span data-stu-id="52fe1-109">create-index: Creates a new index.</span></span>  
  
-   <span data-ttu-id="52fe1-110">índice de Delete: elimina un índice.</span><span class="sxs-lookup"><span data-stu-id="52fe1-110">delete-index: Deletes an index.</span></span>  
  
-   <span data-ttu-id="52fe1-111">Get-archive: Obtiene el comportamiento de la actividad archivada.</span><span class="sxs-lookup"><span data-stu-id="52fe1-111">get-archive: Gets the behavior of archived activity.</span></span>  
  
-   <span data-ttu-id="52fe1-112">Set-archive: establece el comportamiento de la actividad archivada.</span><span class="sxs-lookup"><span data-stu-id="52fe1-112">set-archive: Sets the behavior of archived activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52fe1-113">Puede habilitar el seguimiento de cualquier comando de la utilidad BAM mediante la inclusión de la **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="52fe1-113">You can enable tracing on any BAM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="52fe1-114">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="52fe1-114">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="52fe1-115">El conmutador puede usarse junto con cualquier comando normal de BAM.</span><span class="sxs-lookup"><span data-stu-id="52fe1-115">The switch can be used in conjunction with any normal BAM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52fe1-116">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="52fe1-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-activities-command"></a><span data-ttu-id="52fe1-117">Comando get-activities</span><span class="sxs-lookup"><span data-stu-id="52fe1-117">get-activities Command</span></span>  
 <span data-ttu-id="52fe1-118">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-118">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-119">**bm.exe get-activities [-View:\<nombre de vista >] [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-119">**bm.exe get-activities [ -View:\<view name> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="52fe1-120">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-120">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-121">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-121">Parameter</span></span>|<span data-ttu-id="52fe1-122">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-123">Nombre:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-123">Name:\<activity name></span></span>|<span data-ttu-id="52fe1-124">Nombre de la actividad que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="52fe1-124">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="52fe1-125">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-125">Server:\<server></span></span>|<span data-ttu-id="52fe1-126">Opcional: El nombre del servidor desde el que se va a obtener la lista de actividades.</span><span class="sxs-lookup"><span data-stu-id="52fe1-126">Optional: The name of the server from which to get the list of activities.</span></span> <span data-ttu-id="52fe1-127">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-127">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-128">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-128">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-129">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-129">Database:\<database></span></span>|<span data-ttu-id="52fe1-130">Opcional: El nombre de la base de datos que se va a obtener la lista de actividades.</span><span class="sxs-lookup"><span data-stu-id="52fe1-130">Optional: The name of the database from which to get the list of activities.</span></span> <span data-ttu-id="52fe1-131">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-131">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-132">Enumera las actividades implementadas en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="52fe1-132">Lists the activities deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="52fe1-133">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-133">**Examples**</span></span>  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a><span data-ttu-id="52fe1-134">Comando remove-activity</span><span class="sxs-lookup"><span data-stu-id="52fe1-134">remove-activity Command</span></span>  
 <span data-ttu-id="52fe1-135">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-135">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-136">**bm.exe remove-activity-Name:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-136">**bm.exe remove-activity -Name:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="52fe1-137">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-137">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-138">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-138">Parameter</span></span>|<span data-ttu-id="52fe1-139">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-139">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-140">Nombre:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-140">Name:\<activity name></span></span>|<span data-ttu-id="52fe1-141">Nombre de la actividad que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="52fe1-141">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="52fe1-142">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-142">Server:\<server></span></span>|<span data-ttu-id="52fe1-143">Opcional: El nombre del servidor desde el que se va a quitar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-143">Optional: The name of the server from which to remove the activity.</span></span> <span data-ttu-id="52fe1-144">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-144">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-145">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-145">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-146">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-146">Database:\<database></span></span>|<span data-ttu-id="52fe1-147">Opcional: El nombre de la base de datos que se va a quitar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-147">Optional: The name of the database from which to remove the activity.</span></span> <span data-ttu-id="52fe1-148">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-148">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-149">Quita la actividad especificada de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="52fe1-149">Removes the specified activity from the BAM Primary Import database.</span></span> <span data-ttu-id="52fe1-150">Si la actividad tiene vistas dependientes, el comando no funcionará e informará de un error.</span><span class="sxs-lookup"><span data-stu-id="52fe1-150">If the activity has dependent views, the command will fail and report an error.</span></span> <span data-ttu-id="52fe1-151">Utilice el comando remove-view para quitar todas las vistas dependientes y ejecutar de nuevo el comando remove-activity.</span><span class="sxs-lookup"><span data-stu-id="52fe1-151">Use the remove-view command to remove all the dependent views and execute the remove-activity command again.</span></span>  
  
 <span data-ttu-id="52fe1-152">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-152">**Examples**</span></span>  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a><span data-ttu-id="52fe1-153">Comando get-activitywindow</span><span class="sxs-lookup"><span data-stu-id="52fe1-153">get-activitywindow Command</span></span>  
 <span data-ttu-id="52fe1-154">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-154">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-155">**bm.exe get-activitywindow-actividad:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-155">**bm.exe get-activitywindow -Activity:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="52fe1-156">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-156">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-157">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-157">Parameter</span></span>|<span data-ttu-id="52fe1-158">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-158">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-159">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-159">Activity:\<activity name></span></span>|<span data-ttu-id="52fe1-160">El nombre de la .activity.</span><span class="sxs-lookup"><span data-stu-id="52fe1-160">The name of the .activity.</span></span>|  
|<span data-ttu-id="52fe1-161">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-161">Server:\<server></span></span>|<span data-ttu-id="52fe1-162">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-162">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="52fe1-163">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-163">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-164">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-164">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-165">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-165">Database:\<database></span></span>|<span data-ttu-id="52fe1-166">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-166">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="52fe1-167">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-167">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-168">Muestra la duración de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="52fe1-168">Displays the duration for the specified activity.</span></span> <span data-ttu-id="52fe1-169">El comando recupera la longitud de la duración y las unidades con las que se mide la duración.</span><span class="sxs-lookup"><span data-stu-id="52fe1-169">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="52fe1-170">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-170">**Examples**</span></span>  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a><span data-ttu-id="52fe1-171">Comando set-activitywindow</span><span class="sxs-lookup"><span data-stu-id="52fe1-171">set-activitywindow Command</span></span>  
 <span data-ttu-id="52fe1-172">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-172">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-173">**bm.exe set-activitywindow-actividad:\<nombre de actividad > - TimeLength:\<número entero > - TimeUnit: mes &#124; día &#124; Hora &#124; Minuto [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-173">**bm.exe set-activitywindow -Activity:\<activity name> -TimeLength:\<integer number> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="52fe1-174">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-174">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-175">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-175">Parameter</span></span>|<span data-ttu-id="52fe1-176">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-176">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-177">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-177">Activity:\<activity name></span></span>|<span data-ttu-id="52fe1-178">Nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-178">The name of the activity.</span></span>|  
|<span data-ttu-id="52fe1-179">TimeLength:\<número entero ></span><span class="sxs-lookup"><span data-stu-id="52fe1-179">TimeLength:\<integer number></span></span>|<span data-ttu-id="52fe1-180">Duración de la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-180">The duration for the activity.</span></span>|  
|<span data-ttu-id="52fe1-181">TimeUnit:Month &#124; día &#124; Hora &#124; Minuto</span><span class="sxs-lookup"><span data-stu-id="52fe1-181">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="52fe1-182">Unidad de medida de la duración.</span><span class="sxs-lookup"><span data-stu-id="52fe1-182">The unit measure for the duration.</span></span>|  
|<span data-ttu-id="52fe1-183">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-183">Server:\<server></span></span>|<span data-ttu-id="52fe1-184">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-184">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="52fe1-185">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-186">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-186">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-187">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-187">Database:\<database></span></span>|<span data-ttu-id="52fe1-188">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-188">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="52fe1-189">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-189">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-190">Establece la duración de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="52fe1-190">Sets the duration for the specified activity.</span></span>  
  
 <span data-ttu-id="52fe1-191">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-191">**Examples**</span></span>  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a><span data-ttu-id="52fe1-192">Comando get-index</span><span class="sxs-lookup"><span data-stu-id="52fe1-192">get-index Command</span></span>  
 <span data-ttu-id="52fe1-193">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-193">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-194">**bm.exe get-index-actividad:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-194">**bm.exe get-index -Activity:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="52fe1-195">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-195">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-196">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-196">Parameter</span></span>|<span data-ttu-id="52fe1-197">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-197">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-198">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-198">Activity:\<activity name></span></span>|<span data-ttu-id="52fe1-199">Nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-199">The name of the activity.</span></span>|  
|<span data-ttu-id="52fe1-200">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-200">Server:\<server></span></span>|<span data-ttu-id="52fe1-201">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-201">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="52fe1-202">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-202">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-203">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-203">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-204">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-204">Database:\<database></span></span>|<span data-ttu-id="52fe1-205">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-205">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="52fe1-206">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-206">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-207">Enumera todos los índices que se han creado para la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="52fe1-207">Lists all the indexes that have been created for the specified activity.</span></span>  
  
 <span data-ttu-id="52fe1-208">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-208">**Examples**</span></span>  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a><span data-ttu-id="52fe1-209">Comando create-index</span><span class="sxs-lookup"><span data-stu-id="52fe1-209">create-index Command</span></span>  
 <span data-ttu-id="52fe1-210">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-210">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-211">**bm.exe crear-index - IndexName:\<nombre de índice >-actividad:\<nombre de actividad >-punto de comprobación:\<punto de Control1 > [,\<punto de control2 >...] [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-211">**bm.exe create-index -IndexName:\<index name> -Activity:\<activity name> -Checkpoint:\<checkpoint1>[,\<checkpoint2>...][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="52fe1-212">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-212">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-213">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-213">Parameter</span></span>|<span data-ttu-id="52fe1-214">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-214">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-215">IndexName:\<nombre de índice ></span><span class="sxs-lookup"><span data-stu-id="52fe1-215">IndexName:\<index name></span></span>|<span data-ttu-id="52fe1-216">Nombre del índice nuevo.</span><span class="sxs-lookup"><span data-stu-id="52fe1-216">The name of the new index.</span></span>|  
|<span data-ttu-id="52fe1-217">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-217">Activity:\<activity name></span></span>|<span data-ttu-id="52fe1-218">Nombre de la actividad para la que se crea el índice.</span><span class="sxs-lookup"><span data-stu-id="52fe1-218">The name of the activity for which the index is created.</span></span>|  
|<span data-ttu-id="52fe1-219">Punto de comprobación:\<punto de Control1 > [,\<punto de control2 >...]</span><span class="sxs-lookup"><span data-stu-id="52fe1-219">Checkpoint:\<checkpoint1>[,\<checkpoint2>...]</span></span>|<span data-ttu-id="52fe1-220">Lista delimitada por comas de puntos de control para el índice.</span><span class="sxs-lookup"><span data-stu-id="52fe1-220">A comma-delimited list of checkpoints for the index.</span></span>|  
|<span data-ttu-id="52fe1-221">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-221">Server:\<server></span></span>|<span data-ttu-id="52fe1-222">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-222">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="52fe1-223">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-223">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-224">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-224">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-225">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-225">Database:\<database></span></span>|<span data-ttu-id="52fe1-226">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-226">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="52fe1-227">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-227">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-228">Crea un índice para la actividad especificada mediante los puntos de control especificados.</span><span class="sxs-lookup"><span data-stu-id="52fe1-228">Creates an index for the specified activity using the specified checkpoints.</span></span>  
  
 <span data-ttu-id="52fe1-229">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-229">**Examples**</span></span>  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a><span data-ttu-id="52fe1-230">Comando delete-index</span><span class="sxs-lookup"><span data-stu-id="52fe1-230">delete-index Command</span></span>  
 <span data-ttu-id="52fe1-231">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-231">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-232">**bm.exe delete-index - IndexName:\<nombre de índice >-actividad:\<nombre de actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-232">**bm.exe delete-index -IndexName:\<index name> -Activity:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="52fe1-233">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-233">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-234">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-234">Parameter</span></span>|<span data-ttu-id="52fe1-235">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-235">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-236">IndexName:\<nombre de índice ></span><span class="sxs-lookup"><span data-stu-id="52fe1-236">IndexName:\<index name></span></span>|<span data-ttu-id="52fe1-237">Nombre del índice que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="52fe1-237">The name of the index to delete.</span></span>|  
|<span data-ttu-id="52fe1-238">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-238">Activity:\<activity name></span></span>|<span data-ttu-id="52fe1-239">Nombre de la actividad para la que se elimina el índice.</span><span class="sxs-lookup"><span data-stu-id="52fe1-239">The name of the activity for which the index is deleted.</span></span>|  
|<span data-ttu-id="52fe1-240">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-240">Server:\<server></span></span>|<span data-ttu-id="52fe1-241">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-241">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="52fe1-242">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-242">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-243">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-243">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-244">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-244">Database:\<database></span></span>|<span data-ttu-id="52fe1-245">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-245">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="52fe1-246">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-246">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-247">Elimina el índice especificado con el nombre dado de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="52fe1-247">Deletes the specified index with the given name from the specified activity.</span></span>  
  
 <span data-ttu-id="52fe1-248">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-248">**Examples**</span></span>  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="52fe1-249">Comando set-archive</span><span class="sxs-lookup"><span data-stu-id="52fe1-249">set-archive Command</span></span>  
 <span data-ttu-id="52fe1-250">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-250">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-251">**bm.exe get-archivo-actividad:\<actividad > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-251">**bm.exe get-archive -Activity:\<activity> [-Server:\<server>] [-Database:\<database>]**</span></span>  
  
 <span data-ttu-id="52fe1-252">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-252">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-253">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-253">Parameter</span></span>|<span data-ttu-id="52fe1-254">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-254">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-255">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-255">Activity:\<activity name></span></span>|<span data-ttu-id="52fe1-256">Nombre de la actividad para la que se debe mostrar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="52fe1-256">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="52fe1-257">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-257">Server:\<server></span></span>|<span data-ttu-id="52fe1-258">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-258">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="52fe1-259">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-259">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-260">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-260">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-261">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-261">Database:\<database></span></span>|<span data-ttu-id="52fe1-262">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-262">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="52fe1-263">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-263">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-264">Obtiene el comportamiento del paquete de archivo para la actividad especificada, independientemente de si el paquete archiva datos de actividad o los depura.</span><span class="sxs-lookup"><span data-stu-id="52fe1-264">Gets the behavior of the archiving package for the specified activity, whether the archiving package will archive orpurge activity data.</span></span>  
  
 <span data-ttu-id="52fe1-265">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-265">**Examples**</span></span>  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="52fe1-266">Comando set-archive</span><span class="sxs-lookup"><span data-stu-id="52fe1-266">set-archive Command</span></span>  
 <span data-ttu-id="52fe1-267">**Uso**</span><span class="sxs-lookup"><span data-stu-id="52fe1-267">**Usage**</span></span>  
  
 <span data-ttu-id="52fe1-268">**bm.exe set-archivo - actividad:\<actividad > - ShouldArchive: True [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="52fe1-268">**bm.exe set-archive -Activity:\<activity> -ShouldArchive:True [-Server:\<server>] [-Database:\<database>]**</span></span>  
  
 <span data-ttu-id="52fe1-269">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="52fe1-269">**Parameters**</span></span>  
  
|<span data-ttu-id="52fe1-270">Parámetro</span><span class="sxs-lookup"><span data-stu-id="52fe1-270">Parameter</span></span>|<span data-ttu-id="52fe1-271">Description</span><span class="sxs-lookup"><span data-stu-id="52fe1-271">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52fe1-272">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="52fe1-272">Activity:\<activity name></span></span>|<span data-ttu-id="52fe1-273">Nombre de la actividad para la que se debe mostrar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="52fe1-273">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="52fe1-274">ShouldArchive: True</span><span class="sxs-lookup"><span data-stu-id="52fe1-274">ShouldArchive: True</span></span>|<span data-ttu-id="52fe1-275">Si se define como True, la actividad se traslada a la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="52fe1-275">If set to True, the activity is moved to Archive DB.</span></span> <span data-ttu-id="52fe1-276">Si se define como False, la actividad se purga.</span><span class="sxs-lookup"><span data-stu-id="52fe1-276">If set to False, the activity is purged.</span></span>|  
|<span data-ttu-id="52fe1-277">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="52fe1-277">Server:\<server></span></span>|<span data-ttu-id="52fe1-278">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-278">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="52fe1-279">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="52fe1-279">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52fe1-280">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="52fe1-280">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52fe1-281">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="52fe1-281">Database:\<database></span></span>|<span data-ttu-id="52fe1-282">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="52fe1-282">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="52fe1-283">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="52fe1-283">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52fe1-284">Define el comportamiento del paquete de archivo para la actividad especificada para que los datos de actividad se trasladen a la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="52fe1-284">Sets the behavior of the archiving package for the activity specified so that activity data is moved into the Archive DB.</span></span> <span data-ttu-id="52fe1-285">De forma predeterminada, se define este comportamiento para las actividades nuevas que se implementan.</span><span class="sxs-lookup"><span data-stu-id="52fe1-285">By default, this behavior is set for new activities that are deployed.</span></span>  
  
 <span data-ttu-id="52fe1-286">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="52fe1-286">**Examples**</span></span>  
  
 <span data-ttu-id="52fe1-287">Para purgar los datos de actividad BAM, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52fe1-287">To purge the BAM activity data, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 <span data-ttu-id="52fe1-288">Para trasladar los datos de actividad BAM a la base de datos de archivo BAM, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52fe1-288">To move the BAM activity data to the BAMArchive database, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a><span data-ttu-id="52fe1-289">Vea también</span><span class="sxs-lookup"><span data-stu-id="52fe1-289">See Also</span></span>  
 [<span data-ttu-id="52fe1-290">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="52fe1-290">BAM Management Utility</span></span>](../core/bam-management-utility.md)