---
title: Herramientas de canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline tools, XMLAsm.exe
- pipeline tools, FFDasm.exe
- Pipeline.exe
- FFDasm.exe
- pipeline tools, XMLDasm.exe
- pipeline tools
- XMLAsm.exe
- pipeline tools, DSDump.exe
- FFAsm.exe
- pipeline tools, FFAsm.exe
- pipeline tools, how to
- pipeline tools, about pipeline tools
- pipeline tools, Pipeline.exe
- utilities, pipeline tools
- XMLDasm.exe
ms.assetid: ca4d053a-1473-4d40-8cd0-1ed3a3af988a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c53791906e64930b39b15a89ca20bc269dc8cd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017049"
---
# <a name="pipeline-tools"></a><span data-ttu-id="a5cd4-102">Herramientas de canalización</span><span class="sxs-lookup"><span data-stu-id="a5cd4-102">Pipeline Tools</span></span>
<span data-ttu-id="a5cd4-103">Las herramientas de canalización proporcionadas con el kit de desarrollo de software (SDK) de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permiten comprobar que una canalización está funcionando correctamente sin tener que configurar el entorno de BizTalk Server, por ejemplo, los puertos de recepción y envío.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-103">The pipeline tools supplied with the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK) enable you to verify that a pipeline is functioning correctly without having to configure the BizTalk Server environment, such as send/receive ports.</span></span> <span data-ttu-id="a5cd4-104">Además, puede usar las herramientas de canalización para:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-104">You can also use the pipeline tools to:</span></span>  

-   <span data-ttu-id="a5cd4-105">Depurar los componentes de canalización de terceros fuera del entorno de servidor.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-105">Debug third-party pipeline components outside of the server environment.</span></span>  

-   <span data-ttu-id="a5cd4-106">Diagnosticar mensajes de error del motor de análisis.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-106">Diagnose parsing engine error messages.</span></span>  

-   <span data-ttu-id="a5cd4-107">Experimentar con distintos esquemas sin la carga de compilación, implementación, anulación de la implementación y nueva compilación.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-107">Experiment with different schemas without the burden of compiling, deploying, undeploying, and recompiling.</span></span>  

-   <span data-ttu-id="a5cd4-108">Explorar archivo sin formato y comportamiento de ensamblador y desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-108">Explore flat file and XML assembler/disassembler behavior.</span></span>  

-   <span data-ttu-id="a5cd4-109">Ver salida de desensamblador y descubrir las propiedades de contexto de mensaje que se promocionan, así como sus valores.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-109">View disassembler output and discover which message context properties are promoted and their values.</span></span>  

-   <span data-ttu-id="a5cd4-110">Ejecutar canalizaciones de envío y recepción sin componentes de desensamblador y de ensamblador (por ejemplo, puede ver la salida del decodificador de S/MIME).</span><span class="sxs-lookup"><span data-stu-id="a5cd4-110">Run send/receive pipelines without disassembler and assembler components (for example, you can view the output of the S/MIME decoder).</span></span>  

-   <span data-ttu-id="a5cd4-111">Realizar mediciones de rendimiento precisas solo del componente (en lugar del subsistema de mensajería completo).</span><span class="sxs-lookup"><span data-stu-id="a5cd4-111">Make fine-grained performance measurements of the pipeline alone (rather than the entire messaging subsystem).</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="a5cd4-112">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="a5cd4-112">Location in SDK</span></span>  
 <span data-ttu-id="a5cd4-113">\<*Ruta de instalación*\>\SDK\Utilities\PipelineTools</span><span class="sxs-lookup"><span data-stu-id="a5cd4-113">\<*Installation Path*\>\SDK\Utilities\PipelineTools</span></span>  

 <span data-ttu-id="a5cd4-114">Use herramientas de canalización para ejecutar, depurar y generar perfiles de canalizaciones, además de componentes de canalización (es decir, archivo sin formato y componentes de ensamblador y desensamblador XML).</span><span class="sxs-lookup"><span data-stu-id="a5cd4-114">You use pipeline tools for executing, debugging, and profiling pipelines, and pipeline components (that is, flat file and XML assembler/disassembler components).</span></span>  

