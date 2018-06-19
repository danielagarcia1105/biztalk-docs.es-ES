---
title: Tipos de datos de objetos grandes en el adaptador de la base de datos de Oracle de streaming | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, support in the WCF service model
- streaming, support for
- streaming, support in BizTalk Server
- streaming, support in the WCF channel model
ms.assetid: c6cbe870-6794-4bf1-90c1-db65a242e8fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda4d99eb381321139e4ed493f119f9eaf21623e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22217916"
---
# <a name="streaming-large-object-data-types-in-oracle-database-adapter"></a>Transmisión por secuencias de tipos de datos de objetos grandes en el adaptador de la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con transmisión por secuencias para tipos de datos de objetos grandes (LOB) de Oracle. Con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se invocan las operaciones y las respuestas se devuelven mediante el intercambio de mensajes SOAP. Un cuerpo del mensaje SOAP se compone de los nodos XML.  
  
 Hay dos tipos de transmisión por secuencias de mensajes que son compatibles con el adaptador:  
  
-   **Transmisión por secuencias de nodo**. En el nodo streaming cada nodo se almacena en búfer por el adaptador antes de enviarlo a la base de datos de Oracle (o devuelve al cliente). Esto significa que, para un tipo de datos LOB, se lee el valor completo en un búfer.  
  
-   **Valor del nodo de transmisión por secuencias**. En el valor del nodo la transmisión por secuencias el valor real del nodo se puede transmitir en fragmentos entre la base de datos de Oracle y el cliente. Transmisión por secuencias de valor de nodo admite la transmisión por secuencias to-end de tipos de datos LOB entre el cliente de adaptador y la base de datos de Oracle.  
  
 Ambos modos de transmisión por secuencias se basan en la compatibilidad con transmisión por secuencias de nodo y transmisión por secuencias en mensajes de WCF en el valor de nodo. Por esta razón, transmisión por secuencias para tipos de LOB está estrechamente relacionado con cómo se crean y utilizados por el adaptador y una aplicación cliente de mensajes. Una de las consecuencias es que soporte técnico para los tipos de LOB de transmisión por secuencias no es el mismo en todos los modelos de programación.  
  
 Las secciones de este tema proporcionan:  
  
-   Información fundamental acerca de cómo se admite la transmisión por secuencias de mensajes en WCF y cómo se implementa el adaptador.  
  
-   Obtener información sobre cómo la transmisión por secuencias para tipos de datos LOB se admite cuando se usa el adaptador en cada modelo de programación.  
  
## <a name="streaming-fundamentals"></a>Conceptos básicos de transmisión por secuencias  
 La compatibilidad con streaming implementada por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es una combinación de:  
  
-   Compatibilidad de transmisión por secuencias de mensajes en WCF.  
  
-   Compatibilidad con la transmisión en la biblioteca de cliente de Oracle (ODP.NET).  
  
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
  
### <a name="streaming-support-in-the-oracle-client-library-odpnet"></a>Compatibilidad con la transmisión en la biblioteca de cliente de Oracle (ODP.NET)  
 ODP.NET admite la transmisión de la siguiente manera:  
  
-   Transmisión por secuencias solo se admite en tipos de datos LOB de Oracle.  
  
-   Para algunas operaciones de tabla (y ver), tipos de datos LOB se almacenan en búfer. Por lo tanto, no se admite ninguna transmisión por secuencias.  
  
### <a name="internal-message-handling-by-the-adapter"></a>Control por el adaptador de mensajes interna  
 El adaptador admite la transmisión de la siguiente manera:  
  
-   Extiende el adaptador **mensaje** para implementar una clase de mensaje personalizado, **Microsoft.Adapters.AdapterUtilities.AdapterMessage**. Crea un **AdapterMessage** para WCF todos los mensajes que proporciona al cliente adaptador; Esto incluye los mensajes de respuesta para todas las operaciones de salida y el mensaje de solicitud para la operación de POLLINGSTMT. Esto permite que el adaptador admitir la transmisión por secuencias para la operación ReadLOB proporcionando el valor de nodo un **XmlReader** que admita **ReadValueChunk** a los clientes de adaptador.  
  
-   El adaptador usa todos los mensajes recibidos del cliente mediante el uso de una implementación personalizada de **XmlDictionaryWriter**.  
  
-   El adaptador crea todos los mensajes que envía al cliente mediante el uso de una implementación personalizada de **XmlBodyWriter**, excepto para el mensaje de respuesta ReadLOB. (Esto incluye mensajes de respuesta para todas las operaciones de salida y el mensaje de solicitud para la operación de POLLINGSTMT).  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>Compatibilidad con la transmisión en el modelo del canal de WCF  
 En la tabla siguiente proporciona información detallada sobre cómo se admite la transmisión por secuencias en el modelo de canal WCF.  
  
