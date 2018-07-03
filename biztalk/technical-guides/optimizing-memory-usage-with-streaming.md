---
title: Optimización del uso de memoria con Streaming | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8ba8820-65b4-4161-9f7a-3ae3d39e3d11
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c86fafdab538dcf60f52265e10711b1a43340a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024154"
---
# <a name="optimizing-memory-usage-with-streaming"></a><span data-ttu-id="2bd72-102">Optimizar el uso de memoria con transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="2bd72-102">Optimizing Memory Usage with Streaming</span></span>
<span data-ttu-id="2bd72-103">En este tema proporciona recomendaciones para utilizar patrones de streaming para minimizar la superficie de memoria de mensaje al enviar o recibir mensajes de gran tamaño con un transporte WCF o al cargar mensajes en orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="2bd72-103">This topic provides recommendations for using streaming patterns to minimize message memory footprints when sending or receiving large messages with a WCF transport or when loading messages in orchestrations.</span></span>   
<span data-ttu-id="2bd72-104">Cuando se usa el código en una orquestación para leer el contenido de un mensaje, evite el uso de variables de XmlDocument.</span><span class="sxs-lookup"><span data-stu-id="2bd72-104">When using code in an orchestration to read the contents of a message, avoid using XmlDocument variables.</span></span> <span data-ttu-id="2bd72-105">Carga de un mensaje en una variable XmlDocument conlleva una sobrecarga considerable, especialmente para los mensajes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="2bd72-105">Loading a message into an XmlDocument variable incurs significant overhead, especially for large messages.</span></span> <span data-ttu-id="2bd72-106">Esta sobrecarga es en términos de uso de memoria y procesamiento para generar las estructuras en memoria.</span><span class="sxs-lookup"><span data-stu-id="2bd72-106">This overhead is in terms of memory usage and processing to build the in-memory structures.</span></span> <span data-ttu-id="2bd72-107">El uso de una instancia de XmlDocument fuerza el contenido completo del mensaje que se carga en memoria con el fin de crear el gráfico de objetos para el módulo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="2bd72-107">The use of an XmlDocument instance forces the entire message contents to be loaded into memory in order to build the object graph for the Document Object Module (DOM).</span></span> <span data-ttu-id="2bd72-108">La cantidad total de memoria utilizada por una instancia de esta clase puede ser aproximadamente 10 veces el tamaño de mensaje real.</span><span class="sxs-lookup"><span data-stu-id="2bd72-108">The total amount of memory used by an instance of this class can be around 10 times the actual message size.</span></span> <span data-ttu-id="2bd72-109">Para obtener más información acerca de la superficie de memoria necesaria al cargar un mensaje en una variable de XmlDocument, consulte [capítulo 9: mejorar el rendimiento de XML](http://go.microsoft.com/fwlink/?LinkId=139772) (http://go.microsoft.com/fwlink/?LinkId=139772) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="2bd72-109">For more information about the memory footprint required when loading a message into an XmlDocument variable, see [Chapter 9 – Improving XML Performance](http://go.microsoft.com/fwlink/?LinkId=139772) (http://go.microsoft.com/fwlink/?LinkId=139772) on MSDN.</span></span>   
<span data-ttu-id="2bd72-110">El resto de este tema proporciona los métodos alternativos para leer el contenido del mensaje que no requiere la carga de un mensaje en una variable de XmlDocument.</span><span class="sxs-lookup"><span data-stu-id="2bd72-110">The remainder of this topic provides alternative methods for reading message contents that do not require loading a message into an XmlDocument variable.</span></span>  
  
## <a name="use-streaming-when-sending-or-receiving-large-messages-with-a-wcf-transport"></a><span data-ttu-id="2bd72-111">Usar la transmisión por secuencias al enviar o recibir mensajes de gran tamaño con un transporte WCF</span><span class="sxs-lookup"><span data-stu-id="2bd72-111">Use streaming when sending or receiving large messages with a WCF transport</span></span>  
 <span data-ttu-id="2bd72-112">Al enviar o recibir mensajes de gran tamaño con un transporte WCF, usar el adaptador de WCF-Custom o WCF-CustomIsolated y configurar con un tipo de enlace que admita la **transferMode = transmitido por secuencias** opción, como los siguientes enlaces:</span><span class="sxs-lookup"><span data-stu-id="2bd72-112">When sending or receiving large messages with a WCF transport, use the WCF-Custom or WCF-CustomIsolated adapter and configure with a binding type that supports the **transferMode = Streamed** option, such as the following bindings:</span></span>  
  
- <span data-ttu-id="2bd72-113">**basicHttpBinding + BasicHttpBindingElement, transferMode = transmitido por secuencias**</span><span class="sxs-lookup"><span data-stu-id="2bd72-113">**basicHttpBinding + BasicHttpBindingElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="2bd72-114">**netTcpBinding + NetTcpBindingElement, transferMode = transmitido por secuencias**</span><span class="sxs-lookup"><span data-stu-id="2bd72-114">**netTcpBinding + NetTcpBindingElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="2bd72-115">**customBinding + HttpTransportElement, transferMode = transmitido por secuencias**</span><span class="sxs-lookup"><span data-stu-id="2bd72-115">**customBinding + HttpTransportElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="2bd72-116">**customBinding + ConnectionOrientedTransportElement, transferMode = transmitido por secuencias**</span><span class="sxs-lookup"><span data-stu-id="2bd72-116">**customBinding +ConnectionOrientedTransportElement, transferMode = Streamed**</span></span>  
  
  <span data-ttu-id="2bd72-117">Elección de un adaptador de WCF-Custom o WCF-CustomIsolated, junto con un enlace que admita la **transferMode = transmitido por secuencias** opción implementar el streaming de mensajes grandes en el sistema de archivos según sea necesario y le mitigar posibles problemas de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="2bd72-117">Choosing a WCF-Custom or WCF-CustomIsolated adapter along with a binding that supports the **transferMode = Streamed** option will implement streaming of large messages to the file system as needed, and will mitigate potential out-of-memory issues.</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-orchestrations"></a><span data-ttu-id="2bd72-118">Usar el flujo para minimizar el consumo de memoria necesario al cargar mensajes en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="2bd72-118">Use streaming to minimize the memory footprint required when loading messages in orchestrations</span></span>  
 <span data-ttu-id="2bd72-119">Las técnicas siguientes describen cómo minimizar el consumo de memoria de un mensaje al cargar el mensaje en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="2bd72-119">The following techniques describe how to minimize the memory footprint of a message when loading the message into an orchestration.</span></span>  
  
### <a name="use-an-xlangmessage-variable-to-process-the-contents-of-a-message-or-message-part"></a><span data-ttu-id="2bd72-120">Usar una variable de XLANGMessage para procesar el contenido de un mensaje o parte de mensaje</span><span class="sxs-lookup"><span data-stu-id="2bd72-120">Use an XLANGMessage variable to process the contents of a message or message part</span></span>  
 <span data-ttu-id="2bd72-121">Cuando se pasa un mensaje desde una orquestación a bibliotecas de clases .NET, no pase como XmlDocument variables, por razones mencionadas anteriormente en este tema; usar variables de XLANGMessage en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2bd72-121">When passing a message from an orchestration to .NET class libraries, do not pass them as XmlDocument variables, for reasons mentioned earlier in this topic; use XLANGMessage variables instead.</span></span> <span data-ttu-id="2bd72-122">Las técnicas siguientes muestran los métodos para leer un mensaje o parte del mensaje utilizando una variable de XLANGMessage.</span><span class="sxs-lookup"><span data-stu-id="2bd72-122">The following techniques illustrate methods for reading a message or message part using an XLANGMessage variable.</span></span>  
  
-   <span data-ttu-id="2bd72-123">**Procesar mensajes con XMLReader** : para procesar un mensaje con una instancia de XmlReader, pasar el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento con XmlReader.</span><span class="sxs-lookup"><span data-stu-id="2bd72-123">**Process messages with XMLReader** - To process a message with an XmlReader instance, pass the message to .NET code as an XLANGMessage, and retrieve the Part content using XmlReader.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            using (XmlReader reader = message[0].RetrieveAs(typeof(XmlReader)) as XmlReader)  
            if (reader != null)  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   <span data-ttu-id="2bd72-124">**Recuperar el contenido de un mensaje en una cadena con StreamReader** -uno de los usos habituales de XmlDocument en orquestaciones consiste en recuperar el mensaje como una cadena XML mediante XmlDocument.OuterXml().</span><span class="sxs-lookup"><span data-stu-id="2bd72-124">**Retrieve the contents of a message into a string with StreamReader** - One of the common uses of XmlDocument in orchestrations is to retrieve the message as an XML string using XmlDocument.OuterXml().</span></span> <span data-ttu-id="2bd72-125">El ejemplo de código siguiente muestra un método alternativo que recupera el mensaje como una cadena con una variable de XLANGMessage.</span><span class="sxs-lookup"><span data-stu-id="2bd72-125">The following code example illustrates an alternative method which retrieves the message as a string using an XLANGMessage variable.</span></span>  
  
    ```  
    public static string MessageToString(XLANGMessage message)  
    {  
        string strResults;  
        try  
        {  
            using (Stream stream = message[0].RetrieveAs(typeof(Stream)) as Stream)  
            {  
                using (StreamReader reader = new StreamReader(stream))  
                {  
                    strResults = reader.ReadToEnd();  
                }  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return strResults;  
    }  
    ```  
  
-   <span data-ttu-id="2bd72-126">**Recuperar el contenido de mensajes sencillos de .NET en una cadena** -si el tipo del mensaje es un tipo simple. NET, puede recuperar el mensaje como ese tipo.</span><span class="sxs-lookup"><span data-stu-id="2bd72-126">**Retrieve the contents of simple .NET messages into a string** - If the type of the message is a simple .NET type, you can retrieve the message as that type.</span></span> <span data-ttu-id="2bd72-127">Por ejemplo, para obtener el mensaje como una cadena, pase el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento como una cadena.</span><span class="sxs-lookup"><span data-stu-id="2bd72-127">For example, to get the message as a string, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a string.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            string content = message[0].RetrieveAs(typeof(string)) as string;  
            if (!string.IsNullOrEmpty(content))  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   <span data-ttu-id="2bd72-128">**Recuperar el contenido de un mensaje en una secuencia** : para obtener el mensaje como una secuencia, pasar el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento como una secuencia.</span><span class="sxs-lookup"><span data-stu-id="2bd72-128">**Retrieve the contents of a message into a stream** - To get the message as a stream, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a stream.</span></span>  
  
    ```  
    public Stream ProcessRequestReturnStream(XLANGMessage message, int bufferSize, int thresholdSize)  
    {  
       ...  
       try  
       {  
          using (VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize))  
          {  
             using (Stream partStream = (Stream)message[0].RetrieveAs(typeof(Stream)))  
             //Note that when calling this code, if the XmlDocument is quite large, keeping it in a memory with a MemoryStream may have an adverse effect on performance.   
             //In this case, it may be worthwhile to consider an approach that uses a VirtualStream + ReadonlySeekableStream to buffer it to the file system, if its size is bigger than the thresholdSize parameter.  
             //Keep in mind that:  
             // - If the message size is smaller than the threshold size, the VirtualStream class buffers the stream to a MemoryStream.  
             // - If the message size is bigger than the threshold size, the VirtualStream class buffers the stream to a temporary file.  
                using (ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(partStream, virtualStream, bufferSize))  
                {  
                   using (XmlReader reader = XmlReader.Create(readOnlySeekableStream))  
                   {  
  
                   }  
                }  
             }  
          }  
       }  
       catch (Exception ex)  
       {  
  
       }  
       finally  
       {  
          message.Dispose();  
       }  
       return stream;  
    }  
    ```  
  
-   <span data-ttu-id="2bd72-129">**Recuperar el contenido de un mensaje a un objeto .NET** : para obtener el mensaje como un objeto. NET, pasar el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento como una instancia de una clase. NET.</span><span class="sxs-lookup"><span data-stu-id="2bd72-129">**Retrieve the contents of a message into a .NET object** - To get the message as a .NET object, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as an instance of a .NET class.</span></span> <span data-ttu-id="2bd72-130">Crear este último del esquema Xml del mensaje mediante la herramienta XML Schema Definition Tool (Xsd.exe) proporcionada por Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="2bd72-130">Create this latter from the Xml Schema of the message using the XML Schema Definition Tool (Xsd.exe) tool provided by Visual Studio 2010.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2bd72-131">Esta técnica es válida solo cuando los mensajes son pequeños.</span><span class="sxs-lookup"><span data-stu-id="2bd72-131">This technique is valid only when messages are small.</span></span> <span data-ttu-id="2bd72-132">En caso contrario, este enfoque podría suponer en una sobrecarga considerable al deserializar el mensaje real en un objeto. NET.</span><span class="sxs-lookup"><span data-stu-id="2bd72-132">Otherwise, this approach could incur in a significant overhead to de-serialize the actual message into a .NET object.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
          {  
          Request request = message[0].RetrieveAs(typeof(Request)) as Request;  
          if (request != null)  
          {  
             ...  
          }  
       }  
       finally  
       {  
          message.Dispose();  
       }  
  
    }  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="2bd72-133">El uso de la **Dispose()** método expuesto por el parámetro XLANGMessage antes de devolver desde el código de .NET es especialmente importante en escenarios de bucle orquestaciones de larga ejecución que se pueden acumular instancias de la Objeto XLANGMessage sin liberarlas con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="2bd72-133">Use of the **Dispose()** method exposed by the XLANGMessage parameter before returning from the .NET code is particularly important in looping scenarios and long-running orchestrations that can accumulate instances of the XLANGMessage object without releasing them over time.</span></span> <span data-ttu-id="2bd72-134">Para obtener más información acerca de los mensajes que realiza la llamada. Dispose() de esta manera, vea [mensajes representados como XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) en la documentación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2bd72-134">For more information about calling message.Dispose() in this manner, see [Messages Represented as XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) in the BizTalk Server documentation.</span></span> <span data-ttu-id="2bd72-135">En este tema también proporciona procedimientos recomendados para usar IStreamFactory para construir XLANGMessage variables en el código de usuario mediante un enfoque basado en secuencia.</span><span class="sxs-lookup"><span data-stu-id="2bd72-135">This topic also provides best practices for using IStreamFactory to construct XLANGMessage variables in user code using a stream-based approach.</span></span>  
  
 <span data-ttu-id="2bd72-136">Para obtener más información sobre las distintas formas de procesar un XLANGMessage dentro de un componente de aplicación auxiliar invocado por una orquestación, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bd72-136">For more information about the different ways to process an XLANGMessage within an helper component invoked by an orchestration, see the following topics:</span></span>  
  
