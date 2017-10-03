---
title: "Comandos de administración de infraestructura | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae58ea03f394b0fe8b7223bdd810dbc72ccb2472
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="infrastructure-management-commands"></a><span data-ttu-id="c832b-102">Comandos de administración de infraestructura</span><span class="sxs-lookup"><span data-stu-id="c832b-102">Infrastructure Management Commands</span></span>
<span data-ttu-id="c832b-103">Los comandos de configuración de la utilidad de administración de BAM (BM) permiten obtener y actualizar la configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-103">The BAM Management (BM) utility configuration commands allow you get and update the BAM configuration.</span></span>  
  
-   <span data-ttu-id="c832b-104">Get-config: Obtiene el archivo de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-104">get-config: Gets the BAM configuration file.</span></span>  
  
-   <span data-ttu-id="c832b-105">Update-config: actualiza la configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-105">update-config: Updates the BAM configuration.</span></span>  
  
-   <span data-ttu-id="c832b-106">Get-changes: enumera los cambios de la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-106">get-changes: Lists changes to the BAM infrastructure.</span></span>  
  
-   <span data-ttu-id="c832b-107">Get-defxml: Obtiene un archivo que contiene todos los artefactos de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-107">get-defxml: Gets a file containing all the artifacts in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c832b-108">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="c832b-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="c832b-109">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c832b-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="c832b-110">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="c832b-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c832b-111">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c832b-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-config-command"></a><span data-ttu-id="c832b-112">Comando get-config</span><span class="sxs-lookup"><span data-stu-id="c832b-112">get-config Command</span></span>  
 <span data-ttu-id="c832b-113">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c832b-113">**Usage**</span></span>  
  
 <span data-ttu-id="c832b-114">**bm.exe get-config - FileName:\<archivo de salida > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="c832b-114">**bm.exe get-config -FileName:\<output file> [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="c832b-115">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c832b-115">**Parameters**</span></span>  
  
|<span data-ttu-id="c832b-116">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c832b-116">Parameter</span></span>|<span data-ttu-id="c832b-117">Description</span><span class="sxs-lookup"><span data-stu-id="c832b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c832b-118">Nombre de archivo:\<archivo de salida ></span><span class="sxs-lookup"><span data-stu-id="c832b-118">FileName:\<output file></span></span>|<span data-ttu-id="c832b-119">Ruta de acceso y nombre del archivo en el que se va a guardar el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c832b-119">The path and name to which to save the configuration file.</span></span>|  
|<span data-ttu-id="c832b-120">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="c832b-120">Server:\<server></span></span>|<span data-ttu-id="c832b-121">Opcional: El nombre del servidor desde el que se va a obtener la configuración.</span><span class="sxs-lookup"><span data-stu-id="c832b-121">Optional: The name of the server from which to get the configuration.</span></span> <span data-ttu-id="c832b-122">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="c832b-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c832b-123">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="c832b-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c832b-124">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="c832b-124">Database:\<database></span></span>|<span data-ttu-id="c832b-125">Opcional: El nombre de la base de datos que se va a obtener la configuración.</span><span class="sxs-lookup"><span data-stu-id="c832b-125">Optional: The name of the database from which to get the configuration.</span></span> <span data-ttu-id="c832b-126">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c832b-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c832b-127">Recupera el archivo XML de configuración de BAM y lo guarda en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c832b-127">Retrieves the BAM configuration XML and saves it in the specified file.</span></span> <span data-ttu-id="c832b-128">El **get-config** comando no sobrescribirá el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="c832b-128">The **get-config** command will not overwrite the existing file.</span></span>  
  
 <span data-ttu-id="c832b-129">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c832b-129">**Examples**</span></span>  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a><span data-ttu-id="c832b-130">Comando update-config</span><span class="sxs-lookup"><span data-stu-id="c832b-130">update-config Command</span></span>  
 <span data-ttu-id="c832b-131">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c832b-131">**Usage**</span></span>  
  
 <span data-ttu-id="c832b-132">**bm.exe update-config - FileName:\<el archivo de configuración >**</span><span class="sxs-lookup"><span data-stu-id="c832b-132">**bm.exe update-config -FileName:\<config file>**</span></span>  
  
 <span data-ttu-id="c832b-133">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c832b-133">**Parameters**</span></span>  
  
|<span data-ttu-id="c832b-134">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c832b-134">Parameter</span></span>|<span data-ttu-id="c832b-135">Description</span><span class="sxs-lookup"><span data-stu-id="c832b-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c832b-136">Nombre de archivo:\<el archivo de configuración ></span><span class="sxs-lookup"><span data-stu-id="c832b-136">FileName:\<config file></span></span>|<span data-ttu-id="c832b-137">Ruta y nombre del archivo de configuración desde el que se va a actualizar la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-137">The path and name of the configuration file from which to update the BAM infrastructure.</span></span>|  
  
 <span data-ttu-id="c832b-138">Actualiza la configuración en el equipo local desde un archivo que contiene el XML de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-138">Updates the configuration on the local computer from a file containing BAM configuration XML.</span></span> <span data-ttu-id="c832b-139">Puede agregar nombres de servidor y de base de datos que todavía no existan en la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="c832b-139">You can add server and database names that do not already exist in the current configuration.</span></span> <span data-ttu-id="c832b-140">Si cambia los nombres de servidor o de base de datos que ya tengan implementada la infraestructura dinámica se generará un error y bm.exe lo informará.</span><span class="sxs-lookup"><span data-stu-id="c832b-140">Changing server or database names that already have dynamic infrastructure deployed in will fail and bm.exe will report an error.</span></span>  
  
 <span data-ttu-id="c832b-141">Si modifica la ubicación de descarga de archivos para las alertas entregadas por el archivo,</span><span class="sxs-lookup"><span data-stu-id="c832b-141">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="c832b-142">deberá reiniciar los servicios de notificación de SQL.</span><span class="sxs-lookup"><span data-stu-id="c832b-142">You must restart the SQL Notifications Services.</span></span> <span data-ttu-id="c832b-143">Si no se reinician los servicios de notificación, las alertas se seguirán entregando en la ubicación de entrega de archivos original.</span><span class="sxs-lookup"><span data-stu-id="c832b-143">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
 <span data-ttu-id="c832b-144">Para cambiar la ubicación de entrega de archivos, modifique la siguiente línea del archivo de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-144">The file drop location is changed by modifying the following line of the BAM configuration file.</span></span>  
  
 <span data-ttu-id="c832b-145">\<Nombre de propiedad = "FileDropUNC" >\\\\< nombre de equipo\>\alerts \< /Property ></span><span class="sxs-lookup"><span data-stu-id="c832b-145">\<Property Name="FileDropUNC">\\\\<computer name\>\alerts\</Property></span></span>  
  
 <span data-ttu-id="c832b-146">Para que conocer los pasos adecuados actualizar las referencias, vea [copia de seguridad y restauración de BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="c832b-146">For appropriate steps to update the references, see [Backing Up and Restoring BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c832b-147">Si ejecuta un comando update-database mediante un archivo de configuración de BAM que no contiene una sección de alertas y si ya ha configurado alertas BAM, bm.exe sobrescribirá la configuración de tal manera que ya no funcionarán las alertas.</span><span class="sxs-lookup"><span data-stu-id="c832b-147">If you execute an update-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="c832b-148">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c832b-148">**Examples**</span></span>  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a><span data-ttu-id="c832b-149">Comando get-changes</span><span class="sxs-lookup"><span data-stu-id="c832b-149">get-changes Command</span></span>  
 <span data-ttu-id="c832b-150">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c832b-150">**Usage**</span></span>  
  
 <span data-ttu-id="c832b-151">**bm.exe get-changes [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="c832b-151">**bm.exe get-changes [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="c832b-152">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c832b-152">**Parameters**</span></span>  
  
|<span data-ttu-id="c832b-153">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c832b-153">Parameter</span></span>|<span data-ttu-id="c832b-154">Description</span><span class="sxs-lookup"><span data-stu-id="c832b-154">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c832b-155">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="c832b-155">Server:\<server></span></span>|<span data-ttu-id="c832b-156">Opcional: El nombre del servidor en el que reside la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-156">Optional: The name of the server on which the BAM Primary Import database resides.</span></span> <span data-ttu-id="c832b-157">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="c832b-157">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c832b-158">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="c832b-158">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c832b-159">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="c832b-159">Database:\<database></span></span>|<span data-ttu-id="c832b-160">Opcional: Si no se especifica el nombre, bm.exe utiliza el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c832b-160">Optional: If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c832b-161">Obtiene una lista de cambios aplicados a la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-161">Gets a list of changes applied to the BAM Primary Import database.</span></span> <span data-ttu-id="c832b-162">Puede utilizar este comando para auditar cambios a la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="c832b-162">You can use this command to audit changes to the BAM Infrastructure.</span></span> <span data-ttu-id="c832b-163">El comando devuelve la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="c832b-163">The command returns the following information:</span></span>  
  
 <span data-ttu-id="c832b-164">Tipo de comando del cambio y del archivo desde el que se aplicó el cambio.</span><span class="sxs-lookup"><span data-stu-id="c832b-164">The command type of the change and the file from which the change was applied.</span></span>  
  
 <span data-ttu-id="c832b-165">¿Quién aplicó el cambio?</span><span class="sxs-lookup"><span data-stu-id="c832b-165">Who applied the change.</span></span>  
  
 <span data-ttu-id="c832b-166">¿Qué actividades se cambiaron?</span><span class="sxs-lookup"><span data-stu-id="c832b-166">Which activities were changed.</span></span>  
  
 <span data-ttu-id="c832b-167">¿Qué vistas se cambiaron?</span><span class="sxs-lookup"><span data-stu-id="c832b-167">Which views were changed.</span></span>  
  
 <span data-ttu-id="c832b-168">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c832b-168">**Examples**</span></span>  
  
```  
bm.exe get-changes  
```  
  
 <span data-ttu-id="c832b-169">Salida de comando</span><span class="sxs-lookup"><span data-stu-id="c832b-169">Output of command</span></span>  
  
 <span data-ttu-id="c832b-170">\#1: implemente c:\bam\ordermanagement.xml</span><span class="sxs-lookup"><span data-stu-id="c832b-170">\#1: Deploy c:\bam\ordermanagement.xml</span></span>  
  
 <span data-ttu-id="c832b-171">Por dominio\usuario en 12/30/2005 8:17:08 PM (v3.5.1536.0).</span><span class="sxs-lookup"><span data-stu-id="c832b-171">By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).</span></span>  
  
 <span data-ttu-id="c832b-172">Actividades: OrderMgmt</span><span class="sxs-lookup"><span data-stu-id="c832b-172">Activities: OrderMgmt</span></span>  
  
 <span data-ttu-id="c832b-173">Vistas: SalesManager</span><span class="sxs-lookup"><span data-stu-id="c832b-173">Views: SalesManager</span></span>  
  
## <a name="get-defxml-command"></a><span data-ttu-id="c832b-174">Comando get-defxml</span><span class="sxs-lookup"><span data-stu-id="c832b-174">get-defxml Command</span></span>  
 <span data-ttu-id="c832b-175">**Uso**</span><span class="sxs-lookup"><span data-stu-id="c832b-175">**Usage**</span></span>  
  
 <span data-ttu-id="c832b-176">**bm.exe get-defxml - FileName:\<archivo de salida > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="c832b-176">**bm.exe get-defxml -FileName:\<output file>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="c832b-177">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="c832b-177">**Parameters**</span></span>  
  
|<span data-ttu-id="c832b-178">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c832b-178">Parameter</span></span>|<span data-ttu-id="c832b-179">Description</span><span class="sxs-lookup"><span data-stu-id="c832b-179">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c832b-180">Nombre de archivo:\<archivo de salida ></span><span class="sxs-lookup"><span data-stu-id="c832b-180">FileName:\<output file></span></span>|<span data-ttu-id="c832b-181">Ruta y nombre del archivo en el que se van a guardar las definiciones.</span><span class="sxs-lookup"><span data-stu-id="c832b-181">The path and name of the file to which to save the definitions.</span></span>|  
|<span data-ttu-id="c832b-182">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="c832b-182">Server:\<server></span></span>|<span data-ttu-id="c832b-183">Opcional: El nombre del servidor desde el que se va a obtener las definiciones.</span><span class="sxs-lookup"><span data-stu-id="c832b-183">Optional: The name of the server from which to get the definitions.</span></span> <span data-ttu-id="c832b-184">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="c832b-184">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c832b-185">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="c832b-185">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c832b-186">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="c832b-186">Database:\<database></span></span>|<span data-ttu-id="c832b-187">Opcional: El nombre de la base de datos que se va a obtener las definiciones.</span><span class="sxs-lookup"><span data-stu-id="c832b-187">Optional: The name of the database from which to get the definitions.</span></span> <span data-ttu-id="c832b-188">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c832b-188">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c832b-189">Recupera todos los artefactos de la base de datos de importación principal de BAM y los guarda en un archivo como XML.</span><span class="sxs-lookup"><span data-stu-id="c832b-189">Retrieves all artifacts on from the BAM Primary Import database and saves them in a file as XML.</span></span> <span data-ttu-id="c832b-190">El comando no sobrescribirá archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="c832b-190">The command will not overwrite existing files.</span></span>  
  
 <span data-ttu-id="c832b-191">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="c832b-191">**Examples**</span></span>  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a><span data-ttu-id="c832b-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="c832b-192">See Also</span></span>  
 [<span data-ttu-id="c832b-193">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="c832b-193">BAM Management Utility</span></span>](../core/bam-management-utility.md)