---
title: 'P+F del adaptador de WCF: Conceptos generales | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbeac135-3ba8-4b0b-a8ca-4eb5eb3d3ca3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a33e6ba26f0ba97cb10aa2f9ee728683719dd66
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009253"
---
# <a name="wcf-adapter-faq-general-conceptual"></a>P+F del Adaptador de WCF: Conceptos generales
A continuación, encontrará algunas de las preguntas más frecuentes generales y conceptuales sobre los adaptadores de Windows ® Communication Foundation (WCF).  
  
## <a name="what-is-a-wcf-adapter"></a>¿Qué es un adaptador de WCF?  
 Un adaptador de BizTalk es una pieza clave del modo en que Microsoft® BizTalk® Server se comunica con el mundo exterior. Un adaptador de WCF es un componente que administra el proceso de comunicación entre una aplicación de BizTalk y su necesidad de enviar mensajes a un extremo de WCF y recibir mensajes del mismo. Con el servidor BizTalk Server, los adaptadores de WCF se exponen como enlaces WCF. Esto significa que cualquier aplicación WCF que pueda usar un enlace WCF se puede comunicar directamente con los adaptadores de WCF, sin necesidad de intervención del servidor BizTalk Server. Sin embargo, el uso de adaptadores de WCF mediante BizTalk Server ofrece muchas de las ventajas de la infraestructura de aplicación que BizTalk Server proporciona. Estas preguntas frecuentes se centran principalmente en el uso de adaptadores de WCF desde dentro del entorno de BizTalk Server.  
  
 Un adaptador de WCF permite que BizTalk Server use los enlaces WCF para enviar y recibir mensajes de WCF. Una aplicación cliente WCF puede enviar un mensaje de WCF a una ubicación de recepción de BizTalk, donde el adaptador de recepción de WCF lo recibe. El adaptador toma el mensaje de WCF y lo convierte en un mensaje de BizTalk. La forma en que se lleva a cabo la conversión depende de determinados valores de configuración del adaptador que se configuran mediante la consola de administración de BizTalk Server. El adaptador envía el mensaje de BizTalk a la base de datos interna de cuadro de mensajes de BizTalk. Un puerto de envío de BizTalk que use un adaptador de WCF puede suscribirse a este tipo de mensaje, obtener el mensaje de BizTalk, convertirlo en un mensaje de WCF y transmitir éste a un extremo de servicio WCF que use uno de los protocolos WCF admitidos.  
  
 El uso de adaptadores de WCF desde dentro de BizTalk Server abstrae las complejidades ocultas de una solución de aplicación de BizTalk-WCF, tal como la elección e implementación de protocolos de comunicación, los problemas de seguridad y las operaciones transaccionales.  
  
## <a name="what-are-the-wcf-adapter-bindings"></a>¿Qué son los enlaces del adaptador de WCF?  
 Los enlaces WCF se dividen en dos categorías:  
  
-   **Enlaces personalizados:** para obtener mayor flexibilidad de enlace, existe el enlace personalizado especial. Abarca las situaciones de comunicación que requieren desviaciones de los enlaces estándar. Los adaptadores de WCF-Custom, así como los adaptadores de WCF-CustomIsolated, permiten el desarrollo de amplias personalizaciones de enlace. Esto se lleva a cabo al permitir la composición de elementos de enlace existentes (la clase BindingElement) y la aplicación de comportamientos (la clase Behavior).  
  
-   **Enlaces estándar:** el objetivo de Microsoft es desarrollar adaptadores que se centren en los escenarios más comunes de comunicación. El uso de enlaces estándar simplifica el trabajo del programador, ya que ocultan muchos detalles de los protocolos de comunicación. El conjunto de adaptadores WCF en BizTalk Server refleja el conjunto de enlaces disponibles en las bibliotecas de WCF de .NET Framework 4.0. Los enlaces estándar se introdujeron en las bibliotecas WCF de .NET para facilitar el uso de los patrones de enlace típicos. Abarcan los escenarios de comunicación que se usan con más frecuencia e incluyen:  
  
    -   WCF-WsHttp  
  
    -   WCF-BasicHttp  
  
    -   WCF-NetTcp  
  
    -   WCF-NetMsmg  
  
    -   WCF-NetNamedPipe  
  
 BizTalk Server R2 incluye los siguientes adaptadores de WCF:  
  
