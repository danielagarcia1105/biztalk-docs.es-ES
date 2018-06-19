---
title: Comandos de administración de alertas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f419e7a0019287383080c319961b8a3831d27bb4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967690"
---
# <a name="alert-management-commands"></a><span data-ttu-id="a53b1-102">Comandos de administración de alerta</span><span class="sxs-lookup"><span data-stu-id="a53b1-102">Alert Management Commands</span></span>
<span data-ttu-id="a53b1-103">Los comandos de administración de alertas de la utilidad de administración de BAM permiten trabajar con alertas implementadas.</span><span class="sxs-lookup"><span data-stu-id="a53b1-103">The BAM management utility alert management commands allow you to work with deployed alerts.</span></span>  
  
-   <span data-ttu-id="a53b1-104">Get-alerts: obtener una lista de alertas implementadas.</span><span class="sxs-lookup"><span data-stu-id="a53b1-104">get-alerts: Get a list of deployed alerts.</span></span>  
  
-   <span data-ttu-id="a53b1-105">Remove-alerts: quita una alerta.</span><span class="sxs-lookup"><span data-stu-id="a53b1-105">remove-alerts: Removes an alert.</span></span>  
  
-   <span data-ttu-id="a53b1-106">Activar alertas: habilita todas las alertas en una vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-106">enable-alerts: Enables alerts on a view.</span></span>  
  