## <a name="file-inventory"></a><span data-ttu-id="a5cd4-115">Inventario de archivos</span><span class="sxs-lookup"><span data-stu-id="a5cd4-115">File Inventory</span></span>  
 <span data-ttu-id="a5cd4-116">En la siguiente tabla se enumeran los archivos de herramientas de canalización y se describe el propósito de cada uno.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-116">The following table lists the pipeline tools files and describes their purpose.</span></span>  


|   <span data-ttu-id="a5cd4-117">Archivos</span><span class="sxs-lookup"><span data-stu-id="a5cd4-117">File(s)</span></span>    |                                                                                                                                                                                                                                <span data-ttu-id="a5cd4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5cd4-118">Description</span></span>                                                                                                                                                                                                                                 |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a5cd4-119">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-119">DSDump.exe</span></span>  |                                                <span data-ttu-id="a5cd4-120">Permite volcar la estructura de esquemas de documento, que es una representación ligera en memoria de uno o varios esquemas XSD, con o sin anotaciones de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-120">Enables you to dump the document schema structure, which is an in-memory lightweight representation of the one or more XSD schemas, with or without flat file annotations.</span></span> <span data-ttu-id="a5cd4-121">Esta herramienta puede resultar útil al obtener errores del motor de análisis, por ejemplo, $Root$0$3$2 y cuando sea necesario descodificarlos.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-121">This tool can be helpful when you get parsing engine errors such as $Root$0$3$2 and you need to decode them.</span></span> <span data-ttu-id="a5cd4-122">Los números detrás de $ quieren decir índices o registros de base 0 cuando aparecen en el esquema de documentos.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-122">Numbers after $ mean 0-based index or records as they appear in the document schema.</span></span>                                                |
|  <span data-ttu-id="a5cd4-123">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-123">FFAsm.exe</span></span>   |                                                                                                                                     <span data-ttu-id="a5cd4-124">Ejecuta el componente de ensamblador de archivos sin formato, invocándolo directamente mediante la emulación de un componente de canalización que permite ver cómo serializa o ensambla documentos de XML de usuarios en un documento de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-124">Runs the flat file assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes or assembles a user's XML document(s) into a flat file document.</span></span>                                                                                                                                      |
|  <span data-ttu-id="a5cd4-125">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-125">FFDasm.exe</span></span>  |                                                                                                                               <span data-ttu-id="a5cd4-126">Ejecuta el componente de desensamblador de archivo sin formato, invocándolo directamente mediante la emulación de un componente de canalización de recepción que permite ver cómo analiza o desensambla un documento de archivo sin formato de usuario en uno o varios documentos XML.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-126">Runs the flat file disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses or disassembles a user's flat file document into one or more XML documents.</span></span>                                                                                                                               |
| <span data-ttu-id="a5cd4-127">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-127">Pipeline.exe</span></span> | <span data-ttu-id="a5cd4-128">Ejecuta una canalización de envío o de recepción; acepta uno o varios documentos de entrada y sus partes, esquemas XSD e información relacionada y produce un documento de salida una vez que se ejecute la canalización.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-128">Runs a send or receive pipeline; accepts one or more input documents and their parts, XSD schemas and related information; and produces an output document after the pipeline runs.</span></span> <span data-ttu-id="a5cd4-129">Pipeline.exe no tiene acceso a las bases de datos de BizTalk Server, por lo que las canalizaciones que contienen los componentes de ensamblador y desensamblador de BizTalk Framework que tienen acceso a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos durante la ejecución pueden no ser compatible.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-129">Pipeline.exe does not access BizTalk Server databases, so pipelines containing BizTalk Framework assembler and disassembler components that access [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases during execution may not be supported.</span></span> |
|  <span data-ttu-id="a5cd4-130">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-130">XMLAsm.exe</span></span>  |                                                                                                                                 <span data-ttu-id="a5cd4-131">Ejecuta el componente de ensamblador XML, invocándolo directamente mediante la emulación de una canalización de envío que permite ver cómo serializa, ensambla o protegen con doble cifrado documentos XML de usuario en un documento XML de salida.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-131">Runs the XML assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes, assembles, or envelopes a user's XML document(s) into an output XML document.</span></span>                                                                                                                                  |
| <span data-ttu-id="a5cd4-132">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-132">XMLDasm.exe</span></span>  |                                                                                                                             <span data-ttu-id="a5cd4-133">Ejecuta el componente de desensamblador XML, invocándolo directamente mediante la emulación de una canalización de recepción que permite ver cómo analizar, desensamblar o desproteger un documento XML de usuario con doble cifrado en uno o varios documentos XML.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-133">Runs the XML disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses, disassembles, or un-envelopes a user's XML document into one or more XML documents.</span></span>                                                                                                                              |

