---
title: Procesar el mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing
- messages, pipelines
- routing, about routing
- adapters, about adapters
- routing, message types
- processing, messages
- messages, processing
- routing
- messages, routing
- pipelines, about pipelines
- message types
- messages, message types
- messages, adapters
ms.assetid: e6d1f969-20c9-41f6-85cb-46cf92656348
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49329e23127f051a593596955f808cc879dd76f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987789"
---
# <a name="processing-the-message"></a>Procesar el mensaje
Todos los componentes descritos hasta el momento desempeñan una función en el procesamiento de mensajes, pues se transmiten a través de BizTalk Server. En esta sección se ofrece una descripción más detallada de la forma en la que interactúan estos componentes desde el punto de vista de sus funciones desde que se recibe un mensaje. La siguiente ilustración muestra las partes de un puerto de recepción, así como la forma en la que se transmite un mensaje a través del proceso de recepción.  
  
 Un *puerto de recepción* está formado por una o varias ubicaciones de recepción, y puede contener, o no, asignaciones. Las asignaciones son hojas de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT) que se utilizan para transformar mensajes XML con una estructura o formato específico a otra, y, en el proceso de recepción, para ajustar mensajes a un formato interno. Las ubicaciones de recepción controlan los extremos en los que se reciben los mensajes. Una ubicación de recepción consiste en la configuración de un extremo de un adaptador de recepción y de una canalización de recepción.  
  
 ![Procesamiento y estructura de puerto de recepción](../core/media/arch-message-processing.gif "arch_message_processing")  
  
## <a name="the-role-of-the-adapter"></a>El rol del adaptador  
 El adaptador de recepción inicia el proceso de recepción de mensajes mediante la lectura de una secuencia de datos y la creación de un mensaje. Por ejemplo, el adaptador de archivo observa que se ha colocado un archivo en su ubicación configurada y lo lee en una secuencia. El adaptador crea un mensaje (una implementación de la interfaz Microsoft.BizTalk.Message.Interop.IBaseMessage), le agrega una parte (una implementación de la interfaz Microsoft.BizTalk.Message.Interop.IBasePart) y proporciona la secuencia de datos como el contenido de esa parte.  
  
 Asimismo, el adaptador escribe y promociona en el mensaje propiedades de contexto relacionadas con la ubicación, el tipo de adaptador y otros elementos relacionados con él. Después de haber creado el mensaje y su contexto, el adaptador transmite el mensaje al Gestor extremo. El mensaje se procesa a través de la canalización de recepción, configurada para la ubicación de recepción. Después de que la canalización ha procesado el mensaje, se puede utilizar una asignación para transformar el mensaje en el formato deseado antes de que el Gestor extremo lo publique con el Agente de mensaje.  
  
## <a name="the-role-of-the-pipeline"></a>El rol de la canalización  
 Mientras que el adaptador es el encargado de crear el mensaje inicial, la mayor parte del procesamiento que se realiza sobre un mensaje recibido ocurre en la canalización de recepción. El procesamiento de la canalización se ocupa del contenido del mensaje y de su contexto. El contenido del mensaje se realiza por regla general en las fases de validación, desensamblado y descodificación, mientras que el contexto del mensaje se lleva a cabo en todas las fases. No obstante, una canalización no tiene que actuar necesariamente en el contenido o en el contexto. Por ejemplo, la canalización de paso predeterminada no posee componentes configurados y no procesa el contenido ni el contexto del mensaje. Para facilitar la tarea, este documento se centra en los componentes de desensamblado, pues éstos son los que tienen mayor influencia en el enrutamiento de mensajes.  
  
 La tarea del *desensamblador* consiste en procesar un mensaje entrante de un adaptador, desensamblarlo en varios mensajes y analizar sus datos. Cuando un mensaje entrante tiene muchos mensajes más pequeños, esto se conoce como un *intercambio*. El desensamblador de archivos sin formato y el desensamblador XML controlan los intercambios habilitando a los programadores para configurar el contenido que rodea al núcleo del mensaje (el encabezado y el esquema de delimitación en el desensamblador de archivos sin formato, y el esquema de sobres en el desensamblador XML) y el contenido del cuerpo del mensaje, que será repetitivo con toda probabilidad. Además, los dos desensambladores analizan el mensaje original en contenido XML. Un desensamblador personalizado no tiene que analizar necesariamente el contenido en XML si no es necesario continuar el procesamiento de XML en BizTalk Server. Un escenario de ejemplo puede incluir una situación de enrutamiento sencillo en la que los mensajes que entran al sistema por una ubicación de recepción determinada se envían a un puerto de envío específico sin que se produzcan asignaciones ni procesamientos basados en XML.  
  
