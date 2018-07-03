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
# <a name="optimizing-pipeline-performance"></a>Optimizar el rendimiento de la canalización
En este tema se describe las directrices para optimizar el rendimiento de las canalizaciones de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución.  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a>Procedimientos recomendados para optimizar el rendimiento de las canalizaciones de BizTalk Server  
  
1. Dado que los componentes de canalización tienen un impacto significativo en el rendimiento (por ejemplo, un componente de canalización de paso realiza hasta un 30 por ciento mejor que un componente de canalización de ensamblador y desensamblador XML), asegúrese de que se realice cualquier componente de canalización personalizado óptimamente antes de implementarlos en su implementación. Minimizar el número de componentes de canalización de las canalizaciones personalizadas si desea maximizar el rendimiento general de la aplicación de BizTalk.  
  
2. También puede mejorar el rendimiento general al reducir la frecuencia de persistencia del mensaje en el componente de canalización y codificando el componente para minimizar la redundancia. Todos los ensamblados personalizados y en particular los artefactos que podrían afectar a rendimiento, como los componentes de seguimiento personalizado, se deben probar por separado en condiciones de mucha carga para observar su comportamiento cuando el sistema funciona con la máxima capacidad y buscar posibles cuellos de botella.  
  
3. Si tiene que leer el mensaje entrante dentro de un componente de canalización, evite la carga de todo el documento en memoria mediante una **XmlDocument** objeto. La cantidad de espacio necesario por una instancia de la **XmlDocument** clase para cargar y crear una representación en memoria de un documento XML es hasta 10 veces el tamaño de mensaje real. Para leer un mensaje, se debe usar un **XmlTextReader** objeto junto con una instancia de las clases siguientes:  
  
   -   **VirtualStream (Microsoft.BizTalk.Streaming.dll)** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\ SchemaResolverComponent\SchemaResolverFlatFileDasm.  
  
   -   **ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.  
  
   -   **SeekAbleReadOnlyStream** -el código fuente de esta clase se encuentra en dos ubicaciones en el SDK de canalizaciones como sigue: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\SchemaResolverComponent\ SchemaResolverFlatFileDasm.  
  