-   <span data-ttu-id="a53b1-107">Disable-alerts: deshabilita todas las alertas en una vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-107">disable-alerts: Disables alerts on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a53b1-108">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a53b1-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="a53b1-109">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a53b1-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="a53b1-110">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="a53b1-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a53b1-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a53b1-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-alerts-command"></a><span data-ttu-id="a53b1-112">Comando get-alerts</span><span class="sxs-lookup"><span data-stu-id="a53b1-112">get-alerts Command</span></span>  
 <span data-ttu-id="a53b1-113">**Uso**</span><span class="sxs-lookup"><span data-stu-id="a53b1-113">**Usage**</span></span>  
  
 <span data-ttu-id="a53b1-114">**bm.exe get-alerts [-View:\<nombre de la vista\> ] [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="a53b1-114">**bm.exe get-alerts [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="a53b1-115">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="a53b1-115">**Parameters**</span></span>  
  
|<span data-ttu-id="a53b1-116">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a53b1-116">Parameter</span></span>|<span data-ttu-id="a53b1-117">Description</span><span class="sxs-lookup"><span data-stu-id="a53b1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a53b1-118">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="a53b1-118">View:\<view name\></span></span>|<span data-ttu-id="a53b1-119">Nombre de la vista desde la que se va a obtener la lista de alertas.</span><span class="sxs-lookup"><span data-stu-id="a53b1-119">The name of the view from which to get the list of alerts.</span></span>|  
|<span data-ttu-id="a53b1-120">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="a53b1-120">Server:\<server\></span></span>|<span data-ttu-id="a53b1-121">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-121">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="a53b1-122">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="a53b1-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="a53b1-123">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="a53b1-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="a53b1-124">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="a53b1-124">Database:\<database\></span></span>|<span data-ttu-id="a53b1-125">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-125">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="a53b1-126">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="a53b1-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="a53b1-127">Enumera las alertas definidas en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="a53b1-127">Lists the alerts defined on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="a53b1-128">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="a53b1-128">**Examples**</span></span>  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a><span data-ttu-id="a53b1-129">Comando remove-alerts</span><span class="sxs-lookup"><span data-stu-id="a53b1-129">remove-alerts Command</span></span>  
 <span data-ttu-id="a53b1-130">**Uso**</span><span class="sxs-lookup"><span data-stu-id="a53b1-130">**Usage**</span></span>  
  
 <span data-ttu-id="a53b1-131">**bm.exe remove-alerts-View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="a53b1-131">**bm.exe remove-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="a53b1-132">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="a53b1-132">**Parameters**</span></span>  
  
|<span data-ttu-id="a53b1-133">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a53b1-133">Parameter</span></span>|<span data-ttu-id="a53b1-134">Description</span><span class="sxs-lookup"><span data-stu-id="a53b1-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a53b1-135">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="a53b1-135">View:\<view name\></span></span>|<span data-ttu-id="a53b1-136">Nombre de la vista desde la que se van a quitar las alertas.</span><span class="sxs-lookup"><span data-stu-id="a53b1-136">The name of the view from which to remove alerts.</span></span>|  
|<span data-ttu-id="a53b1-137">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="a53b1-137">Server:\<server\></span></span>|<span data-ttu-id="a53b1-138">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-138">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="a53b1-139">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="a53b1-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="a53b1-140">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="a53b1-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="a53b1-141">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="a53b1-141">Database:\<database\></span></span>|<span data-ttu-id="a53b1-142">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-142">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="a53b1-143">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="a53b1-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="a53b1-144">Quita todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="a53b1-144">Removes all alerts on the specified view.</span></span>  
  
 <span data-ttu-id="a53b1-145">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="a53b1-145">**Examples**</span></span>  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a><span data-ttu-id="a53b1-146">Comando enable-alerts</span><span class="sxs-lookup"><span data-stu-id="a53b1-146">enable-alerts Command</span></span>  
 <span data-ttu-id="a53b1-147">**Uso**</span><span class="sxs-lookup"><span data-stu-id="a53b1-147">**Usage**</span></span>  
  
 <span data-ttu-id="a53b1-148">**bm.exe enable-alerts-View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="a53b1-148">**bm.exe enable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="a53b1-149">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="a53b1-149">**Parameters**</span></span>  
  
|<span data-ttu-id="a53b1-150">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a53b1-150">Parameter</span></span>|<span data-ttu-id="a53b1-151">Description</span><span class="sxs-lookup"><span data-stu-id="a53b1-151">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a53b1-152">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="a53b1-152">View:\<view name\></span></span>|<span data-ttu-id="a53b1-153">Nombre de la vista en la que se van a habilitar las alertas.</span><span class="sxs-lookup"><span data-stu-id="a53b1-153">The name of the view on which to enable alerts.</span></span>|  
|<span data-ttu-id="a53b1-154">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="a53b1-154">Server:\<server\></span></span>|<span data-ttu-id="a53b1-155">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-155">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="a53b1-156">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="a53b1-156">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="a53b1-157">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="a53b1-157">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="a53b1-158">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="a53b1-158">Database:\<database\></span></span>|<span data-ttu-id="a53b1-159">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-159">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="a53b1-160">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="a53b1-160">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="a53b1-161">Habilita todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="a53b1-161">Enables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="a53b1-162">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="a53b1-162">**Examples**</span></span>  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a><span data-ttu-id="a53b1-163">Comando disable-alerts</span><span class="sxs-lookup"><span data-stu-id="a53b1-163">disable-alerts Command</span></span>  
 <span data-ttu-id="a53b1-164">**Uso**</span><span class="sxs-lookup"><span data-stu-id="a53b1-164">**Usage**</span></span>  
  
 <span data-ttu-id="a53b1-165">**bm.exe disable-alerts-View:\<nombre de la vista\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**</span><span class="sxs-lookup"><span data-stu-id="a53b1-165">**bm.exe disable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="a53b1-166">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="a53b1-166">**Parameters**</span></span>  
  
|<span data-ttu-id="a53b1-167">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a53b1-167">Parameter</span></span>|<span data-ttu-id="a53b1-168">Description</span><span class="sxs-lookup"><span data-stu-id="a53b1-168">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a53b1-169">Vista:\<nombre de vista\></span><span class="sxs-lookup"><span data-stu-id="a53b1-169">View:\<view name\></span></span>|<span data-ttu-id="a53b1-170">Nombre de la vista en la que se van a deshabilitar las alertas.</span><span class="sxs-lookup"><span data-stu-id="a53b1-170">The name of the view on which to disable alerts.</span></span>|  
|<span data-ttu-id="a53b1-171">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="a53b1-171">Server:\<server\></span></span>|<span data-ttu-id="a53b1-172">Opcional: El nombre del servidor en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-172">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="a53b1-173">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="a53b1-173">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="a53b1-174">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="a53b1-174">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="a53b1-175">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="a53b1-175">Database:\<database\></span></span>|<span data-ttu-id="a53b1-176">Opcional: El nombre de la base de datos en el que reside la vista.</span><span class="sxs-lookup"><span data-stu-id="a53b1-176">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="a53b1-177">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="a53b1-177">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="a53b1-178">Deshabilita todas las alertas en la vista especificada.</span><span class="sxs-lookup"><span data-stu-id="a53b1-178">Disables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="a53b1-179">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="a53b1-179">**Examples**</span></span>  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="a53b1-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="a53b1-180">See Also</span></span>  
 [<span data-ttu-id="a53b1-181">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="a53b1-181">BAM Management Utility</span></span>](../core/bam-management-utility.md)