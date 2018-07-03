---
title: Información general del modelo del canal WCF con el adaptador de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3afd2a97-5734-4c25-87a3-702d8461898b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcabe727b720c2319b253517ea78c573242df76c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987437"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter"></a>Información general del modelo del canal WCF con el adaptador de Oracle E-Business Suite
Para invocar operaciones en el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], el código actúa como un cliente de WCF y envía las operaciones salientes al adaptador. En el modelo de canal WCF, el código invoca las operaciones en el adaptador mediante el envío de un mensaje de solicitud a través de un canal.  
  
 Para invocar operaciones de entrada, como la recepción de sondeo mensajes basados en datos cambian con el **sondeo** operación proporcionada por el adaptador, el código actúa como un servicio WCF y recibe la operación entrante del adaptador. En otras palabras, el código recibe un mensaje de solicitud del adaptador a través de un canal.  
  
 Los temas de esta sección proporcionan una introducción al uso del [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con el modelo de canal WCF.  
  
## <a name="wcf-channel-model-overview"></a>Información general del modelo de canal de WCF  
 Los clientes y servicios comunican intercambiando mensajes SOAP. El modelo de canal WCF es una abstracción de bajo nivel de este intercambio de mensajes. Proporciona tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que llama a una pila de canales e interfaces. Cada capa de la pila se compone de un canal y cada canal se crea a partir de un enlace WCF. En el nivel más bajo es el canal de transporte. El canal de transporte implementa el mecanismo de transporte subyacente entre un servicio y un cliente y presenta cada mensaje a las capas más elevadas (y, en última instancia, la aplicación consumidora) como un **System.ServiceModel.Message**. WCF **mensaje** clase es una abstracción de un mensaje SOAP. WCF proporciona varias interfaces de canal, llama a las formas del canal, que modelan el básica SOAP mensaje patrones de intercambio, como solicitud-respuesta o unidireccionales. Un transporte WCF enlace proporciona una implementación de uno o más formas de canal superior en capas se pueden usar para enviar y recibir mensajes. Para obtener más información sobre el modelo de canal WCF, vea "Información general del modelo de canal" en [ http://go.microsoft.com/fwlink/?LinkId=82614 ](http://go.microsoft.com/fwlink/?LinkId=82614).  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace de transporte personalizado de WCF que expone un artefacto de Oracle E-Business Suite como un servicio WCF.  
  
## <a name="supported-channel-shapes-for-the-oracle-e-business-suite-adapter"></a>Admite las formas del canal para el adaptador para Oracle E-Business Suite  
 El adaptador implementa las siguientes formas de canal WCF:  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**). El **IRequestChannel** interfaz implementa el cliente de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IRequestChannel** para realizar operaciones para el que quiere usar una respuesta, por ejemplo, para realizar una selección de consulta en una tabla de interfaz.  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**). Esta forma implementa el cliente de un intercambio de mensajes unidireccional. Puede usar un **IOutputChannel** para invocar una operación que no es necesario consumir una respuesta, por ejemplo, para llamar a un procedimiento que no tiene ningún parámetro OUT.  
  
  > [!IMPORTANT]
  >  Todas las llamadas subyacentes por el adaptador para el cliente de Oracle son sincrónicas. Esto incluye las llamadas al cliente de Oracle que son el resultado de invocar a través de las operaciones de un **IOutputChannel**. Cuando se usa un **IOutputChannel**, el adaptador descarta la respuesta recibida desde el cliente de Oracle.  
  
- **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**). Esta forma implementa el lado del servicio de un intercambio de mensajes unidireccional. Usa un **IInputChannel** para recibir los mensajes entrantes desde el adaptador.  
  
  Al igual que cualquier enlace WCF, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa un patrón de fábrica para proporcionar canales al código de aplicación. Usa un **Microsoft.Adapters.OracleEBSBinding** objeto para crear instancias de:  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>**  para proporcionar **IRequestChannel** canales que se puede usar para invocar operaciones de solicitud-respuesta en el adaptador.  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>**  para proporcionar **IOutputChannel** canales puede usar para invocar las operaciones unidireccionales en el adaptador.  
  
- **System.ServiceModel.IChannelListener\<IInputChannel\>**  para proporcionar **IInputChannel** canales que se puede usar para recibir los mensajes entrantes desde el adaptador.  
  
### <a name="creating-messages-for-the-oracle-enterprise-business-solution-in-the-wcf-channel-model"></a>Creación de mensajes para la solución empresarial Oracle en el modelo del canal de WCF  
 En WCF la **System.ServiceModel.Channels.Message** clase proporciona una memoria en representación de un mensaje SOAP. Crear un **mensaje** instancia invocando estático **Message.Create** método.  
  
 Hay dos partes importantes en el mensaje SOAP que debe especificar al crear un **mensaje** instancia para enviar a la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
- La acción del mensaje es una cadena que forma parte del encabezado del mensaje SOAP. La acción de mensaje identifica la operación que debe invocarse en Oracle E-Business Suite. La continuación muestra la acción de mensaje especificada para invocar el **interfaz cliente** programa simultáneo en la **cuentas por cobrar** aplicación en Oracle E-Business Suite: `ConcurrentPrograms/AR/RACUST`.  
  
- El cuerpo del mensaje contiene los datos del parámetro para la operación. El cuerpo del mensaje se compone de XML con formato correcto que se corresponde con el esquema del mensaje esperado por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para la operación solicitada. El cuerpo del mensaje siguiente especifica un mensaje de solicitud para invocar la **interfaz cliente** programa simultáneo.  
  
  ```  
  <RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
    <Description>Customer Interface Program</Description>  
    <StartTime></StartTime>  
    <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
    <ORG_ID>203</ORG_ID>  
  </RACUST>  
  
  ```  
  
  Para obtener información sobre la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] los esquemas de mensajes y las acciones para las operaciones de mensaje, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).  
  
  El **Create** método está sobrecargado y ofrece muchas opciones diferentes para proporcionar el cuerpo del mensaje. El código siguiente muestra cómo crear un **mensaje** instancia mediante el uso de un **XmlReader** para proporcionar el cuerpo del mensaje. En este código, el cuerpo del mensaje se lee desde un archivo.  
  
```  
XmlReader readerIn = XmlReader.Create("ConcProgRequest.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "ConcurrentPrograms/AR/RACUST",  
    readerIn);  
```  
  
 donde, ConProgRequest.xml contiene el mensaje de solicitud.  
  
> [!IMPORTANT]
>  Debe proporcionar una acción del mensaje en su **mensaje** instancia. Normalmente, esto se realiza cuando el **mensaje** se crea la instancia.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)