## <a name="routing-with-the-message-type"></a>Enrutar con el tipo de mensaje  
 Una de las propiedades de mensaje más utilizadas en el enrutamiento es el tipo de mensaje. Cuando un programador crea un esquema para definir la estructura de los mensajes, este esquema define el tipo de mensaje para esos mensajes. El tipo está determinado por el nodo raíz y el espacio de nombres de la definición del esquema. Por ejemplo, un documento XML con el siguiente aspecto tendría un tipo de mensaje http://tempuri.org/samples/MessageType#Message  
  
```  
<Message xmlns=http://tempuri.org/samples/MessageType>  
<SomeOtherElement type="sample"/>  
</Message>  
```  
  
 Para utilizar el tipo de mensaje en el enrutamiento, debe estar promocionado en el contexto. Los desensambladores se utilizan para promocionar este valor en el contexto del mensaje y en los componentes de canalización con el conocimiento más específico de la estructura del mensaje. Los desensambladores XML y de archivos sin formato promocionan el tipo de mensaje a medida que procesan los mensajes. Ningún desensamblador personalizado debe promocionar esta propiedad para garantizar el enrutamiento adecuado.  
  
 Es importante tener en cuenta que el tipo de mensaje no es una propiedad obligatoria en los mensajes. Como se ha mencionado anteriormente, las partes de un mensaje pueden ser datos binarios, y no tienen que disponer de un esquema que defina su estructura. Por regla general, este tipo de parte de mensaje se transmite a través de BizTalk Server sin necesidad de procesamiento adicional, pese a que los componentes de canalización personalizados, los adaptadores o el código de las orquestaciones puedan interactuar con estas partes.  
  
 Los componentes de canalización, como los adaptadores, también escriben y promocionan propiedades en el contexto del mensaje. De hecho, los componentes de canalización constituyen el mecanismo más utilizado por los programadores para obtener propiedades en el contexto del mensaje. Los programadores crean esquemas y pueden promocionar propiedades en el esquema. Esta información se almacena en el esquema en forma de anotaciones y los componentes de canalización pueden hacer uso de ellas. Todos los componentes de ensamblado y desensamblado integrados (archivos sin formato, XML y BizTalk Framework) utilizan el esquema de documento para recuperar información sobre las propiedades que se van a promocionar. Gracias al empleo de la instrucción del lenguaje de rutas XML (XPath) de las anotaciones, el desensamblador conoce la ubicación de los elementos del documento que se van a promocionar. Durante el proceso de transmisión a través del documento, el desensamblador encuentra aquellos elementos que coinciden con una de las instrucciones XPath, y promociona o escribe el valor en el contexto como proceda.  
  
 También es posible escribir los componentes de canalización personalizados para controlar las propiedades que se obtienen en el contexto de los datos arbitrarios de un mensaje enviado o recibido. Con el fin de promocionar una propiedad en el contexto y utilizarla en el enrutamiento, que es lo que supuestamente se persigue con la promoción de valores, es posible crear un esquema de propiedades con una definición para la propiedad e implementarlo en BizTalk Server. Antes de definir un esquema de propiedades para que lo utilicen los componentes personalizados, debe conocer los distintos tipos de propiedades promocionadas. Las propiedades promocionadas definidas en un esquema de propiedades pueden ser de dos tipos de base:  
  
