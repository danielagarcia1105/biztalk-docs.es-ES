---
title: Información general del modelo del canal WCF con el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
ms.assetid: 4712ba62-8360-475c-b2e4-422e499eca21
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1f681b4a4725f4e866d8959d8851362f0214137
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992693"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-database-adapter"></a>Información general del modelo del canal WCF con el adaptador de base de datos de Oracle
Para invocar operaciones en el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], el código actúa como un cliente de WCF y envía las operaciones salientes al adaptador. En el modelo de canal WCF, el código invoca las operaciones en el adaptador mediante el envío de un mensaje de solicitud a través de un canal.  
  
 Para invocar operaciones de entrada, como destinatario sondeo mensajes basados en datos cambiado mediante la operación POLLINGSTMT proporcionada por el adaptador, el código actúa como un servicio WCF y recibe la operación entrante del adaptador. En otras palabras, el código recibe un mensaje de solicitud del adaptador a través de un canal.  
  
 Los temas de esta sección proporcionan una introducción al uso del [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con el modelo de canal WCF.  
  
## <a name="wcf-channel-model-overview"></a>Información general del modelo de canal de WCF  
 Los clientes y servicios comunican intercambiando mensajes SOAP. El modelo de canal WCF es una abstracción de bajo nivel de este intercambio de mensajes. Proporciona tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que llama a una pila de canales e interfaces. Cada capa de la pila se compone de un canal y cada canal se crea a partir de un enlace WCF. En el nivel más bajo es el canal de transporte. El canal de transporte implementa el mecanismo de transporte subyacente entre un servicio y un cliente y presenta cada mensaje a las capas más elevadas (y, en última instancia, la aplicación consumidora) como un **System.ServiceModel.Message**. WCF **mensaje** clase es una abstracción de un mensaje SOAP. WCF proporciona varias interfaces de canal, llama a las formas del canal, que modelan el básica SOAP mensaje patrones de intercambio, como solicitud-respuesta o unidireccionales. Un transporte WCF enlace proporciona una implementación de uno o más formas de canal superior en capas se pueden usar para enviar y recibir mensajes. Para obtener más información sobre el modelo de canal WCF, vea [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).   
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es un enlace de transporte personalizado de WCF que expone una base de datos de Oracle como un servicio WCF.  
  
## <a name="supported-channel-shapes-for-the-oracle-database-adapter"></a>Admite las formas del canal para el adaptador de base de datos de Oracle  
 El adaptador implementa las siguientes formas de canal WCF:  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**). El **IRequestChannel** interfaz implementa el cliente de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IRequestChannel** para realizar operaciones para el que quiere usar una respuesta, por ejemplo, para realizar una selección de consulta en una tabla de Oracle.  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**). Esta forma implementa el cliente de un intercambio de mensajes unidireccional. Puede usar un **IOutputChannel** para invocar una operación que no es necesario consumir una respuesta, por ejemplo, para llamar a un procedimiento de Oracle que no tiene ningún parámetro OUT.  
  
  > [!IMPORTANT]
  >  Todas las llamadas subyacentes por el adaptador para el cliente de Oracle son sincrónicas. Esto incluye las llamadas al cliente de Oracle que son el resultado de invocar a través de las operaciones de un **IOutputChannel**. Cuando se usa un **IOutputChannel**, el adaptador descarta la respuesta recibida desde el cliente de Oracle.  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**). Esta forma implementa el lado del servicio de un intercambio de mensajes unidireccional. Usa un **IInputChannel** para recibir mensajes para operaciones de entrada desde el adaptador.  
  
  Al igual que cualquier enlace WCF, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa un patrón de fábrica para proporcionar canales al código de aplicación. Usa un **Microsoft.Adapters.OracleDBBinding** objeto para crear instancias de:  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>**  para proporcionar **IRequestChannel** canales que se puede usar para invocar operaciones de solicitud-respuesta en el adaptador.  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>**  para proporcionar **IOutputChannel** canales puede usar para invocar las operaciones unidireccionales en el adaptador.  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>**  para proporcionar **IInputChannel** canales que se puede usar para recibir los mensajes de entrada (por ejemplo, la operación de POLLINGSTMT) desde el adaptador.  
  
### <a name="creating-messages-for-the-oracle-database-adapter-in-the-wcf-channel-model"></a>Creación de mensajes para el adaptador de base de datos de Oracle en el modelo del canal de WCF  
 En WCF la **System.ServiceModel.Channels.Message** clase proporciona una memoria en representación de un mensaje SOAP. Crear un **mensaje** instancia invocando estático **Message.Create** método.  
  
 Hay dos partes importantes en el mensaje SOAP que debe especificar al crear un **mensaje** instancia para enviar a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
- La acción del mensaje es una cadena que forma parte del encabezado del mensaje SOAP. La acción de mensaje identifica la operación que se debe invocar en la base de datos de Oracle. La siguiente muestra la acción de mensaje especificada para invocar la operación de selección en la tabla/SCOTT/EMP: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select`.  
  
- El cuerpo del mensaje contiene los datos del parámetro para la operación. El cuerpo del mensaje se compone de XML con formato correcto que se corresponde con el esquema del mensaje esperado por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para la operación solicitada. El siguiente cuerpo del mensaje especifica una operación de selección en el SCOTT. Tabla EMP (seleccionar * desde EMP).  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>  
  <Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP">  
      <COLUMN_NAMES>*</COLUMN_NAMES>  
  </Select>  
  ```  
  
  Para obtener información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] los esquemas de mensajes y las acciones para las operaciones de mensaje, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).  
  
  Esto **Create** método está sobrecargado y ofrece muchas opciones diferentes para proporcionar el cuerpo del mensaje. El código siguiente muestra cómo crear un **mensaje** instancia mediante el uso de un **XmlReader** para proporcionar el cuerpo del mensaje. En este código, el cuerpo del mensaje se lee desde un archivo.  
  
```  
XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  Debe proporcionar una acción del mensaje en su **mensaje** instancia. Normalmente, esto se realiza cuando el **mensaje** se crea la instancia.  
  
## <a name="streaming-support-for-lob-data-types-in-the-wcf-channel-model"></a>Compatibilidad con Streaming para tipos de datos LOB en el modelo del canal de WCF  
 To-end de streaming de tipos de datos LOB se admite para algunas operaciones obtenidas por el adaptador. Para estas operaciones, cómo crear y consumir los mensajes que envían y reciben a través del canal determina si se admite el streaming en los datos de LOB.  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la transmisión por secuencias en datos LOB, consulte [hacer Streaming de tipos de datos de objetos grandes en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).  
  
 Para obtener más información acerca de cómo implementar el valor del nodo en el código para admitir streaming to-end de los datos LOB de transmisión por secuencias, vea [Streaming Oracle base de datos LOB datos tipos con el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)