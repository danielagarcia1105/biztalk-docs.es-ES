---
title: Comandos de administración de interceptor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2be6460-1f81-4bc3-a831-34ff24d65d34
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aefeefc7010c4cefca323782dac5a1349479a07d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023170"
---
# <a name="interceptor-management-commands"></a><span data-ttu-id="7e66d-102">Comandos de administración de interceptor</span><span class="sxs-lookup"><span data-stu-id="7e66d-102">Interceptor Management Commands</span></span>
<span data-ttu-id="7e66d-103">Para el funcionamiento de la nueva funcionalidad del interceptor de BAM, se han agregado cuatro nuevos comandos a la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="7e66d-103">To support the new BAM interceptor functionality, four new commands have been added to the BAM Management utility.</span></span>  
  
 <span data-ttu-id="7e66d-104">Estos comandos permiten la implementación, recuperación y eliminación de interceptores.</span><span class="sxs-lookup"><span data-stu-id="7e66d-104">These commands support the deployment, retrieval, and removal of interceptors.</span></span> <span data-ttu-id="7e66d-105">También se incluye un comando para enumerar los interceptores configurados.</span><span class="sxs-lookup"><span data-stu-id="7e66d-105">A command is also provided to list the configured interceptors.</span></span>  
  
-   <span data-ttu-id="7e66d-106">interceptor de implementar: implementa una configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-106">deploy-interceptor: Deploys an interceptor configuration.</span></span>  
  
-   <span data-ttu-id="7e66d-107">Get-interceptorlist: Obtiene una lista de actividades en el que se implementa la interceptación.</span><span class="sxs-lookup"><span data-stu-id="7e66d-107">get-interceptorlist: Gets a list of activities on which interception is deployed.</span></span>  
  
-   <span data-ttu-id="7e66d-108">Get-interceptor: Obtiene la configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-108">get-interceptor: Gets the interceptor configuration.</span></span>  
  