1.  **Adaptador de WCF-WSHttp:** proporciona WS-* compatibilidad con estándares mediante el transporte HTTP. Este adaptador implementa las especificaciones siguientes: WS-Transaction para las interacciones de transacciones entre aplicaciones externas y la base de datos de cuadro de mensaje y WS-Security para la seguridad y la autenticación de mensajes. El transporte es HTTP o HTTPS, y los mensajes tienen codificación de texto o de Mecanismo de optimización de transmisión del mensaje (MTOM).  
  
2.  **Adaptador de WCF-BasicHttp:** se comunica con servicios Web basados en ASMX y clientes y otros servicios que cumplan con WS-I Basic Profile 1.1. El transporte es HTTP o HTTPS y los mensajes tienen una codificación de texto.  
  
3.  **Adaptador de WCF-NetTcp:** proporciona WS-* compatibilidad con estándares a través del transporte TCP. Este adaptador ofrece una comunicación eficaz e implementa las especificaciones siguientes: WS-Transaction para las interacciones de transacciones entre aplicaciones externas y la base de datos de cuadro de mensaje y WS-Security para la seguridad y la autenticación de mensajes. El transporte es TCP y codificación de mensajes es la codificación binaria.  
  
4.  **Adaptador de WCF-NetMsmq:** proporciona compatibilidad para poner en cola aprovechando Message Queuing (también conocido como MSMQ) como transporte y habilita la compatibilidad para débilmente acoplados aplicaciones, aislamiento de errores, equilibrio de carga y operaciones desconectadas.  
  
5.  **Adaptador de WCF-NetNamedPipe:** proporciona una optimización segura para la comunicación entre procesos en el equipo. Este adaptador usa seguridad de transporte para la seguridad de transferencia, canalizaciones con nombre para la entrega de mensajes y codificación binaria de mensajes.  
  
     Cada uno de los cinco adaptadores que se acaban de mencionar corresponde a un enlace WCF de una relación 1:1. La estructura de los dos adaptadores personalizados que se van a tratar rompe ligeramente con el modelo de WCF, ya que en realidad hay dos adaptadores personalizados distintos que corresponden a un único CustomBinding de WCF.  
  
6.  **Adaptador de WCF-Custom:** habilita el uso de características de extensibilidad WCF. El adaptador permite seleccionar y configurar un enlace WCF y la información de comportamiento para una ubicación de recepción o un puerto de envío hospedado en el proceso de BizTalk Server.  
  
7.  **Adaptador de WCF-CustomIsolated:** habilita el uso de características de extensibilidad WCF mediante el transporte HTTP. El adaptador permite seleccionar y configurar un enlace WCF y la información de comportamiento para una ubicación de recepción que se ejecuta en un host aislado de Internet Information Services (IIS).  
  
## <a name="what-is-the-difference-between-the-wcf-xxx-adapter-and-the-wcf-xxx-binding"></a>¿Cuál es la diferencia entre el adaptador de WCF-xxx y el enlace WCF-xxx?  
 Cada uno de los adaptadores de WCF corresponde a uno de los enlaces WCF integrados. En un nivel superior, estos términos prácticamente se pueden intercambiar al decir que el adaptador de WCF-xxx usa el enlace WCF-xxx. Por ejemplo, el adaptador de WCF-BasicHttp usa la clase BasicHttpBinding de WCF. Un enlace WCF forma parte de la definición de un extremo de WCF. Esto se denomina “ABC” de un extremo de WCF; estas letras significan Address, Binding y Contract (dirección, enlace y contrato).  
  
 Un enlace está formado por una colección de elementos de enlace. Cada elemento describe algunos aspectos de la forma en que el extremo se comunica con los clientes. Un enlace debe incluir:  
  
-   Al menos un elemento de enlace de transporte  
  
-   Al menos una codificación de mensaje de elemento de enlace (que el elemento de enlace de transporte puede proporcionar de forma predeterminada)  
  
