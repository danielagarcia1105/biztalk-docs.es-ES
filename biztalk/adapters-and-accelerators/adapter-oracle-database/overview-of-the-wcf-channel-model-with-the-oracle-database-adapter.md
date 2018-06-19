---
title: Información general sobre el modelo de canal WCF con el adaptador de la base de datos de Oracle | Documentos de Microsoft
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
ms.openlocfilehash: 94cb4b8cfdb0315b55aa88ddd385396ff967b8f6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964272"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-database-adapter"></a>Información general sobre el modelo de canal WCF con el adaptador de la base de datos de Oracle
Para invocar operaciones en el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], el código actúa como un cliente de WCF y envía las operaciones salientes al adaptador. En el modelo de canal WCF, el código invoca las operaciones en el adaptador mediante el envío de un mensaje de solicitud a través de un canal.  
  
 Para invocar operaciones de entrada, como destinatario sondeo mensajes basados en datos cambiado mediante la operación de POLLINGSTMT proporcionada por el adaptador, el código actúa como un servicio WCF y recibe la operación de entrada procedentes del adaptador. En otras palabras, el código recibe un mensaje de solicitud desde el adaptador a través de un canal.  
  
 Los temas de esta sección proporcionan una introducción al uso de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con el modelo de canal WCF.  
  
## <a name="wcf-channel-model-overview"></a>Información general del modelo de canal de WCF  
 Los clientes y servicios se comunican mediante el intercambio de mensajes SOAP. El modelo de canal WCF es una abstracción de bajo nivel de este intercambio de mensajes. Proporciona interfaces y tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que se llama a una pila de canales. Cada nivel de la pila se compone de un canal y se crea cada canal de un enlace de WCF. En el nivel más bajo es el canal de transporte. El canal de transporte implementa el mecanismo de transporte subyacente entre un servicio y un cliente y presenta cada mensaje a las capas más elevadas (y, en última instancia, la aplicación que consume) como un **System.ServiceModel.Message**. WCF **mensaje** clase es una abstracción de un mensaje SOAP. WCF proporciona varias interfaces de canal, llamados a formas del canal, que modelan los básica SOAP mensaje patrones de intercambio, como solicitud-respuesta o unidireccional. Un transporte WCF enlace proporciona una implementación de uno o más formas del canal que coloque en una capa superior pueden usar para enviar y recibir mensajes. Para obtener más información sobre el modelo de canal WCF, vea [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).   
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es un enlace de transporte personalizado de WCF que expone una base de datos de Oracle como un servicio WCF.  
  
## <a name="supported-channel-shapes-for-the-oracle-database-adapter"></a>Admite formas del canal para el adaptador de la base de datos de Oracle  
 El adaptador implementa las siguientes formas de canal WCF:  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**). El **IRequestChannel** interfaz implementa el cliente de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IRequestChannel** para realizar operaciones para el que desea utilizar una respuesta, por ejemplo, para realizar una instrucción SELECT consulta en una tabla de Oracle.  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**). Esta forma implementa el cliente de un intercambio de mensajes unidireccionales. Puede usar un **IOutputChannel** para invocar una operación para la que no es necesario utilizar una respuesta, por ejemplo, para llamar a un procedimiento de Oracle que no tiene ningún parámetro de salida.  
  
    > [!IMPORTANT]
    >  Todas las llamadas subyacentes por el adaptador para el cliente de Oracle son sincrónicas. Esto incluye las llamadas al cliente de Oracle que son el resultado de las operaciones que se invoca en un **IOutputChannel**. Cuando se usa un **IOutputChannel**, el adaptador descarta la respuesta recibida desde el cliente de Oracle.  
  
-   **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**). Esta forma implementa el lado del servicio de un intercambio de mensajes unidireccionales. Usa un **IInputChannel** para recibir mensajes para operaciones de entrada desde el adaptador.  
  
 Al igual que cualquier enlace de WCF, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] utiliza un modelo de generador para proporcionar canales al código de la aplicación. Usa un **Microsoft.Adapters.OracleDBBinding** objeto que se va a crear instancias de:  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel\>**  para proporcionar **IRequestChannel** canales puede usar para invocar operaciones de solicitud-respuesta en el adaptador.  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel\>**  para proporcionar **IOutputChannel** canales puede usar para invocar las operaciones unidireccionales en el adaptador.  
  
-   **System.ServiceModel.IChannelListener\<IInputChannel\>**  para proporcionar **IInputChannel** canales puede utilizar para recibir mensajes de entrada (por ejemplo, una operación POLLINGSTMT) desde el adaptador .  
  
### <a name="creating-messages-for-the-oracle-database-adapter-in-the-wcf-channel-model"></a>Crear mensajes para el adaptador de la base de datos de Oracle en el modelo del canal de WCF  
 En WCF la **System.ServiceModel.Channels.Message** clase proporciona una memoria en representación de un mensaje SOAP. Crear un **mensaje** instancia invocando el método estático **Message.Create** método.  
  
 Hay dos partes importantes para el mensaje SOAP que debe especificar cuando se crea un **mensaje** instancia para enviar a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
-   La acción de mensaje es una cadena que forma parte del encabezado del mensaje SOAP. La acción de mensaje identifica la operación que se debe invocar en la base de datos de Oracle. La siguiente muestra la acción de mensaje especificada para invocar la operación Select en la tabla/SCOTT/EMP: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select`.  
  
-   El cuerpo del mensaje contiene los datos del parámetro para la operación. El cuerpo del mensaje se compone de XML con formato correcto que se corresponde con el esquema del mensaje esperado por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para la operación solicitada. El siguiente cuerpo del mensaje especifica una operación Select en la SCOTT. Tabla EMP (seleccione * de EMP).  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP">  
        <COLUMN_NAMES>*</COLUMN_NAMES>  
    </Select>  
    ```  
  
 Para obtener información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] esquemas de mensajes y las acciones para las operaciones de mensajes, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).  
  
 Esto **Create** método está sobrecargado y ofrece muchas opciones diferentes para proporcionar el cuerpo del mensaje. El código siguiente muestra cómo crear un **mensaje** instancia mediante el uso de un **XmlReader** para proporcionar el cuerpo del mensaje. En este código, el cuerpo del mensaje se lee desde un archivo.  
  
```  
XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  Debe proporcionar una acción de mensaje en su **mensaje** instancia. Esto se hace normalmente cuando la **mensaje** se crea la instancia.  
  
## <a name="streaming-support-for-lob-data-types-in-the-wcf-channel-model"></a>Compatibilidad con Streaming para tipos de datos LOB en el modelo del canal de WCF  
 Se admite la transmisión por secuencias to-end de tipos de datos LOB para algunas operaciones obtenidas por el adaptador. Para estas operaciones, cómo crear y consumir los mensajes que envían y reciben a través del canal determina si se admite la transmisión por secuencias en los datos de LOB.  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la transmisión por secuencias en datos LOB, consulte [transmisión por secuencias de tipos de datos de objetos grandes en el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).  
  
 Para obtener más información acerca de cómo implementar el valor del nodo en el código para admitir-to-end de transmisión por secuencias de datos LOB de transmisión por secuencias, vea [Streaming Oracle base de datos LOB datos tipos con el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)