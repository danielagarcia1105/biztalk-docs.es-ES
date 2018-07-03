---
title: Información general del modelo del canal WCF con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e5f77c-c922-4039-92c7-38d2b7638459
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 819143bd7e65c9cea91232e2529b20cfab2c049d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003173"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sql-adapter"></a>Información general del modelo del canal WCF con el adaptador de SQL
Para invocar operaciones en el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], el código actúa como un cliente de WCF y envía las operaciones salientes al adaptador. En el modelo de canal WCF, el código invoca las operaciones en el adaptador mediante el envío de un mensaje de solicitud a través de un canal.  
  
 Para recibir basados en sondeos mensajes cambio de datos mediante el adaptador, el código actúa como un servicio WCF y recibe la entrada **sondeo**, **TypedPolling**, o **notificación**operación desde el adaptador. En otras palabras, el código recibe un mensaje de solicitud para estas operaciones del adaptador a través de un canal.  
  
 Los temas de esta sección proporcionan una introducción al uso del [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con el modelo de canal WCF.  
  
## <a name="wcf-channel-model-overview"></a>Información general del modelo de canal de WCF  
 Los clientes y servicios comunican intercambiando mensajes SOAP. El modelo de canal WCF es una abstracción de bajo nivel de este intercambio de mensajes. Proporciona tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que llama a una pila de canales e interfaces. Cada capa de la pila se compone de un canal y cada canal se crea a partir de un enlace WCF. En el nivel más bajo es el canal de transporte. El canal de transporte implementa el mecanismo de transporte subyacente entre un servicio y un cliente y presenta cada mensaje a las capas más elevadas (y, en última instancia, la aplicación consumidora) como un **System.ServiceModel.Message**. WCF **mensaje** clase es una abstracción de un mensaje SOAP. WCF proporciona varias interfaces de canal, llama a las formas del canal, que modelan el básica SOAP mensaje patrones de intercambio, como solicitud-respuesta o unidireccionales. Un transporte WCF enlace proporciona una implementación de uno o más formas de canal superior en capas se pueden usar para enviar y recibir mensajes. Para obtener más información sobre el modelo de canal WCF, vea [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace de transporte personalizado de WCF que expone una base de datos de SQL Server como un servicio WCF.  
  
## <a name="supported-channel-shapes-for-the-sql-server-adapter"></a>Admite las formas del canal para el adaptador de SQL Server  
 El adaptador implementa las siguientes formas de canal WCF:  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**). El **IRequestChannel** interfaz implementa el cliente de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IRequestChannel** para realizar operaciones para el que quiere usar una respuesta, por ejemplo, para realizar una selección de consulta en una tabla.  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**). Esta forma implementa el cliente de un intercambio de mensajes unidireccional. Puede usar un **IOutputChannel** para invocar una operación que no es necesario consumir una respuesta, por ejemplo, para llamar a un procedimiento que no tiene ningún parámetro de valor devuelto.  
  
  > [!IMPORTANT]
  >  Todas las llamadas subyacentes por el adaptador para el cliente de SQL Server son sincrónicas. Esto incluye las llamadas al cliente de SQL Server que son el resultado de invocar a través de las operaciones de un **IOutputChannel**. Cuando se usa un **IOutputChannel**, el adaptador descarta la respuesta recibida desde el cliente de SQL Server.  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**). Esta forma implementa el lado del servicio de un intercambio de mensajes unidireccional. Usa un **IInputChannel** para recibir mensajes para operaciones de entrada, como **sondeo** o **notificación**, desde el adaptador.  
  
  Al igual que cualquier enlace WCF, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa un patrón de fábrica para proporcionar canales al código de aplicación. Usa un **Microsoft.Adapters.SQLBinding** objeto para crear instancias de:  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>**  para proporcionar **IRequestChannel** canales que se puede usar para invocar operaciones de solicitud-respuesta en el adaptador.  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>**  para proporcionar **IOutputChannel** canales puede usar para invocar las operaciones unidireccionales en el adaptador.  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>**  para proporcionar **IInputChannel** canales que se puede usar para recibir mensajes para operaciones de entrada, como  **Sondeo** o **notificación**, desde el adaptador.  
  
### <a name="creating-messages-for-the-sql-server-database-adapter-in-the-wcf-channel-model"></a>Creación de mensajes para el adaptador de base de datos SQL Server en el modelo del canal de WCF  
 En WCF la **System.ServiceModel.Channels.Message** clase proporciona una memoria en representación de un mensaje SOAP. Crear un **mensaje** instancia invocando estático **Message.Create** método.  
  
 Hay dos partes importantes en el mensaje SOAP que debe especificar al crear un **mensaje** instancia para enviar a la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
- La acción del mensaje es una cadena que forma parte del encabezado del mensaje SOAP. La acción de mensaje identifica la operación que se debe invocar en la base de datos. La siguiente muestra la acción de mensaje especificada para invocar la operación de selección en la tabla de empleados: `TableOp/Select/dbo/Employee`.  
  
- El cuerpo del mensaje contiene los datos del parámetro para la operación. El cuerpo del mensaje se compone de XML con formato correcto que se corresponde con el esquema del mensaje esperado por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para la operación solicitada. El siguiente cuerpo del mensaje especifica una operación de selección en la tabla Employee (seleccionar * de empleado WHERE id_empleado = 10001).  
  
  ```  
  <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Columns>*</Columns>  
    <Query>where Employee_ID=10001</Query>  
  </Select>  
  
  ```  
  
  Para obtener información sobre la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] los esquemas de mensajes y las acciones para las operaciones de mensaje, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).  
  
  Esto **Create** método está sobrecargado y ofrece muchas opciones diferentes para proporcionar el cuerpo del mensaje. El código siguiente muestra cómo crear un **mensaje** instancia mediante el uso de un **XmlReader** para proporcionar el cuerpo del mensaje. En este código, el cuerpo del mensaje se lee desde un archivo.  
  
```  
XmlReader readerIn = XmlReader.Create("SelectInput.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "TableOp/Select/dbo/Employee",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  Debe proporcionar una acción del mensaje en su **mensaje** instancia. Normalmente, esto se realiza cuando el **mensaje** se crea la instancia.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)