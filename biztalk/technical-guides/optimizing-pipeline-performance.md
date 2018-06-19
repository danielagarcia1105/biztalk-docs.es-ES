---
title: Optimizar el rendimiento de la canalización | Documentos de Microsoft
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
ms.openlocfilehash: 4311efd0d23e29b63f02fc34b1650a894d29d335
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299556"
---
# <a name="optimizing-pipeline-performance"></a><span data-ttu-id="f7e19-102">Optimizar el rendimiento de la canalización</span><span class="sxs-lookup"><span data-stu-id="f7e19-102">Optimizing Pipeline Performance</span></span>
<span data-ttu-id="f7e19-103">Este tema describe las directrices para optimizar el rendimiento de las canalizaciones de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="f7e19-103">This topic describes guidelines for optimizing performance of pipelines in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a><span data-ttu-id="f7e19-104">Prácticas recomendadas para optimizar el rendimiento de las canalizaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f7e19-104">Best practices for optimizing performance of BizTalk Server pipelines</span></span>  
  
1.  <span data-ttu-id="f7e19-105">Dado que los componentes de canalización tienen un impacto significativo en el rendimiento (por ejemplo, un componente de canalización de paso realiza hasta 30 por ciento mejor que un componente de canalización de ensamblador y desensamblador XML), asegúrese de que los componentes de canalización personalizado realizan un rendimiento óptimo antes de implementarlos en su implementación.</span><span class="sxs-lookup"><span data-stu-id="f7e19-105">Because pipeline components have a significant impact on performance (for example, a pass-through pipeline component performs up to 30 percent better than an XML assembler/disassembler pipeline component), make sure that any custom pipeline components perform optimally before implementing them in your deployment.</span></span> <span data-ttu-id="f7e19-106">Minimice el número de componentes de canalización en sus canalizaciones personalizadas si desea maximizar el rendimiento general de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f7e19-106">Minimize the number of pipeline components in your custom pipelines if you want to maximize the overall performance of your BizTalk application.</span></span>  
  
2.  <span data-ttu-id="f7e19-107">También puede mejorar el rendimiento general al reducir la frecuencia de persistencia de mensaje en el componente de canalización y codificando el componente para minimizar la redundancia.</span><span class="sxs-lookup"><span data-stu-id="f7e19-107">You also can improve overall performance by reducing the message persistence frequency in your pipeline component and by coding your component to minimize redundancy.</span></span> <span data-ttu-id="f7e19-108">Todos los ensamblados personalizados y en particular la artefactos que pudieron afectar a rendimiento, como los componentes de seguimiento personalizado, se deben probar por separado en condiciones de sobrecarga para observar su comportamiento cuando el sistema funciona con la máxima capacidad y buscar posibles cuellos de botella.</span><span class="sxs-lookup"><span data-stu-id="f7e19-108">Every custom assembly and in particular artifacts that could potentially disrupt performance, like custom tracking components, should be tested separately under heavy load condition to observe their behavior when the system is working at full capacity and to find any possible bottlenecks.</span></span>  
  
3.  <span data-ttu-id="f7e19-109">Si tiene que leer el mensaje entrante dentro de un componente de canalización, evite cargar todo el documento en la memoria con un **XmlDocument** objeto.</span><span class="sxs-lookup"><span data-stu-id="f7e19-109">If you need to read the inbound message inside a pipeline component, avoid loading the entire document into memory using an **XmlDocument** object.</span></span> <span data-ttu-id="f7e19-110">La cantidad de espacio necesario para una instancia de la **XmlDocument** clase para cargar y crear una representación en memoria de un documento XML es hasta 10 veces el tamaño de mensaje real.</span><span class="sxs-lookup"><span data-stu-id="f7e19-110">The amount of space required by an instance of the **XmlDocument** class to load and create an in-memory representation of a XML document is up to 10 times the actual message size.</span></span> <span data-ttu-id="f7e19-111">Para leer un mensaje, debe utilizar un **XmlTextReader** objeto junto con una instancia de las clases siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7e19-111">In order to read a message, you should use an **XmlTextReader** object along with an instance of the following classes:</span></span>  
  
    -   <span data-ttu-id="f7e19-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\ SchemaResolverComponent\SchemaResolverFlatFileDasm.</span><span class="sxs-lookup"><span data-stu-id="f7e19-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
    -   <span data-ttu-id="f7e19-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.</span><span class="sxs-lookup"><span data-stu-id="f7e19-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.</span></span>  
  
    -   <span data-ttu-id="f7e19-114">**SeekAbleReadOnlyStream** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\SchemaResolverComponent\ SchemaResolverFlatFileDasm.</span><span class="sxs-lookup"><span data-stu-id="f7e19-114">**SeekAbleReadOnlyStream** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
