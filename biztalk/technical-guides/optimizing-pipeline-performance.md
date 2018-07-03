---
title: Optimizar el rendimiento de la canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5137747-0dcf-4c96-90a7-01afb92f56a6
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7102eb3fc0f6f7b1ef16a319e5e04daff6d544d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007877"
---
# <a name="optimizing-pipeline-performance"></a><span data-ttu-id="432e9-102">Optimizar el rendimiento de la canalización</span><span class="sxs-lookup"><span data-stu-id="432e9-102">Optimizing Pipeline Performance</span></span>
<span data-ttu-id="432e9-103">En este tema se describe las directrices para optimizar el rendimiento de las canalizaciones de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="432e9-103">This topic describes guidelines for optimizing performance of pipelines in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a><span data-ttu-id="432e9-104">Procedimientos recomendados para optimizar el rendimiento de las canalizaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="432e9-104">Best practices for optimizing performance of BizTalk Server pipelines</span></span>  
  
1. <span data-ttu-id="432e9-105">Dado que los componentes de canalización tienen un impacto significativo en el rendimiento (por ejemplo, un componente de canalización de paso realiza hasta un 30 por ciento mejor que un componente de canalización de ensamblador y desensamblador XML), asegúrese de que se realice cualquier componente de canalización personalizado óptimamente antes de implementarlos en su implementación.</span><span class="sxs-lookup"><span data-stu-id="432e9-105">Because pipeline components have a significant impact on performance (for example, a pass-through pipeline component performs up to 30 percent better than an XML assembler/disassembler pipeline component), make sure that any custom pipeline components perform optimally before implementing them in your deployment.</span></span> <span data-ttu-id="432e9-106">Minimizar el número de componentes de canalización de las canalizaciones personalizadas si desea maximizar el rendimiento general de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="432e9-106">Minimize the number of pipeline components in your custom pipelines if you want to maximize the overall performance of your BizTalk application.</span></span>  
  
2. <span data-ttu-id="432e9-107">También puede mejorar el rendimiento general al reducir la frecuencia de persistencia del mensaje en el componente de canalización y codificando el componente para minimizar la redundancia.</span><span class="sxs-lookup"><span data-stu-id="432e9-107">You also can improve overall performance by reducing the message persistence frequency in your pipeline component and by coding your component to minimize redundancy.</span></span> <span data-ttu-id="432e9-108">Todos los ensamblados personalizados y en particular los artefactos que podrían afectar a rendimiento, como los componentes de seguimiento personalizado, se deben probar por separado en condiciones de mucha carga para observar su comportamiento cuando el sistema funciona con la máxima capacidad y buscar posibles cuellos de botella.</span><span class="sxs-lookup"><span data-stu-id="432e9-108">Every custom assembly and in particular artifacts that could potentially disrupt performance, like custom tracking components, should be tested separately under heavy load condition to observe their behavior when the system is working at full capacity and to find any possible bottlenecks.</span></span>  
  
3. <span data-ttu-id="432e9-109">Si tiene que leer el mensaje entrante dentro de un componente de canalización, evite la carga de todo el documento en memoria mediante una **XmlDocument** objeto.</span><span class="sxs-lookup"><span data-stu-id="432e9-109">If you need to read the inbound message inside a pipeline component, avoid loading the entire document into memory using an **XmlDocument** object.</span></span> <span data-ttu-id="432e9-110">La cantidad de espacio necesario por una instancia de la **XmlDocument** clase para cargar y crear una representación en memoria de un documento XML es hasta 10 veces el tamaño de mensaje real.</span><span class="sxs-lookup"><span data-stu-id="432e9-110">The amount of space required by an instance of the **XmlDocument** class to load and create an in-memory representation of a XML document is up to 10 times the actual message size.</span></span> <span data-ttu-id="432e9-111">Para leer un mensaje, se debe usar un **XmlTextReader** objeto junto con una instancia de las clases siguientes:</span><span class="sxs-lookup"><span data-stu-id="432e9-111">In order to read a message, you should use an **XmlTextReader** object along with an instance of the following classes:</span></span>  
  
   -   <span data-ttu-id="432e9-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\ SchemaResolverComponent\SchemaResolverFlatFileDasm.</span><span class="sxs-lookup"><span data-stu-id="432e9-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
   -   <span data-ttu-id="432e9-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.</span><span class="sxs-lookup"><span data-stu-id="432e9-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.</span></span>  
  
   -   <span data-ttu-id="432e9-114">**SeekAbleReadOnlyStream** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\SchemaResolverComponent\ SchemaResolverFlatFileDasm.</span><span class="sxs-lookup"><span data-stu-id="432e9-114">**SeekAbleReadOnlyStream** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
