---
title: "Información general sobre el modelo de canal WCF con el adaptador de Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3afd2a97-5734-4c25-87a3-702d8461898b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5317099b1a576c9dd4e0b13593c16f4ef3a6831
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter"></a>Información general sobre el modelo de canal WCF con el adaptador de Oracle E-Business Suite
Para invocar operaciones en el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], el código actúa como un cliente de WCF y envía las operaciones salientes al adaptador. En el modelo de canal WCF, el código invoca las operaciones en el adaptador mediante el envío de un mensaje de solicitud a través de un canal.  
  
 Para invocar operaciones de entrada, como la recepción de sondeo mensajes basados en datos cambian con el **sondeo** operación proporcionadas por el adaptador, el código actúa como un servicio WCF y recibe la operación de entrada procedentes del adaptador. En otras palabras, el código recibe un mensaje de solicitud desde el adaptador a través de un canal.  
  
 Los temas de esta sección proporcionan una introducción al uso de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con el modelo de canal WCF.  
  
## <a name="wcf-channel-model-overview"></a>Información general del modelo de canal de WCF  
 Los clientes y servicios se comunican mediante el intercambio de mensajes SOAP. El modelo de canal WCF es una abstracción de bajo nivel de este intercambio de mensajes. Proporciona interfaces y tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que se llama a una pila de canales. Cada nivel de la pila se compone de un canal y se crea cada canal de un enlace de WCF. En el nivel más bajo es el canal de transporte. El canal de transporte implementa el mecanismo de transporte subyacente entre un servicio y un cliente y presenta cada mensaje a las capas más elevadas (y, en última instancia, la aplicación que consume) como un **System.ServiceModel.Message**. WCF **mensaje** clase es una abstracción de un mensaje SOAP. WCF proporciona varias interfaces de canal, llamados a formas del canal, que modelan los básica SOAP mensaje patrones de intercambio, como solicitud-respuesta o unidireccional. Un transporte WCF enlace proporciona una implementación de uno o más formas del canal que coloque en una capa superior pueden usar para enviar y recibir mensajes. Para obtener más información sobre el modelo de canal WCF, vea "Introducción al modelo de canal" en [http://go.microsoft.com/fwlink/?LinkId=82614](http://go.microsoft.com/fwlink/?LinkId=82614).  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace de transporte personalizado de WCF que expone un artefacto de Oracle E-Business Suite como un servicio WCF.  
  
## <a name="supported-channel-shapes-for-the-oracle-e-business-suite-adapter"></a>Admite formas del canal para el adaptador de Oracle E-Business Suite  
 El adaptador implementa las siguientes formas de canal WCF:  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**). El **IRequestChannel** interfaz implementa el cliente de un intercambio de mensajes de solicitud y respuesta. Puede usar un **IRequestChannel** para realizar operaciones para el que desea utilizar una respuesta, por ejemplo, para realizar una instrucción SELECT consulta en una tabla de interfaz.  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**). Esta forma implementa el cliente de un intercambio de mensajes unidireccionales. Puede usar un **IOutputChannel** para invocar una operación para la que no es necesario utilizar una respuesta, por ejemplo, para llamar a un procedimiento que no tiene ningún parámetro de salida.  
  
    > [!IMPORTANT]
    >  Todas las llamadas subyacentes por el adaptador para el cliente de Oracle son sincrónicas. Esto incluye las llamadas al cliente de Oracle que son el resultado de las operaciones que se invoca en un **IOutputChannel**. Cuando se usa un **IOutputChannel**, el adaptador descarta la respuesta recibida desde el cliente de Oracle.  
  
-   **IInputChannel** (**System.ServiceModel.Channels.IInputChannel**). Esta forma implementa el lado del servicio de un intercambio de mensajes unidireccionales. Usa un **IInputChannel** para recibir mensajes entrantes desde el adaptador.  
  
 Al igual que cualquier enlace de WCF, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza un modelo de generador para proporcionar canales al código de la aplicación. Usa un **Microsoft.Adapters.OracleEBSBinding** objeto que se va a crear instancias de:  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel\>**  para proporcionar **IRequestChannel** canales puede usar para invocar operaciones de solicitud-respuesta en el adaptador.  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel\>**  para proporcionar **IOutputChannel** canales puede usar para invocar las operaciones unidireccionales en el adaptador.  
  
-   **System.ServiceModel.IChannelListener\<IInputChannel\>**  para proporcionar **IInputChannel** canales que se puede utilizar para recibir mensajes entrantes desde el adaptador.  
  
### <a name="creating-messages-for-the-oracle-enterprise-business-solution-in-the-wcf-channel-model"></a>Crear mensajes para la solución de negocio empresarial de Oracle en el modelo del canal de WCF  
 En WCF la **System.ServiceModel.Channels.Message** clase proporciona una memoria en representación de un mensaje SOAP. Crear un **mensaje** instancia invocando el método estático **Message.Create** método.  
  
 Hay dos partes importantes para el mensaje SOAP que debe especificar cuando se crea un **mensaje** instancia para enviar a la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
-   La acción de mensaje es una cadena que forma parte del encabezado del mensaje SOAP. La acción de mensaje identifica la operación que se debe invocar en Oracle E-Business Suite. La siguiente muestra la acción de mensaje especificada para invocar el **interfaz cliente** programa simultáneo en la **cuentas por cobrar** aplicación en Oracle E-Business Suite: `ConcurrentPrograms/AR/RACUST`.  
  
-   El cuerpo del mensaje contiene los datos del parámetro para la operación. El cuerpo del mensaje se compone de XML con formato correcto que se corresponde con el esquema del mensaje esperado por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para la operación solicitada. El cuerpo del mensaje siguiente especifica un mensaje de solicitud para invocar la **interfaz cliente** programa simultáneo.  
  
    ```  
    <RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
      <Description>Customer Interface Program</Description>  
      <StartTime></StartTime>  
      <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
      <ORG_ID>203</ORG_ID>  
    </RACUST>  
  
    ```  
  
 Para obtener información sobre la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] esquemas de mensajes y las acciones para las operaciones de mensajes, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).  
  
 El **Create** método está sobrecargado y ofrece muchas opciones diferentes para proporcionar el cuerpo del mensaje. El código siguiente muestra cómo crear un **mensaje** instancia mediante el uso de un **XmlReader** para proporcionar el cuerpo del mensaje. En este código, el cuerpo del mensaje se lee desde un archivo.  
  
```  
XmlReader readerIn = XmlReader.Create("ConcProgRequest.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "ConcurrentPrograms/AR/RACUST",  
    readerIn);  
```  
  
 WHERE, ConProgRequest.xml contiene el mensaje de solicitud.  
  
> [!IMPORTANT]
>  Debe proporcionar una acción de mensaje en su **mensaje** instancia. Esto se hace normalmente cuando la **mensaje** se crea la instancia.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)