4.  <span data-ttu-id="f7e19-115">Utilice la PassThruReceive y las canalizaciones estándares PassThruTransmit siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="f7e19-115">Use the PassThruReceive and the PassThruTransmit standard pipelines whenever possible.</span></span> <span data-ttu-id="f7e19-116">No contienen un componente de canalización y no realizan ningún procesamiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7e19-116">They do not contain any pipeline component and do not perform any processing of the message.</span></span> <span data-ttu-id="f7e19-117">Por este motivo, asegurar un rendimiento máximo en recibir o enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7e19-117">For this reason, they ensure maximum performance in receiving or sending messages.</span></span> <span data-ttu-id="f7e19-118">Puede usar una canalización PassThruReceive en una ubicación de recepción si necesita publicar un documento binario en BizTalk MessageBox y una canalización PassThruTransmit en un puerto de envío si necesita enviar un mensaje binario.</span><span class="sxs-lookup"><span data-stu-id="f7e19-118">You can use a PassThruReceive pipeline on a receive location if you need to publish a binary document to the BizTalk MessageBox and a PassThruTransmit pipeline on a send port if you need to send out a binary message.</span></span> <span data-ttu-id="f7e19-119">También puede usar la canalización PassThruTransmit en un puerto de envío físico enlazado a una orquestación si el mensaje se ha formateado previamente y está listo para su transmisión.</span><span class="sxs-lookup"><span data-stu-id="f7e19-119">You can also use the PassThruTransmit pipeline on a physical send port bound to an orchestration if the message has been formatted and is ready to be transmitted.</span></span> <span data-ttu-id="f7e19-120">Debe usar un enfoque diferente si necesita realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f7e19-120">You will need to use a different approach if you need to accomplish one of the following actions:</span></span>  
  
    -   <span data-ttu-id="f7e19-121">Promocionar propiedades en el contexto de un mensaje de archivo sin formato o XML entrante.</span><span class="sxs-lookup"><span data-stu-id="f7e19-121">Promote properties on the context of an inbound XML or Flat File message.</span></span>  
  
    -   <span data-ttu-id="f7e19-122">Aplicar una asignación dentro de una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f7e19-122">Apply a map inside a receive location.</span></span>  
  
    -   <span data-ttu-id="f7e19-123">Aplicar una asignación de una orquestación que se suscribe a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7e19-123">Apply a map in an orchestration that subscribes to a message.</span></span>  
  
    -   <span data-ttu-id="f7e19-124">Aplicar una asignación en un puerto de envío que se suscribe a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7e19-124">Apply a map on a send port that subscribes to a message.</span></span>  
  
     <span data-ttu-id="f7e19-125">Para llevar a cabo una de estas acciones, debe sondear y detectar el tipo de documento dentro de la canalización de recepción y asigne el valor (espacio de nombres #root-name) a la propiedad de contexto de MessageType.</span><span class="sxs-lookup"><span data-stu-id="f7e19-125">To accomplish one of these actions, you must probe and discover the document type inside the receive pipeline and assign the (namespace#root-name) value to the MessageType context property.</span></span> <span data-ttu-id="f7e19-126">Esta operación se realiza normalmente por un componente de desensamblador como el componente de desensamblador Xml (XmlDasmComp) o el componente de desensamblador de archivos sin formato (FFDasmComp).</span><span class="sxs-lookup"><span data-stu-id="f7e19-126">This operation is typically accomplished by a disassembler component such as the Xml Disassembler component (XmlDasmComp) or the Flat File disassembler component (FFDasmComp).</span></span> <span data-ttu-id="f7e19-127">En este caso, debe usar un estándar (por ejemplo, la canalización XmlReceive) o una canalización personalizada que contiene un estándar o un componente de desensamblador personalizado.</span><span class="sxs-lookup"><span data-stu-id="f7e19-127">In this case, you need to use a standard (for instance, XmlReceive pipeline) or a custom pipeline that contains a standard or a custom disassembler component.</span></span>  
  
5.  <span data-ttu-id="f7e19-128">Adquirir recursos lo más tarde posible y liberarlos tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="f7e19-128">Acquire resources as late as possible and release them as early as possible.</span></span> <span data-ttu-id="f7e19-129">Por ejemplo, si tiene acceso a datos en una base de datos, abra la conexión lo más tarde posible y cerrarlo tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="f7e19-129">For example, if you need to access data on a database, open the connection as late as possible and close it as soon as possible.</span></span> <span data-ttu-id="f7e19-130">Utilice la instrucción using implícitamente liberar objetos descartables de C# o el bloque finally de una instrucción try-catch-finally para eliminar explícitamente los objetos.</span><span class="sxs-lookup"><span data-stu-id="f7e19-130">Use the C# using statement to implicitly release disposable objects or the finally block of a try-catch-finally statement to explicitly dispose your objects.</span></span> <span data-ttu-id="f7e19-131">Instrumentar el código fuente para hacer que sus componentes fácil de depurar.</span><span class="sxs-lookup"><span data-stu-id="f7e19-131">Instrument your source code to make your components simple to debug.</span></span>  
  
6.  <span data-ttu-id="f7e19-132">Eliminar los componentes de las canalizaciones que no son estrictamente necesarias para acelerar el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7e19-132">Eliminate any components from your pipelines that are not strictly required to speed up message processing.</span></span>  
  
7.  <span data-ttu-id="f7e19-133">Dentro de una canalización de recepción, debe promocionar los elementos en el contexto del mensaje solo si se necesita para el enrutamiento de mensajes (orquestaciones, puertos de envío) o degradación de propiedades de contexto del mensaje (puertos de envío).</span><span class="sxs-lookup"><span data-stu-id="f7e19-133">Inside a receive pipeline, you should promote items to the message context only if you need them for message routing (Orchestrations, Send Ports) or demotion of message context properties (Send Ports).</span></span>  
  
8.  <span data-ttu-id="f7e19-134">Si es necesario incluir metadatos con un mensaje, y no utiliza los metadatos para fines de enrutamiento o degradación, use la **IBaseMessageContext.Write** en lugar del método la **IBaseMessageContext.Promote** método.</span><span class="sxs-lookup"><span data-stu-id="f7e19-134">If you need to include metadata with a message, and you don't use the metadata for routing or demotion purposes, use the **IBaseMessageContext.Write** method instead of the **IBaseMessageContext.Promote** method.</span></span>  
  
9. <span data-ttu-id="f7e19-135">Si necesita extraer información de un mensaje utilizando una expresión XPath, evite cargar todo el documento en la memoria con un **XmlDocument** objeto simplemente que se usará el **SelectNodes** o  **SelectSingleNode** métodos.</span><span class="sxs-lookup"><span data-stu-id="f7e19-135">If you need to extract information from a message using an XPath expression, avoid loading the entire document into memory using an **XmlDocument** object just to use the **SelectNodes** or **SelectSingleNode** methods.</span></span> <span data-ttu-id="f7e19-136">Como alternativa, use las técnicas descritas en [optimizar el uso de memoria con transmisión por secuencias](../technical-guides/optimizing-memory-usage-with-streaming.md).</span><span class="sxs-lookup"><span data-stu-id="f7e19-136">Alternatively, use the techniques described in [Optimizing Memory Usage with Streaming](../technical-guides/optimizing-memory-usage-with-streaming.md).</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a><span data-ttu-id="f7e19-137">Usar la transmisión por secuencias para minimizar el consumo de memoria necesario al cargar mensajes de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="f7e19-137">Use streaming to minimize the memory footprint required when loading messages in pipelines</span></span>  
 <span data-ttu-id="f7e19-138">Las técnicas siguientes describen cómo minimizar el consumo de memoria de un mensaje al cargar el mensaje en una canalización.</span><span class="sxs-lookup"><span data-stu-id="f7e19-138">The following techniques describe how to minimize the memory footprint of a message when loading the message into a pipeline.</span></span>  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="f7e19-139">Use ReadOnlySeekableStream y VirtualStream para procesar un mensaje desde un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="f7e19-139">Use ReadOnlySeekableStream and VirtualStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="f7e19-140">Se considera una práctica recomendada para evitar que se cargue el mensaje completo en la memoria dentro de los componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="f7e19-140">It is considered a best practice to avoid loading the entire message into memory inside pipeline components.</span></span> <span data-ttu-id="f7e19-141">Un enfoque preferible consiste en encapsular la secuencia de entrada con una implementación de secuencia personalizada y, a continuación, como se realizan las solicitudes de lectura, la implementación de secuencia personalizada lee la secuencia subyacente, ajustada y procesa los datos a medida que se lee (en un modo de transmisión por secuencias puro).</span><span class="sxs-lookup"><span data-stu-id="f7e19-141">A preferable approach is to wrap the inbound stream with a custom stream implementation, and then as read requests are made, the custom stream implementation reads the underlying, wrapped stream and processes the data as it is read (in a pure streaming manner).</span></span> <span data-ttu-id="f7e19-142">Esto puede ser muy difícil de implementar y puede no ser posible, dependiendo de qué debe hacerse con la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f7e19-142">This can be very hard to implement and may not be possible, depending on what needs to be done with the stream.</span></span> <span data-ttu-id="f7e19-143">En este caso, utilice la **ReadOnlySeekableStream** y **VirtualStream** clases expuestas por la Microsoft.BizTalk.Streaming.dll.</span><span class="sxs-lookup"><span data-stu-id="f7e19-143">In this case, use the **ReadOnlySeekableStream** and **VirtualStream** classes exposed by the Microsoft.BizTalk.Streaming.dll.</span></span> <span data-ttu-id="f7e19-144">También se proporciona una implementación de estos en [controlador de propiedad XPath arbitrario (ejemplo de BizTalk Server)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) en el SDK de BizTalk. **ReadOnlySeekableStream** garantiza que se puede mover el cursor al principio de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f7e19-144">An implementation of these is also provided in [Arbitrary XPath Property Handler (BizTalk Server Sample)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) in the BizTalk SDK.**ReadOnlySeekableStream** ensures that the cursor can be repositioned to the beginning of the stream.</span></span> <span data-ttu-id="f7e19-145">El **VirtualStream** usará una MemoryStream internamente, a menos que el tamaño está por encima de un umbral especificado, en cuyo caso se escribirá la secuencia en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="f7e19-145">The **VirtualStream** will use a MemoryStream internally, unless the size is over a specified threshold, in which case it will write the stream to the file system.</span></span> <span data-ttu-id="f7e19-146">Uso de estas dos secuencias en combinación (mediante **VirtualStream** como el almacenamiento persistente para la **ReadOnlySeekableStream**) proporciona capacidades de "desbordamiento del sistema de archivos" y "seekability".</span><span class="sxs-lookup"><span data-stu-id="f7e19-146">Use of these two streams in combination (using **VirtualStream** as persistent storage for the **ReadOnlySeekableStream**) provides both “seekability” and “overflow to file system” capabilities.</span></span> <span data-ttu-id="f7e19-147">Esto es útil para el procesamiento de mensajes de gran tamaño sin necesidad de cargar el mensaje completo en la memoria.</span><span class="sxs-lookup"><span data-stu-id="f7e19-147">This accommodates the processing of large messages without loading the entire message into memory.</span></span> <span data-ttu-id="f7e19-148">El código siguiente podría utilizarse en un componente de canalización para implementar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="f7e19-148">The following code could be used in a pipeline component to implement this functionality.</span></span>  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 <span data-ttu-id="f7e19-149">Este código proporciona un umbral de"desbordamiento" mediante la exposición de bufferSize y thresholdSize variables en cada ubicación de recepción o configuración de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f7e19-149">This code provides an “overflow threshold” by exposing bufferSize and thresholdSize variables on each receive location or send port configuration.</span></span> <span data-ttu-id="f7e19-150">Este umbral de desbordamiento, a continuación, puede ser ajustado por los desarrolladores o los administradores de diferentes tipos de mensaje y distintas configuraciones (por ejemplo, 32 bits. 64 bits).</span><span class="sxs-lookup"><span data-stu-id="f7e19-150">This overflow threshold can then be adjusted by developers or administrators for different message types and different configurations (such as 32-bit vs. 64-bit).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a><span data-ttu-id="f7e19-151">Uso de XPathReader y XPathCollection para extraer un objeto determinado de IBaseMessage desde dentro de un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="f7e19-151">Using XPathReader and XPathCollection to extract a given IBaseMessage object from within a custom pipeline component.</span></span>  
 <span data-ttu-id="f7e19-152">Si necesitan valores concretos para extraerse de un documento XML, en lugar de utilizar el **SelectNodes** y **SelectSingleNode** métodos expuestos por la clase XmlDocument, utilizar una instancia de la clase XPathReader proporciona el ensamblado Microsoft.BizTalk.XPathReader.dll como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f7e19-152">If specific values need to be pulled from an XML document, instead of using the **SelectNodes** and **SelectSingleNode** methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7e19-153">Para los mensajes más pequeños, especialmente, mediante un XmlDocument con SelectNodes o SelectSingleNode puede proporcionar un mejor rendimiento que el uso de XPathReader, pero XPathReader le permite mantener un perfil de memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7e19-153">For smaller messages especially, using an XmlDocument with SelectNodes or SelectSingleNode may provide better performance than using XPathReader, but XPathReader allows you to keep a flat memory profile for your application.</span></span>  
  
 <span data-ttu-id="f7e19-154">Este ejemplo muestra cómo utilizar el XPathReader y XPathCollection para extraer un determinado **IBaseMessage** objeto desde dentro de un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="f7e19-154">This example shows how to use the XPathReader and XPathCollection to extract a given **IBaseMessage** object from within a custom pipeline component.</span></span>  
  
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
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="f7e19-155">Usar XMLWriter y XMLReader con XMLTranslatorStream para procesar un mensaje desde un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="f7e19-155">Use XMLReader and XMLWriter with XMLTranslatorStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="f7e19-156">Otro método para implementar un componente de canalización personalizado que usa un método de transmisión por secuencias es usar .NET **XmlReader** y **XmlWriter** clases junto con la  **XmlTranslatorStream** clase proporcionada por el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f7e19-156">Another method for implementing a custom pipeline component which uses a streaming approach is to use the .NET **XmlReader** and **XmlWriter** classes in conjunction with the **XmlTranslatorStream** class provided by BizTalk Server.</span></span> <span data-ttu-id="f7e19-157">Por ejemplo, el **NamespaceTranslatorStream** clase incluida en el ensamblado Microsoft.BizTalk.Pipeline.Components hereda de **XmlTranslatorStream** y puede utilizarse para reemplazar un espacio de nombres anterior con una nueva en el documento XML contenido en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f7e19-157">For example, the **NamespaceTranslatorStream** class contained in the Microsoft.BizTalk.Pipeline.Components assembly inherits from **XmlTranslatorStream** and can be used to replace an old namespace with a new one in the XML document contained in the stream.</span></span> <span data-ttu-id="f7e19-158">Para poder utilizar esta funcionalidad dentro de un componente de canalización personalizado, puede ajustar el flujo de datos original de la parte del cuerpo de mensaje con una nueva instancia de la **NamespaceTranslatorStream** clase y devolver el último.</span><span class="sxs-lookup"><span data-stu-id="f7e19-158">In order to use this functionality inside a custom a pipeline component, you can wrap the original data stream of the message body part with a new instance of the **NamespaceTranslatorStream** class and return the latter.</span></span> <span data-ttu-id="f7e19-159">De esta manera el mensaje entrante no se lee o procesar dentro del componente de canalización, pero sólo cuando el flujo de un componente subsiguientes en la misma canalización lee o finalmente es utilizado por el agente de mensajes antes de publicar el documento en el servidor BizTalk Server Cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7e19-159">In this way the inbound message is not read or processed inside the pipeline component, but only when the stream is read by a subsequent component in the same pipeline or is finally consumed by the Message Agent before publishing the document to the BizTalk Server MessageBox.</span></span>  
  
 <span data-ttu-id="f7e19-160">En el ejemplo siguiente se muestra cómo utilizar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="f7e19-160">The following example illustrates how to use this functionality.</span></span>  
  
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
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a><span data-ttu-id="f7e19-161">Utilizar ResourceTracker en componentes de canalización personalizado</span><span class="sxs-lookup"><span data-stu-id="f7e19-161">Using ResourceTracker in Custom Pipeline Components</span></span>  
 <span data-ttu-id="f7e19-162">Un componente de canalización debe administrar la vigencia de los objetos que crea y realizar la recolección de tan pronto como ya no se requieren estos objetos.</span><span class="sxs-lookup"><span data-stu-id="f7e19-162">A pipeline component should manage the lifetime of the objects it creates and perform garbage collection as soon as these objects are no longer required.</span></span>  <span data-ttu-id="f7e19-163">Si el componente de canalización quiere que la duración de los objetos hasta el último hasta el final de la ejecución de la canalización, a continuación, debe agregar dichos objetos a la herramienta de seguimiento de recursos que la canalización puede capturar desde el contexto de canalización.</span><span class="sxs-lookup"><span data-stu-id="f7e19-163">If the pipeline component wants the lifetime of the objects to last until the end of pipeline execution, then you must add such objects to the resource tracker that your pipeline may fetch from the pipeline context.</span></span>  
  
 <span data-ttu-id="f7e19-164">La herramienta de seguimiento de recursos se utiliza para los siguientes tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="f7e19-164">The resource tracker is used for the following types of objects:</span></span>  
  
-   <span data-ttu-id="f7e19-165">Objetos de flujo</span><span class="sxs-lookup"><span data-stu-id="f7e19-165">Stream objects</span></span>  
  
-   <span data-ttu-id="f7e19-166">Objetos COM</span><span class="sxs-lookup"><span data-stu-id="f7e19-166">COM objects</span></span>  
  
-   <span data-ttu-id="f7e19-167">Objetos IDisposable</span><span class="sxs-lookup"><span data-stu-id="f7e19-167">IDisposable objects</span></span>  
  
 <span data-ttu-id="f7e19-168">El motor de mensajería se asegura de que todos los recursos nativos que se agregan a la herramienta de seguimiento de recursos se liberan en el momento adecuado, que resulta después de la canalización se ejecuta completamente, independientemente de si es correcto o incorrecto.</span><span class="sxs-lookup"><span data-stu-id="f7e19-168">The message engine ensures that all the native resources that are added to the resource tracker are released at an appropriate time, that is after the pipeline is completely executed, regardless of whether it was successful or failed.</span></span> <span data-ttu-id="f7e19-169">La duración de la instancia de seguimiento de recursos y los objetos que está realizando el seguimiento se administra mediante el objeto de contexto de canalización.</span><span class="sxs-lookup"><span data-stu-id="f7e19-169">The lifetime of the Resource Tracker instance and the objects that it is tracking is managed by the pipeline context object.</span></span> <span data-ttu-id="f7e19-170">El contexto de canalización están disponible para todos los tipos de componentes de canalización a través de un objeto que implementa la interfaz IPipelineContext.</span><span class="sxs-lookup"><span data-stu-id="f7e19-170">The pipeline context is made available to all types of pipeline components through an object that implements the IPipelineContext interface.</span></span>  
  
 <span data-ttu-id="f7e19-171">Por ejemplo, el fragmento de código siguiente es un ejemplo que muestra cómo utilizar la propiedad ResourceTracker en componentes de canalización personalizados.</span><span class="sxs-lookup"><span data-stu-id="f7e19-171">For example, the following code snippet is a sample that illustrates how to use ResourceTracker property in custom pipeline components.</span></span> <span data-ttu-id="f7e19-172">Para utilizar la propiedad ResourceTracker, el fragmento de código utiliza el siguiente parámetro `IPipelineContext.ResourceTracker.AddResource`.</span><span class="sxs-lookup"><span data-stu-id="f7e19-172">To use ResourceTracker property, the code snippet uses the following parameter `IPipelineContext.ResourceTracker.AddResource`.</span></span> <span data-ttu-id="f7e19-173">En este parámetro:</span><span class="sxs-lookup"><span data-stu-id="f7e19-173">In this parameter:</span></span>  
  
-   <span data-ttu-id="f7e19-174">IPipelineContext (interfaz) define los métodos utilizados para tener acceso a todas las interfaces específicas de procesamiento de documentos.</span><span class="sxs-lookup"><span data-stu-id="f7e19-174">IPipelineContext interface defines the methods used to access all document processing-specific interfaces.</span></span>  
  
-   <span data-ttu-id="f7e19-175">Propiedad ResourceTracker hace referencia a IPipelineContext y se utiliza para realizar un seguimiento de los objetos que se eliminan de forma explícita al final del procesamiento de canalización.</span><span class="sxs-lookup"><span data-stu-id="f7e19-175">ResourceTracker property references IPipelineContext and is used to keep track of objects that will be explicitly disposed at the end of pipeline processing.</span></span>  
  
-   <span data-ttu-id="f7e19-176">Método ResourceTracker.AddResource se usa para realizar un seguimiento de los objetos COM, los objetos descartables y secuencias y siempre se debe utilizar dentro de un componente de canalización personalizado para explícitamente cerrar (secuencias), dispose (objetos IDisposable) o liberar (objetos COM) estos tipos de recursos cuando se publica un mensaje a BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="f7e19-176">ResourceTracker.AddResource method is used to keep track of COM objects, Disposable objects and Streams, and should always be used inside a custom pipeline component to explicitly close (streams), dispose (IDisposable objects) or release (COM objects) these types of resources when a message is published to the BizTalk MessageBox.</span></span>  
  
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
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a><span data-ttu-id="f7e19-177">Comparación de los mensajes de carga en canalizaciones mediante un enfoque en memoria y mediante un enfoque de transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="f7e19-177">Comparison of loading messages into pipelines using an in-memory approach and using a streaming approach</span></span>  
 <span data-ttu-id="f7e19-178">La siguiente información se toma del blog de Nic Barden, [http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228).</span><span class="sxs-lookup"><span data-stu-id="f7e19-178">The following information was taken from Nic Barden’s blog, [http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228).</span></span> <span data-ttu-id="f7e19-179">Esta tabla proporciona una comparación resumida de los mensajes de carga en canalizaciones mediante un enfoque en memoria y mediante un enfoque de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="f7e19-179">This table provides a summarized comparison of loading messages into pipelines using an in-memory approach and using a streaming approach.</span></span>  
  
|<span data-ttu-id="f7e19-180">Comparación de...</span><span class="sxs-lookup"><span data-stu-id="f7e19-180">Comparison of...</span></span>|<span data-ttu-id="f7e19-181">Transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="f7e19-181">Streaming</span></span>|<span data-ttu-id="f7e19-182">En la memoria</span><span class="sxs-lookup"><span data-stu-id="f7e19-182">In memory</span></span>|  
|----------------------|---------------|---------------|  
|<span data-ttu-id="f7e19-183">Uso de memoria por mensaje</span><span class="sxs-lookup"><span data-stu-id="f7e19-183">Memory usage per message</span></span>|<span data-ttu-id="f7e19-184">Low, independientemente del tamaño del mensaje</span><span class="sxs-lookup"><span data-stu-id="f7e19-184">Low, regardless of message size</span></span>|<span data-ttu-id="f7e19-185">Alta (varía en función del tamaño del mensaje)</span><span class="sxs-lookup"><span data-stu-id="f7e19-185">High (varies depending on message size)</span></span>|  
|<span data-ttu-id="f7e19-186">Clases comunes que se utilizan para procesar datos XML</span><span class="sxs-lookup"><span data-stu-id="f7e19-186">Common classes used to process XML data</span></span>|<span data-ttu-id="f7e19-187">Integrado en y personalizados derivaciones de:</span><span class="sxs-lookup"><span data-stu-id="f7e19-187">Built in and custom derivations of:</span></span><br /><br /> <span data-ttu-id="f7e19-188">XmlTranslatorStream, XmlWriter y XmlReader</span><span class="sxs-lookup"><span data-stu-id="f7e19-188">XmlTranslatorStream, XmlReader and XmlWriter</span></span>|<span data-ttu-id="f7e19-189">XmlDocument, XPathDocument, MemoryStream y VirtualStream</span><span class="sxs-lookup"><span data-stu-id="f7e19-189">XmlDocument, XPathDocument, MemoryStream and VirtualStream</span></span>|  
|<span data-ttu-id="f7e19-190">Documentación</span><span class="sxs-lookup"><span data-stu-id="f7e19-190">Documentation</span></span>|<span data-ttu-id="f7e19-191">Malo: muchas clases de BizTalk no documentadas y no compatibles</span><span class="sxs-lookup"><span data-stu-id="f7e19-191">Poor – many un-supported and un-documented BizTalk classes</span></span>|<span data-ttu-id="f7e19-192">Muy bueno - clases de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7e19-192">Very good - .NET Framework classes</span></span>|  
|<span data-ttu-id="f7e19-193">Ubicación del código de "Lógica de procesamiento"</span><span class="sxs-lookup"><span data-stu-id="f7e19-193">Location of “Processing Logic” code</span></span>|<span data-ttu-id="f7e19-194">-Lectores "Conectar" y secuencias a través del método Execute.</span><span class="sxs-lookup"><span data-stu-id="f7e19-194">-   “Wire up” readers and streams via Execute method.</span></span><br /><span data-ttu-id="f7e19-195">-Ejecución real se produce en los lectores y secuencias cuando se leen los datos.</span><span class="sxs-lookup"><span data-stu-id="f7e19-195">-   Actual execution occurs in the readers and streams as the data is read.</span></span>|<span data-ttu-id="f7e19-196">Directamente desde el método Execute del componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="f7e19-196">Directly from the Execute method of the pipeline component.</span></span>|  
|<span data-ttu-id="f7e19-197">data</span><span class="sxs-lookup"><span data-stu-id="f7e19-197">Data</span></span>|<span data-ttu-id="f7e19-198">Vuelve a crear en cada nivel de ajuste cuando se leen los datos a través de él.</span><span class="sxs-lookup"><span data-stu-id="f7e19-198">Re-created at each wrapping layer as data is read through it.</span></span>|<span data-ttu-id="f7e19-199">Leer, modificar y que se escribe en cada componente antes de que se la llame de componente siguiente.</span><span class="sxs-lookup"><span data-stu-id="f7e19-199">Read in, modified and written out at each component prior to next component being called.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7e19-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7e19-200">See Also</span></span>  
 [<span data-ttu-id="f7e19-201">Optimizar las aplicaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f7e19-201">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)