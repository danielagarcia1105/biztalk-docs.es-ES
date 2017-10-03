---
title: "Transmisión por secuencias y el adaptador SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- streaming, support in WCF service model
- streaming, node-value
- streaming, node
- streaming, support in BizTalk Server
- streaming, and the SAP adapter
- streaming, support in WCF channel model
ms.assetid: 9fa1788b-f21b-4dec-be14-27dd8080a9d4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48b97b0349822dcca1ae6486e4a0b515778b4d4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="streaming-and-the-sap-adapter"></a>Transmisión por secuencias y el adaptador SAP
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite mensajes de transmisión por secuencias entre él y una aplicación cliente. Con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se invocan las operaciones y las respuestas se devuelven mediante el intercambio de mensajes SOAP. Un cuerpo del mensaje SOAP se compone de los nodos XML.  
  
 Hay dos tipos de transmisión por secuencias de mensajes que son compatibles con el adaptador:  
  
-   **Transmisión por secuencias de nodo**. En el nodo de streaming, un mensaje se puede transmitir un nodo cada vez entre el cliente y el adaptador. Esto significa que, todo el valor de un nodo se leen en un búfer y se envía al receptor.  
  
-   **Valor del nodo de transmisión por secuencias**. En el valor del nodo la transmisión por secuencias el valor real del nodo se puede transmitir en fragmentos entre el cliente y el adaptador. Valor del nodo de transmisión por secuencias es útil para enviar o recibir IDOC grande mediante la SendIdoc o las operaciones de ReceiveIdoc. Esto es porque el IDOC completo se encuentra en un único nodo. (En lugar de fuertemente tipadas enviar o recibir operación en el que los datos IDOC se dividen en varios nodos).  
  
> [!IMPORTANT]
>  Valor del nodo de transmisión por secuencias solo se admite entre el adaptador y una aplicación cliente. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no admite la transmisión por secuencias con el sistema SAP de valor de nodo-to-end. Esto es porque esta funcionalidad no es compatible con la biblioteca de cliente SAP.  
  
 Ambos modos de transmisión por secuencias se basan en la compatibilidad con transmisión por secuencias de nodo y transmisión por secuencias en mensajes de WCF en el valor de nodo. Por esta razón, transmisión por secuencias está asociada estrechamente a cómo los mensajes se crean y utilizados por el adaptador y una aplicación cliente. Una de las consecuencias es que la compatibilidad con streaming de mensajes no es el mismo en todos los modelos de programación.  
  
 Las secciones de este tema proporcionan:  
  
-   Información fundamental acerca de cómo se admite la transmisión por secuencias de mensajes en WCF y cómo se implementa el adaptador.  
  
-   Obtener información sobre cómo la transmisión de mensaje se admite cuando se usa el adaptador en cada modelo de programación.  
  
## <a name="streaming-fundamentals"></a>Conceptos básicos de transmisión por secuencias  
 La compatibilidad con streaming implementada por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es una combinación de:  
  
-   Compatibilidad de transmisión por secuencias de mensajes en WCF.  
  
-   Compatibilidad con la transmisión en la biblioteca de cliente SAP.  
  
-   Los mensajes de forma se crean y utilizados internamente por el adaptador.  
  
### <a name="message-streaming-support-in-wcf"></a>Compatibilidad con transmisión por secuencias de mensajes en WCF  
 Cómo WCF admite la transmisión por secuencias en un mensaje depende de cómo se crea el mensaje y cómo se consume el mensaje.  
  
-   Se crea un mensaje de WCF mediante el método estático **crear** método **System.ServiceModel.Channels.Message**. Este método tiene varias sobrecargas que admiten distintas formas de pasar el cuerpo del mensaje. Un mensaje de WCF puede crearse pasando el cuerpo del mensaje utilizando:  
  
    -   A **System.Xml.XmlReader**, o  
  
    -   A **System.ServiceModel.Channels.BodyWriter**.  
  
-   Un mensaje de WCF puede utilizarse con  
  
    -   Un **XmlReader** mediante una llamada a **Message.GetReaderAtBodyContents()**, o  
  
    -   Un **XmlDictionaryWriter** mediante una llamada a **Message.WriteBodyContents(XmlDictionaryWriter)**.  
  
 En la tabla siguiente se muestra cómo se comporta de WCF de combinaciones diferentes de crear y consumir mensajes.  
  
|Mensaje creado con|Mensaje consumida con|Comportamiento de WCF|  
|--------------------------|---------------------------|------------------|  
|**XmlBodyWriter**|**XmlDictionaryWriter**|**Valor del nodo de transmisión por secuencias** se admite. WCF canaliza los dos sistemas de escritura para habilitar la transmisión por secuencias. Tanto el **XmlBodyWriter** y **XmlDictionaryWriter** debe admitir la transmisión por secuencias para que se produzca en el valor de nodo.|  
|**XmlBodyWriter**|**XmlReader**|**Transmisión por secuencias de nodo** se admite. WCF internamente almacena en búfer el **XmlReader**.|  
|**XmlReader**|**XmlDictionaryWriter**|**Transmisión por secuencias de nodo** se admite. WCF internamente almacena en búfer el **XmlReader** y vuelve a llamar a la **XmlDictionaryWriter**.|  
|**XmlReader**|**XmlReader**|**Transmisión por secuencias de nodo** se admite. WCF internamente almacena en búfer el **XmlReader**.|  
  
