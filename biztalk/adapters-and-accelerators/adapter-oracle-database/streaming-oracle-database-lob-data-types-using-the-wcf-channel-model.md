---
title: Tipos de datos de Oracle Database LOB mediante el modelo de canal de WCF de streaming | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, Oracle LOB data types
- WCF channel model, streaming Oracle LOB data types
ms.assetid: 513a7cb8-495d-4019-bce1-b5babca3629f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa8a493c94761ce74d76885ee59fae1425c15523
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013845"
---
# <a name="streaming-oracle-database-lob-data-types-using-the-wcf-channel-model"></a>Streaming tipos de datos LOB de base de datos de Oracle, mediante el modelo de canal de WCF
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] admite la transmisión de extremo a otro de los datos LOB para determinadas operaciones. Las secciones de este tema describen cómo implementar el streaming de datos de LOB cuando se usa el modelo de canal WCF.  
  
 Para obtener información general sobre cómo el adaptador es compatible con transmisión por secuencias de tipos de datos LOB, vea [hacer Streaming de tipos de datos de objetos grandes en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md). Debe leer este tema antes de continuar.  
  
 Un ejemplo que muestra la transmisión de datos LOB está disponible en los ejemplos SDK incluidos en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
## <a name="streaming-outbound-messages-to-the-adapter"></a>Transmisión por secuencias mensajes salientes para el adaptador  
 El adaptador admite datos LOB-to-end para el mensaje de solicitud para la operación UpdateLOB de transmisión por secuencias.  
  
 Para admitir la transmisión por secuencias to-end en UpdateLOB operaciones en el modelo de canal WCF, debe:  
  
1.  Establecer el **UseAmbientTransaction** enlaza la propiedad en true.  
  
2.  Implemente un **System.ServiceModel.Channels.BodyWriter** que es capaz de transmitir los datos de LOB (realizando la transmisión por secuencias en los datos de LOB en el valor de nodo).  
  
3.  Realizar la operación UpdateLOB dentro de un ámbito de transacción.  
  
4.  Crear el **System.ServiceModel.Message** utilizada para invocar la operación si se suministra el cuerpo del mensaje con este **BodyWriter** mediante una sobrecarga adecuada de la **Message.Create** método.  
  
### <a name="setting-the-useambienttransaction-binding-property"></a>Establecer la propiedad de enlace de UseAmbientTransaction  
 El ejemplo siguiente muestra cómo crear un enlace para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y establezca el **UseAmbientTransaction** enlaza la propiedad.  
  
```  
// Create binding  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
//set the binding property  
binding.UseAmbientTransaction = true;  
  
```  
  
### <a name="implementing-a-bodywriter"></a>Implementar un BodyWriter  
 El ejemplo siguiente muestra una implementación de un **BodyWriter** que realiza el valor del nodo de transmisión por secuencias.  
  
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
        if (chunkSize \<= 0)  
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
  
### <a name="perform-the-operations-within-a-transaction-scope"></a>Realizar las operaciones dentro de un ámbito de transacción  
 El ejemplo siguiente muestra cómo realizar operaciones en un ámbito de transacción.  
  
```  
// Create a transaction scope  
using(TransactionScope tx = new TransactionScope())  
{  
  // perform operations within the transaction  
  // ...  
  // ...  
  
  //Complete the transaction  
  tx.Complete()  
}  
  
```  
  
### <a name="creating-a-message-by-using-a-bodywriter"></a>Creación de un mensaje con un BodyWriter  
 El ejemplo siguiente muestra cómo crear un mensaje de solicitud UpdateLOB con el **BodyWriter** en el ejemplo anterior. Los datos del mensaje se leen desde un archivo.  
  
```  
// Create a transaction scope  
using(TransactionScope tx = new TransactionScope())  
{  
    XmlReader readerIn = XmlReader.Create ("updatelob.xml");  
    // StreamingBodyWrtier class is responsible for streaming  
    StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
    Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB",   
    stBW);  
  
    //Send the request message and get the output message  
    OutputMsg = channel.Request(InputMsg);  
  
    tx.Complete();  
}  
  
```  
  
## <a name="streaming-inbound-messages-from-the-adapter"></a>Transmisión por secuencias mensajes entrantes desde el adaptador  
 El adaptador admite streaming para los siguientes mensajes de entrada de datos LOB-to-end:  
  
- Mensaje de respuesta para las funciones con fuera o en los parámetros OUT que contienen datos de LOB. Tenga en cuenta que los parámetros de tipo de registro pueden contener columnas de datos LOB.  
  
- Mensaje de respuesta para las funciones con parámetros de salida de REF CURSOR (o valores devueltos) que contienen datos de LOB. Esto incluye el lado de salida de los parámetros OUT en REF CURSOR.  
  
- Mensaje de respuesta para los procedimientos con IN o OUT en los parámetros que contienen datos de LOB. Tenga en cuenta que los parámetros de tipo de registro pueden contener columnas de datos LOB.  
  
- Mensaje de respuesta para los procedimientos con parámetros de salida de REF CURSOR que contienen datos de LOB. Esto incluye el lado de salida de los parámetros OUT en REF CURSOR  
  
- Mensaje de respuesta para las operaciones de SQLEXECUTE que devuelven conjuntos de resultados que contienen datos de LOB.  
  
- Establece el mensaje de respuesta para la tabla o vista operaciones Select que devuelven datos LOB en el resultado.  
  
- Mensaje de solicitud para la operación POLLINGSTMT (entrante)  
  
  Para admitir la transmisión por secuencias to-end en un mensaje entrante en el modelo de canal WCF, debe:  
  
1.  Implemente un **System.Xml.XmlDictionaryWriter** que es capaz de transmitir los datos de LOB (realizando la transmisión por secuencias en los datos de LOB en el valor de nodo).  
  
2.  Consumir el **mensaje** invocando **WriteBodyContents** método con este **XmlDictionaryWriter**.  
  
### <a name="implementing-an-xmldictionarywriter"></a>Implementar un XmlDictionaryWriter  
 El ejemplo siguiente muestra una implementación de un **XmlDictionaryWriter** que realiza el valor del nodo de transmisión por secuencias.  
  
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
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a>Consumir un mensaje utilizando el escritor XmlDictionaryWriter  
 El ejemplo siguiente muestra cómo consumir un mensaje de respuesta seleccione tabla utilizando la **FileXmlWriter** implementado en el ejemplo anterior. (El **FileWriter** clase creada por subclasificando **XmlDictionaryWriter**.) El ejemplo se usa un **IRequestChannel** canal para invocar la operación de selección. Se han omitido los detalles de la creación del canal. El mensaje de solicitud Select se lee desde un archivo y el mensaje de respuesta Select se escribe en un archivo.  
  
```  
// Read Select message body from a file  
XmlReader readerIn = XmlReader.Create("select.xml");  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/Select", readerIn);  
  
Message OutputMsg = channel.Request(InputMsg);  
  
// Streaming response message to select_output.xml using the custom XmlDictionaryWriter;  
FileXmlWriter fileXmlWriter = new FileXmlWriter("select_output.xml");  
OutputMsg.WriteBodyContents(fileXmlWriter);  
fileXmlWriter.Flush();  
fileXmlWriter.Close();  
  
// Streaming complete close output message;  
OutputMsg.Close();  
```  
  
 El siguiente XML muestra el mensaje de solicitud (el contenido del archivo select.xml) para la operación de selección. La tabla CUSTOMER contiene una columna BLOB denominada PHOTO.  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>NAME='Kim Ralls'</FILTER>  
</Select>  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)