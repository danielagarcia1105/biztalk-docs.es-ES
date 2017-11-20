---
title: "Implementación de comandos (modelo de observación) de definición de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847dd40bc7d0e8fe9ec225ad8af45d06c92d7b63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a><span data-ttu-id="1b9fc-102">Comandos de implementación de definición de BAM (modelo de observación)</span><span class="sxs-lookup"><span data-stu-id="1b9fc-102">Deployment of BAM Definition (Observation Model) Commands</span></span>
<span data-ttu-id="1b9fc-103">Los comandos de implementación de la utilidad de administración de BAM le permiten aplicar, modificar y quitar definiciones.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-103">The BAM management utility deployment commands allow you to apply, modify, and remove definitions.</span></span>  
  
-   <span data-ttu-id="1b9fc-104">implementar-all: implementa una definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-104">deploy-all: Deploys a BAM definition.</span></span>  
  
-   <span data-ttu-id="1b9fc-105">Update-all: actualiza una definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-105">update-all: Updates a BAM definition.</span></span>  
  
-   <span data-ttu-id="1b9fc-106">Remove-all: quita una definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-106">remove-all: Removes a BAM definition.</span></span>  
  
-   <span data-ttu-id="1b9fc-107">Update-livedataworkbook: actualiza la información de conexión de base de datos en un libro de datos en directo.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-107">update-livedataworkbook: Updates the database connection information in a live data workbook.</span></span>  
  
-   <span data-ttu-id="1b9fc-108">Regenerate-livedataworkbook: vuelve a generar el libro de datos activos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-108">regenerate-livedataworkbook: Regenerates the live data workbook on the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b9fc-109">Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-109">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="1b9fc-110">Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-110">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="1b9fc-111">El conmutador puede utilizarse junto con cualquier comando normal de BM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-111">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b9fc-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-all-command"></a><span data-ttu-id="1b9fc-113">Comando deploy-all</span><span class="sxs-lookup"><span data-stu-id="1b9fc-113">deploy-all Command</span></span>  
 <span data-ttu-id="1b9fc-114">**Uso**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-114">**Usage**</span></span>  
  
 <span data-ttu-id="1b9fc-115">**bm.exe implementar-all - DefinitionFile:\<archivo def > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-115">**bm.exe deploy-all -DefinitionFile:\<def file>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="1b9fc-116">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-116">**Parameters**</span></span>  
  