## <a name="usage"></a><span data-ttu-id="a5cd4-134">Uso</span><span class="sxs-lookup"><span data-stu-id="a5cd4-134">Usage</span></span>  
 <span data-ttu-id="a5cd4-135">En las secciones que se muestran a continuación se proporciona una descripción más detallada de cada uno de los archivos.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-135">A more detailed description of each file is provided in the sections that follow.</span></span>  

### <a name="dsdumpexe"></a><span data-ttu-id="a5cd4-136">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-136">DSDump.exe</span></span>  
 <span data-ttu-id="a5cd4-137">DSDump.exe permite volcar la estructura de esquemas de documento, que es una representación ligera en memoria de uno o varios esquemas XSD, con o sin anotaciones de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-137">DSDump.exe enables you to dump the document schema structure, which is an in-memory lightweight representation of one or more XSD schemas, with or without flat file annotations.</span></span>  

 <span data-ttu-id="a5cd4-138">DSDump.exe (herramienta de volcado de esquemas de documentos) es compatible con el siguiente parámetro de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-138">DSDump.exe (document schema dump tool) supports the following command-line parameter:</span></span>  

```  
DSDump.exe schemaFileName  
```  

 <span data-ttu-id="a5cd4-139">En caso de que se realice de forma correcta, DSDump imprime el esquema de documentos en la consola.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-139">In case of success, DSDump prints the document schema to the console.</span></span>  

### <a name="ffasmexe"></a><span data-ttu-id="a5cd4-140">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-140">FFAsm.exe</span></span>  
 <span data-ttu-id="a5cd4-141">FFAsm.exe (ensamblador de archivo sin formato) es compatible con los siguientes parámetros de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-141">FFAsm.exe (flat file assembler) supports the following command-line parameters:</span></span>  

```  
usage: ffasm document... [-dm documentMask...]-bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -c ] [ -d ] [ -sb ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -c                 Display assembled FF message on the console  
  -d                 Demote properties  
  -sb                Set body schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Output message encoding name (e.g. windows-1252) or   
                         code page (e.g. 936)  
  -v                 Verbose mode  

file name macros:  
  %MessageID%        FF message identifier (Guid)  
  %MessagePartID%    FF message part identifier (Guid)  

```  

 <span data-ttu-id="a5cd4-142">Por ejemplo, si desea ensamblar tres documentos XML de entrada en un único documento de archivo sin formato con una degradación de encabezado y de propiedad, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-142">For example, if you want to assemble three input XML documents into a single flat file document with a header and property demotion, use the following command:</span></span>  

