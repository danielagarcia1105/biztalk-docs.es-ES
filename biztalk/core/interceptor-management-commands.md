---
title: Comandos de administración de interceptor | Documentos de Microsoft
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
ms.openlocfilehash: 32392c05f47c00a6c62372acbf8d1ba0bed0da6c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974394"
---
# <a name="interceptor-management-commands"></a><span data-ttu-id="590ab-102">Comandos de administración de interceptor</span><span class="sxs-lookup"><span data-stu-id="590ab-102">Interceptor Management Commands</span></span>
<span data-ttu-id="590ab-103">Para el funcionamiento de la nueva funcionalidad del interceptor de BAM, se han agregado cuatro nuevos comandos a la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="590ab-103">To support the new BAM interceptor functionality, four new commands have been added to the BAM Management utility.</span></span>  
  
 <span data-ttu-id="590ab-104">Estos comandos permiten la implementación, recuperación y eliminación de interceptores.</span><span class="sxs-lookup"><span data-stu-id="590ab-104">These commands support the deployment, retrieval, and removal of interceptors.</span></span> <span data-ttu-id="590ab-105">También se incluye un comando para enumerar los interceptores configurados.</span><span class="sxs-lookup"><span data-stu-id="590ab-105">A command is also provided to list the configured interceptors.</span></span>  
  
-   <span data-ttu-id="590ab-106">implementar-interceptor: implementa una configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-106">deploy-interceptor: Deploys an interceptor configuration.</span></span>  
  
-   <span data-ttu-id="590ab-107">Get-interceptorlist: Obtiene una lista de actividades en el que se implementa la interceptación.</span><span class="sxs-lookup"><span data-stu-id="590ab-107">get-interceptorlist: Gets a list of activities on which interception is deployed.</span></span>  
  
-   <span data-ttu-id="590ab-108">Get-interceptor: Obtiene la configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-108">get-interceptor: Gets the interceptor configuration.</span></span>  
  