|<span data-ttu-id="1b9fc-117">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1b9fc-117">Parameter</span></span>|<span data-ttu-id="1b9fc-118">Description</span><span class="sxs-lookup"><span data-stu-id="1b9fc-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b9fc-119">DefinitionFile:\<archivo def ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-119">DefinitionFile:\<def file></span></span>|<span data-ttu-id="1b9fc-120">Ruta y nombre del archivo que contiene las definiciones que se van a implementar.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-120">The path and name of the file containing the definitions to deploy.</span></span>|  
|<span data-ttu-id="1b9fc-121">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-121">Server:\<server></span></span>|<span data-ttu-id="1b9fc-122">Opcional: El nombre del servidor que se va a implementar las definiciones.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-122">Optional: The name of the server to which to deploy the definitions.</span></span> <span data-ttu-id="1b9fc-123">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="1b9fc-124">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="1b9fc-125">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-125">Database:\<database></span></span>|<span data-ttu-id="1b9fc-126">Opcional: El nombre de la base de datos que se va a implementar las definiciones.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-126">Optional: The name of the database to which to deploy the definitions.</span></span> <span data-ttu-id="1b9fc-127">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="1b9fc-128">Implementa todos los artefactos desde el archivo XML especificado de definición de BAM al servidor y a la base de datos especificados.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-128">Deploys all artifacts from the specified BAM definition XML file to the specified server and database.</span></span> <span data-ttu-id="1b9fc-129">El archivo puede ser un archivo de texto que contenga el XML de definición de BAM o un libro de Excel de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-129">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="1b9fc-130">El archivo de definición debe incluir sólo artefactos nuevos.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-130">The definition file must include only new artifacts.</span></span> <span data-ttu-id="1b9fc-131">Si el archivo contiene artefactos que ya se han implementado, la implementación no funcionará e informará de un error.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-131">If the file contains artifacts that have already been deployed, the deployment will fail and report an error.</span></span>  
  
 <span data-ttu-id="1b9fc-132">**Consideraciones para implementar las definiciones de BAM**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-132">**Considerations for deploying BAM definitions**</span></span>  
  
 <span data-ttu-id="1b9fc-133">Cuando implementa suscripciones de alerta, los Id. de usuario de los suscriptores se deben especificar en formato dominio\usuario.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-133">When deploying alert subscriptions, user IDs of the subscribers must be specified in a domain\user format.</span></span>  
  
 <span data-ttu-id="1b9fc-134">El servicio de coordinador de transacción distribuida debe ejecutarse en el equipo en el que el **all implementar** se emite el comando.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-134">The distributed transaction coordinator (DTC) service must be running on the computer on which the **deploy-all** command is issued.</span></span>  
  
 <span data-ttu-id="1b9fc-135">Cuando implementa una definición, la utilidad de administración de BAM sólo admite 14 niveles de dimensión en la vista Agregación en tiempo real (ATR).</span><span class="sxs-lookup"><span data-stu-id="1b9fc-135">When deploying a definition the BAM Management utility only supports 14 dimension levels in Real-Time Aggregation (RTA) view.</span></span> <span data-ttu-id="1b9fc-136">Implementar niveles adicionales da genera errores de implementación.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-136">Deploying additional levels returns a Deployment failed error.</span></span>  
  
 <span data-ttu-id="1b9fc-137">Si define varias vistas que utilizan diferentes configuraciones de idioma e implementan su solución en un servidor que utiliza un lenguaje único, las vistas no se podrán implementar.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-137">If you define multiple views that use different language settings and deploy your solution to a server that uses a single language, the views will be undeployable.</span></span> <span data-ttu-id="1b9fc-138">Este escenario sólo se admite en caso de que no tenga agregaciones programadas que requieran OLAP como parte de la definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-138">This scenario is supported only in a case where you don't have scheduled aggregations that require OLAP as part of the BAM definition.</span></span>  
  
 <span data-ttu-id="1b9fc-139">La utilidad de administración de BAM le limita a 49 vistas de actividad implementada cuando se habilitan las alertas BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-139">The BAM management utility limits you to 49 deployed activity views when BAM Alerts are enabled.</span></span> <span data-ttu-id="1b9fc-140">El número de vistas de actividad se calcula como el sumatorio de 1 a N de la vista (n) multiplicado por el número de actividades primarias.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-140">The number of activity views is calculated as the Summation 1..N of View(n) multiplied by the number of parent activities.</span></span>  <span data-ttu-id="1b9fc-141">Por ejemplo, si implementa una vista que se esté basada en dos actividades, obtiene dos vistas de actividad.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-141">For example, if you deploy a view that is based on two activities, you get two activity views.</span></span>  <span data-ttu-id="1b9fc-142">Si implementa dos vistas, una que abarque dos actividades y otra que esté basada en una actividad única, tiene 3 vistas de actividad.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-142">If you deploy two views, one of which spans two activities and the other based on a single activity, you have 3 activity views.</span></span>  
  
 <span data-ttu-id="1b9fc-143">La utilidad de administración de BAM bloquea la implementación de las definiciones de BAM, que tienen varios informes de tabla dinámica que se definen en la misma combinación de nombre del cubo y de ATR.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-143">The BAM Management utility blocks deployment of BAM definitions which have multiple PivotTable reports which are defined on the same RTA and cube name combination.</span></span> <span data-ttu-id="1b9fc-144">Bm.exe finalizará la implementación y mostrará el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b9fc-144">Bm.exe will terminate the deployment and return the following error:</span></span>  
  
 <span data-ttu-id="1b9fc-145">Implementando vista... ERROR: Error en la implementación de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-145">Deploying View... ERROR: The BAM deployment failed.</span></span>  
  
 <span data-ttu-id="1b9fc-146">Sólo una vista de tabla dinámica puede definirse en una ATR y un cubo dados.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-146">Only one PivotTable view can be defined on a given RTA and cube.</span></span>  
  
 <span data-ttu-id="1b9fc-147">La lista siguiente de nombres se reserva y generará un error al implementar la definición:</span><span class="sxs-lookup"><span data-stu-id="1b9fc-147">The following list of names are reserved and will cause the definition deployment to fail:</span></span>  
  
-   <span data-ttu-id="1b9fc-148">RecordID</span><span class="sxs-lookup"><span data-stu-id="1b9fc-148">RecordID</span></span>  
  
