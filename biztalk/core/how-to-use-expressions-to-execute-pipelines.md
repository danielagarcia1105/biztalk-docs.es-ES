---
title: Cómo usar expresiones para ejecutar canalizaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ExecuteReceivePipeline() method
- pipelines, schema resolution
- ExecuteSendPipeline() method
- SendPipelineInputMessages class
- pipelines, restrictions
- pipelines, errors
- XLANGPipelineManager class
- receive pipelines, orchestrations
- ReceivePipelineOutputMessages class
- orchestrations, pipelines
- pipelines, component types
- send pipelines, orchestrations
- pipelines, states
- pipelines, executing
- Microsoft.XLANGs.Pipeline namespace
- pipelines, transactional
- pipelines, orchestrations
- Message Assignment shape [Orchestration Designer], pipelines
ms.assetid: f947fa73-526c-4747-8de7-df557a93056c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8c0b0e79f79c351d84ed22b12a5eba8bdc9f3a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005173"
---
# <a name="how-to-use-expressions-to-execute-pipelines"></a><span data-ttu-id="06eb2-102">Cómo usar expresiones para ejecutar canalizaciones</span><span class="sxs-lookup"><span data-stu-id="06eb2-102">How to Use Expressions to Execute Pipelines</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="06eb2-103"> tiene la capacidad de llamar de forma sincrónica a una canalización desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-103"> has the ability to synchronously call a pipeline from within an Orchestration.</span></span> <span data-ttu-id="06eb2-104">Esto permite a las orquestaciones aprovechar el procesamiento de mensajes encapsulado en una canalización (tanto envío como recepción) frente a un conjunto de datos sin tener que enviar los datos a través de la infraestructura de mensajería.</span><span class="sxs-lookup"><span data-stu-id="06eb2-104">This enables orchestrations to leverage the message processing encapsulated within a pipeline (either send or receive) against a body of data without having to send that data through the messaging infrastructure.</span></span>  
  
 <span data-ttu-id="06eb2-105">Puede usar esta característica para permitir que una orquestación llame a una canalización de envío a fin de agregar varios mensajes en un único intercambio de salida.</span><span class="sxs-lookup"><span data-stu-id="06eb2-105">You can use this feature to enable an orchestration to call a send pipeline in order to aggregate several messages into a single outgoing interchange.</span></span> <span data-ttu-id="06eb2-106">A la inversa, una orquestación podría llamar a una canalización de recepción para descodificar y desensamblar un intercambio obtenido fuera de la infraestructura de mensajería, sin incurrir en los costos de procesamiento derivados de atravesar el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="06eb2-106">Conversely, an orchestration could call a receive pipeline to decode and disassemble an interchange obtained outside of the messaging infrastructure, without incurring the processing costs of going through the message box.</span></span>  
  
## <a name="details"></a><span data-ttu-id="06eb2-107">Detalles</span><span class="sxs-lookup"><span data-stu-id="06eb2-107">Details</span></span>  
 <span data-ttu-id="06eb2-108">Las orquestaciones utilizan métodos en el **XLANGPipelineManager** clase (en el **Microsoft.XLANGs.Pipeline** espacio de nombres) para llamar a enviar o canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="06eb2-108">Orchestrations use methods in the **XLANGPipelineManager** class (in the **Microsoft.XLANGs.Pipeline** namespace) to call send or receive pipelines.</span></span>  <span data-ttu-id="06eb2-109">Una canalización de recepción consume un solo mensaje o un intercambio y produce cero o más mensajes, del mismo modo que cuando la canalización se ejecuta al recibir un mensaje dentro de la mensajería de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="06eb2-109">A Receive pipeline consumes either a single message or an interchange and yields zero or more messages, just as when the pipeline executes in the context of receiving a message within BizTalk messaging.</span></span> <span data-ttu-id="06eb2-110">Una canalización de envío consume uno o más mensajes y produce un solo mensaje o intercambio, también del mismo modo que cuando la canalización se ejecuta al enviar un mensaje dentro de la mensajería de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="06eb2-110">A Send pipeline consumes one or more messages and yields a single message or interchange, again, just as when the pipeline executes in the context of sending a message within BizTalk messaging.</span></span>  
  
