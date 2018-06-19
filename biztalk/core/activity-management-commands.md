---
title: Comandos de administración de la actividad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18caccaf5207b5a63d0272c5d9e0277270c3e04c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967922"
---
# <a name="activity-management-commands"></a><span data-ttu-id="fb765-102">Comandos de la administración de la actividad</span><span class="sxs-lookup"><span data-stu-id="fb765-102">Activity Management Commands</span></span>
<span data-ttu-id="fb765-103">Los comandos de administración de la actividad de la utilidad de administración de BAM permiten trabajar con actividades implementadas.</span><span class="sxs-lookup"><span data-stu-id="fb765-103">The BAM Management utility activity management commands allow you to work with deployed activities.</span></span>  
  
-   <span data-ttu-id="fb765-104">Get-activities: Obtiene una lista de actividades implementadas.</span><span class="sxs-lookup"><span data-stu-id="fb765-104">get-activities: Gets a list of deployed activities.</span></span>  
  
-   <span data-ttu-id="fb765-105">Remove-activity: quita una actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-105">remove-activity: Removes an activity.</span></span>  
  
-   <span data-ttu-id="fb765-106">Get-activitywindow: Obtiene la duración de una actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-106">get-activitywindow: Gets the duration for an activity.</span></span>  
  
-   <span data-ttu-id="fb765-107">Set-activitywindow: establece la duración de una actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-107">set-activitywindow: Sets the activity duration for an activity.</span></span>  
  
-   <span data-ttu-id="fb765-108">Get-index: Obtiene la lista de índices.</span><span class="sxs-lookup"><span data-stu-id="fb765-108">get-index: Gets the list of indexes.</span></span>  
  
-   <span data-ttu-id="fb765-109">Crear índice: crea un nuevo índice.</span><span class="sxs-lookup"><span data-stu-id="fb765-109">create-index: Creates a new index.</span></span>  
  
-   <span data-ttu-id="fb765-110">índice de Delete: elimina un índice.</span><span class="sxs-lookup"><span data-stu-id="fb765-110">delete-index: Deletes an index.</span></span>  
  
-   <span data-ttu-id="fb765-111">Get-archive: Obtiene el comportamiento de la actividad archivada.</span><span class="sxs-lookup"><span data-stu-id="fb765-111">get-archive: Gets the behavior of archived activity.</span></span>  
  
