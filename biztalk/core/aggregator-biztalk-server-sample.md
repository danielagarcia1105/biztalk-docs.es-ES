---
title: Agregador (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- pipelines, examples
- orchestrations, messages
- examples, pipelines
- messages, correlating to orchestrations
ms.assetid: eb8121df-4f5b-4f36-8228-4b5ad1abfb4e
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f4d28214a815aca88f214e5efb9cd883e7192
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="aggregator-biztalk-server-sample"></a><span data-ttu-id="901e2-102">Agregación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="901e2-102">Aggregator (BizTalk Server Sample)</span></span>
<span data-ttu-id="901e2-103">La finalidad de este ejemplo consiste en crear una funcionalidad de agregación de mensaje con orquestaciones y canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="901e2-103">The purpose of this sample is to build a message aggregation functionality using orchestration and pipelines.</span></span> <span data-ttu-id="901e2-104">De forma más específica, crearemos una orquestación que:</span><span class="sxs-lookup"><span data-stu-id="901e2-104">Specifically we will build an orchestration that:</span></span>  
  
1.  <span data-ttu-id="901e2-105">Recibe un conjunto de mensajes correlacionados.</span><span class="sxs-lookup"><span data-stu-id="901e2-105">Receives a set of correlated messages.</span></span> <span data-ttu-id="901e2-106">Los mensajes se correlacionan según la información de URI del socio comercial de destino que se extrae del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="901e2-106">Messages are correlated based on the destination partner URI information that is extracted from message content.</span></span>  
  
2.  <span data-ttu-id="901e2-107">Agrega los mensajes recibidos en un lote de intercambio único mediante la ejecución de una canalización de envío de XML.</span><span class="sxs-lookup"><span data-stu-id="901e2-107">Aggregates received messages into a single interchange batch by executing an XML send pipeline.</span></span>  
  
3.  <span data-ttu-id="901e2-108">Produce un mensaje de intercambio de XML cada minuto o en cuanto tiene suficientes mensajes para agregar.</span><span class="sxs-lookup"><span data-stu-id="901e2-108">Produces an XML interchange message every minute or as soon as it has enough messages to aggregate.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="901e2-109">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="901e2-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="901e2-110">*\<Ejemplos de ruta de acceso\>*\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="901e2-110">*\<Samples Path\>*\Pipelines\Aggregator</span></span>  
  
 <span data-ttu-id="901e2-111">En la tabla siguiente se enumeran los archivos que se usan en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="901e2-111">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="901e2-112">Archivos</span><span class="sxs-lookup"><span data-stu-id="901e2-112">File(s)</span></span>|<span data-ttu-id="901e2-113">Description</span><span class="sxs-lookup"><span data-stu-id="901e2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="901e2-114">Aggregator.sln</span><span class="sxs-lookup"><span data-stu-id="901e2-114">Aggregator.sln</span></span>|<span data-ttu-id="901e2-115">Archivo de solución de Visual Studio para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="901e2-115">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="901e2-116">AggretatorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="901e2-116">AggretatorBinding.xml</span></span>|<span data-ttu-id="901e2-117">Archivo de enlace para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="901e2-117">Binding file for the sample.</span></span>|  
|<span data-ttu-id="901e2-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="901e2-118">Cleanup.bat</span></span>|<span data-ttu-id="901e2-119">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="901e2-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="901e2-120">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="901e2-120">Removes send and receive ports.</span></span> <span data-ttu-id="901e2-121">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="901e2-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="901e2-122">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="901e2-122">Setup.bat</span></span>|<span data-ttu-id="901e2-123">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="901e2-123">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="901e2-124">En la carpeta Aggregate:</span><span class="sxs-lookup"><span data-stu-id="901e2-124">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="901e2-125">Aggregate.btproj</span><span class="sxs-lookup"><span data-stu-id="901e2-125">Aggregate.btproj</span></span>|<span data-ttu-id="901e2-126">Proyecto de BizTalk para la orquestación de agregación.</span><span class="sxs-lookup"><span data-stu-id="901e2-126">BizTalk project for aggregating orchestration.</span></span>|  
|<span data-ttu-id="901e2-127">En la carpeta Aggregator:</span><span class="sxs-lookup"><span data-stu-id="901e2-127">In Aggregator folder:</span></span><br /><br /> <span data-ttu-id="901e2-128">Aggregate.odx</span><span class="sxs-lookup"><span data-stu-id="901e2-128">Aggregate.odx</span></span>|<span data-ttu-id="901e2-129">Orquestación que reúne los mensajes correlacionados y después ejecuta la canalización de envío para ensamblarlos en un intercambio único.</span><span class="sxs-lookup"><span data-stu-id="901e2-129">Orchestration that collects correlated messages together and then executes send pipeline to assemble them into a single interchange.</span></span>|  
|<span data-ttu-id="901e2-130">En la carpeta Aggregate:</span><span class="sxs-lookup"><span data-stu-id="901e2-130">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="901e2-131">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="901e2-131">SuspendMessage.odx</span></span>|<span data-ttu-id="901e2-132">Orquestación usada para suspender mensajes que no se pueden procesar en la orquestación de agregación.</span><span class="sxs-lookup"><span data-stu-id="901e2-132">Orchestration used for suspending messages that cannot be processed within aggregating orchestration.</span></span>|  
|<span data-ttu-id="901e2-133">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="901e2-133">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="901e2-134">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="901e2-134">FFReceivePipeline.btp</span></span>|<span data-ttu-id="901e2-135">Canalización de recepción con desensamblador de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="901e2-135">Receive pipeline with flat file disassembler.</span></span>|  
|<span data-ttu-id="901e2-136">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="901e2-136">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="901e2-137">Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt</span><span class="sxs-lookup"><span data-stu-id="901e2-137">Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt</span></span>|<span data-ttu-id="901e2-138">Instancias de documento para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="901e2-138">Document instances for the sample.</span></span> <span data-ttu-id="901e2-139">Instance1.txt e Instance2.txt deben agregarse a un intercambio de socio comercial de destino [http://www.contoso.com](http://www.contoso.com/) mientras que Instance3.txt e Instance4.txt deben agregarse a un intercambio de socio comercial de destino [ http://www.Northwind.com](http://www.northwind.com/).</span><span class="sxs-lookup"><span data-stu-id="901e2-139">Instance1.txt and Instance2.txt should be added to an interchange for destination partner [http://www.contoso.com](http://www.contoso.com/) while Instance3.txt and Instance4.txt should be added to an interchange for destination partner [http://www.northwind.com](http://www.northwind.com/).</span></span>|  
|<span data-ttu-id="901e2-140">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="901e2-140">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="901e2-141">Invoice.xsd, InvoiceEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="901e2-141">Invoice.xsd, InvoiceEnvelope.xsd</span></span>|<span data-ttu-id="901e2-142">Esquema de documento y esquema de sobre para el intercambio de salida.</span><span class="sxs-lookup"><span data-stu-id="901e2-142">Document schema and envelope schema for output interchange.</span></span>|  
|<span data-ttu-id="901e2-143">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="901e2-143">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="901e2-144">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="901e2-144">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="901e2-145">Proyecto de BizTalk para los esquemas y las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="901e2-145">BizTalk project for the schemas and pipelines.</span></span>|  
|<span data-ttu-id="901e2-146">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="901e2-146">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="901e2-147">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="901e2-147">PropertySchema.xsd</span></span>|<span data-ttu-id="901e2-148">Esquema de propiedad del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="901e2-148">Property schema for the sample.</span></span>|  
|<span data-ttu-id="901e2-149">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="901e2-149">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="901e2-150">XMLAggregatingPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="901e2-150">XMLAggregatingPipeline.btp</span></span>|<span data-ttu-id="901e2-151">Canalización de envío que se ejecuta desde la orquestación para ensamblar mensajes recogidos en un intercambio de XML.</span><span class="sxs-lookup"><span data-stu-id="901e2-151">Send pipeline that is executed from orchestration to assemble collected messages into an XML interchange.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="901e2-152">Crear e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="901e2-152">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="901e2-153">Utilice el siguiente procedimiento para crear e inicializar el ejemplo de agregación.</span><span class="sxs-lookup"><span data-stu-id="901e2-153">Use the following procedure to build and initialize the Aggregator sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a><span data-ttu-id="901e2-154">Para crear e inicializar el ejemplo de agregación</span><span class="sxs-lookup"><span data-stu-id="901e2-154">To build and initialize the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="901e2-155">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="901e2-155">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="901e2-156">\<Ejemplos de ruta de acceso\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="901e2-156">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
2.  <span data-ttu-id="901e2-157">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="901e2-157">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="901e2-158">Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta:</span><span class="sxs-lookup"><span data-stu-id="901e2-158">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="901e2-159">\<Ejemplos de ruta de acceso\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="901e2-159">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
    -   <span data-ttu-id="901e2-160">Compila los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="901e2-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
    -   <span data-ttu-id="901e2-161">Crea una aplicación nueva llamada "Aggregator Sample" e implementa los ensamblados de ejemplo en ella.</span><span class="sxs-lookup"><span data-stu-id="901e2-161">Creates a new application called "Aggregator Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="901e2-162">Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="901e2-162">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="901e2-163">Da de alta e inicia la orquestación, habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="901e2-163">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="901e2-164">Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="901e2-164">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="901e2-165">Utilice que este par de claves se usa para firmar los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="901e2-165">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="901e2-166">Antes de intentar ejecutar este ejemplo, confirme que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha notificado ningún error durante el proceso de compilación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="901e2-166">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="901e2-167">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="901e2-167">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="901e2-168">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="901e2-168">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="901e2-169">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="901e2-169">Running the Sample</span></span>  
 <span data-ttu-id="901e2-170">Utilice el siguiente procedimiento para ejecutar el ejemplo de agregación.</span><span class="sxs-lookup"><span data-stu-id="901e2-170">Use the following procedure to run the Aggregator sample.</span></span>  
  
#### <a name="to-run-the-aggregator-sample"></a><span data-ttu-id="901e2-171">Para ejecutar el ejemplo de agregación</span><span class="sxs-lookup"><span data-stu-id="901e2-171">To run the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="901e2-172">Abra los archivos Instance1.txt e Instance2.txt que se encuentran en la carpeta PipelinesAndSchemas para inspeccionar su contenido.</span><span class="sxs-lookup"><span data-stu-id="901e2-172">Open Instance1.txt and Instance2.txt files located in PipelinesAndSchemas folder to inspect their content.</span></span>  
  
     <span data-ttu-id="901e2-173">Tenga en cuenta que en ambos archivos, el elemento DestinationPartnerURI contiene el valor http://www.contoso.com. Este valor se usará para correlacionar estos dos mensajes juntos de modo que se puedan agregar a un intercambio.</span><span class="sxs-lookup"><span data-stu-id="901e2-173">Notice that in both files the DestinationPartnerURI element contains the value http://www.contoso.com. This value will be used to correlate these two messages together so that they can be added to one interchange.</span></span>  
  
     <span data-ttu-id="901e2-174">Del mismo modo, los archivos Instance3.txt e Instance4.txt tienen el elemento DestinationPatnerURI establecido en http://www.northwind.com.</span><span class="sxs-lookup"><span data-stu-id="901e2-174">Similarly Instance3.txt and Instance4.txt files have DestinationPatnerURI element set to http://www.northwind.com.</span></span>  
  
     <span data-ttu-id="901e2-175">Estos dos mensajes juntos se agregarán a un intercambio diferente.</span><span class="sxs-lookup"><span data-stu-id="901e2-175">These two messages together will be added to a different interchange.</span></span>  
  
2.  <span data-ttu-id="901e2-176">Pegue copias de los archivos de texto Instance1.txt, Instance2.txt, Instance3.txt e Instance4.txt en la carpeta In.</span><span class="sxs-lookup"><span data-stu-id="901e2-176">Paste copies of the text files Instance1.txt, Instance2.txt, Instance3.txt, and Instance4.txt into the folder In.</span></span>  
  
3.  <span data-ttu-id="901e2-177">Las orquestaciones de agregación producen intercambios de salida en cuanto recogen 10 mensajes o cuando transcurre 1 minuto de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="901e2-177">Aggregating orchestrations produce output interchanges as soon as they collect 10 messages or after timeout of 1 minute.</span></span> <span data-ttu-id="901e2-178">Debido a eso, los archivos en la carpeta Out pueden aparecer con retraso.</span><span class="sxs-lookup"><span data-stu-id="901e2-178">Because of that, the files in the Out folder may appear with delay.</span></span>  
  
     <span data-ttu-id="901e2-179">Para evitar el tiempo de espera, puede pegar los cuatro archivos de entrada cuatro veces lo que desencadenaría que las orquestaciones de agregación produzcan los intercambios.</span><span class="sxs-lookup"><span data-stu-id="901e2-179">To avoid the timeout, you can paste the four input files four more times, which would trigger the aggregating orchestrations to produce the interchanges.</span></span>  
  
4.  <span data-ttu-id="901e2-180">Observe los archivos XML creados en la carpeta Out. Debería haber dos archivos: uno por cada URI de socio comercial de destino.</span><span class="sxs-lookup"><span data-stu-id="901e2-180">Observe the XML files created in the folder Out. There should be two files – one per each destination partner URI.</span></span>  
  
     <span data-ttu-id="901e2-181">Abra uno de los archivos para inspeccionar su contenido.</span><span class="sxs-lookup"><span data-stu-id="901e2-181">Open one of the file to inspect its content.</span></span> <span data-ttu-id="901e2-182">El archivo debe contener un intercambio de XML que consista en un sobre y dos documentos XML dentro de él.</span><span class="sxs-lookup"><span data-stu-id="901e2-182">The file should contain an XML interchange that consists of an envelope and two XML documents within it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="901e2-183">La implementación de ejemplo puede producir "mensajes entregados, no consumidos" o "Completado con mensajes descartados" con una carga elevado en un escenario de convoyes.</span><span class="sxs-lookup"><span data-stu-id="901e2-183">The sample implementation may cause "Delivered, not consumed messages" or "Completed with discarded messages" under high load in a convoy scenario.</span></span> <span data-ttu-id="901e2-184">Esto se produce cada vez que la ruta de un mensaje se dirige a un proceso empresarial que está en el proceso de finalización o cada vez que llegan mensajes inesperados a un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="901e2-184">This occurs any time a message routes to a business process that is in the process of ending, or any time unexpected messages arrive into a business process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901e2-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="901e2-185">See Also</span></span>  
 [<span data-ttu-id="901e2-186">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="901e2-186">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)