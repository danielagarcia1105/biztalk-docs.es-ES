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
# <a name="optimizing-pipeline-performance"></a>Optimizar el rendimiento de la canalización
Este tema describe las directrices para optimizar el rendimiento de las canalizaciones de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a>Prácticas recomendadas para optimizar el rendimiento de las canalizaciones de BizTalk Server  
  
1.  Dado que los componentes de canalización tienen un impacto significativo en el rendimiento (por ejemplo, un componente de canalización de paso realiza hasta 30 por ciento mejor que un componente de canalización de ensamblador y desensamblador XML), asegúrese de que los componentes de canalización personalizado realizan un rendimiento óptimo antes de implementarlos en su implementación. Minimice el número de componentes de canalización en sus canalizaciones personalizadas si desea maximizar el rendimiento general de la aplicación de BizTalk.  
  
2.  También puede mejorar el rendimiento general al reducir la frecuencia de persistencia de mensaje en el componente de canalización y codificando el componente para minimizar la redundancia. Todos los ensamblados personalizados y en particular la artefactos que pudieron afectar a rendimiento, como los componentes de seguimiento personalizado, se deben probar por separado en condiciones de sobrecarga para observar su comportamiento cuando el sistema funciona con la máxima capacidad y buscar posibles cuellos de botella.  
  
3.  Si tiene que leer el mensaje entrante dentro de un componente de canalización, evite cargar todo el documento en la memoria con un **XmlDocument** objeto. La cantidad de espacio necesario para una instancia de la **XmlDocument** clase para cargar y crear una representación en memoria de un documento XML es hasta 10 veces el tamaño de mensaje real. Para leer un mensaje, debe utilizar un **XmlTextReader** objeto junto con una instancia de las clases siguientes:  
  
    -   **VirtualStream (Microsoft.BizTalk.Streaming.dll)** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\ SchemaResolverComponent\SchemaResolverFlatFileDasm.  
  
    -   **ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.  
  
    -   **SeekAbleReadOnlyStream** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\SchemaResolverComponent\ SchemaResolverFlatFileDasm.  
  