- [Microsoft.XLANGs.BaseTypes.MessageContextPropertyBase](http://msdn.microsoft.com/library/microsoft.xlangs.basetypes.messagecontextpropertybase.aspx) o  
  
- [Microsoft.XLANGs.BaseTypes.MessageDataPropertyBase](http://msdn.microsoft.com/library/microsoft.xlangs.basetypes.messagedatapropertybase.messagedatapropertybase.aspx)  
  
  Un propiedad con el tipo de base MessageDataPropertyBase indica que su valor procede del contenido del mensaje. Éste es el valor predeterminado en las propiedades definidas en esquemas de propiedades y representa el empleo más habitual. MessageContextPropertyBase indica una propiedad diseñada para formar parte del contexto del mensaje, pero no tiene que proceder directamente de los datos del mensaje. Con frecuencia, las propiedades con el tipo de base MessageContextPropertyBase se promocionan mediante adaptadores y desensambladores, e incluyen propiedades comunes como, por ejemplo, tipo de mensaje y tipo de adaptador.  
  
  Es importante comprender los distintos tipos de base y utilizarlos correctamente al definir propiedades. Una de las repercusiones más significativas se produce al obtener acceso a las propiedades de contexto de un mensaje en una orquestación. Si una propiedad se identifica como MessageDataPropertyBase, el Diseñador de orquestaciones analiza el esquema del mensaje que se recibe y se asegura de que define una propiedad promocionada coincidente. Si no existe ninguna propiedad en el esquema que se vincula a la propiedad promocionada en cuestión, el Diseñador no le permite obtener acceso a ella. Por otro lado, si la propiedad está definida como MessageContextPropertyBase, el tipo de mensaje no tiene importancia y es posible obtener acceso a la propiedad.  
  
  En las canalizaciones personalizadas, el mecanismo encargado de promocionar o escribir propiedades en el contexto actúa de una forma similar. Para escribir propiedades, se utiliza una llamada al método IBaseMessageContext.Write para situar el valor en el contexto. Por el contrario, en las propiedades promocionadas únicamente se utiliza el método IBaseMessageContext.Promote. Todos estos métodos adoptan un nombre de propiedad, un espacio de nombres y un valor. En las propiedades promocionadas, el nombre y el espacio de nombres equivalen al de la propiedad definida en el esquema de propiedades. Además, el acceso a ellos resulta mucho más sencillo, pues puede llevarse a cabo haciendo referencia al ensamblado del esquema de propiedades y utilizando las propiedades de la clase que se ha creado para la propiedad. Los campos distintivos utilizan un espacio de nombres común, http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields, y la expresión XPath que se usa para recuperar el valor se utiliza normalmente como el nombre.  
  
  El código siguiente muestra un ejemplo de la escritura y la promoción de propiedades en el contexto. Tenga en cuenta que, en este ejemplo, un campo distintivo se está escribiendo en el contexto. Esto solo resulta de utilidad en aquellas orquestaciones en las que el esquema de mensaje identifica los campos distintivos para que el Diseñador de orquestaciones conozca el campo. Puede servir para escribir propiedades en el contexto a fin de que las utilicen otros componentes de canalización de envío o recepción.  
  
```  
//create an instance of the property to be promoted  
SOAP.MethodName methodName = new SOAP.MethodName();  
  
//call the promote method on the context using the property class for name   
//and namespace  
pInMsg.Context.Promote(methodName.Name.Name, methodName.Name.Namespace,   
"theSOAPMethodName");  
  
//write a distinguished field to the context  
pInMsg.Context.Write("theDistinguishedProperty",   
"http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields",   
"theDistinguishedValue");  
```  
  
 Tenga en cuenta las recomendaciones siguientes a la hora de escribir o promocionar valores en el contexto:  
  
- Si escribe un valor en el contexto con el mismo nombre y espacio de nombres que los que se utilizaron con anterioridad para promocionar la propiedad, no se podrá promocionar de nuevo la propiedad. Básicamente, la escritura sobrescribe la promoción.  
  
- Si escribe un valor nulo en el contexto, el valor se elimina, pues no están permitidas las propiedades con valor nulo.  
  
- Las propiedades promocionadas no pueden poseer más de 256 caracteres de longitud, mientras que en las propiedades escritas no existe limitación.  
  
  Las propiedades promocionadas se utilizan en el enrutamiento de mensajes y poseen un tamaño limitado por motivos de eficacia en su comparación y almacenamiento. Aunque las propiedades escritas no poseen limitaciones en el tamaño, el empleo de valores excesivamente grandes en el contexto puede afectar al rendimiento, ya que pueden procesarse y transmitirse con el mensaje.  
  
  Cuando un mensaje está listo para enviarse desde BizTalk Server, realiza un procesamiento complementario en el puerto de envío. Las asignaciones se aplican a los mensajes antes de que se ejecute la canalización de envío, lo que hace posible la transformación del mensaje en un formato específico del cliente o la aplicación. Esto último se lleva a cabo antes de que la canalización lo procese y el adaptador lo envíe. En la canalización de envío, las propiedades se degradan en el mensaje desde el contexto, en lugar de promocionarse en el contexto del mensaje.  
  
  ![Puerto de envío y proceso de canalización de envío](../core/media/arch-message-processing-2.gif "arch_message_processing-2")  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura en tiempo de ejecución](../core/runtime-architecture.md)   
 [Cómo procesa BizTalk Server los mensajes de gran tamaño](../core/how-biztalk-server-processes-large-messages.md)