4. <span data-ttu-id="432e9-115">Utilice la PassThruReceive y las canalizaciones estándares de PassThruTransmit siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="432e9-115">Use the PassThruReceive and the PassThruTransmit standard pipelines whenever possible.</span></span> <span data-ttu-id="432e9-116">No contienen un componente de canalización y no realizan ningún procesamiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="432e9-116">They do not contain any pipeline component and do not perform any processing of the message.</span></span> <span data-ttu-id="432e9-117">Por este motivo, garantiza un rendimiento máximo en recibir o enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="432e9-117">For this reason, they ensure maximum performance in receiving or sending messages.</span></span> <span data-ttu-id="432e9-118">Puede usar una canalización PassThruReceive en una ubicación de recepción si necesita publicar un documento binario para BizTalk MessageBox y una canalización PassThruTransmit en un puerto de envío si necesita enviar un mensaje binario.</span><span class="sxs-lookup"><span data-stu-id="432e9-118">You can use a PassThruReceive pipeline on a receive location if you need to publish a binary document to the BizTalk MessageBox and a PassThruTransmit pipeline on a send port if you need to send out a binary message.</span></span> <span data-ttu-id="432e9-119">También puede usar la canalización PassThruTransmit en un puerto de envío físicos enlazado a una orquestación si el mensaje se ha formateado y está listo para su transmisión.</span><span class="sxs-lookup"><span data-stu-id="432e9-119">You can also use the PassThruTransmit pipeline on a physical send port bound to an orchestration if the message has been formatted and is ready to be transmitted.</span></span> <span data-ttu-id="432e9-120">Necesita usar un enfoque diferente si necesita realizar una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="432e9-120">You will need to use a different approach if you need to accomplish one of the following actions:</span></span>  
  
   - <span data-ttu-id="432e9-121">Promocionar propiedades en el contexto de un mensaje de archivo sin formato o XML entrante.</span><span class="sxs-lookup"><span data-stu-id="432e9-121">Promote properties on the context of an inbound XML or Flat File message.</span></span>  
  
   - <span data-ttu-id="432e9-122">Aplicar una asignación dentro de una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="432e9-122">Apply a map inside a receive location.</span></span>  
  
   - <span data-ttu-id="432e9-123">Aplicar una asignación de una orquestación que se suscribe a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="432e9-123">Apply a map in an orchestration that subscribes to a message.</span></span>  
  
   - <span data-ttu-id="432e9-124">Aplicar una asignación en un puerto de envío se suscribe a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="432e9-124">Apply a map on a send port that subscribes to a message.</span></span>  
  
     <span data-ttu-id="432e9-125">Para llevar a cabo una de estas acciones, de sondeo y detectar el tipo de documento dentro de la canalización de recepción y asigne el valor de (espacio de nombres #root-name) a la propiedad de contexto de MessageType.</span><span class="sxs-lookup"><span data-stu-id="432e9-125">To accomplish one of these actions, you must probe and discover the document type inside the receive pipeline and assign the (namespace#root-name) value to the MessageType context property.</span></span> <span data-ttu-id="432e9-126">Esta operación se realiza normalmente un componente de desensamblador como el componente de desensamblador Xml (XmlDasmComp) o el componente de desensamblador de archivos sin formato (FFDasmComp).</span><span class="sxs-lookup"><span data-stu-id="432e9-126">This operation is typically accomplished by a disassembler component such as the Xml Disassembler component (XmlDasmComp) or the Flat File disassembler component (FFDasmComp).</span></span> <span data-ttu-id="432e9-127">En este caso, deberá usar un estándar (por ejemplo, la canalización XmlReceive) o una canalización personalizada que contiene un estándar o un componente de desensamblador personalizado.</span><span class="sxs-lookup"><span data-stu-id="432e9-127">In this case, you need to use a standard (for instance, XmlReceive pipeline) or a custom pipeline that contains a standard or a custom disassembler component.</span></span>  
  
5. <span data-ttu-id="432e9-128">Adquiera recursos tan tarde como sea posible y liberarlos tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="432e9-128">Acquire resources as late as possible and release them as early as possible.</span></span> <span data-ttu-id="432e9-129">Por ejemplo, si necesita acceso a datos en una base de datos, abra la conexión tan tarde como sea posible y cerrarlo tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="432e9-129">For example, if you need to access data on a database, open the connection as late as possible and close it as soon as possible.</span></span> <span data-ttu-id="432e9-130">Utilice la instrucción using implícitamente liberar objetos desechables de C# o el bloque finally de una instrucción try-catch-finally desecharlo de forma explícita los objetos.</span><span class="sxs-lookup"><span data-stu-id="432e9-130">Use the C# using statement to implicitly release disposable objects or the finally block of a try-catch-finally statement to explicitly dispose your objects.</span></span> <span data-ttu-id="432e9-131">Instrumentar el código fuente para simplificar la depuración de los componentes.</span><span class="sxs-lookup"><span data-stu-id="432e9-131">Instrument your source code to make your components simple to debug.</span></span>  
  
6. <span data-ttu-id="432e9-132">Elimine los componentes de las canalizaciones que no son estrictamente necesarias para acelerar el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="432e9-132">Eliminate any components from your pipelines that are not strictly required to speed up message processing.</span></span>  
  
7. <span data-ttu-id="432e9-133">Dentro de una canalización de recepción, debe promover elementos en el contexto del mensaje solo si las necesita para el enrutamiento de mensajes (orquestaciones, puertos de envío) o degradación de propiedades de contexto del mensaje (puertos de envío).</span><span class="sxs-lookup"><span data-stu-id="432e9-133">Inside a receive pipeline, you should promote items to the message context only if you need them for message routing (Orchestrations, Send Ports) or demotion of message context properties (Send Ports).</span></span>  
  
8. <span data-ttu-id="432e9-134">Si necesita incluir metadatos con un mensaje y no usa los metadatos para fines de enrutamiento o degradación, use el **IBaseMessageContext.Write** método en lugar de la **IBaseMessageContext.Promote** método.</span><span class="sxs-lookup"><span data-stu-id="432e9-134">If you need to include metadata with a message, and you don't use the metadata for routing or demotion purposes, use the **IBaseMessageContext.Write** method instead of the **IBaseMessageContext.Promote** method.</span></span>  
  
9. <span data-ttu-id="432e9-135">Si necesita extraer información de un mensaje mediante una expresión XPath, evite la carga de todo el documento en memoria mediante una **XmlDocument** objeto solo para usar el **SelectNodes** o  **SelectSingleNode** métodos.</span><span class="sxs-lookup"><span data-stu-id="432e9-135">If you need to extract information from a message using an XPath expression, avoid loading the entire document into memory using an **XmlDocument** object just to use the **SelectNodes** or **SelectSingleNode** methods.</span></span> <span data-ttu-id="432e9-136">Como alternativa, use las técnicas descritas en [optimizar el uso de memoria con Streaming](../technical-guides/optimizing-memory-usage-with-streaming.md).</span><span class="sxs-lookup"><span data-stu-id="432e9-136">Alternatively, use the techniques described in [Optimizing Memory Usage with Streaming](../technical-guides/optimizing-memory-usage-with-streaming.md).</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a><span data-ttu-id="432e9-137">Usar el flujo para minimizar el consumo de memoria necesario al cargar los mensajes en las canalizaciones</span><span class="sxs-lookup"><span data-stu-id="432e9-137">Use streaming to minimize the memory footprint required when loading messages in pipelines</span></span>  
 <span data-ttu-id="432e9-138">Las técnicas siguientes describen cómo minimizar el consumo de memoria de un mensaje al cargar el mensaje en una canalización.</span><span class="sxs-lookup"><span data-stu-id="432e9-138">The following techniques describe how to minimize the memory footprint of a message when loading the message into a pipeline.</span></span>  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="432e9-139">Use ReadOnlySeekableStream y VirtualStream para procesar un mensaje desde un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="432e9-139">Use ReadOnlySeekableStream and VirtualStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="432e9-140">Se considera una práctica recomendada para evitar cargar todo el mensaje en memoria dentro de los componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="432e9-140">It is considered a best practice to avoid loading the entire message into memory inside pipeline components.</span></span> <span data-ttu-id="432e9-141">Un enfoque preferible es ajustar la secuencia entrante con una implementación de secuencia personalizada y, a continuación, como se realizan solicitudes de lectura, la implementación de secuencia personalizada lee la secuencia subyacente, ajustada y procesa los datos a medida que se lee (de forma pura streaming).</span><span class="sxs-lookup"><span data-stu-id="432e9-141">A preferable approach is to wrap the inbound stream with a custom stream implementation, and then as read requests are made, the custom stream implementation reads the underlying, wrapped stream and processes the data as it is read (in a pure streaming manner).</span></span> <span data-ttu-id="432e9-142">Esto puede ser muy difícil de implementar y puede no ser posible, dependiendo de qué debe hacerse con la secuencia.</span><span class="sxs-lookup"><span data-stu-id="432e9-142">This can be very hard to implement and may not be possible, depending on what needs to be done with the stream.</span></span> <span data-ttu-id="432e9-143">En este caso, utilice el **ReadOnlySeekableStream** y **VirtualStream** clases expuestas por la Microsoft.BizTalk.Streaming.dll.</span><span class="sxs-lookup"><span data-stu-id="432e9-143">In this case, use the **ReadOnlySeekableStream** and **VirtualStream** classes exposed by the Microsoft.BizTalk.Streaming.dll.</span></span> <span data-ttu-id="432e9-144">También se proporciona una implementación de estos en [controlador de propiedad XPath arbitrario (ejemplo de BizTalk Server)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) en el SDK de BizTalk. **ReadOnlySeekableStream** garantiza que se puede mover el cursor al principio de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="432e9-144">An implementation of these is also provided in [Arbitrary XPath Property Handler (BizTalk Server Sample)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) in the BizTalk SDK.**ReadOnlySeekableStream** ensures that the cursor can be repositioned to the beginning of the stream.</span></span> <span data-ttu-id="432e9-145">El **VirtualStream** usará un MemoryStream internamente, a menos que el tamaño es a través de un umbral especificado, en cuyo caso escribirá la secuencia en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="432e9-145">The **VirtualStream** will use a MemoryStream internally, unless the size is over a specified threshold, in which case it will write the stream to the file system.</span></span> <span data-ttu-id="432e9-146">Uso de estas dos secuencias en combinación (mediante **VirtualStream** como almacenamiento persistente para el **ReadOnlySeekableStream**) proporciona capacidades de "desbordamiento del sistema de archivos" y "seekability".</span><span class="sxs-lookup"><span data-stu-id="432e9-146">Use of these two streams in combination (using **VirtualStream** as persistent storage for the **ReadOnlySeekableStream**) provides both “seekability” and “overflow to file system” capabilities.</span></span> <span data-ttu-id="432e9-147">Esto permite el procesamiento de mensajes de gran tamaño sin tener que cargar el mensaje completo en la memoria.</span><span class="sxs-lookup"><span data-stu-id="432e9-147">This accommodates the processing of large messages without loading the entire message into memory.</span></span> <span data-ttu-id="432e9-148">El código siguiente podría usarse en un componente de canalización para implementar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="432e9-148">The following code could be used in a pipeline component to implement this functionality.</span></span>  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 <span data-ttu-id="432e9-149">Este código proporciona un umbral de"desbordamiento" exponiendo bufferSize y thresholdSize variables en cada ubicación de recepción o configuración de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="432e9-149">This code provides an “overflow threshold” by exposing bufferSize and thresholdSize variables on each receive location or send port configuration.</span></span> <span data-ttu-id="432e9-150">A continuación, se puede ajustar este umbral desbordamiento por desarrolladores o administradores para diferentes tipos de mensaje y para distintas configuraciones (por ejemplo, 32 bits frente a 64 bits).</span><span class="sxs-lookup"><span data-stu-id="432e9-150">This overflow threshold can then be adjusted by developers or administrators for different message types and different configurations (such as 32-bit vs. 64-bit).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a><span data-ttu-id="432e9-151">Uso de XPathReader y XPathCollection para extraer un objeto determinado de IBaseMessage desde dentro de un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="432e9-151">Using XPathReader and XPathCollection to extract a given IBaseMessage object from within a custom pipeline component.</span></span>  
 <span data-ttu-id="432e9-152">Si los valores específicos que deben extraerse de un documento XML, en lugar de usar el **SelectNodes** y **SelectSingleNode** los métodos expuestos por la clase XmlDocument, use una instancia de la clase XPathReader proporcionado por el ensamblado Microsoft.BizTalk.XPathReader.dll como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="432e9-152">If specific values need to be pulled from an XML document, instead of using the **SelectNodes** and **SelectSingleNode** methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="432e9-153">Para los mensajes más pequeños, especialmente, usa un XmlDocument con SelectNodes o SelectSingleNode puede proporcionar un mejor rendimiento que el uso de XPathReader, pero XPathReader le permite mantener un perfil de memoria planos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="432e9-153">For smaller messages especially, using an XmlDocument with SelectNodes or SelectSingleNode may provide better performance than using XPathReader, but XPathReader allows you to keep a flat memory profile for your application.</span></span>  
  
 <span data-ttu-id="432e9-154">En este ejemplo se muestra cómo usar el XPathReader y XPathCollection para extraer un determinado **IBaseMessage** objeto desde dentro de un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="432e9-154">This example shows how to use the XPathReader and XPathCollection to extract a given **IBaseMessage** object from within a custom pipeline component.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
    try  
    {  
        ...  
        IBaseMessageContext messageContext = message.Context;  
        if (string.IsNullOrEmpty(xPath) && string.IsNullOrEmpty(propertyValue))  
        {  
            throw new ArgumentException(...);  
        }  
        IBaseMessagePart bodyPart = message.BodyPart;  
        Stream inboundStream = bodyPart.GetOriginalDataStream();  
        VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize);  
        ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(inboundStream, virtualStream, bufferSize);  
        XmlTextReader xmlTextReader = new XmlTextReader(readOnlySeekableStream);  
        XPathCollection xPathCollection = new XPathCollection();  
        XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
        xPathCollection.Add(xPath);  
        bool ok = false;  
        while (xPathReader.ReadUntilMatch())  
        {  
            if (xPathReader.Match(0) && !ok)  
            {  
                propertyValue = xPathReader.ReadString();  
                messageContext.Promote(propertyName, propertyNamespace, propertyValue);  
                ok = true;  
            }  
        }  
        readOnlySeekableStream.Position = 0;  
        bodyPart.Data = readOnlySeekableStream;  
    }  
    catch (Exception ex)  
    {  
        if (message != null)  
        {  
            message.SetErrorInfo(ex);  
        }  
        ...  
        throw ex;  
    }  
    return message;  
}  
```  
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="432e9-155">Usar XMLReader y XMLWriter con XMLTranslatorStream para procesar un mensaje desde un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="432e9-155">Use XMLReader and XMLWriter with XMLTranslatorStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="432e9-156">Otro método para implementar un componente de canalización personalizado que usa un enfoque de transmisión por secuencias es usar .NET **XmlReader** y **XmlWriter** clases junto con el  **XmlTranslatorStream** clase proporcionada por el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="432e9-156">Another method for implementing a custom pipeline component which uses a streaming approach is to use the .NET **XmlReader** and **XmlWriter** classes in conjunction with the **XmlTranslatorStream** class provided by BizTalk Server.</span></span> <span data-ttu-id="432e9-157">Por ejemplo, el **NamespaceTranslatorStream** hereda la clase contenida en el ensamblado Microsoft.BizTalk.Pipeline.Components **XmlTranslatorStream** y puede utilizarse para reemplazar un espacio de nombres anterior por otro nuevo en el documento XML contenido en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="432e9-157">For example, the **NamespaceTranslatorStream** class contained in the Microsoft.BizTalk.Pipeline.Components assembly inherits from **XmlTranslatorStream** and can be used to replace an old namespace with a new one in the XML document contained in the stream.</span></span> <span data-ttu-id="432e9-158">Para poder usar esta funcionalidad dentro de un componente de canalización personalizado, puede ajustar el flujo de datos original de la parte del cuerpo de mensaje con una nueva instancia de la **NamespaceTranslatorStream** clase y devolver el último.</span><span class="sxs-lookup"><span data-stu-id="432e9-158">In order to use this functionality inside a custom a pipeline component, you can wrap the original data stream of the message body part with a new instance of the **NamespaceTranslatorStream** class and return the latter.</span></span> <span data-ttu-id="432e9-159">De esta forma el mensaje entrante no se leen o procesan dentro del componente de canalización, pero solo cuando la secuencia se lee mediante un componente subsiguientes en la misma canalización o, por último, se consume el agente de mensaje antes de publicar el documento en el servidor BizTalk Server Cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="432e9-159">In this way the inbound message is not read or processed inside the pipeline component, but only when the stream is read by a subsequent component in the same pipeline or is finally consumed by the Message Agent before publishing the document to the BizTalk Server MessageBox.</span></span>  
  
 <span data-ttu-id="432e9-160">El ejemplo siguiente muestra cómo usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="432e9-160">The following example illustrates how to use this functionality.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
   IBaseMessage outboundMessage = message;  
   try  
   {  
      if (context == null)  
      {  
         throw new ArgumentException(Resources.ContextIsNullMessage);  
      }  
      if (message == null)  
      {  
         throw new ArgumentException(Resources.InboundMessageIsNullMessage);  
      }  
  
      IBaseMessagePart bodyPart = message.BodyPart;  
      Stream stream = new NamespaceTranslatorStream(context,   
                                                    bodyPart.GetOriginalDataStream(),   
                                                    oldNamespace,   
                                                    newNamespace);  
      context.ResourceTracker.AddResource(stream);  
      bodyPart.Data = stream;  
   }  
   catch (Exception ex)  
   {  
      if (message != null)  
      {  
         message.SetErrorInfo(ex);  
      }  
  
      throw ex;  
   }  
   return outboundMessage;  
}  
```  
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a><span data-ttu-id="432e9-161">Uso de ResourceTracker en componentes de canalización personalizados</span><span class="sxs-lookup"><span data-stu-id="432e9-161">Using ResourceTracker in Custom Pipeline Components</span></span>  
 <span data-ttu-id="432e9-162">Un componente de canalización debe administrar la vigencia de los objetos que crea y realizar la recolección de elementos, en cuanto ya no se requieren estos objetos.</span><span class="sxs-lookup"><span data-stu-id="432e9-162">A pipeline component should manage the lifetime of the objects it creates and perform garbage collection as soon as these objects are no longer required.</span></span>  <span data-ttu-id="432e9-163">Si desea que el componente de canalización de la duración de los objetos hasta el último hasta el final de la ejecución de la canalización, a continuación, debe agregar estos objetos para el seguimiento de recursos que la canalización puede capturar desde el contexto de canalización.</span><span class="sxs-lookup"><span data-stu-id="432e9-163">If the pipeline component wants the lifetime of the objects to last until the end of pipeline execution, then you must add such objects to the resource tracker that your pipeline may fetch from the pipeline context.</span></span>  
  
 <span data-ttu-id="432e9-164">La herramienta de seguimiento de recursos se usa para los siguientes tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="432e9-164">The resource tracker is used for the following types of objects:</span></span>  
  
