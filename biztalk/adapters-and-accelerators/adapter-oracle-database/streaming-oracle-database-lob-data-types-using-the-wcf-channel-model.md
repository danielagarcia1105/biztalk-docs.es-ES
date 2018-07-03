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
# <a name="streaming-oracle-database-lob-data-types-using-the-wcf-channel-model"></a><span data-ttu-id="77d7a-102">Streaming tipos de datos LOB de base de datos de Oracle, mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="77d7a-102">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>
<span data-ttu-id="77d7a-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] admite la transmisión de extremo a otro de los datos LOB para determinadas operaciones.</span><span class="sxs-lookup"><span data-stu-id="77d7a-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports end-to-end streaming of LOB data for certain operations.</span></span> <span data-ttu-id="77d7a-104">Las secciones de este tema describen cómo implementar el streaming de datos de LOB cuando se usa el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="77d7a-104">The sections in this topic describe how to implement streaming for LOB data when you use the WCF channel model.</span></span>  
  
 <span data-ttu-id="77d7a-105">Para obtener información general sobre cómo el adaptador es compatible con transmisión por secuencias de tipos de datos LOB, vea [hacer Streaming de tipos de datos de objetos grandes en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="77d7a-105">For background information about how the adapter supports streaming of LOB data types, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="77d7a-106">Debe leer este tema antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="77d7a-106">You should read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="77d7a-107">Un ejemplo que muestra la transmisión de datos LOB está disponible en los ejemplos SDK incluidos en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77d7a-107">A sample that demonstrates LOB data streaming is available in the SDK samples included with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="77d7a-108">Para obtener más información, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="77d7a-108">For more information, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="streaming-outbound-messages-to-the-adapter"></a><span data-ttu-id="77d7a-109">Transmisión por secuencias mensajes salientes para el adaptador</span><span class="sxs-lookup"><span data-stu-id="77d7a-109">Streaming Outbound Messages to the Adapter</span></span>  
 <span data-ttu-id="77d7a-110">El adaptador admite datos LOB-to-end para el mensaje de solicitud para la operación UpdateLOB de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="77d7a-110">The adapter supports end-to-end LOB data streaming for the request message for the UpdateLOB operation.</span></span>  
  
 <span data-ttu-id="77d7a-111">Para admitir la transmisión por secuencias to-end en UpdateLOB operaciones en el modelo de canal WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="77d7a-111">To support end-to-end streaming on UpdateLOB operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="77d7a-112">Establecer el **UseAmbientTransaction** enlaza la propiedad en true.</span><span class="sxs-lookup"><span data-stu-id="77d7a-112">Set the **UseAmbientTransaction** binding property to true.</span></span>  
  
2.  <span data-ttu-id="77d7a-113">Implemente un **System.ServiceModel.Channels.BodyWriter** que es capaz de transmitir los datos de LOB (realizando la transmisión por secuencias en los datos de LOB en el valor de nodo).</span><span class="sxs-lookup"><span data-stu-id="77d7a-113">Implement a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
3.  <span data-ttu-id="77d7a-114">Realizar la operación UpdateLOB dentro de un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="77d7a-114">Perform the UpdateLOB operation within a transaction scope.</span></span>  
  
4.  <span data-ttu-id="77d7a-115">Crear el **System.ServiceModel.Message** utilizada para invocar la operación si se suministra el cuerpo del mensaje con este **BodyWriter** mediante una sobrecarga adecuada de la **Message.Create** método.</span><span class="sxs-lookup"><span data-stu-id="77d7a-115">Create the **System.ServiceModel.Message** used to invoke the operation by supplying the message body with this **BodyWriter** using an appropriate overload of the **Message.Create** method.</span></span>  
  
### <a name="setting-the-useambienttransaction-binding-property"></a><span data-ttu-id="77d7a-116">Establecer la propiedad de enlace de UseAmbientTransaction</span><span class="sxs-lookup"><span data-stu-id="77d7a-116">Setting the UseAmbientTransaction Binding Property</span></span>  
 <span data-ttu-id="77d7a-117">El ejemplo siguiente muestra cómo crear un enlace para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y establezca el **UseAmbientTransaction** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="77d7a-117">The following example shows how to create a binding for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and set the **UseAmbientTransaction** binding property.</span></span>  
  
```  
// Create binding  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
//set the binding property  
binding.UseAmbientTransaction = true;  
  
```  
  
### <a name="implementing-a-bodywriter"></a><span data-ttu-id="77d7a-118">Implementar un BodyWriter</span><span class="sxs-lookup"><span data-stu-id="77d7a-118">Implementing a BodyWriter</span></span>  
 <span data-ttu-id="77d7a-119">El ejemplo siguiente muestra una implementación de un **BodyWriter** que realiza el valor del nodo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="77d7a-119">The following example shows an implementation of a **BodyWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="perform-the-operations-within-a-transaction-scope"></a><span data-ttu-id="77d7a-120">Realizar las operaciones dentro de un ámbito de transacción</span><span class="sxs-lookup"><span data-stu-id="77d7a-120">Perform the Operations Within a Transaction Scope</span></span>  
 <span data-ttu-id="77d7a-121">El ejemplo siguiente muestra cómo realizar operaciones en un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="77d7a-121">The following example shows how to perform operations within a transaction scope.</span></span>  
  
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
  
### <a name="creating-a-message-by-using-a-bodywriter"></a><span data-ttu-id="77d7a-122">Creación de un mensaje con un BodyWriter</span><span class="sxs-lookup"><span data-stu-id="77d7a-122">Creating a Message by using a BodyWriter</span></span>  
 <span data-ttu-id="77d7a-123">El ejemplo siguiente muestra cómo crear un mensaje de solicitud UpdateLOB con el **BodyWriter** en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="77d7a-123">The following example shows how to create an UpdateLOB request message using the **BodyWriter** in the preceding example.</span></span> <span data-ttu-id="77d7a-124">Los datos del mensaje se leen desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="77d7a-124">The message data is read from a file.</span></span>  
  
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
  
## <a name="streaming-inbound-messages-from-the-adapter"></a><span data-ttu-id="77d7a-125">Transmisión por secuencias mensajes entrantes desde el adaptador</span><span class="sxs-lookup"><span data-stu-id="77d7a-125">Streaming Inbound Messages from the Adapter</span></span>  
 <span data-ttu-id="77d7a-126">El adaptador admite streaming para los siguientes mensajes de entrada de datos LOB-to-end:</span><span class="sxs-lookup"><span data-stu-id="77d7a-126">The adapter supports end-to-end LOB data streaming for the following inbound messages:</span></span>  
  
- <span data-ttu-id="77d7a-127">Mensaje de respuesta para las funciones con fuera o en los parámetros OUT que contienen datos de LOB.</span><span class="sxs-lookup"><span data-stu-id="77d7a-127">Response message for functions with OUT or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="77d7a-128">Tenga en cuenta que los parámetros de tipo de registro pueden contener columnas de datos LOB.</span><span class="sxs-lookup"><span data-stu-id="77d7a-128">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
- <span data-ttu-id="77d7a-129">Mensaje de respuesta para las funciones con parámetros de salida de REF CURSOR (o valores devueltos) que contienen datos de LOB.</span><span class="sxs-lookup"><span data-stu-id="77d7a-129">Response message for functions with OUT REF CURSOR parameters (or return values) that contain LOB data.</span></span> <span data-ttu-id="77d7a-130">Esto incluye el lado de salida de los parámetros OUT en REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="77d7a-130">This includes the output side of IN OUT REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="77d7a-131">Mensaje de respuesta para los procedimientos con IN o OUT en los parámetros que contienen datos de LOB.</span><span class="sxs-lookup"><span data-stu-id="77d7a-131">Response message for procedures with IN or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="77d7a-132">Tenga en cuenta que los parámetros de tipo de registro pueden contener columnas de datos LOB.</span><span class="sxs-lookup"><span data-stu-id="77d7a-132">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
- <span data-ttu-id="77d7a-133">Mensaje de respuesta para los procedimientos con parámetros de salida de REF CURSOR que contienen datos de LOB.</span><span class="sxs-lookup"><span data-stu-id="77d7a-133">Response message for procedures with OUT REF CURSOR parameters that contain LOB data.</span></span> <span data-ttu-id="77d7a-134">Esto incluye el lado de salida de los parámetros OUT en REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="77d7a-134">This includes the output side of IN OUT REF CURSOR parameters</span></span>  
  
- <span data-ttu-id="77d7a-135">Mensaje de respuesta para las operaciones de SQLEXECUTE que devuelven conjuntos de resultados que contienen datos de LOB.</span><span class="sxs-lookup"><span data-stu-id="77d7a-135">Response message for SQLEXECUTE operations that return result sets that contain LOB data.</span></span>  
  
- <span data-ttu-id="77d7a-136">Establece el mensaje de respuesta para la tabla o vista operaciones Select que devuelven datos LOB en el resultado.</span><span class="sxs-lookup"><span data-stu-id="77d7a-136">Response message for Table or view Select operations that return LOB data in the result set.</span></span>  
  
- <span data-ttu-id="77d7a-137">Mensaje de solicitud para la operación POLLINGSTMT (entrante)</span><span class="sxs-lookup"><span data-stu-id="77d7a-137">Request message for the (inbound) POLLINGSTMT operation</span></span>  
  
  <span data-ttu-id="77d7a-138">Para admitir la transmisión por secuencias to-end en un mensaje entrante en el modelo de canal WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="77d7a-138">To support end-to-end streaming on an inbound message in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="77d7a-139">Implemente un **System.Xml.XmlDictionaryWriter** que es capaz de transmitir los datos de LOB (realizando la transmisión por secuencias en los datos de LOB en el valor de nodo).</span><span class="sxs-lookup"><span data-stu-id="77d7a-139">Implement a **System.Xml.XmlDictionaryWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
2.  <span data-ttu-id="77d7a-140">Consumir el **mensaje** invocando **WriteBodyContents** método con este **XmlDictionaryWriter**.</span><span class="sxs-lookup"><span data-stu-id="77d7a-140">Consume the **Message** by invoking **WriteBodyContents** method with this **XmlDictionaryWriter**.</span></span>  
  
### <a name="implementing-an-xmldictionarywriter"></a><span data-ttu-id="77d7a-141">Implementar un XmlDictionaryWriter</span><span class="sxs-lookup"><span data-stu-id="77d7a-141">Implementing an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="77d7a-142">El ejemplo siguiente muestra una implementación de un **XmlDictionaryWriter** que realiza el valor del nodo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="77d7a-142">The following example shows an implementation of an **XmlDictionaryWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a><span data-ttu-id="77d7a-143">Consumir un mensaje utilizando el escritor XmlDictionaryWriter</span><span class="sxs-lookup"><span data-stu-id="77d7a-143">Consuming a Message by using an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="77d7a-144">El ejemplo siguiente muestra cómo consumir un mensaje de respuesta seleccione tabla utilizando la **FileXmlWriter** implementado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="77d7a-144">The following example shows how to consume a table Select response message using the **FileXmlWriter** implemented in the preceding example.</span></span> <span data-ttu-id="77d7a-145">(El **FileWriter** clase creada por subclasificando **XmlDictionaryWriter**.) El ejemplo se usa un **IRequestChannel** canal para invocar la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="77d7a-145">(The **FileWriter** class was created by sub-classing **XmlDictionaryWriter**.) The example uses an **IRequestChannel** channel to invoke the Select operation.</span></span> <span data-ttu-id="77d7a-146">Se han omitido los detalles de la creación del canal.</span><span class="sxs-lookup"><span data-stu-id="77d7a-146">The details of the channel creation have been omitted.</span></span> <span data-ttu-id="77d7a-147">El mensaje de solicitud Select se lee desde un archivo y el mensaje de respuesta Select se escribe en un archivo.</span><span class="sxs-lookup"><span data-stu-id="77d7a-147">The Select request message is read from a file and the Select response message is written to a file.</span></span>  
  
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
  
 <span data-ttu-id="77d7a-148">El siguiente XML muestra el mensaje de solicitud (el contenido del archivo select.xml) para la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="77d7a-148">The following XML shows the request message (contents of the select.xml file) for the Select operation.</span></span> <span data-ttu-id="77d7a-149">La tabla CUSTOMER contiene una columna BLOB denominada PHOTO.</span><span class="sxs-lookup"><span data-stu-id="77d7a-149">The CUSTOMER table contains a BLOB column named PHOTO.</span></span>  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>NAME='Kim Ralls'</FILTER>  
</Select>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77d7a-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="77d7a-150">See Also</span></span>  
 [<span data-ttu-id="77d7a-151">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="77d7a-151">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)