-   <span data-ttu-id="590ab-109">Remove-interceptor: quita una configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-109">remove-interceptor: Removes an interceptor configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="590ab-110">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="590ab-110">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="590ab-111">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="590ab-111">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="590ab-112">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="590ab-112">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="590ab-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="590ab-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-interceptor-command"></a><span data-ttu-id="590ab-114">Comando deploy-interceptor:</span><span class="sxs-lookup"><span data-stu-id="590ab-114">deploy-interceptor Command</span></span>  
 <span data-ttu-id="590ab-115">**Uso**</span><span class="sxs-lookup"><span data-stu-id="590ab-115">**Usage**</span></span>  
  
 <span data-ttu-id="590ab-116">**bm.exe implementar-interceptor - FileName:\<nombre de archivo de configuración XML\> [-Force: True] [-Server:\<server\>] [-base de datos:\<base de datos\>]**</span><span class="sxs-lookup"><span data-stu-id="590ab-116">**bm.exe deploy-interceptor -FileName:\<Configuration XML Filename\> [-Force:True ] [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="590ab-117">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="590ab-117">**Parameters**</span></span>  
  
|<span data-ttu-id="590ab-118">Parámetro</span><span class="sxs-lookup"><span data-stu-id="590ab-118">Parameter</span></span>|<span data-ttu-id="590ab-119">Description</span><span class="sxs-lookup"><span data-stu-id="590ab-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="590ab-120">Nombre de archivo:\<el nombre de archivo de configuración XML\></span><span class="sxs-lookup"><span data-stu-id="590ab-120">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="590ab-121">nombre del archivo XML que contiene la configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-121">The name of the XML file containing the interceptor configuration.</span></span>|  
|<span data-ttu-id="590ab-122">Force:True</span><span class="sxs-lookup"><span data-stu-id="590ab-122">Force:True</span></span>|<span data-ttu-id="590ab-123">Opcional: Obliga a implementar la configuración del interceptor cuando se detectan conflictos de nombres de origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="590ab-123">Optional: Forces deployment of the interceptor configuration when event source name collisions are detected.</span></span>|  
|<span data-ttu-id="590ab-124">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="590ab-124">Server:\<server\></span></span>|<span data-ttu-id="590ab-125">Opcional: El nombre del servidor en el que se va a implementar el interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-125">Optional: The name of the server on which to deploy the interceptor.</span></span> <span data-ttu-id="590ab-126">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="590ab-126">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="590ab-127">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="590ab-127">Database:\<database\></span></span>|<span data-ttu-id="590ab-128">Opcional: El nombre de la base de datos de importación principal de BAM en el que se va a configurar el interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-128">Optional: The name of the BAM Primary Import database on which to configure the interceptor.</span></span>|  
  
 <span data-ttu-id="590ab-129">Este comando implementa la configuración del interceptor en la base de datos y el servidor especificados.</span><span class="sxs-lookup"><span data-stu-id="590ab-129">This command deploys the interceptor configuration to the specified server and database.</span></span> <span data-ttu-id="590ab-130">Durante la implementación, la utilidad de administración de BAM lleva a cabo las validaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="590ab-130">During deployment, the BAM Management utility performs the following validations:</span></span>  
  
-   <span data-ttu-id="590ab-131">Validación de XSD: la configuración del interceptor se valida con el esquema de configuración de interceptor común.</span><span class="sxs-lookup"><span data-stu-id="590ab-131">XSD validation: The interceptor configuration is validated against the common interceptor configuration schema.</span></span>  
  
-   <span data-ttu-id="590ab-132">Validación de que la actividad existe (está implementada en la base de datos de importación principal) y de que los puntos de control son válidos (existen y tienen un tipo de datos coincidente).</span><span class="sxs-lookup"><span data-stu-id="590ab-132">Validation that the activity exists (is deployed in the Primary Import database) and that checkpoints are valid (exist and have a matching data type).</span></span>  
  
 <span data-ttu-id="590ab-133">Si se detecta un conflicto en el nombre del origen del evento, se genera una advertencia que describe ese conflicto.</span><span class="sxs-lookup"><span data-stu-id="590ab-133">If a collision is detected in the event source name, a warning is thrown describing the collision.</span></span> <span data-ttu-id="590ab-134">En caso de conflicto, la implementación se producirá un error a menos que la **– Force: True** se utiliza el marcador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="590ab-134">In the case of a collision, the deployment will fail unless the **–Force:True** parameter flag is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="590ab-135">El **– Force: True** parámetro potencialmente elimina configuraciones de interceptores que hacen referencia a orígenes de eventos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="590ab-135">The **–Force:True** parameter potentially removes interceptor configurations that reference event sources with the same name.</span></span> <span data-ttu-id="590ab-136">Debe utilizar el **get-interceptor** comando para crear una copia de seguridad de las configuraciones de interceptor existentes antes de usar el **– Force: True** parámetro.</span><span class="sxs-lookup"><span data-stu-id="590ab-136">You should use the **get-interceptor** command to create a backup of existing interceptor configurations before using the **–Force:True** parameter.</span></span>  
  
 <span data-ttu-id="590ab-137">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="590ab-137">**Examples**</span></span>  
  
```  
bm.exe deploy-interceptor  -FileName:myInceptor.xml  
bm.exe deploy-interceptor  -FileName:myInceptor.xml -Force:True  
```  
  
## <a name="get-interceptorlist-command"></a><span data-ttu-id="590ab-138">Comando get-interceptorlist</span><span class="sxs-lookup"><span data-stu-id="590ab-138">get-interceptorlist Command</span></span>  
 <span data-ttu-id="590ab-139">**Uso**</span><span class="sxs-lookup"><span data-stu-id="590ab-139">**Usage**</span></span>  
  
 <span data-ttu-id="590ab-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-base de datos:\<base de datos\>]**</span><span class="sxs-lookup"><span data-stu-id="590ab-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="590ab-141">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="590ab-141">**Parameters**</span></span>  
  
|<span data-ttu-id="590ab-142">Parámetro</span><span class="sxs-lookup"><span data-stu-id="590ab-142">Parameter</span></span>|<span data-ttu-id="590ab-143">Description</span><span class="sxs-lookup"><span data-stu-id="590ab-143">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="590ab-144">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="590ab-144">Server:\<server\></span></span>|<span data-ttu-id="590ab-145">Opcional: El nombre del servidor desde el que se va a devolver una lista de los interceptores implementados.</span><span class="sxs-lookup"><span data-stu-id="590ab-145">Optional: The name of the server from which to return a list of deployed interceptors.</span></span> <span data-ttu-id="590ab-146">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="590ab-146">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="590ab-147">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="590ab-147">Database:\<database\></span></span>|<span data-ttu-id="590ab-148">Opcional: El nombre de la base de datos de importación principal de BAM desde el que se va a recuperar los interceptores implementados.</span><span class="sxs-lookup"><span data-stu-id="590ab-148">Optional: The name of the BAM Primary Import database from which to retrieve the deployed interceptors.</span></span>|  
  
 <span data-ttu-id="590ab-149">Este comando devuelve una lista de actividades (y de sus orígenes de eventos asociados) para las que se encuentra habilitada la interceptación.</span><span class="sxs-lookup"><span data-stu-id="590ab-149">This command returns a list of the activities, and their associated event sources, for which interception is enabled.</span></span>  
  
 <span data-ttu-id="590ab-150">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="590ab-150">**Example**</span></span>  
  
```  
bm.exe get-interceptorlist   
```  
  
## <a name="get-interceptor-command"></a><span data-ttu-id="590ab-151">Comando get-interceptor</span><span class="sxs-lookup"><span data-stu-id="590ab-151">get-interceptor Command</span></span>  
 <span data-ttu-id="590ab-152">**Uso**</span><span class="sxs-lookup"><span data-stu-id="590ab-152">**Usage**</span></span>  
  
 <span data-ttu-id="590ab-153">**bm.exe get-interceptor [-Server:\<server\>] [-base de datos:\<base de datos\>] - FileName: \<nombre de archivo de configuración XML\> [-actividad: \<nombre de la actividad \>] [-EventSource: \<el nombre del origen de evento\>]**</span><span class="sxs-lookup"><span data-stu-id="590ab-153">**bm.exe get-interceptor [-Server:\<server\>] [-Database:\<database\>] -FileName: \<Configuration XML Filename\> [ -Activity: \<Activity Name\>] [-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="590ab-154">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="590ab-154">**Parameters**</span></span>  
  
|<span data-ttu-id="590ab-155">Parámetro</span><span class="sxs-lookup"><span data-stu-id="590ab-155">Parameter</span></span>|<span data-ttu-id="590ab-156">Description</span><span class="sxs-lookup"><span data-stu-id="590ab-156">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="590ab-157">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="590ab-157">Server:\<server\></span></span>|<span data-ttu-id="590ab-158">Opcional: El nombre del servidor desde el que se va a recuperar el interceptor implementado.</span><span class="sxs-lookup"><span data-stu-id="590ab-158">Optional: The name of the server from which to retrieve the deployed interceptor.</span></span> <span data-ttu-id="590ab-159">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="590ab-159">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="590ab-160">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="590ab-160">Database:\<database\></span></span>|<span data-ttu-id="590ab-161">Opcional: El nombre de la base de datos de importación principal de BAM desde el que se va a recuperar el interceptor implementado.</span><span class="sxs-lookup"><span data-stu-id="590ab-161">Optional: The name of the BAM Primary Import database from which to retrieve deployed interceptor.</span></span>|  
|<span data-ttu-id="590ab-162">Nombre de archivo:\<el nombre de archivo de configuración XML\></span><span class="sxs-lookup"><span data-stu-id="590ab-162">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="590ab-163">nombre del archivo XML en el que escribir la configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-163">The name of the XML file to which to write the interceptor configuration.</span></span>|  
|<span data-ttu-id="590ab-164">Actividad:\<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="590ab-164">Activity:\<Activity Name\></span></span>|<span data-ttu-id="590ab-165">Opcional: Especifica la actividad para la que se va a devolver el interceptor configurado.</span><span class="sxs-lookup"><span data-stu-id="590ab-165">Optional: Specifies the activity for which to return the configured interceptor.</span></span> <span data-ttu-id="590ab-166">Puede utilizarse junto con la **EventSource** parámetro para especificar aún más la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="590ab-166">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="590ab-167">EventSource:\<el nombre del origen de eventos\></span><span class="sxs-lookup"><span data-stu-id="590ab-167">EventSource:\<Event Source Name\></span></span>|<span data-ttu-id="590ab-168">Opcional: Especifica el origen del evento para el que se va a devolver el interceptor configurado.</span><span class="sxs-lookup"><span data-stu-id="590ab-168">Optional: Specifies the event source for which to return the configured interceptor.</span></span> <span data-ttu-id="590ab-169">Puede utilizarse junto con la **actividad** parámetro para especificar aún más la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="590ab-169">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="590ab-170">Si no se proporciona ningún nombre de actividad o de origen de evento, el comando devuelve un archivo de configuración válido que contiene las configuraciones del interceptor para todos los orígenes de eventos y todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="590ab-170">If no activity name or event source name is provided, the command returns a valid configuration file containing the interceptor configurations for all event sources and activities.</span></span>  
  
 <span data-ttu-id="590ab-171">Si sólo se proporciona un nombre de actividad, el comando devuelve un archivo de configuración de interceptor válido para todos los orígenes de eventos de esa actividad.</span><span class="sxs-lookup"><span data-stu-id="590ab-171">If only an activity name is provided, the command returns a valid interceptor configuration file for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="590ab-172">Si sólo se proporciona un nombre de origen de evento, el comando devuelve un archivo de configuración de interceptor válido para ese origen de evento en todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="590ab-172">If only an event source name is provided, the command returns a valid interceptor configuration file for that event source across all activities.</span></span>  
  
 <span data-ttu-id="590ab-173">Si se proporcionan tanto un nombre actividad como uno de origen de evento, entonces el comando devuelve un archivo de configuración de interceptor válido para ese origen de evento en esa actividad.</span><span class="sxs-lookup"><span data-stu-id="590ab-173">If both an activity name and an event source name are provided, then the command returns a valid interceptor configuration file for that event source for that activity.</span></span>  
  
 <span data-ttu-id="590ab-174">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="590ab-174">**Examples**</span></span>  
  
```  
bm.exe get-interceptor   
bm.exe get-interceptor  -Activity:ShippingPO  
```  
  
## <a name="remove-interceptor-command"></a><span data-ttu-id="590ab-175">Comando remove-interceptor</span><span class="sxs-lookup"><span data-stu-id="590ab-175">remove-interceptor Command</span></span>  
 <span data-ttu-id="590ab-176">**Uso**</span><span class="sxs-lookup"><span data-stu-id="590ab-176">**Usage**</span></span>  
  
 <span data-ttu-id="590ab-177">**bm.exe remove-interceptor [-Server:\<server\>] [-base de datos:\<base de datos\>] [-actividad: \<nombre de la actividad\>] [-EventSource: \<nombre de origen del evento\>]**</span><span class="sxs-lookup"><span data-stu-id="590ab-177">**bm.exe remove-interceptor [-Server:\<server\>] [-Database:\<database\>] [ -Activity: \<Activity Name\>][-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="590ab-178">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="590ab-178">**Parameters**</span></span>  
  
|<span data-ttu-id="590ab-179">Parámetro</span><span class="sxs-lookup"><span data-stu-id="590ab-179">Parameter</span></span>|<span data-ttu-id="590ab-180">Description</span><span class="sxs-lookup"><span data-stu-id="590ab-180">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="590ab-181">Servidor:\<server\></span><span class="sxs-lookup"><span data-stu-id="590ab-181">Server:\<server\></span></span>|<span data-ttu-id="590ab-182">Opcional: El nombre del servidor en el que está configurado el interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-182">Optional: The name of the server on which the interceptor is configured.</span></span> <span data-ttu-id="590ab-183">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="590ab-183">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="590ab-184">Base de datos:\<base de datos\></span><span class="sxs-lookup"><span data-stu-id="590ab-184">Database:\<database\></span></span>|<span data-ttu-id="590ab-185">Opcional: El nombre de la base de datos en el que está configurado el interceptor.</span><span class="sxs-lookup"><span data-stu-id="590ab-185">Optional: The name of the database on which the interceptor is configured.</span></span>|  
|<span data-ttu-id="590ab-186">Actividad: \<nombre de la actividad\></span><span class="sxs-lookup"><span data-stu-id="590ab-186">Activity: \<Activity Name\></span></span>|<span data-ttu-id="590ab-187">Opcional: Especifica la actividad para la que se va a eliminar el interceptor especificado.</span><span class="sxs-lookup"><span data-stu-id="590ab-187">Optional: Specifies the activity for which to remove the specified interceptor.</span></span> <span data-ttu-id="590ab-188">Puede utilizarse junto con la **EventSource** parámetro para especificar aún más la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="590ab-188">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="590ab-189">EventSource: \<el nombre del origen de eventos\></span><span class="sxs-lookup"><span data-stu-id="590ab-189">EventSource: \<Event Source Name\></span></span>|<span data-ttu-id="590ab-190">Opcional: Especifica el origen del evento para el que se va a eliminar el interceptor especificado.</span><span class="sxs-lookup"><span data-stu-id="590ab-190">Optional: Specifies the event source for which to remove the specified interceptor.</span></span> <span data-ttu-id="590ab-191">Puede utilizarse junto con la **actividad** parámetro para especificar aún más la configuración para devolver.</span><span class="sxs-lookup"><span data-stu-id="590ab-191">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="590ab-192">Si sólo se proporciona un nombre de actividad, el comando elimina el interceptor de todos los orígenes de eventos de esa actividad.</span><span class="sxs-lookup"><span data-stu-id="590ab-192">If only an activity name is provided, the command removes the interceptor for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="590ab-193">Si sólo se proporciona un nombre de origen de evento, el comando elimina sólo esa porción del origen del evento para esa actividad.</span><span class="sxs-lookup"><span data-stu-id="590ab-193">If only an event source name is provided, the command removes only that event source portion for all activities.</span></span>  
  
 <span data-ttu-id="590ab-194">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="590ab-194">**Example**</span></span>  
  
```  
bm.exe remove-interceptor   
```  
  
## <a name="see-also"></a><span data-ttu-id="590ab-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="590ab-195">See Also</span></span>  
 [<span data-ttu-id="590ab-196">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="590ab-196">BAM Management Utility</span></span>](../core/bam-management-utility.md)