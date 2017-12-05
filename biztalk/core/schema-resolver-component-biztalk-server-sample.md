---
title: "Componente de resolución de esquema (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b59a0606b3cb30827078e28a89d0a51f52c430
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="schema-resolver-component-biztalk-server-sample"></a><span data-ttu-id="a005e-102">Componente de resolución de esquema (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="a005e-102">Schema Resolver Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="a005e-103">El ejemplo del componente de resolución de esquema muestra cómo extender la funcionalidad del componente de desensamblador de archivos sin formato de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a005e-103">The Schema Resolver Component sample demonstrates how to extend the functionality of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] flat file disassembler component.</span></span>  
  
 <span data-ttu-id="a005e-104">El componente desensamblador de archivos sin formato normalmente requiere que se defina un esquema de análisis en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a005e-104">The flat file disassembler component normally requires you to define a parsing schema at design time.</span></span> <span data-ttu-id="a005e-105">De modo que si espera recibir distintos documentos de archivos sin formato en la misma ubicación de recepción, incluiría varios desensambladores de archivos sin formato en la canalización de recepción, uno por cada esquema.</span><span class="sxs-lookup"><span data-stu-id="a005e-105">So if you expect to receive different flat file documents on the same receive location, you typically include several flat file disassemblers in the receive pipeline, one for each schema.</span></span> <span data-ttu-id="a005e-106">En el tiempo de ejecución, el componente del desensamblador correcto se seleccione mediante un mecanismo de búsqueda de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="a005e-106">At run time, the correct disassembler component is selected using a pipeline probing mechanism.</span></span> <span data-ttu-id="a005e-107">Sin embargo, este enfoque resulta caro si tiene varios esquemas de archivos sin formato porque la búsqueda de cada componente de desensamblador correspondiente disminuye el rendimiento de la canalización.</span><span class="sxs-lookup"><span data-stu-id="a005e-107">However, this approach is expensive if you have many flat file schemas because probing for every corresponding disassembler component degrades pipeline performance.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="a005e-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a005e-108">What This Sample Does</span></span>  
 <span data-ttu-id="a005e-109">El componente de resolución de esquema muestra un método alternativo de seleccionar el esquema del componente de desensamblador de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="a005e-109">The Schema Resolver component demonstrates an alternative method of selecting the schema for a flat file disassembler.</span></span> <span data-ttu-id="a005e-110">En este ejemplo, se definen cuatro esquemas y los dos primeros caracteres de un mensaje de cada esquema son únicos.</span><span class="sxs-lookup"><span data-stu-id="a005e-110">In this sample, four schemas are defined and the first two characters of a message for each schema are unique.</span></span> <span data-ttu-id="a005e-111">Se define una asignación entre entre los dos primeros caracteres únicos y el esquema correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a005e-111">A mapping is defined between the unique first two characters and the corresponding schema.</span></span> <span data-ttu-id="a005e-112">Cuando el mensaje de entrada se entrega al componente de resolución de esquema, lee los dos primeros caracteres, determina qué esquema debe utilizarse para el documento correspondiente, guarda la información del esquema en el contexto del mensaje y, a continuación, llama al componente desensamblador de archivos sin formato estándar.</span><span class="sxs-lookup"><span data-stu-id="a005e-112">When the input message is given to the Schema Resolver component, it reads the first two characters, determines which schema to use for the corresponding document, saves the schema information on the message context, and then calls into the standard flat file disassembler component.</span></span> <span data-ttu-id="a005e-113">El componente desensamblador de archivos sin formato estándar lee la información del esquema desde el contexto del mensaje y utiliza ese esquema para analizar el documento.</span><span class="sxs-lookup"><span data-stu-id="a005e-113">The standard flat file disassembler component reads the schema information from the message context and uses that schema to parse the document.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="a005e-114">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a005e-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="a005e-115">*\<Ejemplos de ruta de acceso\>*\Pipelines\SchemaResolverComponent\\</span><span class="sxs-lookup"><span data-stu-id="a005e-115">*\<Samples Path\>*\Pipelines\SchemaResolverComponent\\</span></span>  
  
 <span data-ttu-id="a005e-116">En la siguiente tabla se incluyen los archivos usados en este ejemplo y se describe el propósito de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="a005e-116">The following table shows the files used in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="a005e-117">Archivos</span><span class="sxs-lookup"><span data-stu-id="a005e-117">File(s)</span></span>|<span data-ttu-id="a005e-118">Description</span><span class="sxs-lookup"><span data-stu-id="a005e-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a005e-119">SchemaResolverSample.sln</span><span class="sxs-lookup"><span data-stu-id="a005e-119">SchemaResolverSample.sln</span></span>|<span data-ttu-id="a005e-120">Solución para el proyecto de BizTalk que ejercita el componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="a005e-120">Solution for the BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="a005e-121">SchemaResolverSample.btproj</span><span class="sxs-lookup"><span data-stu-id="a005e-121">SchemaResolverSample.btproj</span></span>|<span data-ttu-id="a005e-122">El proyecto de BizTalk que ejercita el componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="a005e-122">BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="a005e-123">SchemaResolverRP.btp</span><span class="sxs-lookup"><span data-stu-id="a005e-123">SchemaResolverRP.btp</span></span>|<span data-ttu-id="a005e-124">Canalización de recepción que contiene el componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="a005e-124">Receive pipeline that contains the custom component.</span></span>|  
|<span data-ttu-id="a005e-125">PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="a005e-125">PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd</span></span>|<span data-ttu-id="a005e-126">Esquemas de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="a005e-126">Flat file schemas.</span></span>|  
|<span data-ttu-id="a005e-127">POInstance.txt, PRInstance.txt, SOInstance.txt, SRInstance.txt</span><span class="sxs-lookup"><span data-stu-id="a005e-127">POInstance.txt, PRInstance.txt, SOInstance.txt, SRInstance.txt</span></span>|<span data-ttu-id="a005e-128">Instancias de documentos de archivos sin formato correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a005e-128">Corresponding flat file document instances.</span></span>|  
|<span data-ttu-id="a005e-129">SchemaResolverFlatFileDasm.sln</span><span class="sxs-lookup"><span data-stu-id="a005e-129">SchemaResolverFlatFileDasm.sln</span></span>|<span data-ttu-id="a005e-130">Solución para la implementación del componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="a005e-130">Solution for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="a005e-131">SchemaResolverFlatFileDasm.csproj</span><span class="sxs-lookup"><span data-stu-id="a005e-131">SchemaResolverFlatFileDasm.csproj</span></span>|<span data-ttu-id="a005e-132">Proyecto C# para la implementación del componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="a005e-132">C# project for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="a005e-133">SchemaResolverFlatFileDasmComp.cs</span><span class="sxs-lookup"><span data-stu-id="a005e-133">SchemaResolverFlatFileDasmComp.cs</span></span>|<span data-ttu-id="a005e-134">Implementación del componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="a005e-134">Implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="a005e-135">SeekableReadOnlyStream.cs</span><span class="sxs-lookup"><span data-stu-id="a005e-135">SeekableReadOnlyStream.cs</span></span>|<span data-ttu-id="a005e-136">Implementación de la secuencia de sólo lectura en la que se pueden efectuar búsquedas usada por el componente.</span><span class="sxs-lookup"><span data-stu-id="a005e-136">Implementation of the seekable read-only stream used by component.</span></span>|  
|<span data-ttu-id="a005e-137">VirtualStream.cs</span><span class="sxs-lookup"><span data-stu-id="a005e-137">VirtualStream.cs</span></span>|<span data-ttu-id="a005e-138">Implementación de la secuencia virtual usada por el componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="a005e-138">Implementation of the virtual stream used by pipeline component.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="a005e-139">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a005e-139">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="a005e-140">Utilice el siguiente procedimiento para crear e inicializar el ejemplo del componente de resolución de esquema.</span><span class="sxs-lookup"><span data-stu-id="a005e-140">Use the following procedure to build and initialize the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="a005e-141">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a005e-141">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="a005e-142">En una ventana de comandos, cambie el directorio (cd) a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="a005e-142">In a command window, change directory (cd) to the following folder:</span></span>  
  
     <span data-ttu-id="a005e-143">*\<Ejemplos de ruta de acceso\>*\Pipelines\SchemaResolverComponent</span><span class="sxs-lookup"><span data-stu-id="a005e-143">*\<Samples Path\>*\Pipelines\SchemaResolverComponent</span></span>  
  
2.  <span data-ttu-id="a005e-144">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a005e-144">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="a005e-145">Genera el componente.</span><span class="sxs-lookup"><span data-stu-id="a005e-145">Builds the component.</span></span>  
  
    -   <span data-ttu-id="a005e-146">Copia el ensamblado del componente en la carpeta BizTalk \Componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="a005e-146">Copies the component assembly into the BizTalk \Pipeline components folder.</span></span>  
  
    -   <span data-ttu-id="a005e-147">Crea e implementa el proyecto de BizTalk de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a005e-147">Builds and deploys the sample BizTalk project.</span></span>  
  
    -   <span data-ttu-id="a005e-148">Configura la ubicación de recepción y el puerto de envío, y los inicia.</span><span class="sxs-lookup"><span data-stu-id="a005e-148">Configures the receive location and send port, and starts them.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a005e-149">Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a005e-149">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="a005e-150">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a005e-150">Running This Sample</span></span>  
 <span data-ttu-id="a005e-151">Utilice el siguiente procedimiento para ejecutar el ejemplo del componente de resolución de esquema.</span><span class="sxs-lookup"><span data-stu-id="a005e-151">Use the following procedure to run the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="a005e-152">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a005e-152">To run this sample</span></span>  
  
1.  <span data-ttu-id="a005e-153">Coloque los archivos archivos POInstance.txt, PRInstance.txt, SOInstance.txt y SRInstance.txt en la ubicación de recepción \< *ruta de acceso de instalación*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In</span><span class="sxs-lookup"><span data-stu-id="a005e-153">Drop the POInstance.txt, PRInstance.txt, SOInstance.txt, and SRInstance.txt files into the receive location \<*Installation Path*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In</span></span>  
  
2.  <span data-ttu-id="a005e-154">Observe los cuatro archivos .xml escritos en la \<Installdir\>carpeta \SDK\Samples\Pipelines\SchemaResolverComponent\Out.</span><span class="sxs-lookup"><span data-stu-id="a005e-154">Observe the four .xml files written to the \<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a005e-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="a005e-155">See Also</span></span>  
 [<span data-ttu-id="a005e-156">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="a005e-156">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)