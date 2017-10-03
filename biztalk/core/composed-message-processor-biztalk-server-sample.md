---
title: Compone el procesador de mensajes (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- messages, processing
- messages, aggregated
- examples, pipelines
ms.assetid: a0f87f98-6f5f-4edb-8f65-49d22df5de97
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3853a5b903215b6f716a13c33727e60c67107b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="composed-message-processor-biztalk-server-sample"></a><span data-ttu-id="bdc91-102">Procesador de mensajes compuestos  (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="bdc91-102">Composed Message Processor (BizTalk Server Sample)</span></span>
<span data-ttu-id="bdc91-103">Este ejemplo tiene como finalidad crear una aplicación de procesador de mensajes compuestos que procese elementos de línea individuales a partir de mensajes agregados.</span><span class="sxs-lookup"><span data-stu-id="bdc91-103">The purpose of this sample is to build a composed message processor application that processes individual line items from aggregated messages.</span></span>  
  
 <span data-ttu-id="bdc91-104">De forma más específica, crearemos una programación de orquestación que:</span><span class="sxs-lookup"><span data-stu-id="bdc91-104">Specifically we will build an orchestration schedule that:</span></span>  
  
1.  <span data-ttu-id="bdc91-105">Reciba un mensaje de intercambio por lotes compuesto de varios pedidos.</span><span class="sxs-lookup"><span data-stu-id="bdc91-105">Receives a batched interchange message consisting of multiple purchase orders.</span></span>  
  
2.  <span data-ttu-id="bdc91-106">Desensamble el mensaje de intercambio en documentos de pedido individuales.</span><span class="sxs-lookup"><span data-stu-id="bdc91-106">Disassembles the interchange message into individual purchase order documents.</span></span>  
  
3.  <span data-ttu-id="bdc91-107">Procese cada documento: convierta cada pedido en un mensaje de factura.</span><span class="sxs-lookup"><span data-stu-id="bdc91-107">Processes each document – converts each purchase order into an invoice message.</span></span>  
  
4.  <span data-ttu-id="bdc91-108">Ensamble todos los mensajes de factura en un intercambio por lotes.</span><span class="sxs-lookup"><span data-stu-id="bdc91-108">Assembles all the invoice messages into a batched interchange.</span></span>  
  
 <span data-ttu-id="bdc91-109">El paso 3 se simplifica para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-109">Step #3 is simplified for the sample purposes.</span></span> <span data-ttu-id="bdc91-110">Por ejemplo, en aplicaciones más complejas, una orquestación puede enviar pedidos desensamblados a distintos sistemas de servidor de inventario y después tras recopilar todas las respuestas, agregarlos en un mensaje de factura por lotes.</span><span class="sxs-lookup"><span data-stu-id="bdc91-110">For example, in more complex applications, an orchestration may send disassembled purchase orders to different back-end inventory systems and then after collecting all the responses, aggregate them into one batched invoice message.</span></span>  
  
 <span data-ttu-id="bdc91-111">Para obtener más información sobre el patrón del procesador de mensajes compuestos, vea [1].</span><span class="sxs-lookup"><span data-stu-id="bdc91-111">For more information on the composed message processor pattern refer to [1].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="bdc91-112">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdc91-112">What This Sample Does</span></span>  
 <span data-ttu-id="bdc91-113">Existen dos proyectos dentro de la solución de ejemplo, que se describen de forma detallada en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="bdc91-113">There are two projects within the sample solution, both of which are described in detail in the following sections.</span></span>  
  
### <a name="pipelines-and-schemas"></a><span data-ttu-id="bdc91-114">Canalizaciones y esquemas</span><span class="sxs-lookup"><span data-stu-id="bdc91-114">Pipelines and Schemas</span></span>  
 <span data-ttu-id="bdc91-115">El proyecto de canalizaciones y esquemas contiene:</span><span class="sxs-lookup"><span data-stu-id="bdc91-115">Pipelines and schemas project contains:</span></span>  
  
-   <span data-ttu-id="bdc91-116">Esquemas de archivos sin formato para el intercambio de pedidos de entrada y el intercambio de facturas de salida.</span><span class="sxs-lookup"><span data-stu-id="bdc91-116">Flat file schemas for input purchase order interchange and for output invoice interchange.</span></span>  
  
-   <span data-ttu-id="bdc91-117">Asignación para transformar el documento de pedido en un documento de factura.</span><span class="sxs-lookup"><span data-stu-id="bdc91-117">Map to transform purchase order document into an invoice document.</span></span>  
  
-   <span data-ttu-id="bdc91-118">Canalizaciones de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="bdc91-118">Receive and send pipelines.</span></span>  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a><span data-ttu-id="bdc91-119">Esquemas de archivos sin formato para los intercambios de entrada y de salida</span><span class="sxs-lookup"><span data-stu-id="bdc91-119">Flat File Schemas For Input and Output Interchanges</span></span>  
 <span data-ttu-id="bdc91-120">Nuestra aplicación de ejemplo funcionará con los intercambios en el formato de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="bdc91-120">Our sample application will be working with the interchanges in the flat file format.</span></span> <span data-ttu-id="bdc91-121">A continuación, se indican los ejemplos del intercambio de pedidos y el intercambio de facturas:</span><span class="sxs-lookup"><span data-stu-id="bdc91-121">Below are the examples of the purchase order interchange and invoice interchange:</span></span>  
  
 <span data-ttu-id="bdc91-122">Intercambio de pedidos (CMPInput.txt):</span><span class="sxs-lookup"><span data-stu-id="bdc91-122">Purchase order interchange (CMPInput.txt):</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
PO1999-10-21  
US    John Dow       123 Elm Street      Mill Valley    CA 90952  
US    July Dow       8 Pine Avenue       Old Town       PA 95819  
Please ship it urgent!  
ITEMS,ITEM398-BB|Tire|4|324.99|Wrap them up nicely,ITEM201-BB|Engine Oil|1|12.99|SAE10W30|1999-05-22  
PO1999-10-23  
US    John Connor    123 Cedar Street    Mill Valley    CA 90952  
US    Sarah Connor   8 Grass Avenue      Old Town       PA 95819  
Use cheapest shipping method.  
ITEMS,ITEM101-TT|Plastic flowers|10|4.99|Fragile handle with care,ITEM202-RR|Fertilizer|1|10.99|Lawn fertilizer,ITEM453-XS|Weed killer|1|5.99|Lawn weed killer|1999-05-25  
```  
  
 <span data-ttu-id="bdc91-123">El intercambio, o el documento de pedido, tiene un encabezado que identifica el tipo de documentos que contiene:</span><span class="sxs-lookup"><span data-stu-id="bdc91-123">The interchange, or purchase order document, has a header that identifies what type of the documents it contains:</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 <span data-ttu-id="bdc91-124">Este intercambio se compone de tres documentos de pedido.</span><span class="sxs-lookup"><span data-stu-id="bdc91-124">This interchange consist of three purchase order documents.</span></span> <span data-ttu-id="bdc91-125">Una instancia consta de la información que se muestra abajo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-125">One instance consists of the information shown below.</span></span> <span data-ttu-id="bdc91-126">Como se puede apreciar, contiene información como la dirección de facturación y envío, así como la lista de artículos que se han pedido.</span><span class="sxs-lookup"><span data-stu-id="bdc91-126">As you can see, it contains such information as address for billing and shipping as well as the list of items that were ordered.</span></span>  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 <span data-ttu-id="bdc91-127">El intercambio de facturas que queremos generar para esto debería tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="bdc91-127">The invoice interchange we want to generate for this should look like the following:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
INVOICE1999-10-21  
BILLTO,US,John Dow,123 Elm Street,Mill Valley,CA,90952  
398-BB    Tire              4    324.99    Wrap them up nicely  
201-BB    Engine Oil        1    12.99     SAE10W30  
INVOICE1999-10-20  
BILLTO,US,John Connor,123 Cedar Street,Mill Valley,CA,90952  
101-TT    Plastic flowers   10   4.99      Fragile handle with care  
202-RR    Fertilizer        1    10.99     Lawn fertilizer  
453-XS    Weed killer       1    5.99      Lawn weed killer  
```  
  
 <span data-ttu-id="bdc91-128">Este intercambio contiene un subconjunto de información que se encontraba en el intercambio de pedidos y, además, el formato del intercambio y el formato del encabezado son diferentes.</span><span class="sxs-lookup"><span data-stu-id="bdc91-128">This interchange contains a subset of information that was in purchase order interchange and also the format of the interchange as well as format of the header are different.</span></span>  
  
 <span data-ttu-id="bdc91-129">El encabezado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bdc91-129">The header is as follows:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 <span data-ttu-id="bdc91-130">Además, la instancia del documento incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bdc91-130">And the document instance includes the following:</span></span>  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 <span data-ttu-id="bdc91-131">Primero tenemos que crear los esquemas de archivo sin formato para:</span><span class="sxs-lookup"><span data-stu-id="bdc91-131">First thing we need to create flat file schemas for:</span></span>  
  
-   <span data-ttu-id="bdc91-132">El documento de pedido (PO.xsd)</span><span class="sxs-lookup"><span data-stu-id="bdc91-132">Purchase order document (PO.xsd)</span></span>  
  
-   <span data-ttu-id="bdc91-133">El documento de factura (Invoice.xsd)</span><span class="sxs-lookup"><span data-stu-id="bdc91-133">Invoice document (Invoice.xsd)</span></span>  
  
-   <span data-ttu-id="bdc91-134">El encabezado del pedido (POHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="bdc91-134">Purchase order header (POHeader.xsd)</span></span>  
  
-   <span data-ttu-id="bdc91-135">El encabezado de la factura (InvoiceHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="bdc91-135">Invoice header (InvoiceHeader.xsd)</span></span>  
  
 <span data-ttu-id="bdc91-136">Para este ejemplo, no vamos a explicar el proceso de creación de esquemas de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="bdc91-136">For this sample, we are not going to explain the process of creating flat file schemas.</span></span> <span data-ttu-id="bdc91-137">Para aprender a crear esquemas de archivos sin formato a partir de instancias de documentos, vea la sección "Crear esquemas de archivos sin formato a partir de instancias de documentos" de la documentación.</span><span class="sxs-lookup"><span data-stu-id="bdc91-137">To learn how to create flat file schemas from document instances, refer to the "Creating flat file schemas from document instance" documentation section.</span></span>  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a><span data-ttu-id="bdc91-138">Asignación para transformar documentos de pedido en documentos de factura</span><span class="sxs-lookup"><span data-stu-id="bdc91-138">Map to Transform Purchase Order Document Into Invoice Document</span></span>  
 <span data-ttu-id="bdc91-139">La asignación (PO2Invoice.btm) transforma una instancia del pedido en un documento de factura.</span><span class="sxs-lookup"><span data-stu-id="bdc91-139">The map (PO2Invoice.btm) transforms an instance of the purchase order into an invoice document.</span></span>  
  
#### <a name="receive-and-send-pipelines"></a><span data-ttu-id="bdc91-140">Canalizaciones de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="bdc91-140">Receive and Send Pipelines</span></span>  
 <span data-ttu-id="bdc91-141">La canalización de recepción (FFReceivePipeline.btp) contiene un componente desensamblador de archivos sin formato que se emplea para procesar un intercambio de pedidos.</span><span class="sxs-lookup"><span data-stu-id="bdc91-141">The receive pipeline (FFReceivePipeline.btp) contains a flat file disassembler component that is used to process a purchase order interchange.</span></span> <span data-ttu-id="bdc91-142">En concreto, para el intercambio en el archivo CMPInput.txt, quita el encabezado del intercambio y genera tres documentos XML correspondientes a tres pedidos.</span><span class="sxs-lookup"><span data-stu-id="bdc91-142">In particular, for the interchange in file CMPInput.txt, it removes the interchange header and produces three XML documents corresponding to three purchase orders.</span></span>  
  
 <span data-ttu-id="bdc91-143">El desensamblador de archivos sin formato de la canalización de recepción se configura como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="bdc91-143">The flat file disassembler in the receive pipeline is configured as shown:</span></span>  
  
-   <span data-ttu-id="bdc91-144">**Esquema de documento:** PipelinesAndSchemas.PO</span><span class="sxs-lookup"><span data-stu-id="bdc91-144">**Document schema:** PipelinesAndSchemas.PO</span></span>  
  
-   <span data-ttu-id="bdc91-145">**Esquema de encabezado:** PipelinesAndSchemas.POHeader</span><span class="sxs-lookup"><span data-stu-id="bdc91-145">**Header schema:** PipelinesAndSchemas.POHeader</span></span>  
  
-   <span data-ttu-id="bdc91-146">**Conservar encabezado:** False</span><span class="sxs-lookup"><span data-stu-id="bdc91-146">**Preserve header:** False</span></span>  
  
-   <span data-ttu-id="bdc91-147">**Intercambio recuperable:** False</span><span class="sxs-lookup"><span data-stu-id="bdc91-147">**Recoverable interchange:** False</span></span>  
  
-   <span data-ttu-id="bdc91-148">**Esquema de finalizador:** (ninguno)</span><span class="sxs-lookup"><span data-stu-id="bdc91-148">**Trailer schema:** (None)</span></span>  
  
-   <span data-ttu-id="bdc91-149">**Validar la estructura del documento:** False</span><span class="sxs-lookup"><span data-stu-id="bdc91-149">**Validate document structure:** False</span></span>  
  
 <span data-ttu-id="bdc91-150">La canalización de envío (FFSendPipeline.btp) contiene un componente ensamblador de archivos sin formato que se emplea para crear un intercambio de facturas agregadas.</span><span class="sxs-lookup"><span data-stu-id="bdc91-150">The send pipeline (FFSendPipeline.btp) contains a flat file assembler component that is used to create aggregated invoice interchange.</span></span>  
  
 <span data-ttu-id="bdc91-151">El ensamblador de archivos sin formato de la canalización de envío se configura como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="bdc91-151">The flat file assembler in send pipeline is configured as shown:</span></span>  
  
-   <span data-ttu-id="bdc91-152">**Esquema de documento:** PipelinesandSchemas.Invoice</span><span class="sxs-lookup"><span data-stu-id="bdc91-152">**Document schema:** PipelinesandSchemas.Invoice</span></span>  
  
-   <span data-ttu-id="bdc91-153">**Esquema de encabezado:** PipelinesAndSchemas.InvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="bdc91-153">**Header schema:** PipelinesAndSchemas.InvoiceHeader</span></span>  
  
-   <span data-ttu-id="bdc91-154">**Conservar marca de orden de bytes:** False</span><span class="sxs-lookup"><span data-stu-id="bdc91-154">**Preserve byte order mark:** False</span></span>  
  
-   <span data-ttu-id="bdc91-155">**Juego de caracteres de destino:** (ninguno)</span><span class="sxs-lookup"><span data-stu-id="bdc91-155">**Target charset:** (None)</span></span>  
  
-   <span data-ttu-id="bdc91-156">**Esquema de finalizador:** (ninguno)</span><span class="sxs-lookup"><span data-stu-id="bdc91-156">**Trailer schema:** (None)</span></span>  
  
### <a name="orchestration-schedule"></a><span data-ttu-id="bdc91-157">Programación de orquestación</span><span class="sxs-lookup"><span data-stu-id="bdc91-157">Orchestration Schedule</span></span>  
 <span data-ttu-id="bdc91-158">La programación de orquestación (CMP.odx) es el lugar en que se produce todo el procesamiento principal.</span><span class="sxs-lookup"><span data-stu-id="bdc91-158">Orchestration schedule (CMP.odx) is where all the main processing happens.</span></span> <span data-ttu-id="bdc91-159">En concreto, se llevan a cabo las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bdc91-159">Specifically the following actions are performed:</span></span>  
  
-   <span data-ttu-id="bdc91-160">Se ejecuta la canalización de recepción para desensamblar el intercambio de pedidos.</span><span class="sxs-lookup"><span data-stu-id="bdc91-160">Receive pipeline is executed to disassemble purchase order interchange</span></span>  
  
-   <span data-ttu-id="bdc91-161">Se transforman todos los mensajes de salida de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="bdc91-161">Every output message of receive pipeline is transformed</span></span>  
  
-   <span data-ttu-id="bdc91-162">Se ejecuta la canalización de envío para ensamblar el intercambio de facturas.</span><span class="sxs-lookup"><span data-stu-id="bdc91-162">Send pipeline is executed to assemble an invoice interchange</span></span>  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a><span data-ttu-id="bdc91-163">Crear la programación de orquestación y definir variables globales</span><span class="sxs-lookup"><span data-stu-id="bdc91-163">Creating Orchestration Schedule and Defining Global Variables</span></span>  
 <span data-ttu-id="bdc91-164">Nuestra orquestación recibirá un intercambio de archivos sin formato como entrada y enviará un intercambio de archivos sin formato como salida.</span><span class="sxs-lookup"><span data-stu-id="bdc91-164">Our orchestration will receive a flat file interchange as an input and will send a flat file interchange as an output.</span></span> <span data-ttu-id="bdc91-165">Debido a esto, es preciso definir los mensajes de entrada y salida (denominados InputInterchange y OutputInterchange, respectivamente) como de tipo independiente (es decir, que tienen el tipo System.Xml.XmlDocument).</span><span class="sxs-lookup"><span data-stu-id="bdc91-165">Because of that, we need to define input and output messages (called InputInterchange and OutputInterchange respectively) as type agnostic (i.e. having type of System.Xml.XmlDocument).</span></span>  
  
 <span data-ttu-id="bdc91-166">Además, hay que definir un ámbito atómico en el que se procesarán los mensajes.</span><span class="sxs-lookup"><span data-stu-id="bdc91-166">Also, we need to define an atomic scope where we will process messages.</span></span> <span data-ttu-id="bdc91-167">Esto es necesario porque la canalización de recepción se puede ejecutar en un ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="bdc91-167">This is required because the receive pipeline can be executed within atomic scope.</span></span>  
  
#### <a name="executing-receive-pipeline"></a><span data-ttu-id="bdc91-168">Ejecutar canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="bdc91-168">Executing Receive Pipeline</span></span>  
 <span data-ttu-id="bdc91-169">Como siguiente paso, agregaremos lógica para ejecutar una canalización de recepción correspondiente al mensaje que se ha recibido en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="bdc91-169">As a next step, we will add logic to execute a receive pipeline for the message that was received in orchestration.</span></span> <span data-ttu-id="bdc91-170">Para ello, declararemos una variable (con el nombre RcvPipeOutput) de tipo Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="bdc91-170">To do this, first we declare a variable (called RcvPipeOutput) of type Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages within the scope.</span></span> <span data-ttu-id="bdc91-171">Esta variable es un enumerador que permite el desplazamiento por los mensajes de salida de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="bdc91-171">This variable is an enumerator that allows us to cycle through the receive pipeline output messages.</span></span> <span data-ttu-id="bdc91-172">Tenga en cuenta que, para obtener acceso a este tipo, así como a los demás tipos para la ejecución de canalizaciones a partir de la orquestación, es preciso agregar referencias a los ensamblados siguientes:</span><span class="sxs-lookup"><span data-stu-id="bdc91-172">Note that in order to access this type, as well as all the other types for execution of pipelines from orchestration, you need to add references to the following assemblies:</span></span>  
  
-   <span data-ttu-id="bdc91-173">Microsoft.XLANGs.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="bdc91-173">Microsoft.XLANGs.Pipeline.dll</span></span>  
  
-   <span data-ttu-id="bdc91-174">Microsoft.BizTalk.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="bdc91-174">Microsoft.BizTalk.Pipeline.dll</span></span>  
  
 <span data-ttu-id="bdc91-175">No hay ninguna garantía de que la canalización de recepción siempre se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="bdc91-175">There is no guarantee that the receive pipeline will always execute successfully.</span></span> <span data-ttu-id="bdc91-176">En ocasiones, el formato de los mensajes puede ser incorrecto, lo que originaría errores en el procesamiento de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-176">Sometimes messages may be malformed, which would cause the pipeline processing to fail.</span></span> <span data-ttu-id="bdc91-177">Cuando la ejecución de una canalización genera errores en la orquestación, se inicia una excepción que se puede capturar y se puede realizar la lógica de control de errores.</span><span class="sxs-lookup"><span data-stu-id="bdc91-177">When a pipeline fails execution in the orchestration, there is an exception thrown that can be caught and the error handling logic can be performed.</span></span> <span data-ttu-id="bdc91-178">Para capturar la excepción iniciada por la canalización, hay que ejecutar la canalización dentro de un ámbito no atómico con un control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="bdc91-178">In order for us to catch the exception thrown by pipeline, we need to execute the pipeline within a non-atomic scope with an exception handling.</span></span> <span data-ttu-id="bdc91-179">El código real para ejecutar la canalización se invoca desde una forma de expresión dentro de dicho ámbito.</span><span class="sxs-lookup"><span data-stu-id="bdc91-179">The actual code to execute pipeline is invoked from an expression shape within that scope.</span></span>  
  
 <span data-ttu-id="bdc91-180">En la forma de expresión ExecuteRcvPipe, escriba la siguiente línea de código para ejecutar la canalización de recepción:</span><span class="sxs-lookup"><span data-stu-id="bdc91-180">In the ExecuteRcvPipe expression shape, write the following line of code to execute the receive pipeline:</span></span>  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 <span data-ttu-id="bdc91-181">Vamos a analizar esta línea de código de forma detallada.</span><span class="sxs-lookup"><span data-stu-id="bdc91-181">Let's analyze this line of code in more detail.</span></span> <span data-ttu-id="bdc91-182">Como se puede apreciar, se llama a un método estático ExecuteReceivePipeline que toma como parámetro un tipo de canalización de recepción para su ejecución y un mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="bdc91-182">As you can see, we call a static method ExecuteReceivePipeline that takes as a parameter a type of receive pipeline to execute and an input message.</span></span> <span data-ttu-id="bdc91-183">Como resultado, genera un objeto enumerador con el conjunto de mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="bdc91-183">As a result, it produces an enumerator object with the set of output messages.</span></span> <span data-ttu-id="bdc91-184">El resultado se asigna a una variable de tipo ReceivePipelineOutputMessages que se había definido anteriormente en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="bdc91-184">The result is assigned to a variable of type ReceivePipelineOutputMessages that was defined in this scope before.</span></span>  
  
 <span data-ttu-id="bdc91-185">También se ha incluido un bloque de control de excepciones para el ámbito de ejecución de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-185">We have also included an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="bdc91-186">Este bloque capta la excepción de tipo XLANGPipelineManagerException y después, para simplificar, termina una instancia de orquestación con el mensaje de error personalizado.</span><span class="sxs-lookup"><span data-stu-id="bdc91-186">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
 <span data-ttu-id="bdc91-187">En escenarios más complejos, aquí se puede realizar un control de errores adicional, como la generación o el mensaje de notificación de error y su envío a un usuario empresarial o al administrador mediante el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bdc91-187">In more complex scenarios, additional error handling can be performed here, such as generation or the error notification message and sending it to a business user or administrator using email.</span></span>  
  
#### <a name="transforming-pipeline-output-messages"></a><span data-ttu-id="bdc91-188">Transformar mensajes de salida de la canalización</span><span class="sxs-lookup"><span data-stu-id="bdc91-188">Transforming Pipeline Output Messages</span></span>  
 <span data-ttu-id="bdc91-189">Después de que se haya ejecutado la canalización y se haya generado el conjunto de mensajes desensamblados, es preciso transformar cada mensaje de salida en un formato distinto.</span><span class="sxs-lookup"><span data-stu-id="bdc91-189">After the pipeline has been executed and the set of disassembled messages has been produced, we need to transform each output message into a different format.</span></span>  
  
 <span data-ttu-id="bdc91-190">Para usar la transformación en la orquestación, hay que definir dos mensajes: entrada y salida de la transformación.</span><span class="sxs-lookup"><span data-stu-id="bdc91-190">To use transformation in orchestration we need to define two messages – transformation input and output.</span></span> <span data-ttu-id="bdc91-191">Dichos mensajes se definirán dentro del ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="bdc91-191">We will define those messages within the atomic scope.</span></span> <span data-ttu-id="bdc91-192">El mensaje de entrada de la transformación, que recibe el nombre TmpMessageIn, será del tipo PipelinesAndSchemas.PO,</span><span class="sxs-lookup"><span data-stu-id="bdc91-192">The transformation input message called TmpMessageIn will be of type PipelinesAndSchemas.PO.</span></span> <span data-ttu-id="bdc91-193">mientras que el mensaje de salida de la transformación, que recibe el nombre TmpMessageOut, será del tipo PipelinesAndSchemas.Invoice.</span><span class="sxs-lookup"><span data-stu-id="bdc91-193">The transformation output message called TmpMessageOut will be of type PipeliensAndSchemas.Invoice.</span></span> <span data-ttu-id="bdc91-194">Aplicaremos la asignación PO2Invoice.btm que está definida en el proyecto PipelinesAndSchemas.</span><span class="sxs-lookup"><span data-stu-id="bdc91-194">We will apply the map PO2Invoice.btm that is defined in project PipelinesAndSchemas.</span></span>  
  
 <span data-ttu-id="bdc91-195">Puesto que queremos asignar cada mensaje de salida de la canalización, tenemos que realizar la transformación en el bucle.</span><span class="sxs-lookup"><span data-stu-id="bdc91-195">As we want to map each pipeline output message we need to perform transformation in the loop.</span></span> <span data-ttu-id="bdc91-196">Usaremos una forma Bucle con la condición de salida como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="bdc91-196">We will use a loop shape with the condition for exiting as below:</span></span>  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 <span data-ttu-id="bdc91-197">El método MoveNext() es un método estándar de la interfaz IEnumerator .NET que permite desplazarse dentro de la colección de mensajes de salida de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-197">MoveNext() method is a standard method of IEnumerator .NET interface that allows to move within the collection of pipeline output messages.</span></span> <span data-ttu-id="bdc91-198">Cuando lleva al final de la colección, devuelve el valor False.</span><span class="sxs-lookup"><span data-stu-id="bdc91-198">When it reaches the end of collection it returns false.</span></span>  
  
 <span data-ttu-id="bdc91-199">La primera forma Construir se usa para construir un mensaje de orquestación TmpMessageIn fuera del mensaje de salida de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-199">The first construct shape is used to construct an orchestration message TmpMessageIn out of the pipeline output message.</span></span>  
  
 <span data-ttu-id="bdc91-200">El código en la forma Construir es:</span><span class="sxs-lookup"><span data-stu-id="bdc91-200">The code in the construct shape:</span></span>  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 <span data-ttu-id="bdc91-201">En este código, primero se inicializa el mensaje de orquestación como Null y luego se establece como el mensaje actual desde la colección de mensajes de salida de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-201">In this code we first initialize orchestration message to null and then set it to the current message from the pipeline output messages collection.</span></span>  
  
 <span data-ttu-id="bdc91-202">En la segunda forma Construir, se lleva a cabo la transformación real de TmpMessageIn y se construye el mensaje TmpMessageOut de tipo PipelinesAndSchemas.Invoice.</span><span class="sxs-lookup"><span data-stu-id="bdc91-202">In second construct shape the actual transformation of the TmpMessageIn is performed and the TmpMessageOut of type PipelinesAndSchemas.Invoice is constructed.</span></span>  
  
#### <a name="executing-send-pipeline"></a><span data-ttu-id="bdc91-203">Ejecutar una canalización de envío</span><span class="sxs-lookup"><span data-stu-id="bdc91-203">Executing Send Pipeline</span></span>  
 <span data-ttu-id="bdc91-204">El último paso del procesamiento en la orquestación consiste en ejecutar la canalización de envío de archivos sin formato para ensamblar todos los mensajes xml transformados en un intercambio de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="bdc91-204">Last processing step in orchestration is to execute flat file send pipeline to assemble all the transformed xml messages into one flat file interchange.</span></span>  
  
 <span data-ttu-id="bdc91-205">A fin de ejecutar una canalización de envío, hay que usar una variable de tipo Microsoft.XLANGs.Pipeline.SendPipelineInputMessages, denominada SendPipeInput, que contendrá una colección de mensajes de orquestación que deben procesarse en una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="bdc91-205">In order to execute a send pipeline we need to use a variable of type Microsoft.XLANGs.Pipeline.SendPipelineInputMessages called SendPipeInput that will hold a collection of orchestration messages that need to be processed in a send pipeline.</span></span>  
  
 <span data-ttu-id="bdc91-206">En la última expresión del bucle donde se ha realizado la transformación, escribiremos un código que agregará cada mensaje transformado a una colección de mensajes para la canalización de envío:</span><span class="sxs-lookup"><span data-stu-id="bdc91-206">In the last expression of the loop where we performed transformation we will write a code that will add each transformed message to a message collection for send pipeline:</span></span>  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 <span data-ttu-id="bdc91-207">De forma similar a la parte donde se ejecuta la canalización de recepción, el código para la ejecución de la canalización de envío se coloca dentro de un ámbito no atómico con el bloque de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="bdc91-207">Similar to the part where we execute receive pipeline the code for execution of send pipeline is placed within a non-atomic scope with exception handling block.</span></span> <span data-ttu-id="bdc91-208">El código de ejecución de la canalización de envío se encuentra en la forma Asignación de mensajes del bloque Construir.</span><span class="sxs-lookup"><span data-stu-id="bdc91-208">The send pipeline execution code is located in the message assignment shape of the construct block.</span></span>  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 <span data-ttu-id="bdc91-209">El bloque Construir se usa para construir un mensaje de salida de la canalización OutputInterchange de tipo independiente (es decir, System.Xml.XmlDocument).</span><span class="sxs-lookup"><span data-stu-id="bdc91-209">The construct block is used to construct type agnostic (i.e. System.Xml.XmlDocument) pipeline output message OutputInterchange.</span></span> <span data-ttu-id="bdc91-210">Después en la forma Asignación de mensajes, el mensaje recién construido se inicializa como Null.</span><span class="sxs-lookup"><span data-stu-id="bdc91-210">Then in the message assignment shape the newly constructed message is initialized to null.</span></span> <span data-ttu-id="bdc91-211">Después , se invoca al método estático ExecuteSendPipeline para ejecutar una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="bdc91-211">After that the static method ExecuteSendPipeline is invoked to execute a send pipeline.</span></span> <span data-ttu-id="bdc91-212">Este método toma como parámetro un tipo de la canalización de envío para su ejecución, el mensaje de entrada y la referencia al mensaje de salida cuando se almacene la salida de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-212">This method takes as a parameter a type of the send pipeline to execute, the input message and the reference to output message where the pipeline output will be stored.</span></span>  
  
 <span data-ttu-id="bdc91-213">Al igual que ocurre con la ejecución de la canalización de recepción, aquí tenemos un bloque de control de excepciones para el ámbito de ejecución de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-213">As with the execution of the receive pipeline, here we also have an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="bdc91-214">Este bloque capta la excepción de tipo XLANGPipelineManagerException y después, para simplificar, termina una instancia de orquestación con el mensaje de error personalizado.</span><span class="sxs-lookup"><span data-stu-id="bdc91-214">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="bdc91-215">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdc91-215">Where to Find This Sample</span></span>  
 <span data-ttu-id="bdc91-216">En la tabla siguiente se enumeran los archivos que se usan en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-216">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="bdc91-217">Archivos</span><span class="sxs-lookup"><span data-stu-id="bdc91-217">File(s)</span></span>|<span data-ttu-id="bdc91-218">Description</span><span class="sxs-lookup"><span data-stu-id="bdc91-218">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdc91-219">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="bdc91-219">Cleanup.bat</span></span>|<span data-ttu-id="bdc91-220">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="bdc91-220">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span><br /><br /> <span data-ttu-id="bdc91-221">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="bdc91-221">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="bdc91-222">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bdc91-222">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="bdc91-223">ComposedMessageProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="bdc91-223">ComposedMessageProcessor.sln</span></span>|<span data-ttu-id="bdc91-224">Archivo de solución de Visual Studio para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-224">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="bdc91-225">ComposedMessageProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="bdc91-225">ComposedMessageProcessorBinding.xml</span></span>|<span data-ttu-id="bdc91-226">Archivo de enlace para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-226">Binding file for the sample.</span></span>|  
|<span data-ttu-id="bdc91-227">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="bdc91-227">Setup.bat</span></span>|<span data-ttu-id="bdc91-228">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-228">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="bdc91-229">En la carpeta Orchestration:</span><span class="sxs-lookup"><span data-stu-id="bdc91-229">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="bdc91-230">CMP.odx</span><span class="sxs-lookup"><span data-stu-id="bdc91-230">CMP.odx</span></span>|<span data-ttu-id="bdc91-231">Orquestación que ejecuta la canalización de recepción para el mensaje del desensamblador, transforma cada mensaje desensamblado y, después, ejecuta la canalización de envío para ensamblar mensajes en un intercambio.</span><span class="sxs-lookup"><span data-stu-id="bdc91-231">Orchestration that runs the receive pipeline to disassembler message, transforms each disassembled message and then runs send pipeline to assemble messages into an interchange.</span></span>|  
|<span data-ttu-id="bdc91-232">En la carpeta Orchestration:</span><span class="sxs-lookup"><span data-stu-id="bdc91-232">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="bdc91-233">Orchestration.btproj</span><span class="sxs-lookup"><span data-stu-id="bdc91-233">Orchestration.btproj</span></span>|<span data-ttu-id="bdc91-234">Proyecto de BizTalk para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="bdc91-234">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="bdc91-235">En la carpeta Orchestration:</span><span class="sxs-lookup"><span data-stu-id="bdc91-235">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="bdc91-236">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="bdc91-236">SuspendMessage.odx</span></span>|<span data-ttu-id="bdc91-237">Orquestación usada para suspender mensajes que generan errores en el procesamiento de la canalización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-237">Orchestration used for suspending messages that fail pipeline processing.</span></span>|  
|<span data-ttu-id="bdc91-238">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="bdc91-238">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="bdc91-239">CMPInput.xml, CMPOutput.xml</span><span class="sxs-lookup"><span data-stu-id="bdc91-239">CMPInput.xml, CMPOutput.xml</span></span>|<span data-ttu-id="bdc91-240">Instancias de documentos de entrada y salida para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-240">Input and output document instances for the sample.</span></span>|  
|<span data-ttu-id="bdc91-241">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="bdc91-241">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="bdc91-242">FFReceivePipeline.btp, FFSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="bdc91-242">FFReceivePipeline.btp, FFSendPipeline.btp</span></span>|<span data-ttu-id="bdc91-243">Canalizaciones de recepción y envío con componentes de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="bdc91-243">Receive and send pipelines with flat file components.</span></span> <span data-ttu-id="bdc91-244">Estas canalizaciones se ejecutan dentro de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="bdc91-244">These pipelines are run within orchestration.</span></span>|  
|<span data-ttu-id="bdc91-245">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="bdc91-245">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="bdc91-246">Invoice.xsd, InvoiceHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="bdc91-246">Invoice.xsd, InvoiceHeader.xsd</span></span>|<span data-ttu-id="bdc91-247">Esquemas de archivos sin formato para el encabezado y el documento de salida.</span><span class="sxs-lookup"><span data-stu-id="bdc91-247">Flat file schemas for the output document and header.</span></span>|  
|<span data-ttu-id="bdc91-248">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="bdc91-248">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="bdc91-249">PO.xsd, POHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="bdc91-249">PO.xsd, POHeader.xsd</span></span>|<span data-ttu-id="bdc91-250">Esquemas de archivos sin formato para el encabezado y el documento de entrada.</span><span class="sxs-lookup"><span data-stu-id="bdc91-250">Flat file schemas for the input document and header.</span></span>|  
|<span data-ttu-id="bdc91-251">En la carpeta PipelinesAndSchemas:</span><span class="sxs-lookup"><span data-stu-id="bdc91-251">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="bdc91-252">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="bdc91-252">PropertySchema.xsd</span></span>|<span data-ttu-id="bdc91-253">Esquema de propiedad del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-253">Property schema for the sample.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="bdc91-254">Crear e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdc91-254">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="bdc91-255">Utilice el siguiente procedimiento para crear e inicializar el ejemplo de composición.</span><span class="sxs-lookup"><span data-stu-id="bdc91-255">Use the following procedure to build and initialize the Compose sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="bdc91-256">Para crear e inicializar el ejemplo de composición</span><span class="sxs-lookup"><span data-stu-id="bdc91-256">To build and initialize the Compose sample</span></span>  
  
1.  <span data-ttu-id="bdc91-257">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="bdc91-257">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="bdc91-258">\<Ruta de acceso de ejemplos > \Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="bdc91-258">\<Samples Path>\Pipelines\ComposedMessageProcessor</span></span>  
  
2.  <span data-ttu-id="bdc91-259">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bdc91-259">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="bdc91-260">Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta:</span><span class="sxs-lookup"><span data-stu-id="bdc91-260">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="bdc91-261">\<Ruta de acceso de ejemplos > \Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="bdc91-261">\<Samples Path>\Pipelines\ComposedMessageProcessor</span></span>  
  
    -   <span data-ttu-id="bdc91-262">Compila los proyectos de Visual Studio para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdc91-262">Compiles the Visual Studio projects for this sample.</span></span>  
  
    -   <span data-ttu-id="bdc91-263">Crea una aplicación nueva llamada "CMP Sample" e implementa los ensamblados de ejemplo en ella.</span><span class="sxs-lookup"><span data-stu-id="bdc91-263">Creates a new application called "CMP Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="bdc91-264">Crea y enlaza la ubicación de recepción de BizTalk Server y los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="bdc91-264">Creates and binds the BizTalk Server receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="bdc91-265">Da de alta e inicia la orquestación, habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="bdc91-265">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="bdc91-266">Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="bdc91-266">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="bdc91-267">Utilice que este par de claves se usa para firmar los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="bdc91-267">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="bdc91-268">Antes de tratar de ejecutar este ejemplo, confirme que BizTalk Server no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="bdc91-268">Before attempting to run this sample, confirm that BizTalk Server did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="bdc91-269">Para deshacer los cambios realizados por Setup.bat, debe llevar a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bdc91-269">To undo changes made by Setup.bat, you must do the following:</span></span>  
  
    1.  <span data-ttu-id="bdc91-270">Detenga y reinicie la instancia de host desde la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="bdc91-270">Stop and restart the host instance from the BizTalk Server Administration console.</span></span>  
  
    2.  <span data-ttu-id="bdc91-271">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="bdc91-271">Run Cleanup.bat.</span></span> <span data-ttu-id="bdc91-272">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="bdc91-272">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="bdc91-273">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdc91-273">Running the sample</span></span>  
 <span data-ttu-id="bdc91-274">Utilice el siguiente procedimiento para ejecutar el ejemplo ComposedMessageProcessor.</span><span class="sxs-lookup"><span data-stu-id="bdc91-274">Use the following procedure to run the ComposedMessageProcessor sample.</span></span>  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a><span data-ttu-id="bdc91-275">Para ejecutar el ejemplo ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="bdc91-275">To run the ComposedMessageProcessor sample</span></span>  
  
1.  <span data-ttu-id="bdc91-276">Copie el archivo de texto CMPInput.txt ubicado en la carpeta PipelinesAndSchemas.</span><span class="sxs-lookup"><span data-stu-id="bdc91-276">Copy the text file CMPInput.txt located in the PipelinesAndSchemas folder.</span></span> <span data-ttu-id="bdc91-277">Pegue el archivo en la carpeta In.</span><span class="sxs-lookup"><span data-stu-id="bdc91-277">Paste the file into the folder In.</span></span>  
  
2.  <span data-ttu-id="bdc91-278">Observe el archivo de texto que se ha creado en la carpeta Out. El archivo contiene los mismos registros que CMPInput.txt, pero el formato de datos del archivo es diferente.</span><span class="sxs-lookup"><span data-stu-id="bdc91-278">Observe the text file created in the folder Out. This file contains the same records as the CMPInput.txt, but the format of data in the file is different.</span></span>  
  
     <span data-ttu-id="bdc91-279">A medida que el mensaje pasa a través de BizTalk Server, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bdc91-279">As the message passes through the BizTalk Server, the following happens:</span></span>  
  
    1.  <span data-ttu-id="bdc91-280">El mensaje se desensambla y se convierte en mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="bdc91-280">The message gets disassembled and converted into XML messages.</span></span> <span data-ttu-id="bdc91-281">Cada mensaje se asigna a un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="bdc91-281">Each message is mapped to a different format.</span></span>  
  
    2.  <span data-ttu-id="bdc91-282">Todos los mensajes asignados se ensamblan juntos y se convierten a archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="bdc91-282">All mapped messages are assembled together and converted into the flat file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc91-283">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdc91-283">See Also</span></span>  
 [<span data-ttu-id="bdc91-284">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="bdc91-284">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)