- <span data-ttu-id="432e9-165">Objetos Stream</span><span class="sxs-lookup"><span data-stu-id="432e9-165">Stream objects</span></span>  
  
- <span data-ttu-id="432e9-166">Objetos COM</span><span class="sxs-lookup"><span data-stu-id="432e9-166">COM objects</span></span>  
  
- <span data-ttu-id="432e9-167">Objetos IDisposable</span><span class="sxs-lookup"><span data-stu-id="432e9-167">IDisposable objects</span></span>  
  
  <span data-ttu-id="432e9-168">El motor de mensajería garantiza que todos los recursos nativos que se agregan a la herramienta de seguimiento de recursos se liberan en el momento adecuado, que es después de la canalización se ejecuta completamente, independientemente de si es correcta o errónea.</span><span class="sxs-lookup"><span data-stu-id="432e9-168">The message engine ensures that all the native resources that are added to the resource tracker are released at an appropriate time, that is after the pipeline is completely executed, regardless of whether it was successful or failed.</span></span> <span data-ttu-id="432e9-169">El objeto de contexto de canalización administra la duración de la instancia de la herramienta de seguimiento de recursos y los objetos que está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="432e9-169">The lifetime of the Resource Tracker instance and the objects that it is tracking is managed by the pipeline context object.</span></span> <span data-ttu-id="432e9-170">El contexto de canalización está disponible para todos los tipos de componentes de canalización a través de un objeto que implementa la interfaz IPipelineContext.</span><span class="sxs-lookup"><span data-stu-id="432e9-170">The pipeline context is made available to all types of pipeline components through an object that implements the IPipelineContext interface.</span></span>  
  
  <span data-ttu-id="432e9-171">Por ejemplo, el siguiente fragmento de código es un ejemplo que ilustra cómo usar la propiedad ResourceTracker en componentes de canalización personalizados.</span><span class="sxs-lookup"><span data-stu-id="432e9-171">For example, the following code snippet is a sample that illustrates how to use ResourceTracker property in custom pipeline components.</span></span> <span data-ttu-id="432e9-172">Para usar la propiedad ResourceTracker, el fragmento de código usa el parámetro siguiente `IPipelineContext.ResourceTracker.AddResource`.</span><span class="sxs-lookup"><span data-stu-id="432e9-172">To use ResourceTracker property, the code snippet uses the following parameter `IPipelineContext.ResourceTracker.AddResource`.</span></span> <span data-ttu-id="432e9-173">En este parámetro:</span><span class="sxs-lookup"><span data-stu-id="432e9-173">In this parameter:</span></span>  
  