-   Cualquier número de elementos de enlace de protocolo  
  
 El proceso que genera un entorno de tiempo de ejecución a partir de esta descripción permite que cada elemento de enlace contribuya con código a ese entorno. Generalmente, es necesario que los tipos de enlace y adaptador de un cliente coincidan con los que admite el Servicio WCF que se llama. En el nivel de WCF, un enlace se puede definir en forma declarativa en un archivo de configuración o explícitamente mediante código. El adaptador de WCF facilita la comunicación con un enlace WCF específico y, por lo tanto, los términos “adaptador” y “enlace” tienden a convertirse en casi idénticos en su uso.  
  
## <a name="when-using-the-wcf-adapters-how-do-you-decide-which-wcf-binding-to-use"></a>Cuando se usan los adaptadores de WCF, ¿cómo se decide qué enlaces WCF se deben usar?  
 Puede tomar esta decisión en función del patrón de mensajería, las restricciones externas y el rendimiento, en ese orden.  
  
1.  **Patrón de mensajería:** el patrón de comunicación es cómo la comunicación se produce basada en el flujo del mensaje. Por ejemplo, el mensaje puede ser unidireccional (solicitud) o bidireccional (solicitud-respuesta), puede ser de transacción, puede estar en cola, etcétera.  
  
    -   Si está en cola, debe usar el adaptador de WCF-Netmsmq, que admite una comunicación de transacción en cola unidireccional.  
  
    -   Si el patrón es de solicitud-respuesta bidireccional y fluye entre dos equipos, use HTTP (si se preocupa porque sea lo más flexible posible) o WCF-NetTcp (si se preocupa sobre el rendimiento).  
  
    -   Si el mensaje permanece en un único equipo y fluye simplemente entre procesos, puede usar el enlace WCF-NetNamedPipe.  
  
2.  **Restricciones externas:** puede haber problemas que obliguen a usar un enlace específico. Por ejemplo, suponga que el sistema externo requiere Servicios web SOAP versión 1.2 y el direccionamiento 1.0. En este caso, la mejor opción de enlace es WSHttpBinding con el adaptador de WCF-WsHttp. Con toda probabilidad, el sistema externo también tendrá requisitos relativos al modo de seguridad en particular que se debe configurar. Si el sistema externo necesitara los Servicios web SOAP 1.1, usaría el adaptador de WCF-BasicHttp para el enlace HTTP.  
  
3.  **Rendimiento:** ¿con qué rapidez se realiza la llamada puede ser un factor decisivo en el enlace que decide usar en la aplicación:  
  
    -   Si el Servicio WCF está en el mismo equipo que BizTalk Server, el uso del adaptador de WCF-NetNamedPipe es la mejor opción de rendimiento.  
  
    -   Si el Servicio WCF se encuentra en la red local, WCF-NetTcp ofrece el mejor rendimiento.  
  
    -   Si el rendimiento no es una preocupación importante y la llamada se realiza por Internet, cualquiera de los adaptadores basados en HTTP (WCF-WsHttp o WCF-BasicHttp) será el adaptador correcto.  
  
         La decisión sobre cuál es el adaptador basado en HTTP más idóneo dependerá de si usa alguna de las funcionalidades HTTP avanzadas (WCF-WsHttp) o únicamente la funcionalidad básica (WCF-BasicHttp).  
  
