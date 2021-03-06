---
title: Información general del modelo del canal WCF con el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
- WCF channel model, creating messages for the SAP adapter
ms.assetid: 6192d637-efac-4580-8880-b5bae9d16f31
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81eba8c28b3bf11eea38624e0a017d8bca9eb9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013189"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a>Información general del modelo del canal WCF con el adaptador de SAP
Para invocar RFC, trfc o BAPI en un sistema SAP, o para enviar los IDOC a un sistema SAP, el código actúa como un cliente WCF y envía las operaciones salientes al adaptador. En el modelo de canal WCF, el código invoca las operaciones en el adaptador mediante el envío de un mensaje de solicitud a través de un canal.  
  
 Para actuar como servidor RFC a un sistema SAP o tRFC, el código se comporta como un servicio WCF. Es decir, el adaptador invoca una operación entrada en el código, por ejemplo, una solicitud de cambio o la operación ReceiveIdoc (para recibir un IDOC en formato de cadena de un sistema SAP). En este escenario, el código recibe un mensaje de solicitud para la operación a través de un canal desde el adaptador.  
  
 Los temas de esta sección proporcionan una introducción al uso del [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con el modelo de canal WCF.  
  
## <a name="wcf-channel-model-overview"></a>Información general del modelo de canal de WCF  
 Los clientes y servicios comunican intercambiando mensajes SOAP. El modelo de canal WCF es una abstracción de bajo nivel de este intercambio de mensajes. Proporciona tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que llama a una pila de canales e interfaces. Cada capa de la pila se compone de un canal y cada canal se crea a partir de un enlace WCF. En el nivel más bajo es el canal de transporte. El canal de transporte implementa el mecanismo de transporte subyacente entre un servicio y un cliente y presenta cada mensaje a las capas más elevadas (y, en última instancia, la aplicación consumidora) como un **System.ServiceModel.Message**. WCF **mensaje** clase es una abstracción de un mensaje SOAP. WCF proporciona varias interfaces de canal, llama a las formas del canal, que modelan el básica SOAP mensaje patrones de intercambio, como solicitud-respuesta o unidireccionales. Un transporte WCF enlace proporciona una implementación de uno o más formas de canal superior en capas se pueden usar para enviar y recibir mensajes. Para obtener más información sobre el modelo de canal WCF, vea [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace de transporte personalizado de WCF que expone un sistema SAP como un servicio WCF.  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a>Admite las formas del canal para el adaptador de SAP  
 El adaptador implementa las siguientes formas de canal WCF:  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**). El **IRequestChannel** interfaz implementa el cliente de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IRequestChannel** para realizar operaciones para el que quiere usar una respuesta, por ejemplo invocar una solicitud de cambio en el sistema SAP que devuelve datos.  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**). Esta forma implementa el cliente de un intercambio de mensajes unidireccional. Puede usar un **IOutputChannel** para invocar una operación que no es necesario consumir una respuesta, por ejemplo invocar una solicitud de cambio en el sistema SAP que no devuelve ningún dato.  
  
- **IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**). Esta forma implementa el lado del servicio de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IReplyChannel** para implementar un servidor RFC o tRFC o para recibir los IDOC desde un sistema SAP.  
  
  Al igual que cualquier enlace WCF, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa un patrón de fábrica para proporcionar canales al código de aplicación. Usa un **Microsoft.Adapters.SAPBinding** objeto para crear instancias de:  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>**  para proporcionar **IRequestChannel** canales que se puede usar para invocar operaciones de solicitud-respuesta en el adaptador.  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>**  para proporcionar **IOutputChannel** canales puede usar para invocar las operaciones unidireccionales en el adaptador.  
  
- **System.ServiceModel.IChannelListener\<IReplyChannel\>**  para proporcionar **IReplyChannel** canales puede usar para recibir operaciones de solicitud y respuesta desde el adaptador.  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a>Creación de mensajes para el adaptador SAP en el modelo del canal de WCF  
 En WCF la **System.ServiceModel.Channels.Message** clase proporciona una memoria en representación de un mensaje SOAP. Crear un **mensaje** instancia invocando estático **Message.Create** método.  
  
 Hay dos partes importantes en el mensaje SOAP que debe especificar al construir un **mensaje** instancia para enviar a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- La acción del mensaje es una cadena que forma parte del encabezado del mensaje SOAP. La acción de mensaje identifica la operación que debe invocarse en [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. La siguiente muestra la acción de mensaje que se especifica para invocar la RFC SD_RFC_CUSTOMER_GET en un sistema SAP: `http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`.  
  
- El cuerpo del mensaje contiene los datos del parámetro para la operación. El cuerpo del mensaje se compone de XML con formato correcto que se corresponde con el esquema del mensaje esperado por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para la operación solicitada. El siguiente cuerpo del mensaje contiene los parámetros de la RFC SD_RFC_CUSTOMER_GET en un sistema SAP.  
  
  ```  
  <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
  ```  
  
  Para obtener información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] los esquemas de mensajes y las acciones para las operaciones de mensaje, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).  
  
  El **Message.Create** método está sobrecargado y ofrece muchas opciones diferentes para proporcionar el cuerpo del mensaje. El código siguiente muestra cómo crear un **mensaje** instancia mediante el uso de un **System.Xml.XmlReader** para proporcionar el cuerpo del mensaje. En este código, el cuerpo del mensaje se lee de una constante de cadena.  
  
```  
//create an XML message to send to the SAP system  
//We are invoking the SD_RFC_CUSTOMER_GET RFC.  
//The XML below specifies that we want to search for customers with names starting with "AB"  
string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
//create an XML reader from the input XML  
XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
//create a WCF message from the XML reader  
Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
```  
  
> [!IMPORTANT]
>  Debe proporcionar una acción del mensaje en su **mensaje** instancia. Normalmente, esto se realiza cuando el **mensaje** se crea la instancia.  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a>Compatibilidad con Streaming en el adaptador de SAP en el modelo del canal de WCF  
 Cómo crear y consumir los mensajes que intercambian con el adaptador SAP determina cómo se transmite el mensaje entre el código y el adaptador.  
  
### <a name="node-streaming"></a>Nodo de transmisión por secuencias  
 Transmisión por secuencias de nodo es el único nivel de streaming admite para todas las operaciones excepto las operaciones de SendIdoc y ReceiveIdoc.  
  
 Para realizar la transmisión por secuencias para un mensaje, el nodo:  
  
-   Crear un mensaje saliente con un **XmlReader** para proporcionar el cuerpo del mensaje.  
  
-   Consumir un mensaje entrante con un **XmlReader**. Obtenga el lector llamando el **GetReaderAtBodyContents** método en la entrada **mensaje**.  
  
### <a name="node-value-streaming"></a>Valor del nodo de transmisión por secuencias  
 Dado que las operaciones de SendIdoc y ReceiveIdoc contienen los datos IDOC en una cadena en un único nodo XML (\<idocData\>), el adaptador admite nodo-valor transmisión por secuencias en estas operaciones.  
  
 Para llevar a cabo estas operaciones de transmisión por secuencias en el valor de nodo, hacer lo siguiente:  
  
- Crear la SendIdoc solicitud mensaje (salientes) con un **BodyWriter** que implementa el valor del nodo de streaming para proporcionar el cuerpo del mensaje.  
  
- Consumir el mensaje de solicitud ReceiveIdoc (entrante) mediante una llamada a la **WriteBodyContents** método en el mensaje con un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.  
  
  Para obtener más información sobre el streaming de IDOC de archivo sin formato (cadena) mediante el modelo de canal WCF, vea [Streaming de IDOC de archivo plano en SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)