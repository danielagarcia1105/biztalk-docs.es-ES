---
title: Transmitir IDOC de archivo plano en SAP mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF channel model, streaming flat-file IDOCs
ms.assetid: 5010e215-d8d0-47c8-93a6-20cfdeff2951
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8de850022a03a3be0310da3022a2cf496c94f30
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="stream-flat-file-idocs-in-sap-using-the-wcf-channel-model"></a>Secuencia IDOC de archivo plano en SAP mediante el modelo de canal de WCF
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es compatible con transmisión por secuencias para las operaciones de SendIdoc y ReceiveIdoc en el valor de nodo. Estas operaciones se utilizan para enviar y recibir (cadena) IDOC hacia y desde el adaptador de archivo sin formato. En ambas de estas operaciones, los datos para el IDOC completo se encuentran en una cadena en un único nodo (\<idocData\>). Para IDOC grande, la transmisión por secuencias los datos IDOC entre el adaptador y el código puede ahorrar recursos de memoria considerables.  
  
 Para obtener información general acerca de cómo el adaptador es compatible con transmisión por secuencias, vea [transmisión por secuencias y el adaptador SAP](../../adapters-and-accelerators/adapter-sap/streaming-and-the-sap-adapter.md). Debe leer este tema antes de continuar.  
  
 Las secciones de este tema describen cómo implementar la transmisión por secuencias para las operaciones de SendIdoc y ReceiveIdoc cuando se usa el modelo de canal WCF en el valor de nodo.  
  
## <a name="streaming-outbound-flat-file-idocs-to-the-adapter"></a>Transmisión por secuencias IDOC de archivo sin formato salientes al adaptador  
 El adaptador es compatible con transmisión por secuencias en el mensaje de solicitud para la operación de SendIdoc en el valor de nodo.  
  
 Para admitir la transmisión por secuencias en las operaciones de SendIdoc en el modelo de canal WCF en el valor de nodo, debe:  
  
1.  Implemente un **System.ServiceModel.Channels.BodyWriter** que es capaz de transmitir por secuencias los datos IDOC (realizando la transmisión por secuencias en los datos IDOC en el valor de nodo).  
  
2.  Crear el **System.ServiceModel.Message** se utiliza para invocar la operación si se suministra el cuerpo del mensaje a este **BodyWriter** con una sobrecarga adecuada de la **Message.Create** método.  
  
### <a name="implementing-a-bodywriter"></a>Implementar un BodyWriter  
 En el ejemplo siguiente se muestra una implementación de un **BodyWriter** que realiza la transmisión por secuencias de valor de nodo.  
  
```  
/// <summary>  
/// This class overrides the OnWriteBodyContents function to do node-value streaming  
/// </summary>  
class StreamingBodyWriter : BodyWriter, IDisposable  
{  
    XmlReader m_reader = null;  
  
    int m_chunkSize;  
    /// <summary>  
    /// Initializes the body writer  
    /// </summary>  
    /// <param name="reader">Reader for input</param>  
    /// <param name="chunkSize">The chunksize in which the data is passed to adapter</param>  
    public StreamingBodyWriter(XmlReader reader, int chunkSize)  
        : base(false)  
    {  
        m_reader = reader;  
        if (chunkSize <= 0)  
            throw new ApplicationException("ChunkSize should be a positive value");  
        m_chunkSize = chunkSize;  
    }  
  
    protected override void OnWriteBodyContents(XmlDictionaryWriter writer)  
    {  
        if (m_reader == null)  
            throw new ApplicationException("Reader cannot be null");  
  
        while (m_reader.Read())  
        {  
            switch (m_reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    writer.WriteStartElement(m_reader.LocalName, m_reader.NamespaceURI);  
                    break;  
                case XmlNodeType.Text:  
                    #region Streaming Code  
                    char[] tempBuffer = new char[m_chunkSize];  
                    int length = 0;  
                    while ((length = m_reader.ReadValueChunk(tempBuffer, 0, m_chunkSize)) > 0)  
                    {  
                        writer.WriteString(new String(tempBuffer, 0, length));  
                    }  
                    #endregion  
                    break;  
                case XmlNodeType.EndElement:  
                    writer.WriteEndElement();  
                    break;  
            }  
        }  
  
    }  
  
    #region IDisposable Members  
  
    public void Dispose()  
    {  
        if (m_reader != null)  
        {  
            m_reader.Close();  
            m_reader = null;  
        }  
    }  
  
    #endregion  
}  
```  
  
### <a name="creating-a-message-by-using-a-bodywriter"></a>Crear un mensaje mediante un BodyWriter  
 En el ejemplo siguiente se muestra cómo crear un mensaje de solicitud de SendIdoc mediante la **BodyWriter** en el ejemplo anterior. Los datos del mensaje se leen desde un archivo.  
  
