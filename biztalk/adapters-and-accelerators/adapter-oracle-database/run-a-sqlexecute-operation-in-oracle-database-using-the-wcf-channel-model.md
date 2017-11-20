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
# <a name="run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="f0c01-102">Ejecutar una operación SQLEXECUTE en base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="f0c01-102">Run a SQLEXECUTE Operation in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="f0c01-103">Esta sección muestra cómo realizar una operación SQLEXECUTE en una base de datos de Oracle a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="f0c01-103">This section shows how to perform a SQLEXECUTE operation on an Oracle database over a channel.</span></span> <span data-ttu-id="f0c01-104">Debe especificar un mensaje y una acción de mensaje en el mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="f0c01-104">You must specify both a message and a message action on the SOAP message.</span></span> <span data-ttu-id="f0c01-105">Para obtener más información sobre la operación SQLEXECUTE, consulte [operación SQLEXECUTE ejecutar en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="f0c01-105">For more information about the SQLEXECUTE operation, see [Run SQLEXECUTE operation in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="the-sqlexecute-message"></a><span data-ttu-id="f0c01-106">El mensaje SQLEXECUTE</span><span class="sxs-lookup"><span data-stu-id="f0c01-106">The SQLEXECUTE Message</span></span>  
 <span data-ttu-id="f0c01-107">El siguiente XML muestra un mensaje SQLEXECUTE que devuelve el siguiente valor de una secuencia de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f0c01-107">The following XML shows a SQLEXECUTE message that returns the next value of an Oracle SEQUENCE.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>  
\<!-- New Action: http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE -->  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
    <SQLSTATEMENT>SELECT tid_seq.nextval id FROM dual</SQLSTATEMENT>  
</SQLEXECUTE>  
```  
  
 <span data-ttu-id="f0c01-108">El SQLEXECUTE puede especificar un elemento de esquema de parámetro y un bloque de parámetros que contiene varios conjuntos de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f0c01-108">The SQLEXECUTE can specify a parameter schema element and a parameter block that contains multiple sets of parameter data.</span></span> <span data-ttu-id="f0c01-109">El mensaje que se muestra es una sola invocación de la instrucción SQL especificada para que los elementos que especifican el bloque de parámetros de esquema y los parámetros se omiten en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f0c01-109">The message shown is for a single invocation of the specified SQL statement so the elements that specify the parameter schema and parameter block are omitted from the message body.</span></span> <span data-ttu-id="f0c01-110">Para obtener información acerca del esquema de mensaje para la operación SQLEXECUTE, consulte [esquemas de mensaje para la operación SQLEXECUTE](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).</span><span class="sxs-lookup"><span data-stu-id="f0c01-110">For information about the message schema for the SQLEXECUTE operation, see [Message Schemas for the SQLEXECUTE Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).</span></span>  
  
## <a name="specifying-the-sqlexecute-action"></a><span data-ttu-id="f0c01-111">Especifica la acción de SQLEXECUTE</span><span class="sxs-lookup"><span data-stu-id="f0c01-111">Specifying the SQLEXECUTE Action</span></span>  
 <span data-ttu-id="f0c01-112">Debe especificar una acción para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f0c01-112">You must specify an action for the message.</span></span> <span data-ttu-id="f0c01-113">En el fragmento de código siguiente se muestra cómo especificar la acción para el mensaje SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="f0c01-113">The following code excerpt shows how to specify the action for the SQLEXECUTE message.</span></span>  
  
```  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
```  
  
## <a name="sending-the-sqlexecute-message"></a><span data-ttu-id="f0c01-114">Enviar el mensaje SQLEXECUTE</span><span class="sxs-lookup"><span data-stu-id="f0c01-114">Sending the SQLEXECUTE Message</span></span>  
 <span data-ttu-id="f0c01-115">En el fragmento de código siguiente se muestra cómo invocar una operación SQLEXECUTE en una base de datos de Oracle a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="f0c01-115">The following code excerpt demonstrates how to invoke a SQLEXECUTE operation on an Oracle database over a channel.</span></span>  
  
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
>  <span data-ttu-id="f0c01-116">La operación SQLEXECUTE siempre devuelve un conjunto de resultados débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="f0c01-116">The SQLEXECUTE operation always returns a weakly-typed result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c01-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0c01-117">See Also</span></span>  
 [<span data-ttu-id="f0c01-118">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="f0c01-118">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
 [<span data-ttu-id="f0c01-119">Crear un canal con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="f0c01-119">Create a channel using Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)