## <a name="calling-a-receive-pipeline"></a><span data-ttu-id="06eb2-111">Llamar a una canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="06eb2-111">Calling a Receive Pipeline</span></span>  
 <span data-ttu-id="06eb2-112">Para poder llamar a una canalización de recepción desde una orquestación, la aplicación llama a la **ExecuteReceivePipeline()** método de la **XLANGPipelineManager** clase.</span><span class="sxs-lookup"><span data-stu-id="06eb2-112">In order to call a receive pipeline from within an orchestration, the application calls the **ExecuteReceivePipeline()** method of the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="06eb2-113">Este método consume un solo intercambio y devuelve una colección de cero o más mensajes (incluidos en una instancia de la **ReceivePipelineOutputMessages** clase).</span><span class="sxs-lookup"><span data-stu-id="06eb2-113">This method consumes a single interchange and returns a collection of zero or more messages (contained in an instance of the **ReceivePipelineOutputMessages** class).</span></span> <span data-ttu-id="06eb2-114">La sintaxis de este método se detalla en la referencia de biblioteca de clases de .NET para la **XLANGPipelineManager** clase.</span><span class="sxs-lookup"><span data-stu-id="06eb2-114">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  
  
 <span data-ttu-id="06eb2-115">La interfaz API para ejecutar una canalización de recepción desde una orquestación es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="06eb2-115">The API for executing a receive pipeline from within an orchestration is:</span></span>  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 <span data-ttu-id="06eb2-116">Una llamada a una canalización de recepción se suele realizar un **expresión** forma dentro de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-116">A call to a receive pipeline would typically be done in an **Expression** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="06eb2-117">Para llamar a una canalización de recepción desde una orquestación, el programador debe hacer referencia al ensamblado de canalización en el proyecto de orquestación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-117">In order to call a receive pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span> <span data-ttu-id="06eb2-118">A continuación se muestra un ejemplo de una orquestación que llama a una canalización de recepción:</span><span class="sxs-lookup"><span data-stu-id="06eb2-118">Following is an example of an orchestration that calls a receive pipeline:</span></span>  
  
 <span data-ttu-id="06eb2-119">![Pantalla de canalización de recepción de llamada](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="06eb2-119">![Calling Receive Pipeline screen](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span></span>  
  
 <span data-ttu-id="06eb2-120">Para obtener un ejemplo más detallado, vea el ejemplo de SDK [procesador de mensajes compuestos (ejemplo de BizTalk Server)](../core/composed-message-processor-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="06eb2-120">For a more detailed example, see the SDK sample [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06eb2-121">Una variable de tipo **ReceivePipelineOutputMessages** se pueden declarar únicamente dentro de un ámbito atómico de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-121">A variable of type **ReceivePipelineOutputMessages** can be declared only within an atomic scope in an orchestration.</span></span>  <span data-ttu-id="06eb2-122">Esto se debe a que las variables de este tipo no son serializables y, por lo tanto, no sobrevivirían a la persistencia de la orquestación. Además, las orquestaciones nunca persisten al ejecutarse en un ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="06eb2-122">This is because variables of this type are not serializable and thus would not survive persistence of the orchestration, and orchestrations are never persisted while executing within an atomic scope.</span></span>  <span data-ttu-id="06eb2-123">Esto significa que una canalización de recepción solo se puede ejecutar en un ámbito atómico.</span><span class="sxs-lookup"><span data-stu-id="06eb2-123">This means that a receive pipeline can be executed only within an atomic scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06eb2-124">Al llamar a **PassThruReceive** canalización o componente de canalización personalizado desde una orquestación, debe declarar el tipo de variable para el mensaje entrante como System.Xml.XmlDocument, independientemente del tipo de mensaje entrante es XML o no .</span><span class="sxs-lookup"><span data-stu-id="06eb2-124">When calling **PassThruReceive** pipeline or custom pipeline component from within an orchestration, you must declare the variable type for incoming message as System.Xml.XmlDocument despite of the incoming message type is XML or not.</span></span> <span data-ttu-id="06eb2-125">Por lo tanto, puede producirse una excepción si intenta trabajar con él si el mensaje entrante no es un mensaje XML, como un mensaje de archivo de texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="06eb2-125">Therefore, you may encounter exception if you try to operate on it if the incoming message is a non-XML message such as a flat file format message.</span></span> <span data-ttu-id="06eb2-126">Esto se debe a que el motor de orquestaciones pretende usar System.Xml.XmlDocument para cualquier tipo de mensaje entrante en el escenario descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="06eb2-126">This is because of that orchestration engine intends to use System.Xml.XmlDocument for any type of incoming message in the scenario described above.</span></span>  
  
## <a name="calling-a-send-pipeline"></a><span data-ttu-id="06eb2-127">Llamar a una canalización de envío</span><span class="sxs-lookup"><span data-stu-id="06eb2-127">Calling a Send Pipeline</span></span>  
 <span data-ttu-id="06eb2-128">Para llamar a una canalización de envío desde una orquestación, la aplicación llama a la **ExecuteSendPipeline()** método de la **XLANGPipelineManager** clase.</span><span class="sxs-lookup"><span data-stu-id="06eb2-128">To call a send pipeline from within an orchestration, the application calls the **ExecuteSendPipeline()** method of the **XLANGPipelineManager** class.</span></span> <span data-ttu-id="06eb2-129">Este método consume una colección de uno o más mensajes (incluidos en una instancia de la **SendPipelineInputMessages** clase) y devuelve un único intercambio.</span><span class="sxs-lookup"><span data-stu-id="06eb2-129">This method consumes a collection of one or more messages (contained in an instance of the **SendPipelineInputMessages** class) and returns a single interchange.</span></span> <span data-ttu-id="06eb2-130">La sintaxis de este método se detalla en la referencia de biblioteca de clases de .NET para la **XLANGPipelineManager** clase.</span><span class="sxs-lookup"><span data-stu-id="06eb2-130">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="06eb2-131">Dado que la ejecución de una canalización de envío produce un nuevo intercambio, la llamada a **ExecuteSendPipeline()** método debe realizarse dentro de una forma de asignación de mensajes, como tal:</span><span class="sxs-lookup"><span data-stu-id="06eb2-131">Because execution of a send pipeline yields a new interchange, the call to **ExecuteSendPipeline()** method must be made within a message assignment shape, as such:</span></span>  
  
 <span data-ttu-id="06eb2-132">La interfaz API para ejecutar una canalización de envío desde una orquestación es:</span><span class="sxs-lookup"><span data-stu-id="06eb2-132">The API for executing a send pipeline from within an orchestration is:</span></span>  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 <span data-ttu-id="06eb2-133">Una llamada a una canalización de envío debe realizarse dentro de un **asignación de mensajes** forma dentro de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-133">A call to a send pipeline must be done in a **Message Assignment** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="06eb2-134">Para llamar a una canalización de envío desde una orquestación, el programador debe hacer referencia al ensamblado de canalización en el proyecto de orquestación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-134">In order to call a send pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span>  <span data-ttu-id="06eb2-135">A continuación se muestra un ejemplo de una orquestación que llama a una canalización de envío:</span><span class="sxs-lookup"><span data-stu-id="06eb2-135">An example of an orchestration that calls a send pipeline:</span></span>  
  
 <span data-ttu-id="06eb2-136">![Pantalla de canalización de envío llamada](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="06eb2-136">![Calling Send Pipeline screen](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06eb2-137">Al llamar a la canalización XMLTransmit predeterminada, debe establecer la propiedad de contexto de mensaje XMLNORM.EnvelopeSpecName en el nombre completo del esquema de sobres.</span><span class="sxs-lookup"><span data-stu-id="06eb2-137">When calling the default XMLTransmit pipeline, you must set the message context property XMLNORM.EnvelopeSpecName to the fully qualified name of the Envelope schema.</span></span> <span data-ttu-id="06eb2-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="06eb2-138">For example:</span></span>  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 <span data-ttu-id="06eb2-139">Para obtener un ejemplo más detallado, vea el ejemplo de SDK [agregador (ejemplo de BizTalk Server)](../core/aggregator-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="06eb2-139">For a more detailed example, see the SDK sample [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="pipeline-execution---behavioral-differences"></a><span data-ttu-id="06eb2-140">Ejecución de canalización: diferencias de comportamiento</span><span class="sxs-lookup"><span data-stu-id="06eb2-140">Pipeline Execution - Behavioral Differences</span></span>  
 <span data-ttu-id="06eb2-141">La ejecución de una canalización de envío o recepción llamada por una orquestación es, en gran parte, la misma que cuando la misma canalización se ejecuta en una infraestructura de mensajería (es decir, en la ubicación de recepción o en el puerto de envío).</span><span class="sxs-lookup"><span data-stu-id="06eb2-141">The execution of a send or receive pipeline when called by an orchestration is predominantly the same as when the same pipeline executes within the messaging infrastructure (i.e. at receive location or send port).</span></span>  <span data-ttu-id="06eb2-142">No obstante, hay algunas diferencias de comportamiento que se detallan a continuación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-142">However, there are certain behavioral differences that are noted below.</span></span>  
  
### <a name="differences-within-pipeline-stages"></a><span data-ttu-id="06eb2-143">Diferencias dentro de las fases de canalización</span><span class="sxs-lookup"><span data-stu-id="06eb2-143">Differences Within Pipeline Stages</span></span>  
 <span data-ttu-id="06eb2-144">La ejecución de las fases dentro de una canalización de envío o recepción a la que se llama desde una orquestación es prácticamente idéntica a la ejecución de dichas fases cuando se llama a la canalización desde la infraestructura de mensajería de BizTalk, con las excepciones que se apuntan a continuación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-144">The execution of the stages within a send or receive pipeline that is called from within an orchestration is nearly identical to the execution of those stages when the pipeline is called from the BizTalk messaging infrastructure, with the exceptions noted by stage below.</span></span>  
  
-   <span data-ttu-id="06eb2-145">Ensamblador/desensamblador: El ensamblador y desensamblador no procesarán **perfil de seguimiento** datos.</span><span class="sxs-lookup"><span data-stu-id="06eb2-145">Assembler/Disassembler:  The assembler and disassembler stages will not process **Tracking Profile** data.</span></span>  
  
-   <span data-ttu-id="06eb2-146">Codificador/descodificador: El codificador MIME firma digitalmente los mensajes mediante el certificado configurado en el host que está asociado el host.</span><span class="sxs-lookup"><span data-stu-id="06eb2-146">Encoder/Decoder:  The MIME encoder digitally signs messages using the certificate configured at the host with which the host is associated.</span></span>  <span data-ttu-id="06eb2-147">El codificador SMIME cifra mensajes mediante el certificado en el contexto del mensaje pasado a la canalización.</span><span class="sxs-lookup"><span data-stu-id="06eb2-147">The SMIME encoder encrypts messages using the certificate on the context of the message passed into the pipeline.</span></span>  
  
### <a name="schema-resolution"></a><span data-ttu-id="06eb2-148">Resolución de esquemas</span><span class="sxs-lookup"><span data-stu-id="06eb2-148">Schema Resolution</span></span>  
 <span data-ttu-id="06eb2-149">Hay dos algoritmos de búsqueda de esquemas que son compatibles al ejecutar una canalización desde una orquestación:</span><span class="sxs-lookup"><span data-stu-id="06eb2-149">There are two schema lookup algorithms that are supported when executing a pipeline from an orchestration:</span></span>  
  
- <span data-ttu-id="06eb2-150">Resolución por tipo</span><span class="sxs-lookup"><span data-stu-id="06eb2-150">Resolution by type</span></span>  
  
- <span data-ttu-id="06eb2-151">Resolución por nombre</span><span class="sxs-lookup"><span data-stu-id="06eb2-151">Resolution by name</span></span>  
  
  <span data-ttu-id="06eb2-152">En los casos en los que se implementan esquemas duplicados, la lógica del algoritmo para seleccionar el esquema adecuado es idéntica a la usada al ejecutarlo en el contexto de la infraestructura de mensajería.</span><span class="sxs-lookup"><span data-stu-id="06eb2-152">In cases where duplicate schemas are deployed, the algorithm's logic for selecting the appropriate schema is identical to that used when executing in the context of the messaging infrastructure.</span></span>  
  
### <a name="transactional-pipelines"></a><span data-ttu-id="06eb2-153">Canalizaciones transaccionales</span><span class="sxs-lookup"><span data-stu-id="06eb2-153">Transactional Pipelines</span></span>  
 <span data-ttu-id="06eb2-154">Las canalizaciones cuyas etapas llaman a componentes transaccionales no tendrán un contexto transaccional disponible.</span><span class="sxs-lookup"><span data-stu-id="06eb2-154">Pipelines whose stages call transactional components will not have a transactional context available.</span></span>  <span data-ttu-id="06eb2-155">Todas las llamadas a **ipipelinecontext.getTransaction ()** producirá **NotSupportedException**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-155">Any call to **IPipelineContext.GetTransaction()** will throw **NotSupportedException**.</span></span>  <span data-ttu-id="06eb2-156">Esto no impide la ejecución de tal tipo de canalizaciones desde una orquestación. No obstante, significa que la canalización tendrá que detectar y controlar esta situación.</span><span class="sxs-lookup"><span data-stu-id="06eb2-156">This does not preclude execution of such a pipeline from an orchestration, but it does mean that the pipeline will have to detect and handle this situation.</span></span>  
  
### <a name="message-destination"></a><span data-ttu-id="06eb2-157">Destino de mensaje</span><span class="sxs-lookup"><span data-stu-id="06eb2-157">Message Destination</span></span>  
 <span data-ttu-id="06eb2-158">En este contexto, no se admite controlar el destino de mensaje mediante componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="06eb2-158">Controlling message destination by pipeline components is not supported in this context.</span></span>  <span data-ttu-id="06eb2-159">Establecer las propiedades de contexto **MessageDestination** o **SuspendOnRoutingFailure** provocará un **XLANGPipelineManagerException** que se produzca.</span><span class="sxs-lookup"><span data-stu-id="06eb2-159">Setting the context properties **MessageDestination** or **SuspendOnRoutingFailure** will cause an **XLANGPipelineManagerException** to be thrown.</span></span>  
  
### <a name="pipeline-component-types"></a><span data-ttu-id="06eb2-160">Tipos de componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="06eb2-160">Pipeline Component Types</span></span>  
 <span data-ttu-id="06eb2-161">Los componentes de canalización deben estar basados en el siguiente orden para poder ser llamados desde una orquestación:</span><span class="sxs-lookup"><span data-stu-id="06eb2-161">Pipeline components must be based on the following in order to be called from within an orchestration:</span></span>  
  
-   <span data-ttu-id="06eb2-162">.NET Framework v1.1</span><span class="sxs-lookup"><span data-stu-id="06eb2-162">.NET Framework v1.1</span></span>  
  
-   <span data-ttu-id="06eb2-163">.NET Framework v2.0</span><span class="sxs-lookup"><span data-stu-id="06eb2-163">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="06eb2-164">.NET Framework v3.0</span><span class="sxs-lookup"><span data-stu-id="06eb2-164">.NET Framework v3.0</span></span>  
  
-   <span data-ttu-id="06eb2-165">.NET Framework v3.5</span><span class="sxs-lookup"><span data-stu-id="06eb2-165">.NET Framework v3.5</span></span>  
  
-   <span data-ttu-id="06eb2-166">.NET Framework v4.0</span><span class="sxs-lookup"><span data-stu-id="06eb2-166">.NET Framework v4.0</span></span>  
  
-   <span data-ttu-id="06eb2-167">.NET Framework v2.0</span><span class="sxs-lookup"><span data-stu-id="06eb2-167">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="06eb2-168">COM</span><span class="sxs-lookup"><span data-stu-id="06eb2-168">COM</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="06eb2-169">Restrictions</span><span class="sxs-lookup"><span data-stu-id="06eb2-169">Restrictions</span></span>  
 <span data-ttu-id="06eb2-170">Los siguientes tipos de canalizaciones **no** ejecutarse desde una orquestación:</span><span class="sxs-lookup"><span data-stu-id="06eb2-170">The following types of pipelines **cannot** be executed from within an orchestration:</span></span>  
  
- <span data-ttu-id="06eb2-171">Canalizaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="06eb2-171">Transactional pipelines</span></span>  
  
- <span data-ttu-id="06eb2-172">Canalizaciones recuperables</span><span class="sxs-lookup"><span data-stu-id="06eb2-172">Recoverable pipelines</span></span>  
  
- <span data-ttu-id="06eb2-173">Canalizaciones que llaman a la API de interceptor de BAM (un **NotSupportedException** se inicia).</span><span class="sxs-lookup"><span data-stu-id="06eb2-173">Pipelines which call the BAM interceptor API (a **NotSupportedException** will be thrown).</span></span>  
  
- <span data-ttu-id="06eb2-174">La misma instancia de canalización no se puede ejecutar en distintas ramas de la forma paralela a menos que esté colocada en un ámbito sincronizado en cada rama.</span><span class="sxs-lookup"><span data-stu-id="06eb2-174">The same pipeline instance cannot be executed in different branches of the parallel shape unless it is placed in a synchronized scope in every branch.</span></span>  
  
- <span data-ttu-id="06eb2-175">Canalizaciones existentes (ensamblados) que se generaron en el SDK de [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06eb2-175">Existing pipelines (assemblies) that were built against the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK.</span></span>  
  
## <a name="failure-modes-and-effects"></a><span data-ttu-id="06eb2-176">Modos de error y efectos</span><span class="sxs-lookup"><span data-stu-id="06eb2-176">Failure Modes and Effects</span></span>  
 <span data-ttu-id="06eb2-177">Cualquier error en la ejecución de canalizaciones que podría haber tenido como consecuencia un mensaje suspendido si se hubiese llamado a esta canalización desde la infraestructura de mensajería de BizTalk Server, generará una excepción en su lugar.</span><span class="sxs-lookup"><span data-stu-id="06eb2-177">Any failure in pipeline execution which would have resulted in a suspended message were this pipeline to be called from within the BizTalk Server Messaging Infrastructure will instead result in an exception being thrown.</span></span>  <span data-ttu-id="06eb2-178">La excepción producida es de tipo **Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**.</span><span class="sxs-lookup"><span data-stu-id="06eb2-178">The exception thrown is of type **Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**.</span></span>  <span data-ttu-id="06eb2-179">Esta excepción generada se puede controlar en un bloque de filtrado dentro de la orquestación que llama.</span><span class="sxs-lookup"><span data-stu-id="06eb2-179">This thrown exception can be handled in a catch block within the calling orchestration.</span></span>  <span data-ttu-id="06eb2-180">Si la orquestación no filtra la excepción generada, el motor XLANGs notifica un error cuyo texto incluye la información de excepción en la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="06eb2-180">If the orchestration does not catch the thrown exception, the XLANGs engine reports an error the text of which includes the exception information in the thrown exception.</span></span>  
  
 <span data-ttu-id="06eb2-181">La excepción da formato a los mensajes de error generados por los componentes de la canalización.</span><span class="sxs-lookup"><span data-stu-id="06eb2-181">The exception performs formatting of the error messages generated by the pipeline components.</span></span>  
  
 <span data-ttu-id="06eb2-182">El **mensaje** propiedad de la **XLANGPipelineManagerException** clase contiene detalles del error de ejecución de la canalización.</span><span class="sxs-lookup"><span data-stu-id="06eb2-182">The **Message** property of the **XLANGPipelineManagerException** class contains details of the pipeline's execution error.</span></span> <span data-ttu-id="06eb2-183">Estos datos tienen el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="06eb2-183">This detail is in the following format:</span></span>  
  
- <span data-ttu-id="06eb2-184">Se ha producido un error al ejecutar canalización \<tipo de canalización\>.</span><span class="sxs-lookup"><span data-stu-id="06eb2-184">There was a failure executing pipeline \<pipeline type\>.</span></span>  <span data-ttu-id="06eb2-185">Detalles del error \<con el formato de mensaje de error\>.</span><span class="sxs-lookup"><span data-stu-id="06eb2-185">Error details \<formatted error message\>.</span></span>  
  
  <span data-ttu-id="06eb2-186">En este mensaje, \<tipo de canalización\> es el nombre de la clase de canalización y \<con el formato de mensaje de error\> es una descripción del error específico que se produjeron durante la ejecución de la canalización.</span><span class="sxs-lookup"><span data-stu-id="06eb2-186">In this message, \<pipeline type\> is the name of the pipeline class and \<formatted error message\> is a description of the specific failure that occurred during pipeline execution.</span></span>  
  
  <span data-ttu-id="06eb2-187">Por ejemplo, si una orquestación llama a una canalización de recepción y se produce un error en la ejecución de dicha canalización porque ninguno de los componentes de la canalización reconoce el mensaje, los valores de la **XLANGPipelineManagerException**de propiedades sería ser:</span><span class="sxs-lookup"><span data-stu-id="06eb2-187">For example, if an orchestration calls a receive pipeline and that pipeline's execution fails because none of the pipeline's components recognizes the message, the values of the **XLANGPipelineManagerException**'s properties would be:</span></span>  
  
|<span data-ttu-id="06eb2-188">Propiedad XLANGPipelineManagerException</span><span class="sxs-lookup"><span data-stu-id="06eb2-188">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="06eb2-189">Valor</span><span class="sxs-lookup"><span data-stu-id="06eb2-189">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="06eb2-190">de mensaje</span><span class="sxs-lookup"><span data-stu-id="06eb2-190">Message</span></span>|<span data-ttu-id="06eb2-191">Error al ejecutar la canalización de recepción "MyPipelines.ReceivePipeline".</span><span class="sxs-lookup"><span data-stu-id="06eb2-191">There was a failure executing the receive pipeline "MyPipelines.ReceivePipeline".</span></span> <span data-ttu-id="06eb2-192">Detalles del error: "no hay componentes de la fase Desensamblar pueden reconocer los datos.</span><span class="sxs-lookup"><span data-stu-id="06eb2-192">Error details: "No Disassemble stage components can recognize the data.</span></span>|  
|<span data-ttu-id="06eb2-193">Componente</span><span class="sxs-lookup"><span data-stu-id="06eb2-193">Component</span></span>|<span data-ttu-id="06eb2-194">String.Empty</span><span class="sxs-lookup"><span data-stu-id="06eb2-194">String.Empty</span></span>|  
  
 <span data-ttu-id="06eb2-195">Otro ejemplo, si una orquestación llama a una canalización de envío y se produce un error en la ejecución de dicha canalización porque hay un error de validación, el texto en el **mensaje** propiedad de **XLANGPipelineManagerException**sería:</span><span class="sxs-lookup"><span data-stu-id="06eb2-195">As another example, if an orchestration calls a send pipeline and that pipeline's execution fails because there is a validation failure, the text in the **Message** property of **XLANGPipelineManagerException** would be:</span></span>  
  
|<span data-ttu-id="06eb2-196">Propiedad XLANGPipelineManagerException</span><span class="sxs-lookup"><span data-stu-id="06eb2-196">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="06eb2-197">Valor</span><span class="sxs-lookup"><span data-stu-id="06eb2-197">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="06eb2-198">de mensaje</span><span class="sxs-lookup"><span data-stu-id="06eb2-198">Message</span></span>|<span data-ttu-id="06eb2-199">Error al ejecutar la canalización de envío "MyPipelines.SendPipeline".</span><span class="sxs-lookup"><span data-stu-id="06eb2-199">There was a failure executing the send pipeline "MyPipelines.SendPipeline".</span></span>  <span data-ttu-id="06eb2-200">Detalles del error: "no se pudo validar el documento:" el \<nombre del elemento\> elemento no es válido: el valor \<valor del elemento\> no es válido según su tipo de datos 'String' – error de restricción de patrón. ""</span><span class="sxs-lookup"><span data-stu-id="06eb2-200">Error details:  "Failed to validate the document: "The \<element name\> element is invalid - The value \<element value\> is invalid according to its datatype 'String' - The Pattern constraint failed.""</span></span>|  
|<span data-ttu-id="06eb2-201">Componente</span><span class="sxs-lookup"><span data-stu-id="06eb2-201">Component</span></span>|<span data-ttu-id="06eb2-202">“Microsoft.BizTalk.Component.XmlValidator”</span><span class="sxs-lookup"><span data-stu-id="06eb2-202">“Microsoft.BizTalk.Component.XmlValidator”</span></span>|