-   <span data-ttu-id="1b9fc-149">ActivityID</span><span class="sxs-lookup"><span data-stu-id="1b9fc-149">ActivityID</span></span>  
  
-   <span data-ttu-id="1b9fc-150">IsVisible</span><span class="sxs-lookup"><span data-stu-id="1b9fc-150">IsVisible</span></span>  
  
-   <span data-ttu-id="1b9fc-151">IsComplete</span><span class="sxs-lookup"><span data-stu-id="1b9fc-151">IsComplete</span></span>  
  
-   <span data-ttu-id="1b9fc-152">LastModified</span><span class="sxs-lookup"><span data-stu-id="1b9fc-152">LastModified</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b9fc-153">Si bm.exe encuentra un error durante la implementación, la implementación finaliza y se deshacen los cambios en las vistas y en las actividades.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-153">If bm.exe encounters an error during the deployment, the deployment is terminated and changes to the views and activities are rolled back.</span></span> <span data-ttu-id="1b9fc-154">Los cambios a cubo OLAP no se deshacen ya que OLAP no admite implementación transaccional.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-154">Changes to OLAP cubes are not rolled back since OLAP does not support transactional deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b9fc-155">Las definiciones de BAM creadas en un equipo que utiliza una configuración regional no se pueden implementar en un equipo configurado con una configuración regional diferente.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-155">BAM definitions created on a computer using one locale setting cannot be deployed to a computer configured with a different locale setting.</span></span> <span data-ttu-id="1b9fc-156">Por ejemplo, una definición de BAM generada con una versión de idioma inglés de Microsoft Excel en un equipo configurado con una configuración regional en inglés no se puede implementar en un equipo configurado en japonés que utiliza la configuración regional en japonés.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-156">For example, a BAM definition generated using an English language version of Microsoft Excel on a computer configured with a EN locale setting cannot be deployed on a computer configured for Japanese using a JA locale setting.</span></span>  
  
 <span data-ttu-id="1b9fc-157">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-157">**Examples**</span></span>  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a><span data-ttu-id="1b9fc-158">Comando update-all</span><span class="sxs-lookup"><span data-stu-id="1b9fc-158">update-all Command</span></span>  
 <span data-ttu-id="1b9fc-159">**Uso**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-159">**Usage**</span></span>  
  
 <span data-ttu-id="1b9fc-160">**bm.exe update-all - DefinitionFile:\<archivo def > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-160">**bm.exe update-all -DefinitionFile:\<def file>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="1b9fc-161">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-161">**Parameters**</span></span>  
  
