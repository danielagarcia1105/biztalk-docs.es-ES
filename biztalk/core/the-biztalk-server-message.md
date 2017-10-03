---
title: Mensaje de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, properties
- messages, about messages
ms.assetid: 6048c191-b495-4fdc-b547-e3e322340a49
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4fd150a0b93cac10c4d1f79a526846629c62e67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-biztalk-server-message"></a>Mensaje de BizTalk Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]es, en esencia, un motor de control de mensajes. Para conocer los detalles de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es importante comprender los mensajes y cómo se representan, almacenan y procesan en BizTalk Server. Los detalles de cómo trabaja BizTalk Server con los mensajes son más fáciles de comprender una vez que se ha entendido qué es un mensaje.  
  
 Cada mensaje de BizTalk Server se considera un mensaje de varias partes y se compone de cero o más partes. Cada mensaje con una o varias partes tiene una de estas partes identificada como parte del cuerpo. Cada parte consta de un fragmento binario de datos que se puede representar como un documento XML, un archivo sin formato, una clase de .NET serializada u otra secuencia binaria de datos. La parte del cuerpo del mensaje se usa para identificar el tipo del mensaje que se puede usar para enrutamiento.  
  
 Un concepto muy importante entender es que todos los mensajes son inmutables en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto significa que, una vez construido, un mensaje no se puede cambiar. Un mensaje se considera construido cuando se ha colocado en la base de datos de cuadro de mensajes. Los cambios que se deban realizar en un mensaje requieren que se cree un mensaje nuevo y se utilice a partir de ese punto. Esto es especialmente claro en el Diseñador de orquestaciones, donde las reglas de compilación obligan a seguir instrucciones estrictas para construir un mensaje antes de usarlo y no permiten modificar el mensaje fuera de su bloque de construcción. Si necesita cambiar el mensaje, debe crear un nuevo bloque de construcción que cree un mensaje del mismo tipo, copiar el mensaje original en el nuevo mensaje y realizar los cambios en el mensaje nuevo antes de dejar el bloque de construcción.  
  
## <a name="message-properties"></a>Propiedades del mensaje  
 Además de las partes que componen un mensaje, cada mensaje en el sistema tiene un conjunto de propiedades que lo acompañan en lo que se conoce como el *contexto del mensaje*. Estas propiedades pueden ser valores extraídos del mensaje o relacionados con él. Por ejemplo, los adaptadores ponen propiedades en el contexto relacionadas con la recepción de un mensaje, como la ubicación en la que se recibió el mensaje y el tipo de adaptador que se usó para recibir el mensaje. O bien se pueden escribir propiedades al contexto de o *promueve* en el contexto. La diferencia entre estas dos opciones es que las propiedades promocionadas se pueden usar como criterios en el enrutamiento de un mensaje mientras que las propiedades escritas no.  
  
 Este concepto de escribir o promocionar valores en el contexto está relacionado, aunque no es el mismo, con el concepto de promocionar propiedades en el Editor de BizTalk. En el Editor de BizTalk, se puede marcar un elemento o un atributo de un esquema como una propiedad promocionada o un campo distintivo. Los elementos marcados con anotaciones PropertyField en el esquema de mensaje conducirán al desensamblador de canalización a poner una propiedad Promocionada en el contexto. Los elementos marcados con anotaciones DistinguishedField en el esquema de mensaje conducirán al desensamblador de canalización a poner una propiedad Written en el contexto.  
  
 El diseño de las propiedades promocionadas comenzó con el diseño de *correlación de mensajes*: la capacidad para relacionar un mensaje que se recibe a una instancia de orquestación ya se está ejecutando. Para la correlación es necesario definir una propiedad o un conjunto de propiedades que proporcione el vínculo entre los mensajes y la orquestación. Por ejemplo, en un proceso de compra, debe correlacionar los mensajes basados en PurchaseOrderID. Sin embargo, en muchos casos empresariales, el nombre del campo o atributo concreto de los mensajes puede no coincidir. Un esquema de pedido puede tener un elemento denominado POId, mientras que la factura adjunta puede tener un elemento denominado OrderID. Para correlacionar mensajes por una propiedad con nombre como PurchaseOrderID en esta situación, el programador debe poder extraer del origen del valor el nombre de la propiedad por la que se va a crear la correlación. Los esquemas de propiedad admiten esta extracción.  
  
 A *esquema de propiedad* le permite definir las propiedades promocionadas en una ubicación común y pídales que hace referencia a otros esquemas. Al igual que otros esquemas, un esquema de propiedades tiene un espacio de nombres pero, a diferencia de otros esquemas, solo puede tener elementos definidos (es decir, ni registros ni atributos). Cada elemento que se define en el esquema de propiedades tiene un nombre y un tipo. Puesto que puede ser necesario hacer referencia al esquema de propiedades en más de un esquema y puesto que la información del esquema de propiedades debe estar disponible para los componentes en tiempo de ejecución, se debe implementar el esquema de propiedades en BizTalk Server como los demás esquemas. Además de los pasos normales de implementación de esquemas, se extrae información de las propiedades promocionadas y se almacena en la tabla bts_documentSpec de la base de datos de administración.  
  
 Una vez creado un esquema de propiedades, elementos y atributos con el mismo tipo (por ejemplo. valor entero) se puede promocionar como una de las propiedades con nombre en el esquema de propiedades.  
  
 **Para completar el caso del ejemplo anterior, un programador realizaría los pasos siguientes para definir la propiedad compartida necesaria para la correlación.**  
  
