---
title: "Información general sobre el modelo de canal WCF con el adaptador SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
- WCF channel model, creating messages for the SAP adapter
ms.assetid: 6192d637-efac-4580-8880-b5bae9d16f31
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b5469681f7acce2ebb0b55fe63e285d25192e0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a>Información general sobre el modelo de canal WCF con el adaptador SAP
Para invocar las solicitudes de cambio, tRFCs o BAPI en un sistema SAP, o para enviar IDOC a un sistema SAP, el código actúa como un cliente de WCF y envía las operaciones salientes al adaptador. En el modelo de canal WCF, el código invoca las operaciones en el adaptador mediante el envío de un mensaje de solicitud a través de un canal.  
  
 Para que actúe como un servidor RFC a un sistema SAP o tRFC, el código se comporta como un servicio WCF. Es decir, el adaptador invoca una operación de entrada en el código, por ejemplo, una solicitud de cambio o la operación de ReceiveIdoc (para recibir un IDOC en formato de cadena de un sistema SAP). En este escenario, el código recibe un mensaje de solicitud para la operación sobre un canal desde el adaptador.  
  
 Los temas de esta sección proporcionan una introducción al uso de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con el modelo de canal WCF.  
  
## <a name="wcf-channel-model-overview"></a>Información general del modelo de canal de WCF  
 Los clientes y servicios se comunican mediante el intercambio de mensajes SOAP. El modelo de canal WCF es una abstracción de bajo nivel de este intercambio de mensajes. Proporciona interfaces y tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que se llama a una pila de canales. Cada nivel de la pila se compone de un canal y se crea cada canal de un enlace de WCF. En el nivel más bajo es el canal de transporte. El canal de transporte implementa el mecanismo de transporte subyacente entre un servicio y un cliente y presenta cada mensaje a las capas más elevadas (y, en última instancia, la aplicación que consume) como un **System.ServiceModel.Message**. WCF **mensaje** clase es una abstracción de un mensaje SOAP. WCF proporciona varias interfaces de canal, llamados a formas del canal, que modelan los básica SOAP mensaje patrones de intercambio, como solicitud-respuesta o unidireccional. Un transporte WCF enlace proporciona una implementación de uno o más formas del canal que coloque en una capa superior pueden usar para enviar y recibir mensajes. Para obtener más información sobre el modelo de canal WCF, vea [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace de transporte personalizado de WCF que expone un sistema SAP como un servicio WCF.  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a>Admite formas del canal para el adaptador SAP  
 El adaptador implementa las siguientes formas de canal WCF:  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**). El **IRequestChannel** interfaz implementa el cliente de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IRequestChannel** para realizar operaciones para el que desea utilizar una respuesta, por ejemplo invocar una solicitud de cambio en el sistema SAP que devuelve los datos.  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**). Esta forma implementa el cliente de un intercambio de mensajes unidireccionales. Puede usar un **IOutputChannel** para invocar una operación para la que no es necesario utilizar una respuesta, por ejemplo invocar una solicitud de cambio en el sistema SAP que no devolvió ningún dato.  
  
-   **IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**). Esta forma implementa el lado del servicio de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IReplyChannel** para implementar un servidor RFC o tRFC o recibir IDOC desde un sistema SAP.  
  
 Al igual que cualquier enlace de WCF, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza un modelo de generador para proporcionar canales al código de la aplicación. Usa un **Microsoft.Adapters.SAPBinding** objeto que se va a crear instancias de:  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel\>**  para proporcionar **IRequestChannel** canales puede usar para invocar operaciones de solicitud-respuesta en el adaptador.  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel\>**  para proporcionar **IOutputChannel** canales puede usar para invocar las operaciones unidireccionales en el adaptador.  
  
-   **System.ServiceModel.IChannelListener\<IReplyChannel\>**  para proporcionar **IReplyChannel** canales que se puede usar para operaciones de solicitud-respuesta de recepción del adaptador.  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a>Crear mensajes para el adaptador SAP en el modelo del canal de WCF  
 En WCF la **System.ServiceModel.Channels.Message** clase proporciona una memoria en representación de un mensaje SOAP. Crear un **mensaje** instancia invocando el método estático **Message.Create** método.  
  
 Hay dos partes importantes para el mensaje SOAP que debe especificar al construir un **mensaje** instancia para enviar a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   La acción de mensaje es una cadena que forma parte del encabezado del mensaje SOAP. La acción de mensaje identifica la operación que se debe invocar en [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. La acción de mensaje que se especifica para invocar la RFC SD_RFC_CUSTOMER_GET en un sistema SAP muestra lo siguiente: `http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`.  
  
-   El cuerpo del mensaje contiene los datos del parámetro para la operación. El cuerpo del mensaje se compone de XML con formato correcto que se corresponde con el esquema del mensaje esperado por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para la operación solicitada. El siguiente cuerpo del mensaje contiene los parámetros de la solicitud de cambio de SD_RFC_CUSTOMER_GET en un sistema SAP.  
  
    ```  
    <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
    ```  
  
 Para obtener información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] esquemas de mensajes y las acciones para las operaciones de mensajes, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).  
  
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
>  Debe proporcionar una acción de mensaje en su **mensaje** instancia. Esto se hace normalmente cuando la **mensaje** se crea la instancia.  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a>Compatibilidad con la transmisión en el adaptador SAP en el modelo del canal de WCF  
 Cómo crear y consumir los mensajes que intercambian con el adaptador SAP determina cómo se transmite el mensaje entre el código y el adaptador.  
  
### <a name="node-streaming"></a>Transmisión por secuencias de nodo  
 Transmisión por secuencias de nodo es el único nivel de transmisión de datos compatibles con todas las operaciones excepto las operaciones de SendIdoc y ReceiveIdoc.  
  
 Para realizar la transmisión por secuencias para un mensaje, el nodo:  
  
-   Crear un mensaje saliente con un **XmlReader** para proporcionar el cuerpo del mensaje.  
  
-   Consumir un mensaje entrante con un **XmlReader**. Obtenga el lector mediante una llamada a la **GetReaderAtBodyContents** método en la entrada **mensaje**.  
  
### <a name="node-value-streaming"></a>Transmisión por secuencias en el valor de nodo  
 Dado que las operaciones de SendIdoc y ReceiveIdoc contienen los datos IDOC en una cadena en un único nodo XML (\<idocData\>), el adaptador admite nodo valor transmisión por secuencias en estas operaciones.  
  
 Para llevar a cabo para estas operaciones de transmisión por secuencias en el valor de nodo, hacer lo siguiente:  
  
-   Cree el SendIdoc solicitud mensaje (saliente) con un **BodyWriter** que implementa la transmisión por secuencias para proporcionar el cuerpo del mensaje en el valor de nodo.  
  
-   Consumir el mensaje de solicitud de ReceiveIdoc (entrante) mediante una llamada a la **WriteBodyContents** método en el mensaje con un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.  
  
 Para obtener más información sobre el streaming IDOC de archivo sin formato (cadena) mediante el modelo de canal WCF, vea [IDOC de archivo plano de transmisión por secuencias en SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)