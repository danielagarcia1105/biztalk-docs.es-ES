---
title: "P+F del adaptador de WCF: Flujo de mensajes y asignación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 907e5c6a-a095-4b3a-9362-506832b6bc8c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e58b11cff00d4b235a5c14e75663fdf7e581f782
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faq-message-flow-and-mapping"></a>P+F del adaptador de WCF: Flujo de mensajes y asignación
## <a name="what-is-the-message-flow-within-the-wcf-and-biztalk-systems"></a>¿Cómo es el flujo de mensajes en los sistemas WCF y BizTalk?  
 A continuación se proporciona una descripción del flujo de un mensaje entrante de WCF hacia BizTalk Server:  
  
1.  Llega un mensaje de WCF a una ubicación de recepción y BizTalk Server crea una instancia de un Servicio WCF hospedado.  
  
2.  El tiempo de ejecución de WCF crea una instancia pila de canales del servicio y de sus agentes de escucha del canal. Una pila de canales es una secuencia de etapas que controlan diferentes tareas de procesamiento. Cada pila de canales consta de al menos un canal de transporte, con frecuencia un codificador de mensajes, y cero o más canales de protocolo. El canal de transporte lee la secuencia de mensajes entrantes a su llegada. Invoca un codificador para interpretar el mensaje y para producir un objeto de mensaje de WCF. En este momento, cada canal de protocolo podrá funcionar en el mensaje de WCF en orden.  
  
3.  Un agente de escucha recibe el mensaje de WCF, lo reenvía a través de la pila de canales WCF configurado y lo distribuye a la instancia de servicio adecuada. En este momento, el mensaje de WCF se convierte (asigna) en un mensaje de BizTalk. En pocas palabras, los encabezados de los mensajes de WCF se escriben en el contexto del mensaje de BizTalk y el cuerpo del mensaje de WCF se escribe en la parte del cuerpo del mensaje de BizTalk. La asignación controla qué parte del mensaje de WCF se convierte en el cuerpo del mensaje de BizTalk: sobres, cuerpo o un subelemento.  
  
4.  Los componentes de canalización configurados en la ubicación de recepción procesan el mensaje de BizTalk.  
  
5.  El mensaje de BizTalk se almacena en la base de datos de cuadro de mensaje.  
  
 A continuación se proporciona una descripción del flujo de un mensaje saliente de WCF desde BizTalk Server:  
  
1.  Un puerto de envío recibe un mensaje de BizTalk de acuerdo con su suscripción.  
  
2.  Los componentes de canalización configurados en el puerto de envío procesan el mensaje de BizTalk.  
  
3.  Se crea una instancia de una pila de canales de WCF y el mensaje de BizTalk se convierte (asigna) en un mensaje de WCF según el contrato visible externo del servicio.  
  
4.  La pila de canales de WCF transmite el mensaje de WCF al servicio de WCF externo.  
  
## <a name="how-is-a-wcf-message-converted-mapped-into-a-biztalk-message"></a>¿Cómo se convierte (asigna) un mensaje de WCF en un mensaje de BizTalk?  
 Para comprender la asignación, se debe considerar la estructura de un mensaje de WCF y un mensaje de BizTalk.  
  
 Un mensaje de WCF se modela en la estructura de mensajes de SOAP y consta de propiedades, encabezados y un único cuerpo de mensaje.  
  
-   El **propiedades de mensaje** son objetos de Common Language Runtime (CLR) que se adjuntan al objeto de mensaje. Las propiedades son internas para la pila de WCF y la aplicación del usuario en cada extremo de la comunicación. Nunca se transfieren directamente entre cliente y servidor.  
  
-   **Encabezados de mensaje**, sin embargo, se transfieren entre cliente y servidor. Puede haber numerosos encabezados en un mensaje, pero solo hay un cuerpo del mensaje y, a diferencia de los encabezados, el cuerpo del mensaje se transmite por secuencias. Tanto los encabezados como el cuerpo del mensaje se definen como un conjunto de información XML.  
  
-   El **cuerpo** de WCF mensaje es el contenido principal del mensaje para que las propiedades y los encabezados proporcionan más información.  
  
 Los mensajes de BizTalk presentan una estructura diferente.  
  
-   Hay un único conjunto de propiedades de contexto en cada mensaje y propiedad de contexto está formada por un par de nombre de espacio de nombres y valor. Las propiedades de contexto se pueden promover o escribir. Si se promueven, pueden formar parte de las reglas de enrutamiento que se ejecutan en BizTalk Server.  
  
