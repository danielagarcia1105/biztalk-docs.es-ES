---
title: Resolución de entidades personalizadas (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- pipeline components [custom], examples
- pipeline components [custom], parties
- examples, pipeline components [custom]
- parties, pipeline components [custom]
- parties, custom
ms.assetid: 1f88450f-5fe9-486d-bfb8-fd11181c78b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b88d8126a1d63760888edbcd7691ad4bd76426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238700"
---
# <a name="custom-party-resolution-biztalk-server-sample"></a><span data-ttu-id="b578b-102">Resolución de entidades personalizadas (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b578b-102">Custom Party Resolution (BizTalk Server Sample)</span></span>
<span data-ttu-id="b578b-103">El ejemplo de resolución de entidades personalizadas muestra cómo escribir un componente de canalización personalizada para resolver una entidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="b578b-103">The Custom Party Resolution sample demonstrates how to write a custom pipeline component to resolve a custom party.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b578b-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b578b-104">What This Sample Does</span></span>  
 <span data-ttu-id="b578b-105">El ejemplo de resolución de entidades personalizadas acompaña la tarea mediante la siguiente secuencia de pasos:</span><span class="sxs-lookup"><span data-stu-id="b578b-105">The Custom Party Resolution sample accomplishes its task using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="b578b-106">Se recupera un documento XML de una carpeta.</span><span class="sxs-lookup"><span data-stu-id="b578b-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="b578b-107">La canalización resuelve la entidad.</span><span class="sxs-lookup"><span data-stu-id="b578b-107">The pipeline resolves the party.</span></span>  
  
3.  <span data-ttu-id="b578b-108">El mensaje XML se escribe en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="b578b-108">The XML message is written to a folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b578b-109">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b578b-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="b578b-110">*\<Ejemplos de ruta de acceso >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="b578b-110">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
 <span data-ttu-id="b578b-111">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="b578b-111">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b578b-112">Archivos</span><span class="sxs-lookup"><span data-stu-id="b578b-112">File(s)</span></span>|<span data-ttu-id="b578b-113">Description</span><span class="sxs-lookup"><span data-stu-id="b578b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b578b-114">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="b578b-114">AssemblyInfo.cs</span></span>|<span data-ttu-id="b578b-115">Archivo de origen de C# de información de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b578b-115">Assembly information C# source file.</span></span>|  
|<span data-ttu-id="b578b-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="b578b-116">Cleanup.bat</span></span>|<span data-ttu-id="b578b-117">Archivo por lotes de limpieza.</span><span class="sxs-lookup"><span data-stu-id="b578b-117">Cleanup batch file.</span></span>|  
|<span data-ttu-id="b578b-118">CustomPartyResolution.sln</span><span class="sxs-lookup"><span data-stu-id="b578b-118">CustomPartyResolution.sln</span></span>|<span data-ttu-id="b578b-119">Archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="b578b-119">Solution file.</span></span>|  
|<span data-ttu-id="b578b-120">CustomPartyResolutionBinding.xml</span><span class="sxs-lookup"><span data-stu-id="b578b-120">CustomPartyResolutionBinding.xml</span></span>|<span data-ttu-id="b578b-121">Archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="b578b-121">Binding file.</span></span>|  
|<span data-ttu-id="b578b-122">CustomPartyResolutionPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="b578b-122">CustomPartyResolutionPipeline.btp</span></span>|<span data-ttu-id="b578b-123">Archivo de canalización.</span><span class="sxs-lookup"><span data-stu-id="b578b-123">Pipeline file.</span></span>|  
|<span data-ttu-id="b578b-124">CustomPartyResolutionPipeline.btproj</span><span class="sxs-lookup"><span data-stu-id="b578b-124">CustomPartyResolutionPipeline.btproj</span></span>|<span data-ttu-id="b578b-125">Archivo de proyecto de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="b578b-125">Pipeline project file.</span></span>|  
|<span data-ttu-id="b578b-126">CustomPartyResolutionPipelineComponent.cs</span><span class="sxs-lookup"><span data-stu-id="b578b-126">CustomPartyResolutionPipelineComponent.cs</span></span>|<span data-ttu-id="b578b-127">Código de origen de C# de componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="b578b-127">Pipeline component C# source code.</span></span>|  
|<span data-ttu-id="b578b-128">CustomPartyResolutionPipelineComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="b578b-128">CustomPartyResolutionPipelineComponent.csproj</span></span>|<span data-ttu-id="b578b-129">Archivo de proyecto de Visual Studio de componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="b578b-129">Pipeline component Visual Studio project file.</span></span>|  
|<span data-ttu-id="b578b-130">InboundDocumentSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="b578b-130">InboundDocumentSchema.xsd</span></span>|<span data-ttu-id="b578b-131">Esquema de documento de entrada.</span><span class="sxs-lookup"><span data-stu-id="b578b-131">Inbound document schema.</span></span>|  
|<span data-ttu-id="b578b-132">PartyResolutionStream.cs</span><span class="sxs-lookup"><span data-stu-id="b578b-132">PartyResolutionStream.cs</span></span>|<span data-ttu-id="b578b-133">Código de origen de C# de secuencia de resolución de entidad.</span><span class="sxs-lookup"><span data-stu-id="b578b-133">Party resolution stream C# source code.</span></span>|  
|<span data-ttu-id="b578b-134">RoutingPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="b578b-134">RoutingPropertySchema.xsd</span></span>|<span data-ttu-id="b578b-135">Archivo de esquema de propiedad de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b578b-135">Routing property schema file.</span></span>|  
|<span data-ttu-id="b578b-136">SampleInboundDocumentSchema.xml</span><span class="sxs-lookup"><span data-stu-id="b578b-136">SampleInboundDocumentSchema.xml</span></span>|<span data-ttu-id="b578b-137">Archivo de esquema de documento de entrada.</span><span class="sxs-lookup"><span data-stu-id="b578b-137">Inbound document schema file.</span></span>|  
|<span data-ttu-id="b578b-138">SampleInboundDocumentSchema_Party1.xml</span><span class="sxs-lookup"><span data-stu-id="b578b-138">SampleInboundDocumentSchema_Party1.xml</span></span>|<span data-ttu-id="b578b-139">Instancia de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b578b-139">Sample data instance.</span></span>|  
|<span data-ttu-id="b578b-140">SampleInboundDocumentSchema_Party2.xml</span><span class="sxs-lookup"><span data-stu-id="b578b-140">SampleInboundDocumentSchema_Party2.xml</span></span>|<span data-ttu-id="b578b-141">Instancia de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b578b-141">Sample data instance.</span></span>|  
|<span data-ttu-id="b578b-142">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="b578b-142">Setup.bat</span></span>|<span data-ttu-id="b578b-143">Archivo por lotes de componente de canalización de ejemplo de configuración y de versión de compilación.</span><span class="sxs-lookup"><span data-stu-id="b578b-143">Build and setup sample pipeline component batch file.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="b578b-144">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b578b-144">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a><span data-ttu-id="b578b-145">Para crear e iniciar el ejemplo de resolución de entidades personalizadas</span><span class="sxs-lookup"><span data-stu-id="b578b-145">To build and initialize the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="b578b-146">En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="b578b-146">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="b578b-147">*\<Ejemplos de ruta de acceso >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="b578b-147">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
2.  <span data-ttu-id="b578b-148">Ejecute el archivo Setup.bat que realizará las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b578b-148">Run the file Setup.bat, which will perform the following actions:</span></span>  
  
    -   <span data-ttu-id="b578b-149">Crea los directorios de entrada y salida utilizados en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b578b-149">Creates the input and output directories used in the sample.</span></span>  
  
    -   <span data-ttu-id="b578b-150">Genera un archivo de clave nuevo.</span><span class="sxs-lookup"><span data-stu-id="b578b-150">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="b578b-151">Genera e implementa el componente de canalización de resolución de entidades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b578b-151">Builds and deploys the Custom Party Resolution pipeline component.</span></span>  
  
    -   <span data-ttu-id="b578b-152">Copia el componente de canalización generado para el  *\<ruta de acceso de instalación >* directorio \Pipeline Components.</span><span class="sxs-lookup"><span data-stu-id="b578b-152">Copies the built pipeline component to the *\<Installation Path>* \Pipeline Components directory.</span></span>  
  
    -   <span data-ttu-id="b578b-153">Crea los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="b578b-153">Creates the send and receive ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b578b-154">Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b578b-154">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="b578b-155">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b578b-155">Running This Sample</span></span>  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a><span data-ttu-id="b578b-156">Para ejecutar el ejemplo de resolución de entidades personalizadas</span><span class="sxs-lookup"><span data-stu-id="b578b-156">To run the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="b578b-157">Copie el archivo SampleInboundDocumentSchema_Party1.xml o SampleInboundDocumentSchema_Party2.xml en la carpeta \In.</span><span class="sxs-lookup"><span data-stu-id="b578b-157">Copy to file SampleInboundDocumentSchema_Party1.xml or SampleInboundDocumentSchema_Party2.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="b578b-158">Los resultados aparecerán en la carpeta \Out con el nombre de archivo *guid*.xml.</span><span class="sxs-lookup"><span data-stu-id="b578b-158">The results will appear in the \Out folder with the filename *guid*.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b578b-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="b578b-159">See Also</span></span>  
 [<span data-ttu-id="b578b-160">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b578b-160">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)