## <a name="when-do-you-use-one-of-the-two-custom-wcf-adapters"></a>¿Cuándo se usa uno de los dos adaptadores personalizados de WCF?  
 Hay dos adaptadores personalizados de WCF que se suministran con BizTalk Server. La razón de que haya dos adaptadores personalizados es porque BizTalk Server necesita que el hospedaje de un tipo de adaptador en particular forme parte de su registro en el sistema. Aunque únicamente hay un tipo de CustomBinding en el marco de WCF, hay dos adaptadores personalizados en BizTalk Server para acomodar esta limitación en el modelo de adaptador de BizTalk preexistente. De hecho, estos adaptadores son realmente los únicos adaptadores que necesitará porque permiten un control completo sobre la configuración de pila de canal WCF.  
  
 El único inconveniente de los adaptadores personalizados es que también requieren tener un gran conocimiento sobre la configuración de WCF y las distintas técnicas de ampliación.  La simplificación de la configuración es la razón por la que Microsoft proporciona adaptadores para enlaces WCF estándar. Los enlaces estándar están predefinidos y abarcan la mayoría de los casos de uso común; simplifican lo máximo posible el envío y la recepción de mensajes mediante BizTalk Server. Normalmente, la necesidad de usar uno de estos adaptadores personalizados surge únicamente cuando los enlaces estándar no pueden satisfacer completamente o con precisión los requisitos para el puerto de envío o la ubicación de recepción. Por ejemplo, puede haber una aplicación que use un esquema de compresión propietario para sus mensajes. Para admitirlo, tendrá que escribir un elemento de enlace personalizado. El uso de uno de los dos adaptadores personalizados estándar permite que la configuración de este enlace personalizado controle la necesidad de transmisión. Por lo tanto, un adaptador personalizado permite un nivel superior de control sobre la configuración de los enlaces para ese proceso de comunicación mediante la pila de canal.  
  
 La diferencia principal entre los adaptadores personalizados y los aislados personalizados es la del hospedaje, y el hospedaje únicamente influye en el lado de recepción de BizTalk Server. El adaptador de WCF-CustomIsolated se usa únicamente con una ubicación de recepción y no con un puerto de envío. El término “aislado” pertenece a BizTalk y hace referencia a estar hospedado fuera del proceso BtsNtSvc.exe de BizTalk Server. Por lo tanto, el adaptador de WCF-CustomIsolated se usa cuando el transporte se hospeda fuera del proceso estándar BtsNtSvc.exe dentro de Internet Information Services (IIS) mediante el transporte HTTP. El adaptador de WCF-Custom se puede usar con una ubicación de recepción o un puerto de envío. Se usa cuando el transporte se hospeda dentro del proceso de BtsNtSvc.exe estándar.  
  
## <a name="how-does-a-wcf-endpoint-relate-to-biztalk-server"></a>¿Cómo se relaciona un extremo de WCF con BizTalk Server?  
 Un extremo de WCF se compone de una dirección, un enlace y un contrato (ABC). En BizTalk Server, el usuario especifica la dirección en la ubicación de recepción o el puerto de envío. El enlace viene determinado por el adaptador de WCF que el usuario ha elegido. El contrato está controlado por el programador porque especifica la interfaz expuesta por el extremo.  
  
 El extremo real existe como una ubicación de recepción a la que se envían los mensajes de WCF.  Hay varias maneras de exponer un extremo de WCF en una aplicación de BizTalk Server:  
  
-   Puede usar el Asistente para publicación de Servicio WCF de BizTalk para publicar una orquestación de BizTalk como extremo de WCF.  
  
-   Puede usar el Asistente para publicación de Servicio WCF de BizTalk para crear una ubicación de recepción en una aplicación BizTalk existente.  
  
-   Puede crear manualmente un extremo de WCF mediante la configuración en código del enlace y la dirección de una ubicación de recepción.  En este caso, la ubicación de recepción es, en realidad, sin tipo.  Tiene un contrato que se especifica puramente en términos de clase de mensaje de WCF, lo que le permite recibir cualquier formato de mensaje en la base de datos de cuadro de mensajes.  
  
 Cada ubicación de recepción de BizTalk que usa un adaptador de WCF se muestra como un extremo de WCF al que un cliente WCF puede llamar.  Una ubicación de recepción usa internamente su propio ServiceHost de WCF para permitir la habilitación o deshabilitación de las distintas ubicaciones de recepción independientemente las unas de las otras. La vigencia del extremo de servicio existe mientras la ubicación de recepción está habilitada. Es por este problema de vigencia que los ServiceHosts de WCF corresponden a las ubicaciones de recepción en lugar de a los puertos de recepción. El diseño de WCF asegura que los ServiceHosts individuales no sean costosos en cuanto a recursos de tiempo de ejecución y que muchos se puedan ejecutar dentro el mismo ejecutable sin ningún problema.  
  
 Cada puerto de envío de BizTalk que usa un adaptador de WCF corresponde a una llamada realizada a un Servicio WCF. Cuando hay mensajes para enviar, el servidor BizTalk Server entrega al adaptador los mensajes que corresponden a la creación del proxy de cliente WCF dentro del adaptador de WCF de BizTalk. Una vez enviados los mensajes, el proxy de cliente WCF se libera. La vigencia de WCF en un puerto de envío existe y desaparece constantemente a medida que se crea, usa y desmonta un proxy.