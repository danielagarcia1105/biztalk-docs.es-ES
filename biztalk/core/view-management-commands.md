---
title: "Ver los comandos de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0a641c6d461d02f8db3e0fb0112321e0657e44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="view-management-commands"></a><span data-ttu-id="9a6c4-102">Comandos de administración de vistas</span><span class="sxs-lookup"><span data-stu-id="9a6c4-102">View Management Commands</span></span>
<span data-ttu-id="9a6c4-103">Los comandos de administración de vistas de la utilidad de administración de BAM permiten trabajar con vistas implementadas.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-103">The BAM Management utility view management commands allow you to work with deployed views.</span></span>  
  
-   <span data-ttu-id="9a6c4-104">Get-views: enumera todas las vistas implementadas.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-104">get-views: Lists all the deployed views.</span></span>  
  
-   <span data-ttu-id="9a6c4-105">Remove-view: quita una vista implementada.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-105">remove-view: Removes a deployed view.</span></span>  
  
-   <span data-ttu-id="9a6c4-106">Get-rtawindow: Obtiene la duración de una vista.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-106">get-rtawindow: Gets the duration on a view.</span></span>  
  
-   <span data-ttu-id="9a6c4-107">Set-rtawindow: establece la duración de una vista.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-107">set-rtawindow: Sets the duration on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a6c4-108">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="9a6c4-109">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="9a6c4-110">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a6c4-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-views-command"></a><span data-ttu-id="9a6c4-112">get-views (comando)</span><span class="sxs-lookup"><span data-stu-id="9a6c4-112">get-views Command</span></span>  
 <span data-ttu-id="9a6c4-113">**Uso**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-113">**Usage**</span></span>  
  
 <span data-ttu-id="9a6c4-114">**bm.exe get-views [-actividad:\<nombre de actividad >] [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-114">**bm.exe get-views [ -Activity:\<activity name> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="9a6c4-115">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-115">**Parameters**</span></span>  
  
|<span data-ttu-id="9a6c4-116">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9a6c4-116">Parameter</span></span>|<span data-ttu-id="9a6c4-117">Description</span><span class="sxs-lookup"><span data-stu-id="9a6c4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a6c4-118">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-118">Activity:\<activity name></span></span>|<span data-ttu-id="9a6c4-119">Nombre de la actividad desde la que se van a enumerar las vistas.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-119">The name of the activity from which to list the views.</span></span>|  
|<span data-ttu-id="9a6c4-120">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-120">Server:\<server></span></span>|<span data-ttu-id="9a6c4-121">Opcional: El nombre del servidor desde el que se va a obtener la lista de vistas.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-121">Optional: The name of the server from which to get the list of views.</span></span> <span data-ttu-id="9a6c4-122">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="9a6c4-123">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="9a6c4-124">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-124">Database:\<database></span></span>|<span data-ttu-id="9a6c4-125">Opcional: El nombre de la base de datos que se va a obtener la lista de vistas.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-125">Optional: The name of the database from which to get the list of views.</span></span> <span data-ttu-id="9a6c4-126">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="9a6c4-127">Enumera las vistas implementadas en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-127">Lists the views deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="9a6c4-128">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-128">**Examples**</span></span>  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a><span data-ttu-id="9a6c4-129">remove-view (comando)</span><span class="sxs-lookup"><span data-stu-id="9a6c4-129">remove-view Command</span></span>  
 <span data-ttu-id="9a6c4-130">**Uso**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-130">**Usage**</span></span>  
  
 <span data-ttu-id="9a6c4-131">**bm.exe remove-view-Name:\<nombre de vista > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-131">**bm.exe remove-view -Name:\<view name> [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="9a6c4-132">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-132">**Parameters**</span></span>  
  
|<span data-ttu-id="9a6c4-133">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9a6c4-133">Parameter</span></span>|<span data-ttu-id="9a6c4-134">Description</span><span class="sxs-lookup"><span data-stu-id="9a6c4-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a6c4-135">Nombre:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-135">Name:\<view name></span></span>|<span data-ttu-id="9a6c4-136">Nombre de la vista que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-136">The name of the view to remove.</span></span>|  
|<span data-ttu-id="9a6c4-137">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-137">Server:\<server></span></span>|<span data-ttu-id="9a6c4-138">Opcional: El nombre del servidor desde el que se va a quitar de la vista.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-138">Optional: The name of the server from which to remove the view.</span></span> <span data-ttu-id="9a6c4-139">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="9a6c4-140">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="9a6c4-141">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-141">Database:\<database></span></span>|<span data-ttu-id="9a6c4-142">Opcional: El nombre de la base de datos que se va a quitar de la vista.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-142">Optional: The name of the database from which to remove the view.</span></span> <span data-ttu-id="9a6c4-143">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="9a6c4-144">Quita la vista especificada de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-144">Removes the specified view from the BAM Primary Import database.</span></span> <span data-ttu-id="9a6c4-145">Si la vista tiene alertas dependientes, se quitan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-145">If the view has dependent alerts, they are removed at the same time.</span></span>  
  
 <span data-ttu-id="9a6c4-146">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-146">**Examples**</span></span>  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a><span data-ttu-id="9a6c4-147">get-rtawindow (comando)</span><span class="sxs-lookup"><span data-stu-id="9a6c4-147">get-rtawindow Command</span></span>  
 <span data-ttu-id="9a6c4-148">**Uso**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-148">**Usage**</span></span>  
  
 <span data-ttu-id="9a6c4-149">**bm.exe get-rtawindow-View:\<nombre de la vista >-actividad:\<nombre de la actividad > -ATR:\<nombre de ATR > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-149">**bm.exe get-rtawindow -View:\<view name> -Activity:\<activity name> -Rta:\<RTA name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="9a6c4-150">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-150">**Parameters**</span></span>  
  
|<span data-ttu-id="9a6c4-151">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9a6c4-151">Parameter</span></span>|<span data-ttu-id="9a6c4-152">Description</span><span class="sxs-lookup"><span data-stu-id="9a6c4-152">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a6c4-153">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-153">View:\<view name></span></span>|<span data-ttu-id="9a6c4-154">Nombre de vista.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-154">The view name.</span></span>|  
|<span data-ttu-id="9a6c4-155">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-155">Activity:\<activity name></span></span>|<span data-ttu-id="9a6c4-156">Nombre de actividad.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-156">The activity name.</span></span>|  
|<span data-ttu-id="9a6c4-157">RTA:\<nombre de ATR ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-157">Rta:\<RTA name></span></span>|<span data-ttu-id="9a6c4-158">Nombre de agregación en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-158">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="9a6c4-159">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-159">Server:\<server></span></span>|<span data-ttu-id="9a6c4-160">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-160">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="9a6c4-161">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-161">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="9a6c4-162">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-162">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="9a6c4-163">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-163">Database:\<database></span></span>|<span data-ttu-id="9a6c4-164">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-164">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="9a6c4-165">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-165">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="9a6c4-166">Muestra la duración de la agregación en tiempo real especificada.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-166">Displays the duration of the specified real-time aggregation.</span></span> <span data-ttu-id="9a6c4-167">El comando recupera la longitud de la duración y las unidades con las que se mide la duración.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-167">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="9a6c4-168">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-168">**Examples**</span></span>  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a><span data-ttu-id="9a6c4-169">set-rtawindow (comando)</span><span class="sxs-lookup"><span data-stu-id="9a6c4-169">set-rtawindow Command</span></span>  
 <span data-ttu-id="9a6c4-170">**Uso**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-170">**Usage**</span></span>  
  
 <span data-ttu-id="9a6c4-171">**bm.exe set-rtawindow-View:\<nombre de vista >-actividad:\<nombre de actividad >-nombre:\<nombre de ATR > - TimeLength:\<número entero >-TimeUnit:Day &#124; Hora &#124; Minuto [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-171">**bm.exe set-rtawindow -View:\<view name> -Activity:\<activity name> -Name:\<RTA name> -TimeLength:\<integer number>-TimeUnit:Day&#124;Hour&#124;Minute[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="9a6c4-172">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-172">**Parameters**</span></span>  
  
|<span data-ttu-id="9a6c4-173">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9a6c4-173">Parameter</span></span>|<span data-ttu-id="9a6c4-174">Description</span><span class="sxs-lookup"><span data-stu-id="9a6c4-174">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a6c4-175">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-175">View:\<view name></span></span>|<span data-ttu-id="9a6c4-176">Nombre de vista.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-176">The view name.</span></span>|  
|<span data-ttu-id="9a6c4-177">Actividad:\<nombre de actividad ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-177">Activity:\<activity name></span></span>|<span data-ttu-id="9a6c4-178">Nombre de actividad.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-178">The activity name.</span></span>|  
|<span data-ttu-id="9a6c4-179">Nombre:\<nombre de ATR ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-179">Name:\<RTA name></span></span>|<span data-ttu-id="9a6c4-180">Nombre de agregación en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-180">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="9a6c4-181">TimeLength:\<número entero ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-181">TimeLength:\<integer number></span></span>|<span data-ttu-id="9a6c4-182">Duración de la agregación en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-182">The duration for the real-time aggregation.</span></span>|  
|<span data-ttu-id="9a6c4-183">TimeUnit:Month &#124; día &#124; Hora &#124; Minuto</span><span class="sxs-lookup"><span data-stu-id="9a6c4-183">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="9a6c4-184">Unidad de medida de la duración de la ventana.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-184">The unit measure for the window duration.</span></span>|  
|<span data-ttu-id="9a6c4-185">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-185">Server:\<server></span></span>|<span data-ttu-id="9a6c4-186">Opcional: El nombre del servidor en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-186">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="9a6c4-187">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-187">The server must be in the same domain as the machine from which you are running bm.exe.</span></span> <span data-ttu-id="9a6c4-188">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-188">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="9a6c4-189">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="9a6c4-189">Database:\<database></span></span>|<span data-ttu-id="9a6c4-190">Opcional: El nombre de la base de datos en el que reside la actividad.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-190">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="9a6c4-191">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-191">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="9a6c4-192">Establece la duración para la agregación en tiempo real especificada.</span><span class="sxs-lookup"><span data-stu-id="9a6c4-192">Sets the duration for the specified real-time aggregation.</span></span>  
  
 <span data-ttu-id="9a6c4-193">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="9a6c4-193">**Examples**</span></span>  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a6c4-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a6c4-194">See Also</span></span>  
 [<span data-ttu-id="9a6c4-195">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="9a6c4-195">BAM Management Utility</span></span>](../core/bam-management-utility.md)