4.  Utilice la PassThruReceive y las canalizaciones estándares PassThruTransmit siempre que sea posible. No contienen un componente de canalización y no realizan ningún procesamiento del mensaje. Por este motivo, asegurar un rendimiento máximo en recibir o enviar mensajes. Puede usar una canalización PassThruReceive en una ubicación de recepción si necesita publicar un documento binario en BizTalk MessageBox y una canalización PassThruTransmit en un puerto de envío si necesita enviar un mensaje binario. También puede usar la canalización PassThruTransmit en un puerto de envío físico enlazado a una orquestación si el mensaje se ha formateado previamente y está listo para su transmisión. Debe usar un enfoque diferente si necesita realizar una de las siguientes acciones:  
  
    -   Promocionar propiedades en el contexto de un mensaje de archivo sin formato o XML entrante.  
  
    -   Aplicar una asignación dentro de una ubicación de recepción.  
  
    -   Aplicar una asignación de una orquestación que se suscribe a un mensaje.  
  
    -   Aplicar una asignación en un puerto de envío que se suscribe a un mensaje.  
  
     Para llevar a cabo una de estas acciones, debe sondear y detectar el tipo de documento dentro de la canalización de recepción y asigne el valor (espacio de nombres #root-name) a la propiedad de contexto de MessageType. Esta operación se realiza normalmente por un componente de desensamblador como el componente de desensamblador Xml (XmlDasmComp) o el componente de desensamblador de archivos sin formato (FFDasmComp). En este caso, debe usar un estándar (por ejemplo, la canalización XmlReceive) o una canalización personalizada que contiene un estándar o un componente de desensamblador personalizado.  
  
5.  Adquirir recursos lo más tarde posible y liberarlos tan pronto como sea posible. Por ejemplo, si tiene acceso a datos en una base de datos, abra la conexión lo más tarde posible y cerrarlo tan pronto como sea posible. Utilice la instrucción using implícitamente liberar objetos descartables de C# o el bloque finally de una instrucción try-catch-finally para eliminar explícitamente los objetos. Instrumentar el código fuente para hacer que sus componentes fácil de depurar.  
  
6.  Eliminar los componentes de las canalizaciones que no son estrictamente necesarias para acelerar el procesamiento de mensajes.  
  
7.  Dentro de una canalización de recepción, debe promocionar los elementos en el contexto del mensaje solo si se necesita para el enrutamiento de mensajes (orquestaciones, puertos de envío) o degradación de propiedades de contexto del mensaje (puertos de envío).  
  
8.  Si es necesario incluir metadatos con un mensaje, y no utiliza los metadatos para fines de enrutamiento o degradación, use la **IBaseMessageContext.Write** en lugar del método la **IBaseMessageContext.Promote** método.  
  
9. Si necesita extraer información de un mensaje utilizando una expresión XPath, evite cargar todo el documento en la memoria con un **XmlDocument** objeto simplemente que se usará el **SelectNodes** o  **SelectSingleNode** métodos. Como alternativa, use las técnicas descritas en [optimizar el uso de memoria con transmisión por secuencias](../technical-guides/optimizing-memory-usage-with-streaming.md).  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a>Usar la transmisión por secuencias para minimizar el consumo de memoria necesario al cargar mensajes de canalizaciones  
 Las técnicas siguientes describen cómo minimizar el consumo de memoria de un mensaje al cargar el mensaje en una canalización.  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a>Use ReadOnlySeekableStream y VirtualStream para procesar un mensaje desde un componente de canalización  
 Se considera una práctica recomendada para evitar que se cargue el mensaje completo en la memoria dentro de los componentes de canalización. Un enfoque preferible consiste en encapsular la secuencia de entrada con una implementación de secuencia personalizada y, a continuación, como se realizan las solicitudes de lectura, la implementación de secuencia personalizada lee la secuencia subyacente, ajustada y procesa los datos a medida que se lee (en un modo de transmisión por secuencias puro). Esto puede ser muy difícil de implementar y puede no ser posible, dependiendo de qué debe hacerse con la secuencia. En este caso, utilice la **ReadOnlySeekableStream** y **VirtualStream** clases expuestas por la Microsoft.BizTalk.Streaming.dll. También se proporciona una implementación de estos en [controlador de propiedad XPath arbitrario (ejemplo de BizTalk Server)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) en el SDK de BizTalk. **ReadOnlySeekableStream** garantiza que se puede mover el cursor al principio de la secuencia. El **VirtualStream** usará una MemoryStream internamente, a menos que el tamaño está por encima de un umbral especificado, en cuyo caso se escribirá la secuencia en el sistema de archivos. Uso de estas dos secuencias en combinación (mediante **VirtualStream** como el almacenamiento persistente para la **ReadOnlySeekableStream**) proporciona capacidades de "desbordamiento del sistema de archivos" y "seekability". Esto es útil para el procesamiento de mensajes de gran tamaño sin necesidad de cargar el mensaje completo en la memoria. El código siguiente podría utilizarse en un componente de canalización para implementar esta funcionalidad.  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 Este código proporciona un umbral de"desbordamiento" mediante la exposición de bufferSize y thresholdSize variables en cada ubicación de recepción o configuración de puerto de envío. Este umbral de desbordamiento, a continuación, puede ser ajustado por los desarrolladores o los administradores de diferentes tipos de mensaje y distintas configuraciones (por ejemplo, 32 bits. 64 bits).  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a>Uso de XPathReader y XPathCollection para extraer un objeto determinado de IBaseMessage desde dentro de un componente de canalización personalizado.  
 Si necesitan valores concretos para extraerse de un documento XML, en lugar de utilizar el **SelectNodes** y **SelectSingleNode** métodos expuestos por la clase XmlDocument, utilizar una instancia de la clase XPathReader proporciona el ensamblado Microsoft.BizTalk.XPathReader.dll como se muestra en el ejemplo de código siguiente.  
  
> [!NOTE]  
>  Para los mensajes más pequeños, especialmente, mediante un XmlDocument con SelectNodes o SelectSingleNode puede proporcionar un mejor rendimiento que el uso de XPathReader, pero XPathReader le permite mantener un perfil de memoria de la aplicación.  
  
 Este ejemplo muestra cómo utilizar el XPathReader y XPathCollection para extraer un determinado **IBaseMessage** objeto desde dentro de un componente de canalización personalizado.  
  
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
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a>Usar XMLWriter y XMLReader con XMLTranslatorStream para procesar un mensaje desde un componente de canalización  
 Otro método para implementar un componente de canalización personalizado que usa un método de transmisión por secuencias es usar .NET **XmlReader** y **XmlWriter** clases junto con la  **XmlTranslatorStream** clase proporcionada por el servidor BizTalk Server. Por ejemplo, el **NamespaceTranslatorStream** clase incluida en el ensamblado Microsoft.BizTalk.Pipeline.Components hereda de **XmlTranslatorStream** y puede utilizarse para reemplazar un espacio de nombres anterior con una nueva en el documento XML contenido en la secuencia. Para poder utilizar esta funcionalidad dentro de un componente de canalización personalizado, puede ajustar el flujo de datos original de la parte del cuerpo de mensaje con una nueva instancia de la **NamespaceTranslatorStream** clase y devolver el último. De esta manera el mensaje entrante no se lee o procesar dentro del componente de canalización, pero sólo cuando el flujo de un componente subsiguientes en la misma canalización lee o finalmente es utilizado por el agente de mensajes antes de publicar el documento en el servidor BizTalk Server Cuadro de mensajes.  
  
 En el ejemplo siguiente se muestra cómo utilizar esta funcionalidad.  
  
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
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a>Utilizar ResourceTracker en componentes de canalización personalizado  
 Un componente de canalización debe administrar la vigencia de los objetos que crea y realizar la recolección de tan pronto como ya no se requieren estos objetos.  Si el componente de canalización quiere que la duración de los objetos hasta el último hasta el final de la ejecución de la canalización, a continuación, debe agregar dichos objetos a la herramienta de seguimiento de recursos que la canalización puede capturar desde el contexto de canalización.  
  
 La herramienta de seguimiento de recursos se utiliza para los siguientes tipos de objetos:  
  
-   Objetos de flujo  
  
-   Objetos COM  
  
-   Objetos IDisposable  
  
 El motor de mensajería se asegura de que todos los recursos nativos que se agregan a la herramienta de seguimiento de recursos se liberan en el momento adecuado, que resulta después de la canalización se ejecuta completamente, independientemente de si es correcto o incorrecto. La duración de la instancia de seguimiento de recursos y los objetos que está realizando el seguimiento se administra mediante el objeto de contexto de canalización. El contexto de canalización están disponible para todos los tipos de componentes de canalización a través de un objeto que implementa la interfaz IPipelineContext.  
  
 Por ejemplo, el fragmento de código siguiente es un ejemplo que muestra cómo utilizar la propiedad ResourceTracker en componentes de canalización personalizados. Para utilizar la propiedad ResourceTracker, el fragmento de código utiliza el siguiente parámetro `IPipelineContext.ResourceTracker.AddResource`. En este parámetro:  
  
-   IPipelineContext (interfaz) define los métodos utilizados para tener acceso a todas las interfaces específicas de procesamiento de documentos.  
  
-   Propiedad ResourceTracker hace referencia a IPipelineContext y se utiliza para realizar un seguimiento de los objetos que se eliminan de forma explícita al final del procesamiento de canalización.  
  
-   Método ResourceTracker.AddResource se usa para realizar un seguimiento de los objetos COM, los objetos descartables y secuencias y siempre se debe utilizar dentro de un componente de canalización personalizado para explícitamente cerrar (secuencias), dispose (objetos IDisposable) o liberar (objetos COM) estos tipos de recursos cuando se publica un mensaje a BizTalk MessageBox.  
  
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
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a>Comparación de los mensajes de carga en canalizaciones mediante un enfoque en memoria y mediante un enfoque de transmisión por secuencias  
 La siguiente información se toma del blog de Nic Barden, [http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228). Esta tabla proporciona una comparación resumida de los mensajes de carga en canalizaciones mediante un enfoque en memoria y mediante un enfoque de transmisión por secuencias.  
  
|Comparación de...|Transmisión por secuencias|En la memoria|  
|----------------------|---------------|---------------|  
|Uso de memoria por mensaje|Low, independientemente del tamaño del mensaje|Alta (varía en función del tamaño del mensaje)|  
|Clases comunes que se utilizan para procesar datos XML|Integrado en y personalizados derivaciones de:<br /><br /> XmlTranslatorStream, XmlWriter y XmlReader|XmlDocument, XPathDocument, MemoryStream y VirtualStream|  
|Documentación|Malo: muchas clases de BizTalk no documentadas y no compatibles|Muy bueno - clases de .NET Framework|  
|Ubicación del código de "Lógica de procesamiento"|-Lectores "Conectar" y secuencias a través del método Execute.<br />-Ejecución real se produce en los lectores y secuencias cuando se leen los datos.|Directamente desde el método Execute del componente de canalización.|  
|data|Vuelve a crear en cada nivel de ajuste cuando se leen los datos a través de él.|Leer, modificar y que se escribe en cada componente antes de que se la llame de componente siguiente.|  
  
## <a name="see-also"></a>Vea también  
 [Optimizar las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md)