- <span data-ttu-id="432e9-174">IPipelineContext (interfaz) define los métodos utilizados para tener acceso a todas las interfaces específicas de procesamiento de documentos.</span><span class="sxs-lookup"><span data-stu-id="432e9-174">IPipelineContext interface defines the methods used to access all document processing-specific interfaces.</span></span>  
  
- <span data-ttu-id="432e9-175">Propiedad ResourceTracker hace referencia a IPipelineContext y se usa para realizar un seguimiento de los objetos que se eliminarán de forma explícita al final del procesamiento de canalización.</span><span class="sxs-lookup"><span data-stu-id="432e9-175">ResourceTracker property references IPipelineContext and is used to keep track of objects that will be explicitly disposed at the end of pipeline processing.</span></span>  
  
- <span data-ttu-id="432e9-176">Método ResourceTracker.AddResource se usa para realizar un seguimiento de los objetos COM, objetos desechables y secuencias y siempre se debe usar dentro de un componente de canalización personalizado para explícitamente cerrar (secuencias), eliminar (objetos IDisposable) o liberar (objetos COM) estos tipos de recursos cuando se publica un mensaje a BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="432e9-176">ResourceTracker.AddResource method is used to keep track of COM objects, Disposable objects and Streams, and should always be used inside a custom pipeline component to explicitly close (streams), dispose (IDisposable objects) or release (COM objects) these types of resources when a message is published to the BizTalk MessageBox.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
  
