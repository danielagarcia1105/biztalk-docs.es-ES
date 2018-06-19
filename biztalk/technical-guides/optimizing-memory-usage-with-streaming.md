---
title: Optimizar el uso de memoria con transmisión por secuencias | Documentos de Microsoft
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
ms.openlocfilehash: 0e1707007eab19a86e4fabedfe9e16bfa9c8fc59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299348"
---
# <a name="optimizing-memory-usage-with-streaming"></a>Optimizar el uso de memoria con transmisión por secuencias
Este tema proporciona recomendaciones sobre el uso de patrones de transmisión por secuencias para minimizar la superficie de memoria de mensajes al enviar o recibir mensajes de gran tamaño con un transporte WCF o al cargar mensajes de orquestaciones.   
Al utilizar código en una orquestación para leer el contenido de un mensaje, evite usar variables de XmlDocument. Carga un mensaje en una variable XmlDocument supone una sobrecarga significativa, especialmente para los mensajes grandes. Esta sobrecarga es en cuanto a uso de memoria y procesamiento para compilar las estructuras en memoria. El uso de una instancia de XmlDocument fuerza el contenido completo del mensaje para cargarse en memoria para crear el gráfico de objetos para el módulo de objetos de documento (DOM). La cantidad total de memoria utilizada por una instancia de esta clase puede ser aproximadamente 10 veces el tamaño de mensaje real. Para obtener más información sobre la superficie de memoria necesaria al cargar un mensaje en una variable de XmlDocument, vea [capítulo 9: mejorar el rendimiento de XML](http://go.microsoft.com/fwlink/?LinkId=139772) (http://go.microsoft.com/fwlink/?LinkId=139772) en MSDN.   
El resto de este tema proporciona métodos alternativos para leer el contenido del mensaje que no requieren que se cargue un mensaje en una variable de XmlDocument.  
  
## <a name="use-streaming-when-sending-or-receiving-large-messages-with-a-wcf-transport"></a>Usar la transmisión por secuencias al enviar o recibir mensajes de gran tamaño con un transporte WCF  
 Al enviar o recibir mensajes de gran tamaño con un transporte WCF, usa el adaptador WCF-Custom o WCF-CustomIsolated y configurar con un tipo de enlace que admita la **transferMode = transmitido por secuencias** opción, como los siguientes enlaces:  
  
-   **basicHttpBinding + BasicHttpBindingElement, transferMode = transmitido por secuencias**  
  
-   **netTcpBinding + NetTcpBindingElement, transferMode = transmitido por secuencias**  
  
-   **customBinding + HttpTransportElement, transferMode = transmitido por secuencias**  
  
-   **customBinding + ConnectionOrientedTransportElement, transferMode = transmitido por secuencias**  
  
 Elegir un adaptador de WCF-Custom o WCF-CustomIsolated junto con un enlace que admita la **transferMode = transmitido por secuencias** opción implementar la transmisión por secuencias de mensajes grandes en el sistema de archivos según sea necesario y le mitigar posibles problemas de memoria insuficiente.  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-orchestrations"></a>Usar la transmisión por secuencias para minimizar el consumo de memoria necesario al cargar mensajes en orquestaciones  
 Las técnicas siguientes describen cómo minimizar el consumo de memoria de un mensaje al cargar el mensaje en una orquestación.  
  
### <a name="use-an-xlangmessage-variable-to-process-the-contents-of-a-message-or-message-part"></a>Utilizar una variable de XLANGMessage para procesar el contenido de un mensaje o parte de mensaje  
 Cuando se pasa un mensaje desde una orquestación a bibliotecas de clases. NET, no pasarlas como variables de XmlDocument, por razones mencionadas anteriormente en este tema; usar variables de XLANGMessage en su lugar. Las técnicas siguientes muestran métodos para leer un mensaje o parte de mensaje utilizando una variable de XLANGMessage.  
  
-   **Procesar mensajes con XMLReader** : para procesar un mensaje con una instancia de XmlReader, para pasar el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento mediante XmlReader.  
  
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
  
-   **Recuperar el contenido de un mensaje en una cadena con StreamReader** -uno de los usos habituales de XmlDocument en orquestaciones consiste en recuperar el mensaje como una cadena XML mediante XmlDocument.OuterXml(). En el ejemplo de código siguiente se muestra un método alternativo que recupera el mensaje como una cadena con una variable de XLANGMessage.  
  
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
  
-   **Recuperar el contenido de mensajes .NET simples en una cadena** -si el tipo del mensaje es un tipo simple. NET, puede recuperar el mensaje como ese tipo. Por ejemplo, para obtener el mensaje como una cadena, pasar el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento como una cadena.  
  
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
  
-   **Recuperar el contenido de un mensaje en una secuencia** : para obtener el mensaje como una secuencia, pasar el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento como una secuencia.  
  
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
  
-   **Recuperar el contenido de un mensaje en un objeto .NET** : para obtener el mensaje como un objeto. NET, pasar el mensaje al código de .NET como un XLANGMessage y recuperar el contenido del elemento como una instancia de una clase. NET. Crear esta última desde el esquema Xml del mensaje mediante la herramienta de la herramienta de definición de esquemas XML (Xsd.exe) proporcionada por Visual Studio 2010.  
  
    > [!NOTE]  
    >  Esta técnica es válida sólo cuando los mensajes son pequeños. En caso contrario, este enfoque puede experimentar importantes en una sobrecarga considerable para deserializar el mensaje real en un objeto. NET.  
  
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
>  El uso de la **Dispose()** método expuesto por el parámetro XLANGMessage antes de devolver desde el código de .NET es especialmente importante en bucle escenarios y orquestaciones de larga duración que se pueden acumular instancias de la Objeto XLANGMessage sin su liberación con el tiempo. Para obtener más información acerca de los mensajes que realiza la llamada. Dispose() de esta manera, consulte [mensajes representados como XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) en la documentación de BizTalk Server. En este tema también proporciona prácticas recomendadas para utilizar IStreamFactory para construir las variables de XLANGMessage en el código de usuario usa un enfoque basado en secuencias.  
  
 Para obtener más información sobre las distintas maneras para procesar un XLANGMessage dentro de un componente de aplicación auxiliar que invoca una orquestación, vea los temas siguientes:  
  
-   [4 maneras diferentes para procesar un XLANGMessage dentro de un componente de aplicación auxiliar invocado por una orquestación parte 1](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420).  
  
-   [4 maneras diferentes para procesar un XLANGMessage dentro de un componente de aplicación auxiliar invocado por una orquestación parte 2](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421).  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-value-from-an-xlangmessage-object-from-a-method-invoked-by-an-orchestration"></a>Con XPathReader y XPathCollection para extraer un valor de un objeto XLANGMessage desde un método invocado por una orquestación  
 Evite el uso de la clase XMLDocument para leer el contenido de los mensajes XML desde código personalizado, como los componentes de canalización personalizados o clases auxiliares que invoca las orquestaciones. Al utilizar una instancia de XMLDocument para cargar un mensaje XML, el mensaje completo se carga en memoria, esto es ineficiente y puede requerir la memoria hasta 10 veces el tamaño real del mensaje. Una manera más eficaz de leer el contenido de los mensajes XML es utilizar una técnica de transmisión por secuencias para ajustar la secuencia original con una de las clases de la secuencia proporcionadas por el ensamblado Microsoft.BizTalk.Streaming.dll. Esta técnica es especialmente útil cuando se cargan los mensajes de gran tamaño.  
  
 Si necesitan valores concretos para extraerse de un documento XML, en lugar de utilizar los métodos SelectNodes y SelectSingleNode expuestos por la clase XmlDocument, utilizar una instancia de la clase XPathReader proporcionada por el ensamblado Microsoft.BizTalk.XPathReader.dll como se muestra en el ejemplo de código siguiente.  
  
-   En este ejemplo se muestra cómo utilizar el XPathReader y XPathCollection para extraer un valor determinado de un objeto XLANGMessage dentro de un método invocado por una orquestación.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Optimizar las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md)