|Operación|Transmisión por secuencias de nodo|Transmisión por secuencias en el valor de nodo|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|Operación de inserción de tabla|Compatible*|No se admite entre el adaptador y la base de datos de Oracle. Compatible entre el cliente y adapter.*|Transmisión por secuencias de valor de nodo-to-end no se admite porque los valores de columnas LOB se almacenan en búfer por ODP.NET y, a continuación, se lleva a cabo la inserción. Sin embargo, es posible para las columnas LOB, si el cliente crea el mensaje con el valor del nodo entre el cliente y el adaptador de transmisión por secuencias un **BodyWriter**.|  
|Operación de selección de tabla|Compatible|Compatible|El adaptador utiliza un **BodyWriter** para crear el mensaje de respuesta. Si el cliente consume el mensaje mediante un **XmlDictionaryWriter**, se produce la transmisión por secuencias para las columnas LOB en el valor de nodo.|  
|Operación de actualización de tabla|Compatible|No se admite entre el adaptador y la base de datos de Oracle. Compatible entre el cliente y el adaptador.|Transmisión por secuencias de valor de nodo-to-end no se admite porque los valores de columnas LOB se almacenan en búfer por ODP.NET y, a continuación, se lleva a cabo la actualización. Sin embargo, es posible para las columnas LOB entre el cliente y el adaptador de transmisión por secuencias en el valor de nodo si el cliente crea el mensaje con un **BodyWriter**.|  
|Operación de eliminación de tabla|Compatible|No se admite entre el adaptador y la base de datos de Oracle. Compatible entre el cliente y el adaptador.|Transmisión por secuencias de valor de nodo-to-end no se admite porque los valores de columnas LOB se almacenan en búfer por ODP.NET y, a continuación, se lleva a cabo la eliminación. Sin embargo, es posible para las columnas LOB entre el cliente y el adaptador de transmisión por secuencias en el valor de nodo si el cliente crea el mensaje con un **BodyWriter**.|  
|Operación de tabla ReadLOB|Compatible|Compatible|La operación de ReadLOB se ha diseñado principalmente para columnas de datos LOB de flujo en el modelo de servicio WCF. En el modelo de canal WCF, si el cliente consume el mensaje mediante un **XmlReader** (invocando la **GetReaderAtBodyContents** método en el mensaje de respuesta), valor de nodo de extremo a extremo de streaming se produce. Esto es porque el adaptador devuelve un **XmlReader** que admita **ReadValueChunk** llama para el mensaje de respuesta ReadLOB. Sin embargo, se recomienda que no realice la operación de ReadLOB desde el modelo de canal WCF. Puede usar una operación Select o una operación SQLEXECUTE en su lugar.|  
|Operación de tabla UpdateLOB|Compatible|Compatible|El adaptador utiliza un **XmlDictionaryWriter** para consumir el mensaje de solicitud. Si el cliente utiliza un **BodyWriter** para crear el mensaje de solicitud, se produce la transmisión por secuencias de datos LOB de valor de nodo-to-end.|  
|Operación SQLEXECUTE|Compatible|Compatible|El adaptador utiliza un **BodyWriter** para crear el mensaje de respuesta.<br /><br /> Si el cliente utiliza un **XmlDictionaryWriter** para consumir el mensaje de respuesta, se produce la transmisión por secuencias para los datos de LOB de valor de nodo-to-end.<br /><br /> Transmisión por secuencias de valor de nodo-to-end no es compatible con el mensaje de solicitud porque el adaptador debe almacenar en búfer todos los operandos antes de que puede invocar la operación en la base de datos de Oracle.|  
|Operación de procedimiento y la función almacenado|Compatible|Compatible|El adaptador utiliza un **BodyWriter** para crear el mensaje de respuesta.<br /><br /> Si el cliente utiliza un **XmlDictionaryWriter** para consumir el mensaje de respuesta, se produce la transmisión por secuencias para los datos de LOB de valor de nodo-to-end. (Esto significa que se admite la transmisión por secuencias para horizontal y en procedimiento y función de los parámetros OUT en el mensaje de respuesta.)<br /><br /> Transmisión por secuencias de valor de nodo-to-end no es compatible con el mensaje de solicitud porque el adaptador debe almacenar en búfer todos los operandos antes de que puede invocar la operación en la base de datos de Oracle.|  
|Operación POLLINGSTMT|Compatible|Compatible|El adaptador utiliza un **BodyWriter** para crear el mensaje de solicitud POLLINGSTMT. Si el cliente consume el mensaje mediante un **XmlDictionaryWriter**, a continuación, se produce la transmisión por secuencias para las columnas LOB en el valor de nodo.|  
  
 Para obtener información sobre cómo implementar datos LOB de transmisión por secuencias en el código cuando se usa el modelo de canal WCF, vea [Streaming Oracle base de datos LOB datos tipos con el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>Compatibilidad con la transmisión en el modelo de servicio WCF  
 Serializar y deserializar entre la representación XML de un mensaje y la representación de objeto de código administrado de ese mensaje requieren escribir y leer el mensaje completo en la memoria. Por este motivo, ni de transmisión por secuencias de nodo ni de transmisión por secuencias en el valor de nodo se admite para la mayoría de las operaciones.  
  
 La única excepción a esto es la operación de ReadLOB. Esta operación se implementa específicamente para admitir la transmisión por secuencias to-end para leer columnas LOB de tablas y vistas en el modelo de servicio WCF.  
  
## <a name="streaming-support-in-biztalk-server"></a>Compatibilidad con la transmisión en BizTalk Server  
 En la tabla siguiente proporciona información detallada sobre cómo se admite la transmisión por secuencias en BizTalk Server. (Todas las referencias al "adaptador" se refieren a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; el adaptador WCF-Custom siempre se conoce por su nombre completo de esta tabla.)  
  
|Operación|Transmisión por secuencias de nodo|Transmisión por secuencias en el valor de nodo|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|Operación de inserción de tabla|Compatible*|No se admite entre el adaptador y la base de datos de Oracle; Sin embargo, se transmite por secuencias de datos entre BizTalk Server y el adaptador.|Transmisión por secuencias de valor de nodo-to-end no se admite porque los valores de columnas LOB se almacenan en búfer por ODP.NET y, a continuación, se lleva a cabo la inserción. Sin embargo, se admite entre BizTalk Server y el adaptador de transmisión por secuencias en el valor de nodo para tipos de datos LOB porque el adaptador de WCF-Custom crea el mensaje con un **BodyWriter**.|  
|Operación de selección de tabla|Compatible|Compatible|El adaptador de WCF-Custom utiliza un **XmlDictionaryWriter** para consumir el mensaje de respuesta, por lo que se admite la transmisión por secuencias para tipos de LOB de valor de nodo-to-end.|  
|Operación de actualización de tabla|Compatible|No se admite entre el adaptador y la base de datos de Oracle; Sin embargo, se transmite por secuencias de datos entre BizTalk Server y el adaptador.|Transmisión por secuencias de valor de nodo-to-end no se admite porque los valores de columnas LOB se almacenan en búfer por ODP.NET y, a continuación, se lleva a cabo la actualización. Sin embargo, se admite entre BizTalk Server y el adaptador de transmisión por secuencias en el valor de nodo para tipos de datos LOB porque el adaptador de WCF-Custom crea el mensaje con un **BodyWriter**.|  
|Operación de eliminación de tabla|Compatible|No se admite entre el adaptador y la base de datos de Oracle; Sin embargo, se transmite por secuencias de datos entre BizTalk Server y el adaptador.|Transmisión por secuencias de valor de nodo-to-end no se admite porque los valores de columnas LOB se almacenan en búfer por ODP.NET y, a continuación, se lleva a cabo la eliminación. Sin embargo, se admite entre BizTalk Server y el adaptador de transmisión por secuencias en el valor de nodo para tipos de datos LOB porque el adaptador de WCF-Custom crea el mensaje con un **BodyWriter**.|  
|Operación de tabla ReadLOB|La operación de ReadLOB no es compatible con BizTalk Server.|La operación de ReadLOB no es compatible con BizTalk Server.|La operación de ReadLOB no es compatible con BizTalk Server. Utilice en su lugar la operación de selección o una operación SQLEXECUTE.|  
|Operación de tabla UpdateLOB|Compatible|Compatible|El adaptador de WCF-Custom utiliza un **BodyWriter** para crear el mensaje de solicitud, por lo que se admite la transmisión por secuencias para tipos de datos LOB de valor de nodo-to-end.|  
|Operación SQLEXECUTE|Compatible|Compatible|El adaptador de WCF-Custom utiliza un **XmlDictionaryWriter** para consumir el mensaje de respuesta, por lo que se admite la transmisión por secuencias para tipos de datos LOB en el mensaje de respuesta de valor de nodo-to-end.<br /><br /> Transmisión por secuencias de valor de nodo-to-end no es compatible con el mensaje de solicitud porque el adaptador debe almacenar en búfer todos los operandos antes de que puede invocar la operación en la base de datos de Oracle.|  
|Operación de procedimiento y la función almacenado|Compatible|Compatible|El adaptador de WCF-Custom utiliza un **XmlDictionaryWriter** para consumir el mensaje de respuesta, por lo que se admite la transmisión por secuencias para tipos de datos LOB en el mensaje de respuesta de valor de nodo-to-end. (Esto significa que se admite la transmisión por secuencias para horizontal y en procedimiento y función de los parámetros OUT en el mensaje de respuesta.)<br /><br /> Transmisión por secuencias de valor de nodo-to-end no es compatible con el mensaje de solicitud porque el adaptador debe almacenar en búfer todos los operandos antes de que puede invocar la operación en la base de datos de Oracle.|  
|Operación POLLINGSTMT|Compatible|Compatible|El adaptador de WCF-Custom utiliza un **XmlDictionaryWriter** consumir el mensaje de solicitud (entrante), por lo que se admite la transmisión por secuencias para tipos de datos LOB de valor de nodo-to-end.|  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)