-   Los datos de un mensaje en BizTalk Server pueden constar de varias secuencias. Los mensajes de BizTalk son de varias partes, ya que cada secuencia se puede leer de forma independiente. Una de las partes del mensaje es especial y se conoce como la parte del cuerpo.  
  
 Debido a que la comunicación puede ser en ocasiones bidireccional, el adaptador de WCF permite configurar la conversión o asignación particular para las direcciones tanto de entrada como de salida en el intercambio de mensajes. Esto se puede realizar tanto para las ubicaciones de recepción como para los puertos de envío en BizTalk Server.  
  
 Los adaptadores de WCF de BizTalk admiten varias permutaciones de conversiones en tiempo de ejecución entre estas dos estructuras de mensajes. Asignación se controla mediante la **mensajes** pestaña en el **propiedades de transporte** cuadro de diálogo para un adaptador de WCF. Por ejemplo, la conversión más obvia, y la predeterminada, se da cuando el cuerpo de un mensaje de WCF entrante se convierte en el cuerpo del mensaje de BizTalk. Para obtener más información acerca de los modos de asignación, consulte [http://go.microsoft.com/fwlink/?LinkID=119792](http://go.microsoft.com/fwlink/?LinkID=119792).  
  
## <a name="how-can-you-preserve-the-complete-incoming-wcf-message-inside-the-biztalk-message"></a>¿Cómo se puede conservar el mensaje de WCF entrante completo dentro del mensaje de BizTalk?  
 Una de las opciones de cuerpo de mensaje de BizTalk entrantes es la **sobres** opción. Al elegir esta opción, todo el mensaje de SOAP incluido en el elemento soap:Envelope se convierte en el cuerpo del mensaje de BizTalk entrante. El mensaje de BizTalk resultante contiene las etiquetas Sobre, todos los encabezados y el cuerpo.  
  
## <a name="how-can-you-extract-specific-elements-of-the-incoming-wcf-message-into-a-biztalk-message-or-map-elements-of-an-outgoing-biztalk-message-to-an-outgoing-wcf-message"></a>¿Cómo se pueden extraer elementos específicos del mensaje de WCF entrante en un mensaje de BizTalk o asignar elementos de un mensaje de BizTalk saliente a un mensaje de WCF saliente?  
 Para asignar una sección de un cuerpo de mensaje de WCF o BizTalk, use la opción Ruta o Plantilla. De este modo, podrá especificar una expresión XPath para extraer partes específicas del cuerpo del mensaje. En esta situación, la sintaxis completa de XPath no se admite, ya que la extracción se transmite por secuencias y, por tanto, el lector deberá ir siempre hacia adelante. Se trata de motivo, en la **mensajes** ficha se denomina "Ruta – contenido ubicado por la ruta de cuerpo" en lugar de "XPath – contenido ubicado por la ruta de cuerpo".  
  
 En el lado de recepción, use una expresión Ruta que indique cómo deben leerse los datos desde el mensaje de WCF. Para un mensaje entrante, el elemento específico que extrae la declaración Ruta se sustituye por el contenido del mensaje de BizTalk. El adaptador usa esta expresión Ruta para localizar y extraer los datos deseados para el mensaje de BizTalk.  
  
 En el lado de envío, use una plantilla para crear un mensaje de WCF a partir del mensaje de BizTalk. La opción de plantilla para los mensajes salientes está diseñada para permitir el contrario exacto de la opción XPath. En la configuración del adaptador de WCF, el fragmento de XML se usa como base para la estructura del mensaje saliente. El contenido del mensaje de BizTalk se inserta en tiempo de ejecución dentro de esta estructura.  
  
 Para un mensaje saliente, también debe elegir el tipo de elemento escrito mediante la opción Codificación de nodo de XML, Base64, Cadena o Hexadecimal. Esta opción resulta muy útil para extraer una secuencia de datos binarios incluida en un mensaje de WCF. El uso de esta función indica al adaptador de WCF que debe usar las llamadas ReadContextAsBase64 en el lector del cuerpo del mensaje de WCF. Esta llamada permite que los datos binarios se lean directamente a través de la API de XmlReader, por lo que el uso de estos datos binarios de funciones puede moverse directamente desde el transporte de WCF a la base de datos de cuadro de mensaje de BizTalk. Al escribir una ruta en el nodo que contiene los datos binarios, puede extraer éstos y colocarlos en el mensaje de BizTalk.  
  
## <a name="how-do-you-access-wcf-message-properties-within-an-incoming-wcf-message"></a>¿Cómo se obtiene acceso a las propiedades de mensaje de WCF dentro de un mensaje de WCF entrante?  
 Para obtener acceso a un mensaje de WCF entrante antes de que se transforme en un mensaje de BizTalk, puede usar un componente de canal de WCF personalizado o un punto de extensibilidad de modelo de servicio con un comportamiento de WCF. Por ejemplo, un **IDispatchMessageInspector** objeto. Los adaptadores de BizTalk WCF-Custom y WCF-CustomIsolated proporcionan una manera sencilla para la aplicación para que se conecte a la capacidad de los comportamientos WCF mediante el **comportamiento** pestaña en el **propiedades de transporte** cuadro de diálogo dichos adaptadores.  
  
 Para permitir que las propiedades de un mensaje de WCF estén disponibles para el adaptador de WCF, es necesario que dichas propiedades se escriban primero en el cuerpo o encabezado del mensaje como contenido. Los encabezados se copian automáticamente en el contexto de mensaje de BizTalk. Si desea que un valor de propiedad promocionado, puede usar un componente de canalización de BizTalk personalizado para promover la propiedad de mensaje WCF en el contexto de mensaje de BizTalk desde el **IComponent: ejecutar** método. El uso de los comportamientos de WCF personalizados con los adaptadores personalizados de WCF permite aprovechar la extensibilidad tanto de WCF como de BizTalk para mejorar la eficacia y la flexibilidad de la solución. El adaptador de WCF permite combinar las extensibilidades existentes de BizTalk y WCF para solucionar el problema.  
  
 Afortunadamente, existe un atajo en el adaptador de WCF para este caso de propiedad común. En lugar de tener que escribir en ambas historias de extensibilidad, puede hacer simplemente que la extensión de WCF cree una nueva propiedad “bien conocida” que comprenda el adaptador de WCF.  
  
 Para escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk, el mensaje de WCF debe contener una colección de parejas de valores que se componen de nombres de propiedad y espacios de nombres. De este modo, los adaptadores de WCF reconocerán que los valores de encabezado se deben escribir o promover.  
  
 Un adaptador de WCF espera las siguientes propiedades del mensaje en los mensajes de WCF para escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk:  
  
-   Para promover los valores del encabezado SOAP en el contexto de mensaje de BizTalk, los adaptadores de WCF se buscan la pareja de clave **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote** y el valor **lista < KeyValuePair\<XmlQualifiedName, objeto >>**. Con esta pareja, adaptadores de WCF toman el espacio de nombres, el nombre y el valor de la **XmlQualifiedName** objeto y usarlos para la promoción de los valores de encabezado.  
  
-   Para escribir pero no promover los valores del encabezado SOAP en el contexto de mensaje de BizTalk, adaptadores de WCF se buscan la pareja de clave **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext** y valor **Lista < KeyValuePair\<XmlQualifiedName, objeto >>.** Con esta pareja, los adaptadores de WCF escriben los valores en el contexto del mensaje.  
  
> [!NOTE]
>  Las propiedades promovidas también deben especificarse en el esquema de propiedades de BizTalk para que lo pueda aceptar el tiempo de ejecución de BizTalk.  
  
## <a name="you-have-an-existing-orchestration-or-send-port-etc-that-expects-a-biztalk-multipart-message-how-can-you-get-a-multipart-message-in-the-wcf-scenario"></a>Tiene una orquestación (o puerto de envío, etc.) existente que espera un mensaje de varias partes de BizTalk. ¿Cómo se puede obtener un mensaje de varias partes en el escenario de WCF?  
 Un mensaje de varias partes de BizTalk se compone de una o más partes de mensaje. Sin embargo, WCF no tiene el concepto de mensaje de varias partes. Dado que WCF no usa mensajes de varias partes, los adaptadores de WCF de BizTalk WCF tampoco los usan. El problema es que puede que tenga una orquestación o canalización de BizTalk ya existente escrita para producir o consumir mensajes de varias partes.  
  
 Si tiene que llevar un mensaje de varias partes a BizTalk Server mediante un mensaje de WCF entrante y los adaptadores de WCF, presente los datos de varias partes como XML en el mensaje de WCF. Desarrolle un componente de canalización de BizTalk personalizado para procesar la secuencia de XML entrante (mensaje de WCF) y cree el mensaje de varias partes de BizTalk adecuado para la aplicación. Estos pasos se pueden realizar en orden inverso para el lado de envío, si fuera necesario.