-   <span data-ttu-id="2bd72-137">[4 formas diferentes para procesar un XLANGMessage dentro de un componente de aplicación auxiliar invocado por una orquestación, parte 1](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420).</span><span class="sxs-lookup"><span data-stu-id="2bd72-137">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 1](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420).</span></span>  
  
-   <span data-ttu-id="2bd72-138">[4 formas diferentes para procesar un XLANGMessage dentro de un componente de aplicación auxiliar invocado por una orquestación, parte 2](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421).</span><span class="sxs-lookup"><span data-stu-id="2bd72-138">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 2](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-value-from-an-xlangmessage-object-from-a-method-invoked-by-an-orchestration"></a><span data-ttu-id="2bd72-139">Uso de XPathReader y XPathCollection para extraer un valor de un objeto XLANGMessage desde un método invocado por una orquestación</span><span class="sxs-lookup"><span data-stu-id="2bd72-139">Using XPathReader and XPathCollection to extract a value from an XLANGMessage object from a method invoked by an orchestration</span></span>  
 <span data-ttu-id="2bd72-140">Evite el uso de la clase XMLDocument para leer el contenido de los mensajes XML desde código personalizado, como los componentes de canalización personalizados o clases auxiliares que invoca las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="2bd72-140">Avoid using the XMLDocument class to read the contents of XML messages from custom code, such as custom pipeline components or helper classes invoked by orchestrations.</span></span> <span data-ttu-id="2bd72-141">Cuando se usa una instancia de XMLDocument para cargar un mensaje XML, el mensaje completo se carga en memoria, esto es ineficiente y puede requerir la memoria hasta 10 veces el tamaño real del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2bd72-141">When using an XMLDocument instance to load an XML message, the entire message is loaded into memory, which is inefficient and may require memory up to 10 times the actual size of the message.</span></span> <span data-ttu-id="2bd72-142">Una forma más eficaz de leer el contenido de los mensajes XML es utilizar una técnica de transmisión por secuencias para ajustar la secuencia original con una de las clases de secuencia proporcionadas por el ensamblado Microsoft.BizTalk.Streaming.dll.</span><span class="sxs-lookup"><span data-stu-id="2bd72-142">A more efficient way of reading the contents of XML messages is to use a streaming technique to wrap the original stream with one of the stream classes provided by the Microsoft.BizTalk.Streaming.dll assembly.</span></span> <span data-ttu-id="2bd72-143">Esta técnica es especialmente útil cuando se cargan los mensajes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="2bd72-143">This technique is particularly useful when loading large messages.</span></span>  
  
 <span data-ttu-id="2bd72-144">Si los valores específicos deben extraerse de un documento XML, en lugar de usar los métodos SelectNodes y SelectSingleNode expuestos por la clase XmlDocument, use una instancia de la clase XPathReader proporcionada por el ensamblado Microsoft.BizTalk.XPathReader.dll como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="2bd72-144">If specific values need to be pulled from an XML document, instead of using the SelectNodes and SelectSingleNode methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
-   <span data-ttu-id="2bd72-145">En este ejemplo se muestra cómo utilizar el XPathReader y XPathCollection para extraer un valor determinado de un objeto XLANGMessage dentro de un método invocado por una orquestación.</span><span class="sxs-lookup"><span data-stu-id="2bd72-145">This example illustrates using the XPathReader and XPathCollection to extract a given value from an XLANGMessage object inside a method invoked by an orchestration.</span></span>  
  
    ```  
    public static string SelectSingleNode(XLANGMessage message, string xPath)   
    {  
        try  
        {  
            if (message == null || string.IsNullOrEmpty(xPath))  
            {  
                return string.Empty;  
            }  
            using (XmlReader reader = (XmlReader)message[0].RetrieveAs(typeof(XmlReader)))  
            {  
                XPathCollection xPathCollection = new XPathCollection();  
                XPathReader xPathReader = new XPathReader(reader, xPathCollection);  
                xPathCollection.Add(xPath);  
                while (xPathReader.ReadUntilMatch())  
                {  
                    if (xPathReader.Match(0))  
                    {  
                        return xPathReader.ReadString();  
                    }  
                }  
            }  
        }  
        catch (Exception ex)  
        {  
            ...  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return string.Empty;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2bd72-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bd72-146">See Also</span></span>  
 [<span data-ttu-id="2bd72-147">Optimización de las aplicaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2bd72-147">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)