{  
      IBaseMessage outMessage = pContext.GetMessageFactory().CreateMessage();  
  
      IBaseMessagePart outMsgBodyPart = pContext.GetMessageFactory().CreateMessagePart();  
  
      outMsgBodyPart.Charset = Encoding.UTF8.WebName;   
  
      outMsgBodyPart.ContentType = "text/xml";  
  
//Code to load message content in the MemoryStream object//  
  
      MemoryStream messageData = new MemoryStream();  
  
   //The MemoryStream needs to be closed after the whole pipeline has executed, thus adding it into ResourceTracker//  
  
      pContext.ResourceTracker.AddResource(messageData);  
  
//Custom pipeline code to load message data into xmlPayload//  
  
      XmlDocument xmlPayLoad = new XmlDocument();  
  
      xmlPayLoad.Save(messageData);  
  
      messageData.Seek(0, SeekOrigin.Begin);  
  
//The new stream is assigned to the message part’s data//  
  
      outMsgBodyPart.Data = messageData;  
  
// Pipeline component logic here//  
  
      return outMessage;  
  
}  
```  
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a><span data-ttu-id="432e9-177">Comparación de los mensajes de la carga en las canalizaciones mediante un enfoque en memoria y uso de un enfoque de transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="432e9-177">Comparison of loading messages into pipelines using an in-memory approach and using a streaming approach</span></span>  
 <span data-ttu-id="432e9-178">La siguiente información se tomó del blog de Nic Barden, [ http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx ](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228).</span><span class="sxs-lookup"><span data-stu-id="432e9-178">The following information was taken from Nic Barden’s blog, [http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228).</span></span> <span data-ttu-id="432e9-179">Esta tabla proporciona una comparación resumida de los mensajes de la carga en canalizaciones mediante un enfoque en memoria y uso de un enfoque de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="432e9-179">This table provides a summarized comparison of loading messages into pipelines using an in-memory approach and using a streaming approach.</span></span>  
  
|<span data-ttu-id="432e9-180">Comparación de...</span><span class="sxs-lookup"><span data-stu-id="432e9-180">Comparison of...</span></span>|<span data-ttu-id="432e9-181">Transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="432e9-181">Streaming</span></span>|<span data-ttu-id="432e9-182">En la memoria</span><span class="sxs-lookup"><span data-stu-id="432e9-182">In memory</span></span>|  
|----------------------|---------------|---------------|  
|<span data-ttu-id="432e9-183">Uso de memoria por mensaje</span><span class="sxs-lookup"><span data-stu-id="432e9-183">Memory usage per message</span></span>|<span data-ttu-id="432e9-184">Baja, independientemente del tamaño de mensaje</span><span class="sxs-lookup"><span data-stu-id="432e9-184">Low, regardless of message size</span></span>|<span data-ttu-id="432e9-185">Alto (varía según el tamaño del mensaje)</span><span class="sxs-lookup"><span data-stu-id="432e9-185">High (varies depending on message size)</span></span>|  
|<span data-ttu-id="432e9-186">Clases comunes que se usan para procesar datos XML</span><span class="sxs-lookup"><span data-stu-id="432e9-186">Common classes used to process XML data</span></span>|<span data-ttu-id="432e9-187">Compila las derivaciones de en y personalizadas de:</span><span class="sxs-lookup"><span data-stu-id="432e9-187">Built in and custom derivations of:</span></span><br /><br /> <span data-ttu-id="432e9-188">XmlTranslatorStream, XmlReader y XmlWriter</span><span class="sxs-lookup"><span data-stu-id="432e9-188">XmlTranslatorStream, XmlReader and XmlWriter</span></span>|<span data-ttu-id="432e9-189">XmlDocument, XPathDocument, MemoryStream y VirtualStream</span><span class="sxs-lookup"><span data-stu-id="432e9-189">XmlDocument, XPathDocument, MemoryStream and VirtualStream</span></span>|  
|<span data-ttu-id="432e9-190">Documentación</span><span class="sxs-lookup"><span data-stu-id="432e9-190">Documentation</span></span>|<span data-ttu-id="432e9-191">Deficiente: muchas clases de BizTalk no es compatibles y no documentadas</span><span class="sxs-lookup"><span data-stu-id="432e9-191">Poor – many un-supported and un-documented BizTalk classes</span></span>|<span data-ttu-id="432e9-192">Muy bueno: clases de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="432e9-192">Very good - .NET Framework classes</span></span>|  
|<span data-ttu-id="432e9-193">Ubicación del código de la "Lógica de procesamiento"</span><span class="sxs-lookup"><span data-stu-id="432e9-193">Location of “Processing Logic” code</span></span>|<span data-ttu-id="432e9-194">-Lectores "Conectar" y secuencias a través del método Execute.</span><span class="sxs-lookup"><span data-stu-id="432e9-194">-   “Wire up” readers and streams via Execute method.</span></span><br /><span data-ttu-id="432e9-195">-Ejecución real se produce en los flujos y los lectores que se leen los datos.</span><span class="sxs-lookup"><span data-stu-id="432e9-195">-   Actual execution occurs in the readers and streams as the data is read.</span></span>|<span data-ttu-id="432e9-196">Directamente desde el método Execute del componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="432e9-196">Directly from the Execute method of the pipeline component.</span></span>|  
|<span data-ttu-id="432e9-197">data</span><span class="sxs-lookup"><span data-stu-id="432e9-197">Data</span></span>|<span data-ttu-id="432e9-198">Volver a crearse en cada capa de ajuste que se leen los datos a través de él.</span><span class="sxs-lookup"><span data-stu-id="432e9-198">Re-created at each wrapping layer as data is read through it.</span></span>|<span data-ttu-id="432e9-199">Leer, modificar y que se escriben en cada componente antes del siguiente componente que se llama.</span><span class="sxs-lookup"><span data-stu-id="432e9-199">Read in, modified and written out at each component prior to next component being called.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="432e9-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="432e9-200">See Also</span></span>  
 [<span data-ttu-id="432e9-201">Optimización de las aplicaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="432e9-201">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)