### <a name="streaming-support-in-the-sap-client-library"></a>Compatibilidad con la transmisión en la biblioteca de cliente SAP  
 La biblioteca de cliente SAP no es compatible con la transmisión por secuencias. Por lo tanto, el valor de nodo-to-end de transmisión por secuencias no es compatible con la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="internal-message-handling-by-the-adapter"></a>Control por el adaptador de mensajes interna  
 El adaptador admite la transmisión de la siguiente manera:  
  
-   El adaptador consume el mensaje de solicitud de SendIdDoc recibido desde el cliente mediante el uso de una implementación personalizada de **XmlDictionaryWriter**. Consume todos los demás mensajes recibidos desde el cliente mediante un **XmlReader**.  
  
-   El adaptador crea el mensaje de solicitud de ReceiveIdoc que envía al cliente mediante el uso de una implementación personalizada de **XmlBodyWriter**. Crea todos los demás mensajes que envía al cliente utilizando un **XmlReader**.  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>Compatibilidad con la transmisión en el modelo del canal de WCF  
 En la tabla siguiente proporciona información detallada sobre cómo se admite la transmisión por secuencias en el modelo de canal WCF.  
  
|Operación|Transmisión por secuencias de nodo|Transmisión por secuencias en el valor de nodo|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|Operaciones de RFC y BAPI salientes (desde el cliente al adaptador)|No compatible|No compatible||  
|Operaciones de tRFC salientes (desde el cliente al adaptador)|No compatible|No compatible||  
|Operación de envío de IDOC (establecimiento inflexible de tipos)|No compatible|No compatible||  
|Operación de recepción IDOC (establecimiento inflexible de tipos)|Admitida|No compatible||  
|Operación SendIdoc (cadena)|Admitida|Admitida|El adaptador utiliza un **XmlDictionaryWriter** para consumir el mensaje de solicitud. Si el cliente crea el mensaje con un **BodyWriter**, se produce la transmisión por secuencias desde el cliente para el adaptador en el valor de nodo.|  
|Operación ReceiveIdoc (cadena)|Admitida|Admitida|El adaptador utiliza un **BodyWriter** para crear el mensaje de solicitud. Si el cliente consume el mensaje mediante un **XmlDictionaryWriter**, se produce la transmisión por secuencias desde el adaptador al cliente en el valor de nodo.|  
|Operaciones de RFC entrantes|No compatible|No compatible||  
|Operaciones de tRFC entrantes|No compatible|No compatible||  
  
 Para obtener información sobre cómo implementar el valor del nodo en el código para enviar y recibir IDOC de archivo sin formato (cadena) mediante las operaciones de SendIdoc y ReceiveIdoc de transmisión por secuencias, vea [secuencia IDOC de archivo plano en SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>Compatibilidad con la transmisión en el modelo de servicio WCF  
 Serializar y deserializar entre la representación XML de un mensaje y la representación de objeto de código administrado de ese mensaje requieren escribir y leer el mensaje completo en la memoria. Por este motivo, ni de transmisión por secuencias de nodo ni de transmisión por secuencias en el valor de nodo se admite desde el modelo de servicio WCF.  
  
## <a name="streaming-support-in-biztalk-server"></a>Compatibilidad con la transmisión en BizTalk Server  
 En la tabla siguiente proporciona información detallada sobre cómo se admite la transmisión por secuencias en BizTalk Server.  
  
|Operación|Transmisión por secuencias de nodo|Transmisión por secuencias en el valor de nodo|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|Operaciones de RFC y BAPI (desde el cliente al adaptador)|No compatible|No compatible||  
|operaciones de tRFC (desde el cliente al adaptador)|No compatible|No compatible||  
|Operación de envío de IDOC (establecimiento inflexible de tipos)|No compatible|No compatible||  
|Operación de recepción IDOC (establecimiento inflexible de tipos)|Admitida|No compatible||  
|Operación SendIdoc (cadena)|Admitida|Admitida|El adaptador de WCF-Custom utiliza un **BodyWriter** para crear el mensaje de solicitud, por lo que se admite la transmisión por secuencias de valor de nodo.|  
|Operación ReceiveIdoc (cadena)|Admitida|Admitida|El adaptador de WCF-Custom utiliza un **XmlDictionaryWriter** para consumir el mensaje de solicitud, por lo que se admite la transmisión por secuencias de valor de nodo.|  
|Operaciones de RFC entrantes|No compatible|No compatible||  
|Operaciones de tRFC entrantes|No compatible|No compatible||  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)