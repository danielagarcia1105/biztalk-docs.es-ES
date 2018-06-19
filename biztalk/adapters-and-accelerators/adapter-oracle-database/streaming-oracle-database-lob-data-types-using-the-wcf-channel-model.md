---
title: Tipos de datos de Oracle base de datos LOB utilizando el modelo del canal de WCF de streaming | Documentos de Microsoft
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
ms.openlocfilehash: bf0ee2f8d1c90f69a206a3006398d52e67f819e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215796"
---
# <a name="streaming-oracle-database-lob-data-types-using-the-wcf-channel-model"></a><span data-ttu-id="60972-102">Transmisión por secuencias tipos de datos LOB de base de datos de Oracle, utilizando el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="60972-102">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>
<span data-ttu-id="60972-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] admite-to-end de transmisión por secuencias de datos LOB para determinadas operaciones.</span><span class="sxs-lookup"><span data-stu-id="60972-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports end-to-end streaming of LOB data for certain operations.</span></span> <span data-ttu-id="60972-104">Las secciones de este tema describen cómo implementar la transmisión por secuencias de datos LOB cuando se usa el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="60972-104">The sections in this topic describe how to implement streaming for LOB data when you use the WCF channel model.</span></span>  
  
 <span data-ttu-id="60972-105">Para obtener información general acerca de cómo el adaptador es compatible con transmisión por secuencias de tipos de datos LOB, vea [transmisión por secuencias de tipos de datos de objetos grandes en el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="60972-105">For background information about how the adapter supports streaming of LOB data types, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="60972-106">Debe leer este tema antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="60972-106">You should read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="60972-107">Un ejemplo que muestra la transmisión por secuencias de datos LOB está disponible en los ejemplos de SDK que se incluyen con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60972-107">A sample that demonstrates LOB data streaming is available in the SDK samples included with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="60972-108">Para obtener más información, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="60972-108">For more information, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="streaming-outbound-messages-to-the-adapter"></a><span data-ttu-id="60972-109">Transmisión de mensajes salientes al adaptador</span><span class="sxs-lookup"><span data-stu-id="60972-109">Streaming Outbound Messages to the Adapter</span></span>  
 <span data-ttu-id="60972-110">El adaptador admite datos LOB-to-end para el mensaje de solicitud para la operación de UpdateLOB de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="60972-110">The adapter supports end-to-end LOB data streaming for the request message for the UpdateLOB operation.</span></span>  
  
 <span data-ttu-id="60972-111">Para admitir la transmisión por secuencias to-end en las operaciones de UpdateLOB en el modelo de canal WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="60972-111">To support end-to-end streaming on UpdateLOB operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="60972-112">Establecer el **UseAmbientTransaction** enlaza la propiedad en true.</span><span class="sxs-lookup"><span data-stu-id="60972-112">Set the **UseAmbientTransaction** binding property to true.</span></span>  
  
2.  <span data-ttu-id="60972-113">Implemente un **System.ServiceModel.Channels.BodyWriter** que es capaz de transmitir por secuencias los datos LOB (realizando la transmisión por secuencias en los datos de LOB en el valor de nodo).</span><span class="sxs-lookup"><span data-stu-id="60972-113">Implement a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
3.  <span data-ttu-id="60972-114">Realizar la operación de UpdateLOB dentro de un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="60972-114">Perform the UpdateLOB operation within a transaction scope.</span></span>  
  
4.  <span data-ttu-id="60972-115">Crear el **System.ServiceModel.Message** se utiliza para invocar la operación si se suministra el cuerpo del mensaje a este **BodyWriter** con una sobrecarga adecuada de la **Message.Create** método.</span><span class="sxs-lookup"><span data-stu-id="60972-115">Create the **System.ServiceModel.Message** used to invoke the operation by supplying the message body with this **BodyWriter** using an appropriate overload of the **Message.Create** method.</span></span>  
  
### <a name="setting-the-useambienttransaction-binding-property"></a><span data-ttu-id="60972-116">Establecer la propiedad de enlace de UseAmbientTransaction</span><span class="sxs-lookup"><span data-stu-id="60972-116">Setting the UseAmbientTransaction Binding Property</span></span>  
 <span data-ttu-id="60972-117">En el ejemplo siguiente se muestra cómo crear un enlace para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y establezca el **UseAmbientTransaction** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="60972-117">The following example shows how to create a binding for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and set the **UseAmbientTransaction** binding property.</span></span>  
  
```  
// Create binding  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
//set the binding property  
binding.UseAmbientTransaction = true;  
  
```  
  
### <a name="implementing-a-bodywriter"></a><span data-ttu-id="60972-118">Implementar un BodyWriter</span><span class="sxs-lookup"><span data-stu-id="60972-118">Implementing a BodyWriter</span></span>  
 <span data-ttu-id="60972-119">En el ejemplo siguiente se muestra una implementación de un **BodyWriter** que realiza la transmisión por secuencias de valor de nodo.</span><span class="sxs-lookup"><span data-stu-id="60972-119">The following example shows an implementation of a **BodyWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="perform-the-operations-within-a-transaction-scope"></a><span data-ttu-id="60972-120">Realizar las operaciones dentro de un ámbito de transacción</span><span class="sxs-lookup"><span data-stu-id="60972-120">Perform the Operations Within a Transaction Scope</span></span>  
 <span data-ttu-id="60972-121">En el ejemplo siguiente se muestra cómo realizar operaciones dentro de un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="60972-121">The following example shows how to perform operations within a transaction scope.</span></span>  
  
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
  
### <a name="creating-a-message-by-using-a-bodywriter"></a><span data-ttu-id="60972-122">Crear un mensaje mediante un BodyWriter</span><span class="sxs-lookup"><span data-stu-id="60972-122">Creating a Message by using a BodyWriter</span></span>  
 <span data-ttu-id="60972-123">En el ejemplo siguiente se muestra cómo crear un mensaje de solicitud de UpdateLOB con el **BodyWriter** en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="60972-123">The following example shows how to create an UpdateLOB request message using the **BodyWriter** in the preceding example.</span></span> <span data-ttu-id="60972-124">Los datos del mensaje se leen desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="60972-124">The message data is read from a file.</span></span>  
  
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
  
## <a name="streaming-inbound-messages-from-the-adapter"></a><span data-ttu-id="60972-125">Transmisión de mensajes entrantes desde el adaptador</span><span class="sxs-lookup"><span data-stu-id="60972-125">Streaming Inbound Messages from the Adapter</span></span>  
 <span data-ttu-id="60972-126">El adaptador admite datos LOB-to-end de transmisión por secuencias para los mensajes entrantes siguientes:</span><span class="sxs-lookup"><span data-stu-id="60972-126">The adapter supports end-to-end LOB data streaming for the following inbound messages:</span></span>  
  
-   <span data-ttu-id="60972-127">Mensaje de respuesta para las funciones con fuera o en los parámetros OUT que contienen datos LOB.</span><span class="sxs-lookup"><span data-stu-id="60972-127">Response message for functions with OUT or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="60972-128">Tenga en cuenta que los parámetros de tipo de registro pueden contener columnas de datos LOB.</span><span class="sxs-lookup"><span data-stu-id="60972-128">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
-   <span data-ttu-id="60972-129">Mensaje de respuesta para las funciones con parámetros de salida de REF CURSOR (o los valores devueltos) que contienen datos LOB.</span><span class="sxs-lookup"><span data-stu-id="60972-129">Response message for functions with OUT REF CURSOR parameters (or return values) that contain LOB data.</span></span> <span data-ttu-id="60972-130">Esto incluye el lado de salida de parámetros en espera REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="60972-130">This includes the output side of IN OUT REF CURSOR parameters.</span></span>  
  
-   <span data-ttu-id="60972-131">Mensaje de respuesta para los procedimientos con IN o en los parámetros OUT que contienen datos LOB.</span><span class="sxs-lookup"><span data-stu-id="60972-131">Response message for procedures with IN or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="60972-132">Tenga en cuenta que los parámetros de tipo de registro pueden contener columnas de datos LOB.</span><span class="sxs-lookup"><span data-stu-id="60972-132">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
-   <span data-ttu-id="60972-133">Mensaje de respuesta para los procedimientos con parámetros de salida de REF CURSOR que contienen datos LOB.</span><span class="sxs-lookup"><span data-stu-id="60972-133">Response message for procedures with OUT REF CURSOR parameters that contain LOB data.</span></span> <span data-ttu-id="60972-134">Esto incluye el lado de salida de parámetros en espera REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="60972-134">This includes the output side of IN OUT REF CURSOR parameters</span></span>  
  
-   <span data-ttu-id="60972-135">Mensaje de respuesta para las operaciones de SQLEXECUTE que devuelven conjuntos de resultados que contienen datos LOB.</span><span class="sxs-lookup"><span data-stu-id="60972-135">Response message for SQLEXECUTE operations that return result sets that contain LOB data.</span></span>  
  
-   <span data-ttu-id="60972-136">Establece el mensaje de respuesta para la tabla o vista operaciones Select que devuelven datos LOB en el resultado.</span><span class="sxs-lookup"><span data-stu-id="60972-136">Response message for Table or view Select operations that return LOB data in the result set.</span></span>  
  
-   <span data-ttu-id="60972-137">Mensaje de solicitud para la operación de POLLINGSTMT (entrante)</span><span class="sxs-lookup"><span data-stu-id="60972-137">Request message for the (inbound) POLLINGSTMT operation</span></span>  
  
 <span data-ttu-id="60972-138">Para admitir la transmisión por secuencias to-end en un mensaje entrante en el modelo de canal WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="60972-138">To support end-to-end streaming on an inbound message in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="60972-139">Implemente un **System.Xml.XmlDictionaryWriter** que es capaz de transmitir por secuencias los datos LOB (realizando la transmisión por secuencias en los datos de LOB en el valor de nodo).</span><span class="sxs-lookup"><span data-stu-id="60972-139">Implement a **System.Xml.XmlDictionaryWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
2.  <span data-ttu-id="60972-140">Consumir la **mensaje** invocando **WriteBodyContents** método con este **XmlDictionaryWriter**.</span><span class="sxs-lookup"><span data-stu-id="60972-140">Consume the **Message** by invoking **WriteBodyContents** method with this **XmlDictionaryWriter**.</span></span>  
  
### <a name="implementing-an-xmldictionarywriter"></a><span data-ttu-id="60972-141">Implementar un XmlDictionaryWriter</span><span class="sxs-lookup"><span data-stu-id="60972-141">Implementing an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="60972-142">En el ejemplo siguiente se muestra una implementación de un **XmlDictionaryWriter** que realiza la transmisión por secuencias de valor de nodo.</span><span class="sxs-lookup"><span data-stu-id="60972-142">The following example shows an implementation of an **XmlDictionaryWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a><span data-ttu-id="60972-143">Usar un mensaje utilizando un XmlDictionaryWriter</span><span class="sxs-lookup"><span data-stu-id="60972-143">Consuming a Message by using an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="60972-144">En el ejemplo siguiente se muestra cómo utilizar un mensaje de respuesta seleccione tabla utilizando la **FileXmlWriter** implementado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="60972-144">The following example shows how to consume a table Select response message using the **FileXmlWriter** implemented in the preceding example.</span></span> <span data-ttu-id="60972-145">(El **FileWriter** clase creó subclasificando **XmlDictionaryWriter**.) El ejemplo se usa un **IRequestChannel** canal para invocar la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="60972-145">(The **FileWriter** class was created by sub-classing **XmlDictionaryWriter**.) The example uses an **IRequestChannel** channel to invoke the Select operation.</span></span> <span data-ttu-id="60972-146">Se han omitido los detalles de la creación del canal.</span><span class="sxs-lookup"><span data-stu-id="60972-146">The details of the channel creation have been omitted.</span></span> <span data-ttu-id="60972-147">El mensaje de solicitud Select se lee desde un archivo y el mensaje de respuesta Select se escribe en un archivo.</span><span class="sxs-lookup"><span data-stu-id="60972-147">The Select request message is read from a file and the Select response message is written to a file.</span></span>  
  
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
  
 <span data-ttu-id="60972-148">El siguiente XML muestra el mensaje de solicitud (contenido del archivo select.xml) para la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="60972-148">The following XML shows the request message (contents of the select.xml file) for the Select operation.</span></span> <span data-ttu-id="60972-149">La tabla CUSTOMER contiene una columna BLOB denominada PHOTO.</span><span class="sxs-lookup"><span data-stu-id="60972-149">The CUSTOMER table contains a BLOB column named PHOTO.</span></span>  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>NAME='Kim Ralls'</FILTER>  
</Select>  
```  
  
## <a name="see-also"></a><span data-ttu-id="60972-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="60972-150">See Also</span></span>  
 [<span data-ttu-id="60972-151">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="60972-151">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)