|<span data-ttu-id="1b9fc-162">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1b9fc-162">Parameter</span></span>|<span data-ttu-id="1b9fc-163">Description</span><span class="sxs-lookup"><span data-stu-id="1b9fc-163">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b9fc-164">DefinitionFile:\<archivo def ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-164">DefinitionFile:\<def file></span></span>|<span data-ttu-id="1b9fc-165">Ruta y nombre del archivo que contiene las definiciones desde el que se va a realizar la actualización.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-165">The path and name of the file containing the definitions from which to perform the update.</span></span>|  
|<span data-ttu-id="1b9fc-166">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-166">Server:\<server></span></span>|<span data-ttu-id="1b9fc-167">Opcional: El nombre del servidor que se va a implementar las actualizaciones de definiciones.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-167">Optional: The name of the server to which to deploy the definition updates.</span></span> <span data-ttu-id="1b9fc-168">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-168">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="1b9fc-169">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-169">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="1b9fc-170">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-170">Database:\<database></span></span>|<span data-ttu-id="1b9fc-171">Opcional: El nombre de la base de datos que se va a implementar las actualizaciones de definiciones.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-171">Optional: The name of the database to which to deploy the definition updates.</span></span> <span data-ttu-id="1b9fc-172">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-172">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="1b9fc-173">Actualiza ciertos artefactos del XML de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-173">Updates certain artifacts from the BAM definition XML.</span></span> <span data-ttu-id="1b9fc-174">El archivo puede ser un archivo de texto que contenga el XML de definición de BAM o un libro de Excel de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-174">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="1b9fc-175">La actualización no elimina artefactos que no se describen en el archivo actual de definición.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-175">The update does not delete artifacts that are not described in the current definition file.</span></span> <span data-ttu-id="1b9fc-176">Puede agregar puntos nuevos de comprobación a actividades, pero no puede quitar puntos de control de actividades implementadas.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-176">It can add new checkpoints to activities, but cannot drop checkpoints from deployed activities.</span></span> <span data-ttu-id="1b9fc-177">La actualización no puede ni cambiar el nombre de los puntos de control ni modificar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-177">The update can neither rename checkpoints nor change checkpoint properties.</span></span>  
  
 <span data-ttu-id="1b9fc-178">Una vez implementada una actividad, las acciones que puede realizar sobre ella están restringidas.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-178">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="1b9fc-179">Específicamente, no puede eliminar elementos de una actividad a menos que esté dispuesto a que su administrador anule la implementación de toda la actividad de BAM y sus conjuntos de vista y los vuelva a implementar.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-179">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="1b9fc-180">Esto puede provocar una interrupción de la visibilidad y pérdidas de datos a menos que el administrador haga una copia de seguridad de los datos y los restaure.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-180">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b9fc-181">No puede usar este comando para agregar actividades nuevas a una vista existente.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-181">You cannot use this command to add new activities to an existing view.</span></span> <span data-ttu-id="1b9fc-182">Para agregar una vista a una actividad, debe crear una nueva vista que incluya la actividad nueva.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-182">To add a view to an activity you must create a new view that includes the new activity.</span></span> <span data-ttu-id="1b9fc-183">Puede anular la implementación de la vista antigua, pero sea consciente de que perderá su historial de datos OLAP.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-183">You can then undeploy the old view, but be aware that you will then lose your OLAP data history.</span></span>  
  
 <span data-ttu-id="1b9fc-184">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-184">**Examples**</span></span>  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a><span data-ttu-id="1b9fc-185">comando remove-all</span><span class="sxs-lookup"><span data-stu-id="1b9fc-185">remove-all Command</span></span>  
 <span data-ttu-id="1b9fc-186">**Uso**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-186">**Usage**</span></span>  
  
 <span data-ttu-id="1b9fc-187">**bm.exe remove-all DefinitionFile:\<archivo def > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-187">**bm.exe remove-all DefinitionFile:\<def file> [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="1b9fc-188">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-188">**Parameters**</span></span>  
  
|<span data-ttu-id="1b9fc-189">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1b9fc-189">Parameter</span></span>|<span data-ttu-id="1b9fc-190">Description</span><span class="sxs-lookup"><span data-stu-id="1b9fc-190">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b9fc-191">DefinitionFile:\<archivo def ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-191">DefinitionFile:\<def file></span></span>|<span data-ttu-id="1b9fc-192">Ruta y nombre del archivo que contiene las definiciones que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-192">The path and name of the file containing the definitions to remove.</span></span>|  
|<span data-ttu-id="1b9fc-193">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-193">Server:\<server></span></span>|<span data-ttu-id="1b9fc-194">Opcional: El nombre del servidor desde el que se quitarán las definiciones.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-194">Optional: The name of the server from which the definitions will be removed.</span></span> <span data-ttu-id="1b9fc-195">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-195">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="1b9fc-196">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-196">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="1b9fc-197">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-197">Database:\<database></span></span>|<span data-ttu-id="1b9fc-198">Opcional: El nombre de la base de datos desde el que se quitarán las definiciones.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-198">Optional: The name of the database from which the definitions will be removed.</span></span> <span data-ttu-id="1b9fc-199">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-199">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="1b9fc-200">Quita todos los artefactos especificados en el archivo XML de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-200">Removes all artifacts specified in the BAM definition XML file.</span></span> <span data-ttu-id="1b9fc-201">El archivo puede ser un archivo de texto que contenga el XML de definición de BAM o un libro de Excel de BAM.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-201">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="1b9fc-202">La definición de cada artefacto debe coincidir exactamente con la definición original que se utilizó para implementación.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-202">The definition for each artifact must exactly match the original definition that was used for deployment.</span></span>  
  
 <span data-ttu-id="1b9fc-203">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-203">**Examples**</span></span>  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a><span data-ttu-id="1b9fc-204">Comando update-livedataworkbook</span><span class="sxs-lookup"><span data-stu-id="1b9fc-204">update-livedataworkbook Command</span></span>  
 <span data-ttu-id="1b9fc-205">**Uso**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-205">**Usage**</span></span>  
  
 <span data-ttu-id="1b9fc-206">**bm.exe update-livedataworkbook-nombre:\<nombre de archivo de libro de trabajo de datos dinámicos > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-206">**bm.exe update-livedataworkbook -Name:\<livedata workbook file name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="1b9fc-207">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-207">**Parameters**</span></span>  
  