-   <span data-ttu-id="7e66d-109">Remove-interceptor: quita una configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-109">remove-interceptor: Removes an interceptor configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e66d-110">Habilitar seguimiento de cualquier comando de la utilidad BM, incluya el **-Trace: en&#124;desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="7e66d-110">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="7e66d-111">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7e66d-111">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="7e66d-112">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="7e66d-112">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e66d-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7e66d-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-interceptor-command"></a><span data-ttu-id="7e66d-114">Comando deploy-interceptor:</span><span class="sxs-lookup"><span data-stu-id="7e66d-114">deploy-interceptor Command</span></span>  
 <span data-ttu-id="7e66d-115">**Usage**</span><span class="sxs-lookup"><span data-stu-id="7e66d-115">**Usage**</span></span>  
  
 <span data-ttu-id="7e66d-116">**bm.exe implementar-interceptor - FileName:\<el nombre de archivo de configuración XML\> [-Force: True] [-Server:\<server\>] [-base de datos:\<base de datos\>]**</span><span class="sxs-lookup"><span data-stu-id="7e66d-116">**bm.exe deploy-interceptor -FileName:\<Configuration XML Filename\> [-Force:True ] [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="7e66d-117">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="7e66d-117">**Parameters**</span></span>  
  
|<span data-ttu-id="7e66d-118">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7e66d-118">Parameter</span></span>|<span data-ttu-id="7e66d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e66d-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e66d-120">Nombre de archivo:\<el nombre de archivo de configuración XML\></span><span class="sxs-lookup"><span data-stu-id="7e66d-120">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="7e66d-121">nombre del archivo XML que contiene la configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-121">The name of the XML file containing the interceptor configuration.</span></span>|  
|<span data-ttu-id="7e66d-122">Force:True</span><span class="sxs-lookup"><span data-stu-id="7e66d-122">Force:True</span></span>|<span data-ttu-id="7e66d-123">Opcional: Fuerza la implementación de la configuración del interceptor cuando se detectan conflictos de nombres de origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="7e66d-123">Optional: Forces deployment of the interceptor configuration when event source name collisions are detected.</span></span>|  
|<span data-ttu-id="7e66d-124">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="7e66d-124">Server:\<server\></span></span>|<span data-ttu-id="7e66d-125">Opcional: El nombre del servidor en el que se va a implementar el interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-125">Optional: The name of the server on which to deploy the interceptor.</span></span> <span data-ttu-id="7e66d-126">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="7e66d-126">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="7e66d-127">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="7e66d-127">Database:\<database\></span></span>|<span data-ttu-id="7e66d-128">Opcional: El nombre de la base de datos de importación principal de BAM en el que se va a configurar el interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-128">Optional: The name of the BAM Primary Import database on which to configure the interceptor.</span></span>|  
  
 <span data-ttu-id="7e66d-129">Este comando implementa la configuración del interceptor en la base de datos y el servidor especificados.</span><span class="sxs-lookup"><span data-stu-id="7e66d-129">This command deploys the interceptor configuration to the specified server and database.</span></span> <span data-ttu-id="7e66d-130">Durante la implementación, la utilidad de administración de BAM lleva a cabo las validaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e66d-130">During deployment, the BAM Management utility performs the following validations:</span></span>  
  
- <span data-ttu-id="7e66d-131">Validación de XSD: la configuración del interceptor se valida con respecto al esquema de configuración del interceptor común.</span><span class="sxs-lookup"><span data-stu-id="7e66d-131">XSD validation: The interceptor configuration is validated against the common interceptor configuration schema.</span></span>  
  
- <span data-ttu-id="7e66d-132">Validación de que la actividad existe (está implementada en la base de datos de importación principal) y de que los puntos de control son válidos (existen y tienen un tipo de datos coincidente).</span><span class="sxs-lookup"><span data-stu-id="7e66d-132">Validation that the activity exists (is deployed in the Primary Import database) and that checkpoints are valid (exist and have a matching data type).</span></span>  
  
  <span data-ttu-id="7e66d-133">Si se detecta un conflicto en el nombre del origen del evento, se genera una advertencia que describe ese conflicto.</span><span class="sxs-lookup"><span data-stu-id="7e66d-133">If a collision is detected in the event source name, a warning is thrown describing the collision.</span></span> <span data-ttu-id="7e66d-134">En caso de conflicto, la implementación se producirá un error a menos que el **– Force: True** marcador de parámetro se utiliza.</span><span class="sxs-lookup"><span data-stu-id="7e66d-134">In the case of a collision, the deployment will fail unless the **–Force:True** parameter flag is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e66d-135">El **– Force: True** parámetro potencialmente elimina configuraciones de interceptores que hacen referencia a orígenes de eventos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="7e66d-135">The **–Force:True** parameter potentially removes interceptor configurations that reference event sources with the same name.</span></span> <span data-ttu-id="7e66d-136">Debe usar el **get-interceptor** comando para crear una copia de seguridad de las configuraciones de interceptor existentes antes de usar el **– Force: True** parámetro.</span><span class="sxs-lookup"><span data-stu-id="7e66d-136">You should use the **get-interceptor** command to create a backup of existing interceptor configurations before using the **–Force:True** parameter.</span></span>  
  
 <span data-ttu-id="7e66d-137">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="7e66d-137">**Examples**</span></span>  
  
```  
bm.exe deploy-interceptor  -FileName:myInceptor.xml  
bm.exe deploy-interceptor  -FileName:myInceptor.xml -Force:True  
```  
  
## <a name="get-interceptorlist-command"></a><span data-ttu-id="7e66d-138">Comando get-interceptorlist</span><span class="sxs-lookup"><span data-stu-id="7e66d-138">get-interceptorlist Command</span></span>  
 <span data-ttu-id="7e66d-139">**Usage**</span><span class="sxs-lookup"><span data-stu-id="7e66d-139">**Usage**</span></span>  
  
 <span data-ttu-id="7e66d-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-base de datos:\<base de datos\>]**</span><span class="sxs-lookup"><span data-stu-id="7e66d-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="7e66d-141">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="7e66d-141">**Parameters**</span></span>  
  
|<span data-ttu-id="7e66d-142">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7e66d-142">Parameter</span></span>|<span data-ttu-id="7e66d-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e66d-143">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e66d-144">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="7e66d-144">Server:\<server\></span></span>|<span data-ttu-id="7e66d-145">Opcional: El nombre del servidor desde el que se va a devolver una lista de los interceptores implementados.</span><span class="sxs-lookup"><span data-stu-id="7e66d-145">Optional: The name of the server from which to return a list of deployed interceptors.</span></span> <span data-ttu-id="7e66d-146">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="7e66d-146">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="7e66d-147">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="7e66d-147">Database:\<database\></span></span>|<span data-ttu-id="7e66d-148">Opcional: El nombre de la base de datos de importación principal de BAM desde el que se va a recuperar los interceptores implementados.</span><span class="sxs-lookup"><span data-stu-id="7e66d-148">Optional: The name of the BAM Primary Import database from which to retrieve the deployed interceptors.</span></span>|  
  
 <span data-ttu-id="7e66d-149">Este comando devuelve una lista de actividades (y de sus orígenes de eventos asociados) para las que se encuentra habilitada la interceptación.</span><span class="sxs-lookup"><span data-stu-id="7e66d-149">This command returns a list of the activities, and their associated event sources, for which interception is enabled.</span></span>  
  
 <span data-ttu-id="7e66d-150">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="7e66d-150">**Example**</span></span>  
  
```  
bm.exe get-interceptorlist   
```  
  
## <a name="get-interceptor-command"></a><span data-ttu-id="7e66d-151">Comando get-interceptor</span><span class="sxs-lookup"><span data-stu-id="7e66d-151">get-interceptor Command</span></span>  
 <span data-ttu-id="7e66d-152">**Usage**</span><span class="sxs-lookup"><span data-stu-id="7e66d-152">**Usage**</span></span>  
  
 <span data-ttu-id="7e66d-153">**bm.exe get-interceptor [-Server:\<server\>] [-base de datos:\<base de datos\>] - FileName: \<el nombre de archivo de configuración XML\> [-actividad: \<denombredeactividad\>] [-EventSource: \<nombre origen del evento\>]**</span><span class="sxs-lookup"><span data-stu-id="7e66d-153">**bm.exe get-interceptor [-Server:\<server\>] [-Database:\<database\>] -FileName: \<Configuration XML Filename\> [ -Activity: \<Activity Name\>] [-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="7e66d-154">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="7e66d-154">**Parameters**</span></span>  
  
|<span data-ttu-id="7e66d-155">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7e66d-155">Parameter</span></span>|<span data-ttu-id="7e66d-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e66d-156">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e66d-157">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="7e66d-157">Server:\<server\></span></span>|<span data-ttu-id="7e66d-158">Opcional: El nombre del servidor desde el que se va a recuperar el interceptor implementado.</span><span class="sxs-lookup"><span data-stu-id="7e66d-158">Optional: The name of the server from which to retrieve the deployed interceptor.</span></span> <span data-ttu-id="7e66d-159">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="7e66d-159">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="7e66d-160">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="7e66d-160">Database:\<database\></span></span>|<span data-ttu-id="7e66d-161">Opcional: El nombre de la base de datos de importación principal de BAM desde el que se va a recuperar el interceptor implementado.</span><span class="sxs-lookup"><span data-stu-id="7e66d-161">Optional: The name of the BAM Primary Import database from which to retrieve deployed interceptor.</span></span>|  
|<span data-ttu-id="7e66d-162">Nombre de archivo:\<el nombre de archivo de configuración XML\></span><span class="sxs-lookup"><span data-stu-id="7e66d-162">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="7e66d-163">nombre del archivo XML en el que escribir la configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-163">The name of the XML file to which to write the interceptor configuration.</span></span>|  
|<span data-ttu-id="7e66d-164">Actividad:\<nombre de actividad\></span><span class="sxs-lookup"><span data-stu-id="7e66d-164">Activity:\<Activity Name\></span></span>|<span data-ttu-id="7e66d-165">Opcional: Especifica la actividad que se va a devolver el interceptor configurado.</span><span class="sxs-lookup"><span data-stu-id="7e66d-165">Optional: Specifies the activity for which to return the configured interceptor.</span></span> <span data-ttu-id="7e66d-166">Se puede usar junto con el **EventSource** parámetro para especificar la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="7e66d-166">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="7e66d-167">EventSource:\<el nombre del origen de eventos\></span><span class="sxs-lookup"><span data-stu-id="7e66d-167">EventSource:\<Event Source Name\></span></span>|<span data-ttu-id="7e66d-168">Opcional: Especifica el origen del evento que se va a devolver el interceptor configurado.</span><span class="sxs-lookup"><span data-stu-id="7e66d-168">Optional: Specifies the event source for which to return the configured interceptor.</span></span> <span data-ttu-id="7e66d-169">Se puede usar junto con el **actividad** parámetro para especificar la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="7e66d-169">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="7e66d-170">Si no se proporciona ningún nombre de actividad o de origen de evento, el comando devuelve un archivo de configuración válido que contiene las configuraciones del interceptor para todos los orígenes de eventos y todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="7e66d-170">If no activity name or event source name is provided, the command returns a valid configuration file containing the interceptor configurations for all event sources and activities.</span></span>  
  
 <span data-ttu-id="7e66d-171">Si sólo se proporciona un nombre de actividad, el comando devuelve un archivo de configuración de interceptor válido para todos los orígenes de eventos de esa actividad.</span><span class="sxs-lookup"><span data-stu-id="7e66d-171">If only an activity name is provided, the command returns a valid interceptor configuration file for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="7e66d-172">Si sólo se proporciona un nombre de origen de evento, el comando devuelve un archivo de configuración de interceptor válido para ese origen de evento en todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="7e66d-172">If only an event source name is provided, the command returns a valid interceptor configuration file for that event source across all activities.</span></span>  
  
 <span data-ttu-id="7e66d-173">Si se proporcionan tanto un nombre actividad como uno de origen de evento, entonces el comando devuelve un archivo de configuración de interceptor válido para ese origen de evento en esa actividad.</span><span class="sxs-lookup"><span data-stu-id="7e66d-173">If both an activity name and an event source name are provided, then the command returns a valid interceptor configuration file for that event source for that activity.</span></span>  
  
 <span data-ttu-id="7e66d-174">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="7e66d-174">**Examples**</span></span>  
  
```  
bm.exe get-interceptor   
bm.exe get-interceptor  -Activity:ShippingPO  
```  
  
## <a name="remove-interceptor-command"></a><span data-ttu-id="7e66d-175">Comando remove-interceptor</span><span class="sxs-lookup"><span data-stu-id="7e66d-175">remove-interceptor Command</span></span>  
 <span data-ttu-id="7e66d-176">**Usage**</span><span class="sxs-lookup"><span data-stu-id="7e66d-176">**Usage**</span></span>  
  
 <span data-ttu-id="7e66d-177">**bm.exe remove-interceptor [-Server:\<server\>] [-base de datos:\<base de datos\>] [-actividad: \<nombre de la actividad\>] [-EventSource: \<denombredeorigendeeventos\>]**</span><span class="sxs-lookup"><span data-stu-id="7e66d-177">**bm.exe remove-interceptor [-Server:\<server\>] [-Database:\<database\>] [ -Activity: \<Activity Name\>][-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="7e66d-178">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="7e66d-178">**Parameters**</span></span>  
  
|<span data-ttu-id="7e66d-179">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7e66d-179">Parameter</span></span>|<span data-ttu-id="7e66d-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e66d-180">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e66d-181">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="7e66d-181">Server:\<server\></span></span>|<span data-ttu-id="7e66d-182">Opcional: El nombre del servidor en el que está configurado el interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-182">Optional: The name of the server on which the interceptor is configured.</span></span> <span data-ttu-id="7e66d-183">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="7e66d-183">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="7e66d-184">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="7e66d-184">Database:\<database\></span></span>|<span data-ttu-id="7e66d-185">Opcional: El nombre de la base de datos en el que está configurado el interceptor.</span><span class="sxs-lookup"><span data-stu-id="7e66d-185">Optional: The name of the database on which the interceptor is configured.</span></span>|  
|<span data-ttu-id="7e66d-186">Actividad: \<nombre de actividad\></span><span class="sxs-lookup"><span data-stu-id="7e66d-186">Activity: \<Activity Name\></span></span>|<span data-ttu-id="7e66d-187">Opcional: Especifica la actividad que se va a eliminar el interceptor especificado.</span><span class="sxs-lookup"><span data-stu-id="7e66d-187">Optional: Specifies the activity for which to remove the specified interceptor.</span></span> <span data-ttu-id="7e66d-188">Se puede usar junto con el **EventSource** parámetro para especificar la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="7e66d-188">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="7e66d-189">EventSource: \<el nombre del origen de eventos\></span><span class="sxs-lookup"><span data-stu-id="7e66d-189">EventSource: \<Event Source Name\></span></span>|<span data-ttu-id="7e66d-190">Opcional: Especifica el origen del evento que se va a eliminar el interceptor especificado.</span><span class="sxs-lookup"><span data-stu-id="7e66d-190">Optional: Specifies the event source for which to remove the specified interceptor.</span></span> <span data-ttu-id="7e66d-191">Se puede usar junto con el **actividad** parámetro para especificar la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="7e66d-191">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="7e66d-192">Si sólo se proporciona un nombre de actividad, el comando elimina el interceptor de todos los orígenes de eventos de esa actividad.</span><span class="sxs-lookup"><span data-stu-id="7e66d-192">If only an activity name is provided, the command removes the interceptor for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="7e66d-193">Si sólo se proporciona un nombre de origen de evento, el comando elimina sólo esa porción del origen del evento para esa actividad.</span><span class="sxs-lookup"><span data-stu-id="7e66d-193">If only an event source name is provided, the command removes only that event source portion for all activities.</span></span>  
  
 <span data-ttu-id="7e66d-194">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="7e66d-194">**Example**</span></span>  
  
```  
bm.exe remove-interceptor   
```  
  
## <a name="see-also"></a><span data-ttu-id="7e66d-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e66d-195">See Also</span></span>  
 [<span data-ttu-id="7e66d-196">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="7e66d-196">BAM Management Utility</span></span>](../core/bam-management-utility.md)