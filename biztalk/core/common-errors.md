---
title: Errores comunes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c5dfe58f7b31bb5ef461249765d527f78d9264
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009061"
---
# <a name="common-errors"></a><span data-ttu-id="de149-102">Errores comunes</span><span class="sxs-lookup"><span data-stu-id="de149-102">Common Errors</span></span>
<span data-ttu-id="de149-103">En este tema se muestran mensajes de error habituales que pueden aparecer al crear asignaciones usando el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="de149-103">This topic lists out common error messages you may encounter while creating maps using BizTalk Mapper.</span></span>  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a><span data-ttu-id="de149-104">Recibe el evento de error ID 324 al analizar las fechas</span><span class="sxs-lookup"><span data-stu-id="de149-104">You receive error event ID 324 when parsing dates</span></span>  
  
### <a name="problem"></a><span data-ttu-id="de149-105">Problema</span><span class="sxs-lookup"><span data-stu-id="de149-105">Problem</span></span>  
 <span data-ttu-id="de149-106">Cuando se usa la base de datos **Extractor de valor** functoid en una asignación para extraer un campo de fecha, el documento puede producir un error de validación en la definición de documento de salida.</span><span class="sxs-lookup"><span data-stu-id="de149-106">When you use the Database **Value Extractor** functoid in a map to extract a date field, your document may fail validation against the outbound document definition.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="de149-107"> puede registrar un error de validación similar al siguiente en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="de149-107"> may log a validation error similar to the following in the event log:</span></span>  
  
 <span data-ttu-id="de149-108">Origen del evento: Servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="de149-108">Event Source: BizTalk Server</span></span>  
  
 <span data-ttu-id="de149-109">Categoría del evento: Procesamiento de documentos de</span><span class="sxs-lookup"><span data-stu-id="de149-109">Event Category: Document Processing</span></span>  
  
 <span data-ttu-id="de149-110">Id. de evento: 324</span><span class="sxs-lookup"><span data-stu-id="de149-110">Event ID: 324</span></span>  
  
 <span data-ttu-id="de149-111">Descripción:</span><span class="sxs-lookup"><span data-stu-id="de149-111">Description:</span></span>  
  
 <span data-ttu-id="de149-112">Error en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="de149-112">An error occurred in BizTalk Server.</span></span>  
  
 <span data-ttu-id="de149-113">Detalles:</span><span class="sxs-lookup"><span data-stu-id="de149-113">Details:</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="de149-114">El documento XML no pudo validar por el siguiente motivo: Error al analizar ' 10/12/1995 ' como tipo de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="de149-114">The XML document has failed validation for the following reason: Error parsing '10/12/1995' as date datatype.</span></span>  
  
 <span data-ttu-id="de149-115">Id. de cola de suspensión: "{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span><span class="sxs-lookup"><span data-stu-id="de149-115">Suspended Queue ID: "{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span></span>  
  
### <a name="cause"></a><span data-ttu-id="de149-116">Causa</span><span class="sxs-lookup"><span data-stu-id="de149-116">Cause</span></span>  
 <span data-ttu-id="de149-117">El formato de fecha (como se devuelve del origen de datos) no está en formato ISO 8601, que es el formato que XML necesita.</span><span class="sxs-lookup"><span data-stu-id="de149-117">The date format (as it is returned from the data source) is not in ISO 8601 format, which is the format required by XML.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="de149-118">Solución</span><span class="sxs-lookup"><span data-stu-id="de149-118">Resolution</span></span>  
 <span data-ttu-id="de149-119">Para resolver este problema, realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="de149-119">To resolve this issue, do one of the following:</span></span>  
  
- <span data-ttu-id="de149-120">Edite la definición del documento de salida para usar un tipo de datos de cadena en vez de un tipo de datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="de149-120">Edit your outbound document definition to use a string datatype instead of a date datatype.</span></span>  
  
- <span data-ttu-id="de149-121">Crear un personalizado [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)] **Script** functoid que va a convertir el resultado de la base de datos **Extractor de valor** functoid en el formato ISO 8601.</span><span class="sxs-lookup"><span data-stu-id="de149-121">Create a custom [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**Script** functoid that will convert the output of the Database **Value Extractor** functoid into the ISO 8601 format.</span></span>  
  
  <span data-ttu-id="de149-122">Para obtener más información, consulte el artículo de KB [278737](http://support.microsoft.com/kb/278737/en-us).</span><span class="sxs-lookup"><span data-stu-id="de149-122">For more information, see KB article [278737](http://support.microsoft.com/kb/278737/en-us).</span></span>  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a><span data-ttu-id="de149-123">Recibe un error del compilador interno (0xc0000005 en la dirección 53624FD6) al compilar las asignaciones</span><span class="sxs-lookup"><span data-stu-id="de149-123">You receive Internal Compiler Error (0xc0000005 at address 53624FD6) when compiling the maps</span></span>  
  
### <a name="problem"></a><span data-ttu-id="de149-124">Problema</span><span class="sxs-lookup"><span data-stu-id="de149-124">Problem</span></span>  
 <span data-ttu-id="de149-125">Al compilar un único proyecto de BizTalk que consta de esquemas, asignaciones u orquestaciones de gran tamaño, el compilador puede generar un error parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="de149-125">When you compile a single BizTalk project that consists of large schemas, maps, or orchestrations, the compiler may generate an error similar to the following:</span></span>  
  
 <span data-ttu-id="de149-126">Error interno del compilador (0xc0000005 en la dirección 53624FD6): probablemente la causa sea 'CODEGEN'.</span><span class="sxs-lookup"><span data-stu-id="de149-126">Internal Compiler Error (0xc0000005 at address 53624FD6): likely culprit is 'CODEGEN'.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="de149-127">Causa</span><span class="sxs-lookup"><span data-stu-id="de149-127">Cause</span></span>  
 <span data-ttu-id="de149-128">El compilador de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tiene un límite de 16 megabytes en el tamaño total de todas las cadenas en un único proyecto.</span><span class="sxs-lookup"><span data-stu-id="de149-128">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="de149-129">Al compilar proyectos de BizTalk, el compilador serializa esquemas, asignaciones y orquestaciones para crear los ensamblados y, por ello, el tamaño total de todas las cadenas aumenta y puede superar el límite.</span><span class="sxs-lookup"><span data-stu-id="de149-129">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="de149-130">Solución</span><span class="sxs-lookup"><span data-stu-id="de149-130">Resolution</span></span>  
 <span data-ttu-id="de149-131">Para resolver este problema, puede separar esquemas o asignaciones en varios proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="de149-131">To resolve this issue, you can separate schemas or maps into different BizTalk projects.</span></span>  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a><span data-ttu-id="de149-132">Recibe errores sobre el nombre de tipo de un artefacto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="de149-132">You receive errors about the Type Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="de149-133">Problema</span><span class="sxs-lookup"><span data-stu-id="de149-133">Problem</span></span>  
 <span data-ttu-id="de149-134">En un proyecto de BizTalk, cree un mapa con el nombre de archivo **System.btm** o **Microsoft.btm**.</span><span class="sxs-lookup"><span data-stu-id="de149-134">In a BizTalk project, create a map with filename **System.btm** or **Microsoft.btm**.</span></span> <span data-ttu-id="de149-135">Al generar el proyecto, el Asignador de BizTalk genera un error similar a alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="de149-135">When you build the project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="de149-136">“El nombre de tipo ‘SerializableAttribute’ no existe…”</span><span class="sxs-lookup"><span data-stu-id="de149-136">“The typename ‘SerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="de149-137">“El nombre de tipo ‘NonSerializableAttribute’ no existe…”</span><span class="sxs-lookup"><span data-stu-id="de149-137">“The typename ‘NonSerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="de149-138">“El nombre de tipo ‘SerializableAttributeAttribute’ no existe…”</span><span class="sxs-lookup"><span data-stu-id="de149-138">“The typename ‘SerializableAttributeAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="de149-139">“El nombre de tipo ‘XLANs’ no existe…”</span><span class="sxs-lookup"><span data-stu-id="de149-139">“The typename ‘XLANs’ does not exist…”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="de149-140">Causa</span><span class="sxs-lookup"><span data-stu-id="de149-140">Cause</span></span>  
 <span data-ttu-id="de149-141">El **nombre de tipo** en el **propiedades** cuadrícula no debe tener, como los espacios de nombres .NET reservado, **sistema**, **Microsoft**, etcetera.</span><span class="sxs-lookup"><span data-stu-id="de149-141">The **Type Name** in the **Properties** grid should not have any reserved .NET namespaces, such as **System**, **Microsoft**, etc.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="de149-142">Solución</span><span class="sxs-lookup"><span data-stu-id="de149-142">Resolution</span></span>  
 <span data-ttu-id="de149-143">Para resolver este problema, puede seguir cualquiera de estas soluciones:</span><span class="sxs-lookup"><span data-stu-id="de149-143">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="de149-144">Modifique el nombre de la asignación por cualquier cadena que no sea una palabra reservada de .NET.</span><span class="sxs-lookup"><span data-stu-id="de149-144">Modify the name of the map to any string which is not a .NET reserved word.</span></span> <span data-ttu-id="de149-145">De forma predeterminada, el sistema del proyecto de BizTalk crea el **nombre de tipo** desde el nombre del artefacto respectivo.</span><span class="sxs-lookup"><span data-stu-id="de149-145">By default, the BizTalk project system creates the **Type Name** from the name of the respective artifact.</span></span>  
  
     <span data-ttu-id="de149-146">Para p. ej.: crear una nueva asignación con el nombre **Map1.btm** establece la **nombre de tipo** valor de propiedad **Map1**.</span><span class="sxs-lookup"><span data-stu-id="de149-146">For e.g.: Creating a new map with name **Map1.btm** sets the **Type Name** property value to **Map1**.</span></span> <span data-ttu-id="de149-147">Sin embargo, al cambiar el nombre de un BizTalk existente artefacto no cambia el **nombre de tipo**.</span><span class="sxs-lookup"><span data-stu-id="de149-147">However, renaming an existing BizTalk artifact does not change the **Type Name**.</span></span>  
  
-   <span data-ttu-id="de149-148">Asegúrese de que el nombre de archivo de cualquiera de los artefactos del proyecto BizTalk no es un espacio de nombres reservado de .NET.</span><span class="sxs-lookup"><span data-stu-id="de149-148">Ensure the filename of any of the artifacts in the BizTalk project is not a .NET reserved namespace.</span></span>  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a><span data-ttu-id="de149-149">Recibe errores sobre el nombre de archivo de un artefacto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="de149-149">You receive errors about the File Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="de149-150">Problema</span><span class="sxs-lookup"><span data-stu-id="de149-150">Problem</span></span>  
 <span data-ttu-id="de149-151">Al generar un proyecto de BizTalk, el Asignador de BizTalk genera un error similar a alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="de149-151">When you build a BizTalk project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="de149-152">"El archivo \<filename\> tiene valores duplicados para las propiedades de nombre de espacio de nombres y tipo."</span><span class="sxs-lookup"><span data-stu-id="de149-152">“The File \<filename\> has duplicate values for namespace and type name properties.”</span></span>  
  
-   <span data-ttu-id="de149-153">"El espacio de nombres \<nombre\> ya contiene una definición para '_'."</span><span class="sxs-lookup"><span data-stu-id="de149-153">“The namespace \<name\> already contains a definition for ‘_’.”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="de149-154">Causa</span><span class="sxs-lookup"><span data-stu-id="de149-154">Cause</span></span>  
 <span data-ttu-id="de149-155">En el proyecto de BizTalk, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="de149-155">In the BizTalk project, check for the following:</span></span>  
  
-   <span data-ttu-id="de149-156">Varios artefactos tienen el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="de149-156">Multiple artifacts have the same filename.</span></span> <span data-ttu-id="de149-157">Para p. ej., **Map1.xsd** y**Map1.btm**.</span><span class="sxs-lookup"><span data-stu-id="de149-157">For e.g., **Map1.xsd** and**Map1.btm**.</span></span>  
  
-   <span data-ttu-id="de149-158">El nombre de archivo consta únicamente de caracteres especiales (**~**, **!**, **@**, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="de149-158">The filename comprises of only special characters (**~**, **!**, **@**, etc.).</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="de149-159">Solución</span><span class="sxs-lookup"><span data-stu-id="de149-159">Resolution</span></span>  
 <span data-ttu-id="de149-160">Para resolver este problema, puede seguir cualquiera de estas soluciones:</span><span class="sxs-lookup"><span data-stu-id="de149-160">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="de149-161">Cambie el nombre de los archivos.</span><span class="sxs-lookup"><span data-stu-id="de149-161">Rename the files.</span></span> <span data-ttu-id="de149-162">Asegúrese de que los nombres de archivo para todos los artefactos del proyecto de BizTalk son únicos.</span><span class="sxs-lookup"><span data-stu-id="de149-162">Ensure the filenames for all artifacts in the BizTalk project are unique.</span></span>  
  
-   <span data-ttu-id="de149-163">Asegúrese de que los nombres de tipo para todos los artefactos del proyecto de BizTalk son únicos.</span><span class="sxs-lookup"><span data-stu-id="de149-163">Ensure Type Name for all artifacts in the BizTalk project are unique.</span></span>  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a><span data-ttu-id="de149-164">La generación de un proyecto de flujo de trabajo C# con el Asignador de BizTalk muestra una advertencia relacionada con el conflicto de versiones de EnvDTE.dll</span><span class="sxs-lookup"><span data-stu-id="de149-164">Building any C# workflow project with BizTalk Mapper shows a warning regarding version conflict for EnvDTE.dll</span></span>  
  
### <a name="problem"></a><span data-ttu-id="de149-165">Problema</span><span class="sxs-lookup"><span data-stu-id="de149-165">Problem</span></span>  
 <span data-ttu-id="de149-166">La generación de un proyecto de flujo de trabajo C# con una actividad del Asignador de BizTalk muestra la siguiente advertencia relacionada con el conflicto de versiones de EnvDTE.dll</span><span class="sxs-lookup"><span data-stu-id="de149-166">Building any C# workflow project with BizTalk Mapper acitivity always shows the following warning about version conflict for EnvDTE.dll.</span></span>  
  
 <span data-ttu-id="de149-167">No hay forma de resolver el conflicto entre "EnvDTE, Version = 8.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a" y "EnvDTE, Version = 7.0.3300.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a".</span><span class="sxs-lookup"><span data-stu-id="de149-167">No way to resolve conflict between "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" and "EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a".</span></span> <span data-ttu-id="de149-168">Selección arbitraria de "EnvDTE, Version = 8.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a".</span><span class="sxs-lookup"><span data-stu-id="de149-168">Choosing "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" arbitrarily.</span></span>  <span data-ttu-id="de149-169">Considere la reasignación del archivo app.config del ensamblado "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" desde la versión "7.0.3300.0" [] a la versión "8.0.0.0" [C:\Archivos de programa (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] para resolver el conflicto y eliminar la advertencia.</span><span class="sxs-lookup"><span data-stu-id="de149-169">Consider app.config remapping of assembly "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" from Version "7.0.3300.0" [] to Version "8.0.0.0" [C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] to solve conflict and get rid of warning.</span></span> <span data-ttu-id="de149-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): advertencia MSB3247: se encontraron conflictos entre versiones diferentes del mismo ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="de149-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): warning MSB3247: Found conflicts between different versions of the same dependent assembly.</span></span>  
  
 <span data-ttu-id="de149-171">WorkflowConsoleApplication3-> C:\Usuarios\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span><span class="sxs-lookup"><span data-stu-id="de149-171">WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span></span>  
  
### <a name="cause"></a><span data-ttu-id="de149-172">Causa</span><span class="sxs-lookup"><span data-stu-id="de149-172">Cause</span></span>  
 <span data-ttu-id="de149-173">Esto sucede debido al archivo Microsoft.BizTalk.Mapper.OM.dll al que hace referencia la actividad del Asignador.</span><span class="sxs-lookup"><span data-stu-id="de149-173">This happens because of the Microsoft.BizTalk.Mapper.OM.dll which the Mapper activity references.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="de149-174">Solución</span><span class="sxs-lookup"><span data-stu-id="de149-174">Resolution</span></span>  
 <span data-ttu-id="de149-175">Pasar por alto la advertencia.</span><span class="sxs-lookup"><span data-stu-id="de149-175">Ignore the warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de149-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="de149-176">See Also</span></span>  
 [<span data-ttu-id="de149-177">Solución de problemas de mapas</span><span class="sxs-lookup"><span data-stu-id="de149-177">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)