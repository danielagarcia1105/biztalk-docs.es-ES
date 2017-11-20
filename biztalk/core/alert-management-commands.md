---
title: "Comandos de administración de alertas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b73129d884fea81bdb64609de5e95570275a344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="alert-management-commands"></a><span data-ttu-id="c9ab4-102">Comandos de administración de alerta</span><span class="sxs-lookup"><span data-stu-id="c9ab4-102">Alert Management Commands</span></span>
<span data-ttu-id="c9ab4-103">Los comandos de administración de alertas de la utilidad de administración de BAM permiten trabajar con alertas implementadas.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-103">The BAM management utility alert management commands allow you to work with deployed alerts.</span></span>  
  
-   <span data-ttu-id="c9ab4-104">Get-alerts: obtener una lista de alertas implementadas.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-104">get-alerts: Get a list of deployed alerts.</span></span>  
  
-   <span data-ttu-id="c9ab4-105">Remove-alerts: quita una alerta.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-105">remove-alerts: Removes an alert.</span></span>  
  
-   <span data-ttu-id="c9ab4-106">Activar alertas: habilita todas las alertas en una vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-106">enable-alerts: Enables alerts on a view.</span></span>  
  
-   <span data-ttu-id="c9ab4-107">Disable-alerts: deshabilita todas las alertas en una vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-107">disable-alerts: Disables alerts on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9ab4-108">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="c9ab4-109">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="c9ab4-110">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9ab4-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-alerts-command"></a><span data-ttu-id="c9ab4-112">Comando get-alerts</span><span class="sxs-lookup"><span data-stu-id="c9ab4-112">get-alerts Command</span></span>  
 <span data-ttu-id="c9ab4-113">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-113">**Usage**</span></span>  
  
 <span data-ttu-id="c9ab4-114">**bm.exe get-alerts [-View:\<nombre de vista >] [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-114">**bm.exe get-alerts [ -View:\<view name> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="c9ab4-115">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-115">**Parameters**</span></span>  
  
|<span data-ttu-id="c9ab4-116">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c9ab4-116">Parameter</span></span>|<span data-ttu-id="c9ab4-117">Description</span><span class="sxs-lookup"><span data-stu-id="c9ab4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9ab4-118">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-118">View:\<view name></span></span>|<span data-ttu-id="c9ab4-119">Nombre de la vista desde la que se va a obtener la lista de alertas.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-119">The name of the view from which to get the list of alerts.</span></span>|  
|<span data-ttu-id="c9ab4-120">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-120">Server:\<server></span></span>|<span data-ttu-id="c9ab4-121">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-121">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="c9ab4-122">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c9ab4-123">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c9ab4-124">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-124">Database:\<database></span></span>|<span data-ttu-id="c9ab4-125">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-125">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="c9ab4-126">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c9ab4-127">Enumera las alertas definidas en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-127">Lists the alerts defined on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="c9ab4-128">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-128">**Examples**</span></span>  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a><span data-ttu-id="c9ab4-129">Comando remove-alerts</span><span class="sxs-lookup"><span data-stu-id="c9ab4-129">remove-alerts Command</span></span>  
 <span data-ttu-id="c9ab4-130">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-130">**Usage**</span></span>  
  
 <span data-ttu-id="c9ab4-131">**bm.exe remove-alerts-View:\<nombre de vista > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-131">**bm.exe remove-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="c9ab4-132">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-132">**Parameters**</span></span>  
  
|<span data-ttu-id="c9ab4-133">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c9ab4-133">Parameter</span></span>|<span data-ttu-id="c9ab4-134">Description</span><span class="sxs-lookup"><span data-stu-id="c9ab4-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9ab4-135">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-135">View:\<view name></span></span>|<span data-ttu-id="c9ab4-136">Nombre de la vista desde la que se van a quitar las alertas.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-136">The name of the view from which to remove alerts.</span></span>|  
|<span data-ttu-id="c9ab4-137">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-137">Server:\<server></span></span>|<span data-ttu-id="c9ab4-138">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-138">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="c9ab4-139">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c9ab4-140">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c9ab4-141">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-141">Database:\<database></span></span>|<span data-ttu-id="c9ab4-142">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-142">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="c9ab4-143">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c9ab4-144">Quita todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-144">Removes all alerts on the specified view.</span></span>  
  
 <span data-ttu-id="c9ab4-145">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-145">**Examples**</span></span>  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a><span data-ttu-id="c9ab4-146">Comando enable-alerts</span><span class="sxs-lookup"><span data-stu-id="c9ab4-146">enable-alerts Command</span></span>  
 <span data-ttu-id="c9ab4-147">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-147">**Usage**</span></span>  
  
 <span data-ttu-id="c9ab4-148">**bm.exe enable-alerts-View:\<nombre de vista > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-148">**bm.exe enable-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="c9ab4-149">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-149">**Parameters**</span></span>  
  
|<span data-ttu-id="c9ab4-150">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c9ab4-150">Parameter</span></span>|<span data-ttu-id="c9ab4-151">Description</span><span class="sxs-lookup"><span data-stu-id="c9ab4-151">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9ab4-152">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-152">View:\<view name></span></span>|<span data-ttu-id="c9ab4-153">Nombre de la vista en la que se van a habilitar las alertas.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-153">The name of the view on which to enable alerts.</span></span>|  
|<span data-ttu-id="c9ab4-154">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-154">Server:\<server></span></span>|<span data-ttu-id="c9ab4-155">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-155">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="c9ab4-156">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-156">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c9ab4-157">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-157">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c9ab4-158">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-158">Database:\<database></span></span>|<span data-ttu-id="c9ab4-159">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-159">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="c9ab4-160">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-160">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c9ab4-161">Habilita todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-161">Enables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="c9ab4-162">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-162">**Examples**</span></span>  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a><span data-ttu-id="c9ab4-163">Comando disable-alerts</span><span class="sxs-lookup"><span data-stu-id="c9ab4-163">disable-alerts Command</span></span>  
 <span data-ttu-id="c9ab4-164">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-164">**Usage**</span></span>  
  
 <span data-ttu-id="c9ab4-165">**bm.exe disable-alerts-View:\<nombre de vista > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-165">**bm.exe disable-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="c9ab4-166">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-166">**Parameters**</span></span>  
  
|<span data-ttu-id="c9ab4-167">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c9ab4-167">Parameter</span></span>|<span data-ttu-id="c9ab4-168">Description</span><span class="sxs-lookup"><span data-stu-id="c9ab4-168">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9ab4-169">Vista:\<nombre de vista ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-169">View:\<view name></span></span>|<span data-ttu-id="c9ab4-170">Nombre de la vista en la que se van a deshabilitar las alertas.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-170">The name of the view on which to disable alerts.</span></span>|  
|<span data-ttu-id="c9ab4-171">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-171">Server:\<server></span></span>|<span data-ttu-id="c9ab4-172">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-172">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="c9ab4-173">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-173">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c9ab4-174">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-174">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c9ab4-175">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="c9ab4-175">Database:\<database></span></span>|<span data-ttu-id="c9ab4-176">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-176">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="c9ab4-177">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-177">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c9ab4-178">Deshabilita todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="c9ab4-178">Disables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="c9ab4-179">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c9ab4-179">**Examples**</span></span>  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9ab4-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9ab4-180">See Also</span></span>  
 [<span data-ttu-id="c9ab4-181">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c9ab4-181">BAM Management Utility</span></span>](../core/bam-management-utility.md)