```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  

### <a name="ffdasmexe"></a><span data-ttu-id="a5cd4-143">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-143">FFDasm.exe</span></span>  
 <span data-ttu-id="a5cd4-144">FFDasm.exe (desensamblador de archivos sin formato) es compatible con los siguientes parámetros de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-144">FFDasm.exe (flat file disassembler) supports the following command-line parameters:</span></span>  

```  
usage: ffdasm document -bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -s ] [ -c ] [ -p ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           Flat File document  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  encoding           Input message body part encoding name (e.g. windows-1252) or code page (e.g., 396)  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 <span data-ttu-id="a5cd4-145">Por ejemplo, si desea desensamblar un documento de archivo sin formato que tiene un encabezado, cuerpo y finalizador, y se muestran los resultados en la consola, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-145">For example, if you want to disassemble a flat file document that has a header, body, and trailer, and display the results to the console, use the following command:</span></span>  

```  
FFDasm.exe file_in.txt –hs myHeaderSchema.xsd –bs myBodySchema.xsd –ts myTrailerSchema.xsd –c  
```  

### <a name="pipelineexe"></a><span data-ttu-id="a5cd4-146">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-146">Pipeline.exe</span></span>  
 <span data-ttu-id="a5cd4-147">Pipeline.exe (herramienta de canalización) es compatible con los siguientes parámetros de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-147">Pipeline.exe (the Pipeline tool) supports the following command-line parameters:</span></span>  

```  
usage: pipeline ( pipeline[.btp] | -pt pipelineTypeName [ -an assemblyName ] ) -d document... [ -part part... ] [ -s schema[.xsd][:namespace.type]... ] [ -proj project[.btproj] ] [ -p ] [ -c ] [ -t ] [ -m filenamemask ] [ -pm partfilenamemask ] [ -en encoding ] [ -v ]  

where:  
  pipeline                Pipeline file name  
  pipelineTypeName     Compiled pipeline assembly qualified type name (e.g.   
"MyPipelines.ReceivePipeline, MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66" or full name (e.g.   
"MyPipelines.ReceivePipeline") if assembly name is   
specified  
  assemblyName         Compiled pipeline assembly file name (e.g.   
MyPipelines.dll) or name (e.g. "MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66")  
  document             Input document(s)  
  part                 Input document's part  
  schema               Schema file name  
  namespace            Schema namespace (as in BizTalk project system)  
  type                 Schema type (as in BizTalk project system)  
  project              BizTalk project file  
  -p                   Display promoted context properties for receive and   
send pipelines, and promote context properties for   
send pipelines  
  -c                      Display output document on the console  
  -t                      Display elapsed time of components execution  
  filenamemask         Output message file name mask (default is   
Message_%MessageID%.out)  
  partfilenamemask     Output part file name mask (default is   
Part_%MessagePartID%.out)  
  encoding             Output message encoding name (e.g. windows-1252)   
or code page (e.g. 936)  
  -v                   Verbous mode  

note:  
You can specify namespace and type for schemas either using namespace.type notation in schema file reference or by using BizTalk project file.  

file name macros:  
  %MessageID%           Message identifier (Guid)  
  %MessagePartID%       Message part identifier (Guid)  
  %MessageNumber%       Message number  

```  

 <span data-ttu-id="a5cd4-148">Por ejemplo, si desea ejecutar una canalización de recepción desde el archivo ReceivePipeline.btp (que tiene componentes de desensamblador XML y de validador de XML) mediante mySchema.xsd y mostrar los resultados en la consola, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-148">For example, if you want to run a receive pipeline from the file ReceivePipeline.btp (which has XML disassembler and XML validator components) using mySchema.xsd and display the results to the console, use the following command:</span></span>  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  

```  

 <span data-ttu-id="a5cd4-149">\- O bien</span><span class="sxs-lookup"><span data-stu-id="a5cd4-149">\- Or -</span></span>  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  

```  

 <span data-ttu-id="a5cd4-150">En el primer ejemplo, un nombre de tipo completo (**MyProject.MySchema**) para el esquema se incluye como un argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-150">In the first example, a qualified type name (**MyProject.MySchema**) for the schema is included as a command-line argument.</span></span> <span data-ttu-id="a5cd4-151">En el segundo ejemplo, el esquema se obtiene del archivo de proyecto de BizTalk especificado.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-151">In the second example, the schema is obtained from the specified BizTalk project file.</span></span>  

 <span data-ttu-id="a5cd4-152">También puede ejecutar canalizaciones de compilado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivos de proyecto, como se muestra en el ejemplo siguiente (la canalización se hace referencia por su nombre de tipo calificado con el ensamblado):</span><span class="sxs-lookup"><span data-stu-id="a5cd4-152">You can also run pipelines from the compiled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project files, as in the following example (the pipeline is referenced by its assembly-qualified type name):</span></span>  

```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 <span data-ttu-id="a5cd4-153">En el siguiente ejemplo, se hace referencia por separado a una canalización mediante el nombre de tipo y el nombre de archivo de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-153">In the following example, a pipeline is referenced by its type name and assembly file name separately:</span></span>  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  

 <span data-ttu-id="a5cd4-154">En el siguiente ejemplo se muestra una canalización a la que se hace referencia mediante el nombre de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-154">The following example shows a pipeline referenced by its assembly name:</span></span>  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 <span data-ttu-id="a5cd4-155">Pipeline.exe se ejecuta con cualquiera de las credenciales usadas para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-155">Pipeline.exe runs with whatever credentials you have used to launch it.</span></span> <span data-ttu-id="a5cd4-156">No utiliza la cuenta es normal [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutarán las instancias de host, por lo que no podrá ejecutar canalizaciones que contienen componentes que requieren acceso de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-156">It does not use the account that normal [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances run under, so you may not be able to run pipelines that contain components that require database access.</span></span> <span data-ttu-id="a5cd4-157">Asegúrese de que ejecuta Pipeline.exe en una cuenta que dispone de todos los privilegios necesarios.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-157">Make sure you run Pipeline.exe under an account that has all the required privileges.</span></span>  

 <span data-ttu-id="a5cd4-158">Solo debe usar Pipeline.exe para comprobar las canalizaciones personalizadas sin componentes personalizados de terceros.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-158">You should only use Pipeline.exe to verify custom pipelines without third-party custom components.</span></span> <span data-ttu-id="a5cd4-159">Si usa pipeline.exe para comprobar una canalización personalizada con componentes personalizados de terceros, Pipeline.exe producirá el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-159">If you use pipeline.exe to verify a custom pipeline with third-party custom components, Pipeline.exe will produce the desired output.</span></span> <span data-ttu-id="a5cd4-160">Sin embargo, si implementa la misma canalización personalizada con componentes personalizados de terceros, use la canalización en un puerto de envío o de recepción y, a continuación, usa Pipeline.exe para enviar un mensaje a la canalización, la canalización producirá errores y el servidor BizTalk Server devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="a5cd4-160">However, if you deploy the same custom pipeline with third-party custom components, use the pipeline in a receive or send port, and then use Pipeline.exe to submit a message to the pipeline, the pipeline will fail and BizTalk Server will return an error.</span></span>  

### <a name="xmlasmexe"></a><span data-ttu-id="a5cd4-161">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-161">XMLAsm.exe</span></span>  
 <span data-ttu-id="a5cd4-162">XMLAsm.exe (herramienta de ensamblador XML) es compatible con los siguientes parámetros de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-162">XMLAsm.exe  (XML Assembler tool) supports the following command-line parameters:</span></span>  

```  
usage: xmlasm document...[-dm documentmask...] -ds documentSchema... [ -es envelopeSchema... ] [ -c ] [ -d ] [ -sd ] [ -m filenamemask ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -c                 Display assembled XML message on the console  
  -d                 Demote properties  
  -sd                Set document schema(s) as design-time property  
  -d                 Demote properties  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 <span data-ttu-id="a5cd4-163">Por ejemplo, si desea ensamblar dos documentos XML de entrada en un único documento XML con un sobre y mostrar los resultados en la consola, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-163">For example, if you want to assemble two input XML documents into a single XML document with an envelope and display the results to the console, use the following command:</span></span>  

```  
FFAsm.exe file_in1.xml file_in2.xml–es myEnvelopeSchema.xsd –ds myBodySchema.xsd –c  
```  

### <a name="xmldasmexe"></a><span data-ttu-id="a5cd4-164">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a5cd4-164">XMLDasm.exe</span></span>  
 <span data-ttu-id="a5cd4-165">XMLDasm.exe es compatible con los siguientes parámetros de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-165">XMLDasm.exe supports the following command-line parameters:</span></span>  

```  
usage: xmldasm document -ds documentSchema... [ -es envelopeSchema... ] [ -s ] [ -c ] [ -p ] [ -sd ] [ -se ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  -sd                Set document schema(s) as design-time property  
  -se                Set envelope schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Input message body part encoding name (e.g., windows-1252) or code page (e.g., 936)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  %MessageNumber%    XML message number  

```  

 <span data-ttu-id="a5cd4-166">Por ejemplo, si desea desensamblar un documento XML con dos sobres anidados y mostrar los resultados en la consola, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5cd4-166">For example, if you want to disassemble an XML document with two nested envelopes and display the results to the console, use the following command:</span></span>  

```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  

## <a name="see-also"></a><span data-ttu-id="a5cd4-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5cd4-167">See Also</span></span>  
 [<span data-ttu-id="a5cd4-168">Utilidades del SDK</span><span class="sxs-lookup"><span data-stu-id="a5cd4-168">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)