|<span data-ttu-id="1b9fc-208">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1b9fc-208">Parameter</span></span>|<span data-ttu-id="1b9fc-209">Description</span><span class="sxs-lookup"><span data-stu-id="1b9fc-209">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b9fc-210">Nombre:\<libro de trabajo de datos dinámicos ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-210">Name:\<livedata workbook></span></span>|<span data-ttu-id="1b9fc-211">El nombre del libro de trabajo dinámico existente que se debe actualizar.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-211">The name of the existing live workbook to update.</span></span>|  
|<span data-ttu-id="1b9fc-212">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-212">Server:\<server></span></span>|<span data-ttu-id="1b9fc-213">Opcional: El nombre del servidor en el que reside el libro.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-213">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="1b9fc-214">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-214">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="1b9fc-215">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-215">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="1b9fc-216">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-216">Database:\<database></span></span>|<span data-ttu-id="1b9fc-217">Opcional: El nombre de la base de datos en el que reside el libro.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-217">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="1b9fc-218">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-218">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="1b9fc-219">Actualiza la información de conexión de la base de datos de importación principal de BAM del libro de trabajo de datos activos de BAM especificado.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-219">Updates the BAM Primary Import database connection information in the specified BAM live data workbook.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b9fc-220">Al configurar una nueva cadena de conexión, debe reiniciar el servicio de TDDS para asegurarse de que éste reconoce el cambio.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-220">When configuring new connection string, you must restart the TDDS service to ensure that the service recognizes the change.</span></span> <span data-ttu-id="1b9fc-221">Para obtener más información sobre el servicio TDDS, vea [procedimientos almacenados en el servicio de Bus de eventos BAM](../core/bam-event-bus-service-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1b9fc-221">For more information on the TDDS service, see [BAM Event Bus Service Stored Procedures](../core/bam-event-bus-service-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="1b9fc-222">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-222">**Examples**</span></span>  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a><span data-ttu-id="1b9fc-223">Comando regenerate-livedataworkbook</span><span class="sxs-lookup"><span data-stu-id="1b9fc-223">regenerate-livedataworkbook Command</span></span>  
 <span data-ttu-id="1b9fc-224">**Uso**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-224">**Usage**</span></span>  
  
 <span data-ttu-id="1b9fc-225">**bm.exe regenerate-livedataworkbook - WorkbookName:\<nombre de archivo de libro de trabajo de datos dinámicos > [-Server:\<servidor >] [-base de datos:\<base de datos >]**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-225">**bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="1b9fc-226">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="1b9fc-226">**Parameters**</span></span>  
  
|<span data-ttu-id="1b9fc-227">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1b9fc-227">Parameter</span></span>|<span data-ttu-id="1b9fc-228">Description</span><span class="sxs-lookup"><span data-stu-id="1b9fc-228">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b9fc-229">WorkbookName:\<nombre de archivo de libro de trabajo de datos dinámicos ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-229">WorkbookName:\<livedata workbook file name></span></span>|<span data-ttu-id="1b9fc-230">Nombre del libro de trabajo que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-230">The name of the workbook to update.</span></span>|  
|<span data-ttu-id="1b9fc-231">Servidor:\<server ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-231">Server:\<server></span></span>|<span data-ttu-id="1b9fc-232">Opcional: El nombre del servidor en el que reside el libro.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-232">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="1b9fc-233">El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-233">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="1b9fc-234">Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-234">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="1b9fc-235">Base de datos:\<base de datos ></span><span class="sxs-lookup"><span data-stu-id="1b9fc-235">Database:\<database></span></span>|<span data-ttu-id="1b9fc-236">Opcional: El nombre de la base de datos en el que reside el libro.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-236">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="1b9fc-237">Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-237">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="1b9fc-238">Genera un libro de trabajo de datos activos de BAM, pero no implementa el libro de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1b9fc-238">Generates a BAM live data workbook but does not deploy the workbook.</span></span>  
  
 <span data-ttu-id="1b9fc-239">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1b9fc-239">Examples</span></span>  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b9fc-240">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b9fc-240">See Also</span></span>  
 [<span data-ttu-id="1b9fc-241">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="1b9fc-241">BAM Management Utility</span></span>](../core/bam-management-utility.md)