```  
XmlReader readerIn = XmlReader.Create ("sendidoc.xml");  
// StreamingBodyWrtier class is responsible for streaming  
StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.SAP/2007/03/Idoc/SendIdoc",   
    stBW);  
  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-adapter"></a>Transmisión por secuencias IDOC de archivo sin formato entrante del adaptador  
 Recibir un IDOC de archivo sin formato en la operación de ReceiveIdoc entrante. El adaptador es compatible con transmisión por secuencias en el mensaje de solicitud para la operación de ReceiveIdoc en el valor de nodo.  
  
 Para admitir la transmisión por secuencias en las operaciones de ReceiveIdoc en el modelo de canal WCF en el valor de nodo, debe:  
  
1.  Implemente un **System.Xml.XmlDictionaryWriter** que es capaz de transmitir por secuencias los datos IDOC (realizando la transmisión por secuencias en los datos IDOC en el valor de nodo).  
  
2.  Consumir la **mensaje** invocando su **WriteBodyContents** método con este **XmlDictionaryWriter**.  
  
### <a name="implementing-an-xmldictionarywriter"></a>Implementar un XmlDictionaryWriter  
 En el ejemplo siguiente se muestra una implementación de un **XmlDictionaryWriter** que realiza la transmisión por secuencias de valor de nodo.  
  
```  
using System;  
using System.Xml;  
using System.Text;  
  
class FileXmlWriter : XmlDictionaryWriter  
{  
    XmlTextWriter xts;  
  
    public FileXmlWriter(string file)  
    {  
        xts = new XmlTextWriter(file, Encoding.UTF8);  
    }  
  
    public override void WriteBase64(byte[] buffer, int index, int count)  
    {  
        xts.WriteBase64(buffer, index, count);  
    }  
  
    public override void WriteCData(string text)  
    {  
        xts.WriteCData(text);  
    }  
  
    public override void WriteCharEntity(char ch)  
    {  
        xts.WriteCharEntity(ch);  
    }  
  
    public override void WriteChars(char[] buffer, int index, int count)  
    {  
        xts.WriteChars(buffer, index, count);  
    }  
  
    public override void WriteComment(string text)  
    {  
        xts.WriteComment(text);  
    }  
  
    public override void WriteDocType(string name, string pubid, string sysid, string subset)  
    {  
        xts.WriteDocType(name, pubid, sysid, subset);  
    }  
  
    public override void WriteEndAttribute()  
    {  
        xts.WriteEndAttribute();  
    }  
  
    public override void WriteEndDocument()  
    {  
        xts.WriteEndDocument();  
    }  
  
    public override void WriteEndElement()  
    {  
        xts.WriteEndElement();  
    }  
  
    public override void WriteEntityRef(string name)  
    {  
        xts.WriteEntityRef(name);  
    }  
  
    public override void WriteFullEndElement()  
    {  
        xts.WriteFullEndElement();  
    }  
  
    public override void WriteProcessingInstruction(string name, string text)  
    {  
        xts.WriteProcessingInstruction(name, text);  
    }  
  
    public override void WriteRaw(string data)  
    {  
        xts.WriteRaw(data);  
    }  
  
    public override void WriteRaw(char[] buffer, int index, int count)  
    {  
        xts.WriteRaw(buffer, index, count);  
    }  
  
    public override void WriteStartAttribute(string prefix, string localName, string ns)  
    {  
        xts.WriteStartAttribute(prefix, localName, ns);  
    }  
  
    public override void WriteStartDocument(bool standalone)  
    {  
        xts.WriteStartDocument(standalone);  
    }  
  
    public override void WriteStartDocument()  
    {  
        xts.WriteStartDocument();  
    }  
  
    public override void WriteStartElement(string prefix, string localName, string ns)  
    {  
        xts.WriteStartElement(localName);  
    }  
  
    public override void WriteString(string text)  
    {  
        xts.WriteString(text);  
    }  
  
    public override void WriteSurrogateCharEntity(char lowChar, char highChar)  
    {  
        xts.WriteSurrogateCharEntity(lowChar, highChar);  
    }  
  
    public override void WriteWhitespace(string ws)  
    {  
        xts.WriteWhitespace(ws);  
    }  
  
    public override void Close()  
    {  
        xts.Close();  
    }  
  
    public override void Flush()  
    {  
        xts.Flush();  
    }  
  
    public override string LookupPrefix(string ns)  
    {  
        return xts.LookupPrefix(ns);  
    }  
  
    public override WriteState WriteState  
    {  
        get { return xts.WriteState; }  
    }  
  
}  
```  
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a>Usar un mensaje utilizando un XmlDictionaryWriter  
 En el ejemplo siguiente se muestra cómo utilizar un mensaje de solicitud de ReceiveIdoc mediante la **FileXmlWriter** implementado en el ejemplo anterior. (El **FileWriter** clase creó subclasificando **XmlDictionaryWriter**.) El ejemplo se usa un **IReplyChannel** canal para recibir la operación ReceiveIdoc. Se han omitido los detalles de la creación del canal. El mensaje de solicitud de ReceiveIdoc se escribe en un archivo.  
  
```  
// Receive the ReceiveIdoc request message from the adapter.  
RequestContext rc = channel.ReceiveRequest();  
Message inputMsg = rc.RequestMessage;  
  
// Stream the request message to received_idoc.xml using the custom XmlDictionaryWriter.  
FileXmlWriter fileXmlWriter = new FileXmlWriter("received_idoc.xml");  
inputMsg.WriteBodyContents(fileXmlWriter);  
fileXmlWriter.Flush();  
fileXmlWriter.Close();  
  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)