1.  Crear un esquema de propiedades y definir un elemento de tipo xs:int denominado PurchaseOrderId.  
  
2.  Crear un esquema PurchaseOrder y agregar un elemento o atributo de tipo xs:int denominado POId.  
  
3.  Con el comando Mostrar promociones en el Editor de BizTalk, el programador agrega el campo POId a la lista de propiedades promocionadas e indica que se debe promocionar como la propiedad PurchaseOrderId definida en el esquema de propiedades seleccionando la propiedad denominada PurchaseOrderId en la lista.  
  
4.  Crear un esquema Invoice y agregar un elemento o atributo de tipo xs:int denominado OrderId.  
  
5.  Con el comando Mostrar promociones del Editor de BizTalk, el programador agrega el campo OrderId a la lista de propiedades promocionadas e indica que se debe promocionar como la propiedad PurchaseOrderId definida en el esquema de propiedades seleccionando la propiedad denominada PurchaseOrderId en la lista.  
  
 Ahora que existe esta definición en los esquemas de documento, los componentes de canalización pueden promocionar correctamente OrderId y POId como la propiedad con nombre PurchaseOrderID para poder utilizarla para enrutamiento y correlación. Para obtener información más detallada acerca de este proceso de promoción, consulte el tema "Procesamiento de mensajes" en este documento.  
  
 Una de las ventajas de las propiedades promocionadas es que el valor del elemento que se promociona está disponible en el contexto del mensaje. Esto significa que recuperar ese valor no consume recursos, ya que no se requiere cargar el mensaje en memoria para ejecutar la instrucción XPath en el mensaje. En su lugar, se puede usar una bolsa de propiedades sencilla junto con una clave para obtener el valor. Este tipo de comportamiento es deseable en situaciones que no sean enrutamiento de mensajes y es el motivo para crear campos distintivos. Si bien las propiedades promocionadas se promocionan en el contexto del mensaje, los campos distintivos se escriben en el contexto del mensaje. No obstante, a diferencia de las propiedades promocionadas, no hay ningún esquema de propiedades para campos distintivos. Éste es el motivo para que no se puedan usar campos distintivos para enrutamiento y, por tanto, no están disponibles como criterio de filtro en una forma de recepción de orquestación o puerto de envío. Sin embargo, se pueden usar campos distintivos en orquestaciones para leer o escribir valores del contexto del mensaje en lugar de tener que cargar el mensaje en memoria y extraer el valor.  
  
 Además de promocionar o escribir propiedades en el contexto del mensaje, se pueden agregar también predicados de mensaje al contexto. Los predicados de mensaje se usan como medida de seguridad en BizTalk Server y proporcionan información contextual del mensaje, que debe coincidir con los valores especificados para cualquier servidor al que se va a enrutar el mensaje. Esta medida de seguridad permite configurar el entorno de BizTalk Server de forma que permita que hosts específicos sean los únicos hosts que pueden recibir y procesar mensajes concretos. Como ejemplo, en la consola de administración de BizTalk Server, se puede configurar un host con la huella digital de un certificado para descodificar y descifrar mensajes. Al configurar esta propiedad se crea una propiedad de aplicación para ese host en el cuadro de mensajes. Los mensajes protegidos que se reciben y descifran con esta huella digital se enrutan únicamente hacia los hosts que tienen la huella digital configurada.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura en tiempo de ejecución](../core/runtime-architecture.md)