-   <span data-ttu-id="fb765-112">Set-archive: establece el comportamiento de la actividad archivada.</span><span class="sxs-lookup"><span data-stu-id="fb765-112">set-archive: Sets the behavior of archived activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb765-113">Puede habilitar el seguimiento de cualquier comando de la utilidad BAM mediante la inclusión de la **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="fb765-113">You can enable tracing on any BAM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="fb765-114">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="fb765-114">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="fb765-115">El conmutador puede usarse junto con cualquier comando normal de BAM.</span><span class="sxs-lookup"><span data-stu-id="fb765-115">The switch can be used in conjunction with any normal BAM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb765-116">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="fb765-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-activities-command"></a><span data-ttu-id="fb765-117">Comando get-activities</span><span class="sxs-lookup"><span data-stu-id="fb765-117">get-activities Command</span></span>  
 <span data-ttu-id="fb765-118">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-118">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-119">**bm.exe get-activities [-View:\<nombre de la vista\> ] [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="fb765-119">**bm.exe get-activities [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fb765-120">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-120">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-121">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-121">Parameter</span></span>|<span data-ttu-id="fb765-122">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-123">Nombre:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-123">Name:\<activity name\></span></span>|<span data-ttu-id="fb765-124">Nombre de la actividad que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="fb765-124">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="fb765-125">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-125">Server:\<server\></span></span>|<span data-ttu-id="fb765-126">Opcional: El nombre del servidor desde el que se va a obtener la lista de actividades.</span><span class="sxs-lookup"><span data-stu-id="fb765-126">Optional: The name of the server from which to get the list of activities.</span></span> <span data-ttu-id="fb765-127">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-127">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-128">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-128">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-129">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-129">Database:\<database\></span></span>|<span data-ttu-id="fb765-130">Opcional: El nombre de la base de datos que se va a obtener la lista de actividades.</span><span class="sxs-lookup"><span data-stu-id="fb765-130">Optional: The name of the database from which to get the list of activities.</span></span> <span data-ttu-id="fb765-131">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-131">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-132">Enumera las actividades implementadas en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="fb765-132">Lists the activities deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="fb765-133">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-133">**Examples**</span></span>  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a><span data-ttu-id="fb765-134">Comando remove-activity</span><span class="sxs-lookup"><span data-stu-id="fb765-134">remove-activity Command</span></span>  
 <span data-ttu-id="fb765-135">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-135">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-136">**bm.exe remove-activity-Name:\<nombre de la actividad\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="fb765-136">**bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fb765-137">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-137">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-138">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-138">Parameter</span></span>|<span data-ttu-id="fb765-139">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-139">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-140">Nombre:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-140">Name:\<activity name\></span></span>|<span data-ttu-id="fb765-141">Nombre de la actividad que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="fb765-141">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="fb765-142">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-142">Server:\<server\></span></span>|<span data-ttu-id="fb765-143">Opcional: El nombre del servidor desde el que se va a quitar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-143">Optional: The name of the server from which to remove the activity.</span></span> <span data-ttu-id="fb765-144">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-144">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-145">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-145">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-146">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-146">Database:\<database\></span></span>|<span data-ttu-id="fb765-147">Opcional: El nombre de la base de datos que se va a quitar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-147">Optional: The name of the database from which to remove the activity.</span></span> <span data-ttu-id="fb765-148">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-148">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-149">Quita la actividad especificada de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="fb765-149">Removes the specified activity from the BAM Primary Import database.</span></span> <span data-ttu-id="fb765-150">Si la actividad tiene vistas dependientes, el comando no funcionará e informará de un error.</span><span class="sxs-lookup"><span data-stu-id="fb765-150">If the activity has dependent views, the command will fail and report an error.</span></span> <span data-ttu-id="fb765-151">Utilice el comando remove-view para quitar todas las vistas dependientes y ejecutar de nuevo el comando remove-activity.</span><span class="sxs-lookup"><span data-stu-id="fb765-151">Use the remove-view command to remove all the dependent views and execute the remove-activity command again.</span></span>  
  
 <span data-ttu-id="fb765-152">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-152">**Examples**</span></span>  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a><span data-ttu-id="fb765-153">Comando get-activitywindow</span><span class="sxs-lookup"><span data-stu-id="fb765-153">get-activitywindow Command</span></span>  
 <span data-ttu-id="fb765-154">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-154">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-155">**bm.exe get-activitywindow-actividad:\<nombre de la actividad\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="fb765-155">**bm.exe get-activitywindow -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fb765-156">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-156">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-157">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-157">Parameter</span></span>|<span data-ttu-id="fb765-158">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-158">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-159">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-159">Activity:\<activity name\></span></span>|<span data-ttu-id="fb765-160">El nombre de la .activity.</span><span class="sxs-lookup"><span data-stu-id="fb765-160">The name of the .activity.</span></span>|  
|<span data-ttu-id="fb765-161">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-161">Server:\<server\></span></span>|<span data-ttu-id="fb765-162">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-162">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="fb765-163">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-163">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-164">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-164">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-165">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-165">Database:\<database\></span></span>|<span data-ttu-id="fb765-166">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-166">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="fb765-167">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-167">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-168">Muestra la duración de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="fb765-168">Displays the duration for the specified activity.</span></span> <span data-ttu-id="fb765-169">El comando recupera la longitud de la duración y las unidades con las que se mide la duración.</span><span class="sxs-lookup"><span data-stu-id="fb765-169">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="fb765-170">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-170">**Examples**</span></span>  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a><span data-ttu-id="fb765-171">Comando set-activitywindow</span><span class="sxs-lookup"><span data-stu-id="fb765-171">set-activitywindow Command</span></span>  
 <span data-ttu-id="fb765-172">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-172">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-173">**bm.exe set-activitywindow-actividad:\<nombre de la actividad\> - TimeLength:\<número entero\> - TimeUnit: mes &#124; día &#124; Hora &#124; Minuto [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="fb765-173">**bm.exe set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fb765-174">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-174">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-175">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-175">Parameter</span></span>|<span data-ttu-id="fb765-176">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-176">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-177">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-177">Activity:\<activity name\></span></span>|<span data-ttu-id="fb765-178">Nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-178">The name of the activity.</span></span>|  
|<span data-ttu-id="fb765-179">TimeLength:\<número entero\></span><span class="sxs-lookup"><span data-stu-id="fb765-179">TimeLength:\<integer number\></span></span>|<span data-ttu-id="fb765-180">Duración de la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-180">The duration for the activity.</span></span>|  
|<span data-ttu-id="fb765-181">TimeUnit:Month &#124; día &#124; Hora &#124; Minuto</span><span class="sxs-lookup"><span data-stu-id="fb765-181">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="fb765-182">Unidad de medida de la duración.</span><span class="sxs-lookup"><span data-stu-id="fb765-182">The unit measure for the duration.</span></span>|  
|<span data-ttu-id="fb765-183">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-183">Server:\<server\></span></span>|<span data-ttu-id="fb765-184">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-184">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="fb765-185">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-186">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-186">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-187">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-187">Database:\<database\></span></span>|<span data-ttu-id="fb765-188">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-188">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="fb765-189">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-189">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-190">Establece la duración de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="fb765-190">Sets the duration for the specified activity.</span></span>  
  
 <span data-ttu-id="fb765-191">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-191">**Examples**</span></span>  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a><span data-ttu-id="fb765-192">Comando get-index</span><span class="sxs-lookup"><span data-stu-id="fb765-192">get-index Command</span></span>  
 <span data-ttu-id="fb765-193">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-193">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-194">**bm.exe get-index-actividad:\<nombre de la actividad\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="fb765-194">**bm.exe get-index -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fb765-195">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-195">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-196">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-196">Parameter</span></span>|<span data-ttu-id="fb765-197">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-197">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-198">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-198">Activity:\<activity name\></span></span>|<span data-ttu-id="fb765-199">Nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-199">The name of the activity.</span></span>|  
|<span data-ttu-id="fb765-200">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-200">Server:\<server\></span></span>|<span data-ttu-id="fb765-201">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-201">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="fb765-202">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-202">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-203">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-203">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-204">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-204">Database:\<database\></span></span>|<span data-ttu-id="fb765-205">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-205">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="fb765-206">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-206">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-207">Enumera todos los índices que se han creado para la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="fb765-207">Lists all the indexes that have been created for the specified activity.</span></span>  
  
 <span data-ttu-id="fb765-208">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-208">**Examples**</span></span>  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a><span data-ttu-id="fb765-209">Comando create-index</span><span class="sxs-lookup"><span data-stu-id="fb765-209">create-index Command</span></span>  
 <span data-ttu-id="fb765-210">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-210">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-211">**bm.exe crear-index - IndexName:\<nombre del índice\> -actividad:\<nombre de la actividad\> -punto de comprobación:\<punto de Control1\>[,\<punto de control2\>...] [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="fb765-211">**bm.exe create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fb765-212">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-212">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-213">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-213">Parameter</span></span>|<span data-ttu-id="fb765-214">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-214">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-215">IndexName:\<nombre de índice\></span><span class="sxs-lookup"><span data-stu-id="fb765-215">IndexName:\<index name\></span></span>|<span data-ttu-id="fb765-216">Nombre del índice nuevo.</span><span class="sxs-lookup"><span data-stu-id="fb765-216">The name of the new index.</span></span>|  
|<span data-ttu-id="fb765-217">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-217">Activity:\<activity name\></span></span>|<span data-ttu-id="fb765-218">Nombre de la actividad para la que se crea el índice.</span><span class="sxs-lookup"><span data-stu-id="fb765-218">The name of the activity for which the index is created.</span></span>|  
|<span data-ttu-id="fb765-219">Punto de comprobación:\<punto de Control1\>[,\<punto de control2\>...]</span><span class="sxs-lookup"><span data-stu-id="fb765-219">Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...]</span></span>|<span data-ttu-id="fb765-220">Lista delimitada por comas de puntos de control para el índice.</span><span class="sxs-lookup"><span data-stu-id="fb765-220">A comma-delimited list of checkpoints for the index.</span></span>|  
|<span data-ttu-id="fb765-221">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-221">Server:\<server\></span></span>|<span data-ttu-id="fb765-222">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-222">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="fb765-223">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-223">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-224">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-224">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-225">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-225">Database:\<database\></span></span>|<span data-ttu-id="fb765-226">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-226">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="fb765-227">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-227">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-228">Crea un índice para la actividad especificada mediante los puntos de control especificados.</span><span class="sxs-lookup"><span data-stu-id="fb765-228">Creates an index for the specified activity using the specified checkpoints.</span></span>  
  
 <span data-ttu-id="fb765-229">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-229">**Examples**</span></span>  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a><span data-ttu-id="fb765-230">Comando delete-index</span><span class="sxs-lookup"><span data-stu-id="fb765-230">delete-index Command</span></span>  
 <span data-ttu-id="fb765-231">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-231">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-232">**bm.exe delete-index - IndexName:\<nombre del índice\> -actividad:\<nombre de la actividad\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="fb765-232">**bm.exe delete-index -IndexName:\<index name\> -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fb765-233">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-233">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-234">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-234">Parameter</span></span>|<span data-ttu-id="fb765-235">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-235">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-236">IndexName:\<nombre de índice\></span><span class="sxs-lookup"><span data-stu-id="fb765-236">IndexName:\<index name\></span></span>|<span data-ttu-id="fb765-237">Nombre del índice que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="fb765-237">The name of the index to delete.</span></span>|  
|<span data-ttu-id="fb765-238">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-238">Activity:\<activity name\></span></span>|<span data-ttu-id="fb765-239">Nombre de la actividad para la que se elimina el índice.</span><span class="sxs-lookup"><span data-stu-id="fb765-239">The name of the activity for which the index is deleted.</span></span>|  
|<span data-ttu-id="fb765-240">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-240">Server:\<server\></span></span>|<span data-ttu-id="fb765-241">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-241">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="fb765-242">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-242">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-243">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-243">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-244">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-244">Database:\<database\></span></span>|<span data-ttu-id="fb765-245">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-245">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="fb765-246">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-246">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-247">Elimina el índice especificado con el nombre dado de la actividad especificada.</span><span class="sxs-lookup"><span data-stu-id="fb765-247">Deletes the specified index with the given name from the specified activity.</span></span>  
  
 <span data-ttu-id="fb765-248">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-248">**Examples**</span></span>  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="fb765-249">Comando set-archive</span><span class="sxs-lookup"><span data-stu-id="fb765-249">set-archive Command</span></span>  
 <span data-ttu-id="fb765-250">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-250">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-251">**bm.exe get-archivo-actividad:\<actividad\> [-Server:\<server\>] [-base de datos:\<base de datos\>]**</span><span class="sxs-lookup"><span data-stu-id="fb765-251">**bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="fb765-252">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-252">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-253">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-253">Parameter</span></span>|<span data-ttu-id="fb765-254">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-254">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-255">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-255">Activity:\<activity name\></span></span>|<span data-ttu-id="fb765-256">Nombre de la actividad para la que se debe mostrar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="fb765-256">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="fb765-257">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-257">Server:\<server\></span></span>|<span data-ttu-id="fb765-258">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-258">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="fb765-259">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-259">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-260">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-260">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-261">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-261">Database:\<database\></span></span>|<span data-ttu-id="fb765-262">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-262">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="fb765-263">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-263">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-264">Obtiene el comportamiento del paquete de archivo para la actividad especificada, independientemente de si el paquete archiva datos de actividad o los depura.</span><span class="sxs-lookup"><span data-stu-id="fb765-264">Gets the behavior of the archiving package for the specified activity, whether the archiving package will archive orpurge activity data.</span></span>  
  
 <span data-ttu-id="fb765-265">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-265">**Examples**</span></span>  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="fb765-266">Comando set-archive</span><span class="sxs-lookup"><span data-stu-id="fb765-266">set-archive Command</span></span>  
 <span data-ttu-id="fb765-267">**Uso**</span><span class="sxs-lookup"><span data-stu-id="fb765-267">**Usage**</span></span>  
  
 <span data-ttu-id="fb765-268">**bm.exe set-archivo - actividad:\<actividad\> - ShouldArchive: True [-Server:\<server\>] [-base de datos:\<base de datos\>]**</span><span class="sxs-lookup"><span data-stu-id="fb765-268">**bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="fb765-269">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="fb765-269">**Parameters**</span></span>  
  
|<span data-ttu-id="fb765-270">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fb765-270">Parameter</span></span>|<span data-ttu-id="fb765-271">Description</span><span class="sxs-lookup"><span data-stu-id="fb765-271">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb765-272">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="fb765-272">Activity:\<activity name\></span></span>|<span data-ttu-id="fb765-273">Nombre de la actividad para la que se debe mostrar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="fb765-273">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="fb765-274">ShouldArchive: True</span><span class="sxs-lookup"><span data-stu-id="fb765-274">ShouldArchive: True</span></span>|<span data-ttu-id="fb765-275">Si se define como True, la actividad se traslada a la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="fb765-275">If set to True, the activity is moved to Archive DB.</span></span> <span data-ttu-id="fb765-276">Si se define como False, la actividad se purga.</span><span class="sxs-lookup"><span data-stu-id="fb765-276">If set to False, the activity is purged.</span></span>|  
|<span data-ttu-id="fb765-277">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="fb765-277">Server:\<server\></span></span>|<span data-ttu-id="fb765-278">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-278">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="fb765-279">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="fb765-279">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fb765-280">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="fb765-280">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fb765-281">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="fb765-281">Database:\<database\></span></span>|<span data-ttu-id="fb765-282">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="fb765-282">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="fb765-283">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="fb765-283">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fb765-284">Define el comportamiento del paquete de archivo para la actividad especificada para que los datos de actividad se trasladen a la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="fb765-284">Sets the behavior of the archiving package for the activity specified so that activity data is moved into the Archive DB.</span></span> <span data-ttu-id="fb765-285">De forma predeterminada, se define este comportamiento para las actividades nuevas que se implementan.</span><span class="sxs-lookup"><span data-stu-id="fb765-285">By default, this behavior is set for new activities that are deployed.</span></span>  
  
 <span data-ttu-id="fb765-286">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="fb765-286">**Examples**</span></span>  
  
 <span data-ttu-id="fb765-287">Para purgar los datos de actividad BAM, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb765-287">To purge the BAM activity data, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 <span data-ttu-id="fb765-288">Para trasladar los datos de actividad BAM a la base de datos de archivo BAM, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb765-288">To move the BAM activity data to the BAMArchive database, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb765-289">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb765-289">See Also</span></span>  
 [<span data-ttu-id="fb765-290">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="fb765-290">BAM Management Utility</span></span>](../core/bam-management-utility.md)