---
title: RemoveResource (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95b636083542bb1291cd10881bd74ca9d41c15b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976997"
---
# <a name="removeresource-command"></a><span data-ttu-id="f3b12-102">RemoveResource (comando)</span><span class="sxs-lookup"><span data-stu-id="f3b12-102">RemoveResource Command</span></span>
<span data-ttu-id="f3b12-103">Quita (elimina) un artefacto de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f3b12-103">Removes (deletes) an artifact from the BizTalk Management database.</span></span> <span data-ttu-id="f3b12-104">Ejecutar este comando no quita el artefacto de la caché de ensamblados global (GAC), del sistema de archivos, del almacén de certificados, de Internet Information Services o del Registro de Windows si existe en cualquiera de estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="f3b12-104">Running this command does not remove the artifact from the global assembly cache (GAC), file system, certificate store, Internet Information Services, or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="f3b12-105">No quita una definición de BAM de la base de datos de importación principal de BAM ni directivas de la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="f3b12-105">It does not remove a BAM definition from the BAM Primary Import database nor does it remove policies from the Rule Engine database.</span></span> <span data-ttu-id="f3b12-106">Si ejecuta este comando para quitar un archivo de enlace, los enlaces no se modificarán. Solo se quita el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f3b12-106">If you run this command to remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
 <span data-ttu-id="f3b12-107">Puede utilizar este comando para quitar los tipos de artefactos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3b12-107">You can use this command to remove the following artifact types:</span></span>  
  
- <span data-ttu-id="f3b12-108">Ensamblado .NET(System.BizTalk:Assembly)</span><span class="sxs-lookup"><span data-stu-id="f3b12-108">.NET assembly (System.BizTalk:Assembly)</span></span>  
  
- <span data-ttu-id="f3b12-109">Definición de BAM (System.BizTalk:Bam)</span><span class="sxs-lookup"><span data-stu-id="f3b12-109">BAM definition (System.BizTalk:Bam)</span></span>  
  
- <span data-ttu-id="f3b12-110">Ensamblado de BizTalk (System.BizTalk:BizTalkAssembly</span><span class="sxs-lookup"><span data-stu-id="f3b12-110">BizTalk assembly (System.BizTalk:BizTalkAssembly</span></span>  
  
- <span data-ttu-id="f3b12-111">Archivo de enlace de BizTalk (System.BizTalk:BizTalkBinding)</span><span class="sxs-lookup"><span data-stu-id="f3b12-111">BizTalk binding file (System.BizTalk:BizTalkBinding)</span></span>  
  
- <span data-ttu-id="f3b12-112">Certificado de seguridad (System.BizTalk:Certificate)</span><span class="sxs-lookup"><span data-stu-id="f3b12-112">Security certificate (System.BizTalk:Certificate)</span></span>  
  
- <span data-ttu-id="f3b12-113">Componente COM (System.BizTalk:Com)</span><span class="sxs-lookup"><span data-stu-id="f3b12-113">COM component (System.BizTalk:Com)</span></span>  
  
- <span data-ttu-id="f3b12-114">Archivo ad hoc (System.BizTalk:File)</span><span class="sxs-lookup"><span data-stu-id="f3b12-114">Ad hoc file (System.BizTalk:File)</span></span>  
  
- <span data-ttu-id="f3b12-115">Secuencia de comandos posterior al procesamiento (System.BizTalk:PostProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="f3b12-115">Postprocessing script (System.BizTalk:PostProcessingScript)</span></span>  
  
- <span data-ttu-id="f3b12-116">Secuencia de comandos previa al procesamiento (System.BizTalk:PreProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="f3b12-116">Preprocessing script (System.BizTalk:PreProcessingScript)</span></span>  
  
- <span data-ttu-id="f3b12-117">Directiva o regla (System.BizTalk:rules)</span><span class="sxs-lookup"><span data-stu-id="f3b12-117">Policy or rule (System.BizTalk:Rules)</span></span>  
  
- <span data-ttu-id="f3b12-118">Directorio virtual (System.BizTalk:WebDirectory)</span><span class="sxs-lookup"><span data-stu-id="f3b12-118">Virtual directory (System.BizTalk:WebDirectory)</span></span>  
  
  <span data-ttu-id="f3b12-119">Se producirá un error en la operación de quitar cuando:</span><span class="sxs-lookup"><span data-stu-id="f3b12-119">The remove operation will fail in the following cases:</span></span>  
  
- <span data-ttu-id="f3b12-120">Intenta quitar un ensamblado de BizTalk del que tiene una referencia otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f3b12-120">You attempt to remove a BizTalk assembly to which another assembly has a reference.</span></span>  
  
- <span data-ttu-id="f3b12-121">Intenta quitar un ensamblado de BizTalk que incluye una canalización que utiliza el puerto de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="f3b12-121">You attempt to remove a BizTalk assembly that includes a pipeline that is used by a send or receive port.</span></span>  
  
- <span data-ttu-id="f3b12-122">Intenta quitar un ensamblado de BizTalk que incluye una asignación que utiliza un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f3b12-122">You attempt to remove a BizTalk assembly that includes a map used by a send port.</span></span>  
  
- <span data-ttu-id="f3b12-123">Intenta quitar un ensamblado de BizTalk que incluye una orquestación que no está en un estado dado de baja o que tiene una instancia suspendida.</span><span class="sxs-lookup"><span data-stu-id="f3b12-123">You attempt to remove a BizTalk assembly that includes an orchestration that is not in an unenlisted state or that has a suspended instance.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f3b12-124">Uso</span><span class="sxs-lookup"><span data-stu-id="f3b12-124">Usage</span></span>  
 <span data-ttu-id="f3b12-125">**/ ApplicationName BTSTask RemoveResource:** *valor* **/Luid:** *valor* [**/Server:**<em>valor</em> ] [**/Database:**<em>valor</em>]</span><span class="sxs-lookup"><span data-stu-id="f3b12-125">**BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="f3b12-126">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3b12-126">Parameters</span></span>  
  
|<span data-ttu-id="f3b12-127">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f3b12-127">Parameter</span></span>|<span data-ttu-id="f3b12-128">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="f3b12-128">Required</span></span>|<span data-ttu-id="f3b12-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3b12-129">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="f3b12-130">**/ ApplicationName** (o **/A**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="f3b12-130">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="f3b12-131">Sí</span><span class="sxs-lookup"><span data-stu-id="f3b12-131">Yes</span></span>|<span data-ttu-id="f3b12-132">Nombre de la aplicación de BizTalk que contiene el artefacto de recurso que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="f3b12-132">Name of the BizTalk application containing the resource artifact to delete.</span></span> <span data-ttu-id="f3b12-133">Si el nombre incluye espacios, debe encerrar entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="f3b12-133">If the name includes spaces, you must enclose it with double quotation marks (").</span></span>|  
|<span data-ttu-id="f3b12-134">**/ Luid** (o **/l**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="f3b12-134">**/Luid** (or **/L**, see Remarks)</span></span>|<span data-ttu-id="f3b12-135">Sí</span><span class="sxs-lookup"><span data-stu-id="f3b12-135">Yes</span></span>|<span data-ttu-id="f3b12-136">Identificador local único (LUID) del artefacto.</span><span class="sxs-lookup"><span data-stu-id="f3b12-136">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="f3b12-137">Puede obtener el LUID mediante el [comando ListApp](../core/listapp-command.md).</span><span class="sxs-lookup"><span data-stu-id="f3b12-137">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
|<span data-ttu-id="f3b12-138">**/ Servidor** (o **/S**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="f3b12-138">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="f3b12-139">no</span><span class="sxs-lookup"><span data-stu-id="f3b12-139">No</span></span>|<span data-ttu-id="f3b12-140">Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.</span><span class="sxs-lookup"><span data-stu-id="f3b12-140">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="f3b12-141">Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="f3b12-141">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="f3b12-142">Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)</span><span class="sxs-lookup"><span data-stu-id="f3b12-142">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="f3b12-143">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="f3b12-143">Examples:</span></span><br /><br /> <span data-ttu-id="f3b12-144">Servidor = MyServer</span><span class="sxs-lookup"><span data-stu-id="f3b12-144">Server=MyServer</span></span><br /><br /> <span data-ttu-id="f3b12-145">Servidor = MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="f3b12-145">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="f3b12-146">Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f3b12-146">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="f3b12-147">**/ Base de datos** (o **/D**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="f3b12-147">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="f3b12-148">no</span><span class="sxs-lookup"><span data-stu-id="f3b12-148">No</span></span>|<span data-ttu-id="f3b12-149">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f3b12-149">Name of the BizTalk Management database.</span></span> <span data-ttu-id="f3b12-150">Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3b12-150">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="f3b12-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3b12-151">Sample</span></span>  
 <span data-ttu-id="f3b12-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, versión = 1.0.0.0, Culture = neutral, PublicKeyToken = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="f3b12-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3b12-153">Notas</span><span class="sxs-lookup"><span data-stu-id="f3b12-153">Remarks</span></span>  
 <span data-ttu-id="f3b12-154">Los parámetros no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f3b12-154">Parameters are not case-sensitive.</span></span> <span data-ttu-id="f3b12-155">No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="f3b12-155">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b12-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3b12-156">See Also</span></span>  
 <span data-ttu-id="f3b12-157">[Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f3b12-157">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="f3b12-158">Cómo quitar un artefacto de una aplicación</span><span class="sxs-lookup"><span data-stu-id="f3b12-158">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)