4. Utilice la PassThruReceive y las canalizaciones estándares de PassThruTransmit siempre que sea posible. No contienen un componente de canalización y no realizan ningún procesamiento del mensaje. Por este motivo, garantiza un rendimiento máximo en recibir o enviar mensajes. Puede usar una canalización PassThruReceive en una ubicación de recepción si necesita publicar un documento binario para BizTalk MessageBox y una canalización PassThruTransmit en un puerto de envío si necesita enviar un mensaje binario. También puede usar la canalización PassThruTransmit en un puerto de envío físicos enlazado a una orquestación si el mensaje se ha formateado y está listo para su transmisión. Necesita usar un enfoque diferente si necesita realizar una de las acciones siguientes:  
  
   - Promocionar propiedades en el contexto de un mensaje de archivo sin formato o XML entrante.  
  
   - Aplicar una asignación dentro de una ubicación de recepción.  
  
   - Aplicar una asignación de una orquestación que se suscribe a un mensaje.  
  
   - Aplicar una asignación en un puerto de envío se suscribe a un mensaje.  
  
     Para llevar a cabo una de estas acciones, de sondeo y detectar el tipo de documento dentro de la canalización de recepción y asigne el valor de (espacio de nombres #root-name) a la propiedad de contexto de MessageType. Esta operación se realiza normalmente un componente de desensamblador como el componente de desensamblador Xml (XmlDasmComp) o el componente de desensamblador de archivos sin formato (FFDasmComp). En este caso, deberá usar un estándar (por ejemplo, la canalización XmlReceive) o una canalización personalizada que contiene un estándar o un componente de desensamblador personalizado.  
  
5. Adquiera recursos tan tarde como sea posible y liberarlos tan pronto como sea posible. Por ejemplo, si necesita acceso a datos en una base de datos, abra la conexión tan tarde como sea posible y cerrarlo tan pronto como sea posible. Utilice la instrucción using implícitamente liberar objetos desechables de C# o el bloque finally de una instrucción try-catch-finally desecharlo de forma explícita los objetos. Instrumentar el código fuente para simplificar la depuración de los componentes.  
  
6. Elimine los componentes de las canalizaciones que no son estrictamente necesarias para acelerar el procesamiento de mensajes.  
  
7. Dentro de una canalización de recepción, debe promover elementos en el contexto del mensaje solo si las necesita para el enrutamiento de mensajes (orquestaciones, puertos de envío) o degradación de propiedades de contexto del mensaje (puertos de envío).  
  
8. Si necesita incluir metadatos con un mensaje y no usa los metadatos para fines de enrutamiento o degradación, use el **IBaseMessageContext.Write** método en lugar de la **IBaseMessageContext.Promote** método.  
  
9. Si necesita extraer información de un mensaje mediante una expresión XPath, evite la carga de todo el documento en memoria mediante una **XmlDocument** objeto solo para usar el **SelectNodes** o  **SelectSingleNode** métodos. Como alternativa, use las técnicas descritas en [optimizar el uso de memoria con Streaming](../technical-guides/optimizing-memory-usage-with-streaming.md).  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a>Usar el flujo para minimizar el consumo de memoria necesario al cargar los mensajes en las canalizaciones  
 Las técnicas siguientes describen cómo minimizar el consumo de memoria de un mensaje al cargar el mensaje en una canalización.  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a>Use ReadOnlySeekableStream y VirtualStream para procesar un mensaje desde un componente de canalización  
 Se considera una práctica recomendada para evitar cargar todo el mensaje en memoria dentro de los componentes de canalización. Un enfoque preferible es ajustar la secuencia entrante con una implementación de secuencia personalizada y, a continuación, como se realizan solicitudes de lectura, la implementación de secuencia personalizada lee la secuencia subyacente, ajustada y procesa los datos a medida que se lee (de forma pura streaming). Esto puede ser muy difícil de implementar y puede no ser posible, dependiendo de qué debe hacerse con la secuencia. En este caso, utilice el **ReadOnlySeekableStream** y **VirtualStream** clases expuestas por la Microsoft.BizTalk.Streaming.dll. También se proporciona una implementación de estos en [controlador de propiedad XPath arbitrario (ejemplo de BizTalk Server)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) en el SDK de BizTalk. **ReadOnlySeekableStream** garantiza que se puede mover el cursor al principio de la secuencia. El **VirtualStream** usará un MemoryStream internamente, a menos que el tamaño es a través de un umbral especificado, en cuyo caso escribirá la secuencia en el sistema de archivos. Uso de estas dos secuencias en combinación (mediante **VirtualStream** como almacenamiento persistente para el **ReadOnlySeekableStream**) proporciona capacidades de "desbordamiento del sistema de archivos" y "seekability". Esto permite el procesamiento de mensajes de gran tamaño sin tener que cargar el mensaje completo en la memoria. El código siguiente podría usarse en un componente de canalización para implementar esta funcionalidad.  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 Este código proporciona un umbral de"desbordamiento" exponiendo bufferSize y thresholdSize variables en cada ubicación de recepción o configuración de puerto de envío. A continuación, se puede ajustar este umbral desbordamiento por desarrolladores o administradores para diferentes tipos de mensaje y para distintas configuraciones (por ejemplo, 32 bits frente a 64 bits).  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a>Uso de XPathReader y XPathCollection para extraer un objeto determinado de IBaseMessage desde dentro de un componente de canalización personalizado.  
 Si los valores específicos que deben extraerse de un documento XML, en lugar de usar el **SelectNodes** y **SelectSingleNode** los métodos expuestos por la clase XmlDocument, use una instancia de la clase XPathReader proporcionado por el ensamblado Microsoft.BizTalk.XPathReader.dll como se muestra en el ejemplo de código siguiente.  
  
> [!NOTE]  
>  Para los mensajes más pequeños, especialmente, usa un XmlDocument con SelectNodes o SelectSingleNode puede proporcionar un mejor rendimiento que el uso de XPathReader, pero XPathReader le permite mantener un perfil de memoria planos de la aplicación.  
  
 En este ejemplo se muestra cómo usar el XPathReader y XPathCollection para extraer un determinado **IBaseMessage** objeto desde dentro de un componente de canalización personalizado.  
  
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
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a>Usar XMLReader y XMLWriter con XMLTranslatorStream para procesar un mensaje desde un componente de canalización  
 Otro método para implementar un componente de canalización personalizado que usa un enfoque de transmisión por secuencias es usar .NET **XmlReader** y **XmlWriter** clases junto con el  **XmlTranslatorStream** clase proporcionada por el servidor BizTalk Server. Por ejemplo, el **NamespaceTranslatorStream** hereda la clase contenida en el ensamblado Microsoft.BizTalk.Pipeline.Components **XmlTranslatorStream** y puede utilizarse para reemplazar un espacio de nombres anterior por otro nuevo en el documento XML contenido en la secuencia. Para poder usar esta funcionalidad dentro de un componente de canalización personalizado, puede ajustar el flujo de datos original de la parte del cuerpo de mensaje con una nueva instancia de la **NamespaceTranslatorStream** clase y devolver el último. De esta forma el mensaje entrante no se leen o procesan dentro del componente de canalización, pero solo cuando la secuencia se lee mediante un componente subsiguientes en la misma canalización o, por último, se consume el agente de mensaje antes de publicar el documento en el servidor BizTalk Server Cuadro de mensajes.  
  
 El ejemplo siguiente muestra cómo usar esta funcionalidad.  
  
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
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a>Uso de ResourceTracker en componentes de canalización personalizados  
 Un componente de canalización debe administrar la vigencia de los objetos que crea y realizar la recolección de elementos, en cuanto ya no se requieren estos objetos.  Si desea que el componente de canalización de la duración de los objetos hasta el último hasta el final de la ejecución de la canalización, a continuación, debe agregar estos objetos para el seguimiento de recursos que la canalización puede capturar desde el contexto de canalización.  
  
 La herramienta de seguimiento de recursos se usa para los siguientes tipos de objetos:  
  
- Objetos Stream  
  
- Objetos COM  
  
- Objetos IDisposable  
  
  El motor de mensajería garantiza que todos los recursos nativos que se agregan a la herramienta de seguimiento de recursos se liberan en el momento adecuado, que es después de la canalización se ejecuta completamente, independientemente de si es correcta o errónea. El objeto de contexto de canalización administra la duración de la instancia de la herramienta de seguimiento de recursos y los objetos que está realizando el seguimiento. El contexto de canalización está disponible para todos los tipos de componentes de canalización a través de un objeto que implementa la interfaz IPipelineContext.  
  
  Por ejemplo, el siguiente fragmento de código es un ejemplo que ilustra cómo usar la propiedad ResourceTracker en componentes de canalización personalizados. Para usar la propiedad ResourceTracker, el fragmento de código usa el parámetro siguiente `IPipelineContext.ResourceTracker.AddResource`. En este parámetro:  
  
- IPipelineContext (interfaz) define los métodos utilizados para tener acceso a todas las interfaces específicas de procesamiento de documentos.  
  
- Propiedad ResourceTracker hace referencia a IPipelineContext y se usa para realizar un seguimiento de los objetos que se eliminarán de forma explícita al final del procesamiento de canalización.  
  
- Método ResourceTracker.AddResource se usa para realizar un seguimiento de los objetos COM, objetos desechables y secuencias y siempre se debe usar dentro de un componente de canalización personalizado para explícitamente cerrar (secuencias), eliminar (objetos IDisposable) o liberar (objetos COM) estos tipos de recursos cuando se publica un mensaje a BizTalk MessageBox.  
  
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
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a>Comparación de los mensajes de la carga en las canalizaciones mediante un enfoque en memoria y uso de un enfoque de transmisión por secuencias  
 La siguiente información se tomó del blog de Nic Barden, [ http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx ](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228). Esta tabla proporciona una comparación resumida de los mensajes de la carga en canalizaciones mediante un enfoque en memoria y uso de un enfoque de transmisión por secuencias.  
  
|Comparación de...|Transmisión por secuencias|En la memoria|  
|----------------------|---------------|---------------|  
|Uso de memoria por mensaje|Baja, independientemente del tamaño de mensaje|Alto (varía según el tamaño del mensaje)|  
|Clases comunes que se usan para procesar datos XML|Compila las derivaciones de en y personalizadas de:<br /><br /> XmlTranslatorStream, XmlReader y XmlWriter|XmlDocument, XPathDocument, MemoryStream y VirtualStream|  
|Documentación|Deficiente: muchas clases de BizTalk no es compatibles y no documentadas|Muy bueno: clases de .NET Framework|  
|Ubicación del código de la "Lógica de procesamiento"|-Lectores "Conectar" y secuencias a través del método Execute.<br />-Ejecución real se produce en los flujos y los lectores que se leen los datos.|Directamente desde el método Execute del componente de canalización.|  
|data|Volver a crearse en cada capa de ajuste que se leen los datos a través de él.|Leer, modificar y que se escriben en cada componente antes del siguiente componente que se llama.|  
  
## <a name="see-also"></a>Vea también  
 [Optimización de las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md)