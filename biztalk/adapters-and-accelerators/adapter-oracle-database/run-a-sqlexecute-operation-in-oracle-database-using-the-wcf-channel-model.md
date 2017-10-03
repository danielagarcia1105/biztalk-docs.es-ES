---
title: "Ejecutar una operación SQLEXECUTE en base de datos de Oracle mediante el modelo de canal de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running a SQLEXECUTE statement, using a channel
- how to, run a SQLEXECUTE statement by using a channel
- WCF channel model, running a SQLEXECUTE statement
ms.assetid: e1af11ef-3f44-4726-99ca-d6961d79e651
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c7928affeafd40197401fa75d44658e0e975507
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model"></a>Ejecutar una operación SQLEXECUTE en base de datos de Oracle mediante el modelo de canal de WCF
Esta sección muestra cómo realizar una operación SQLEXECUTE en una base de datos de Oracle a través de un canal. Debe especificar un mensaje y una acción de mensaje en el mensaje SOAP. Para obtener más información sobre la operación SQLEXECUTE, consulte [operación SQLEXECUTE ejecutar en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).  
  
## <a name="the-sqlexecute-message"></a>El mensaje SQLEXECUTE  
 El siguiente XML muestra un mensaje SQLEXECUTE que devuelve el siguiente valor de una secuencia de Oracle.  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>  
\<!-- New Action: http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE -->  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
    <SQLSTATEMENT>SELECT tid_seq.nextval id FROM dual</SQLSTATEMENT>  
</SQLEXECUTE>  
```  
  
 El SQLEXECUTE puede especificar un elemento de esquema de parámetro y un bloque de parámetros que contiene varios conjuntos de datos del parámetro. El mensaje que se muestra es una sola invocación de la instrucción SQL especificada para que los elementos que especifican el bloque de parámetros de esquema y los parámetros se omiten en el cuerpo del mensaje. Para obtener información acerca del esquema de mensaje para la operación SQLEXECUTE, consulte [esquemas de mensaje para la operación SQLEXECUTE](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).  
  
## <a name="specifying-the-sqlexecute-action"></a>Especifica la acción de SQLEXECUTE  
 Debe especificar una acción para el mensaje. En el fragmento de código siguiente se muestra cómo especificar la acción para el mensaje SQLEXECUTE.  
  
```  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
```  
  
## <a name="sending-the-sqlexecute-message"></a>Enviar el mensaje SQLEXECUTE  
 En el fragmento de código siguiente se muestra cómo invocar una operación SQLEXECUTE en una base de datos de Oracle a través de un canal.  
  
```  
// Create Endpoint  
EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
  
// Create Binding  
OracleDBBinding binding = new OracleDBBinding();  
  
// Create Channel Factory  
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
factory.Open();  
  
// Create Request Channel  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
  
// Send Request  
System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create("SQLExecute.xml");  
  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
Message messageOut = channel.Request(messageIn);  
  
// Get Response XML  
XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
// Get tid_seq SEQUENCE  
string id = null;  
XmlDocument doc = new XmlDocument();  
doc.Load(readerOut);  
XmlNodeList list = doc.GetElementsByTagName("ColumnValue");  
if (list.Count > 0) id = list[0].InnerXml;  
```  
  
> [!NOTE]
>  La operación SQLEXECUTE siempre devuelve un conjunto de resultados débilmente tipada.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
 [Crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)