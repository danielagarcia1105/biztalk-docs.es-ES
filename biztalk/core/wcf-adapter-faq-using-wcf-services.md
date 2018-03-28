---
title: 'P+F del adaptador de WCF: Utilizar servicios de WCF | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: befa2268-8a65-465f-8086-70a66808845e
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41d02fe0b7be1f53edaac4c18cfd7717a25c3a71
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="wcf-adapter-faq-using-wcf-services"></a>P+F del Adaptador de WCF: Utilizar Servicios de WCF
## <a name="how-does-biztalk-server-use-its-wcf-adapters-to-access-wcf-services"></a>¿Cómo usa BizTalk Server sus adaptadores de WCF para obtener acceso a los servicios WCF?  
 Los adaptadores de WCF de BizTalk se configuran en BizTalk Server mediante una ubicación de recepción o un puerto de envío WCF. Cuando se habilita una ubicación de recepción que usa un adaptador de WCF, se crea una instancia única de ServiceHost y se inicializa para cada ubicación de recepción. ServiceHost ejecuta un servicio genérico que acepta los mensajes de WCF entrantes y los convierte en mensajes de BizTalk antes de publicarlos en la base de datos de cuadro de mensajes de BizTalk. El servicio ServiceHost genérico es interno en la implementación del adaptador de recepción de BizTalk de WCF y expone un contrato sin tipo. En WCF, un contrato sin tipo consiste en firmas de funcionamiento que toman un único parámetro de tipo System.ServiceModel.Channel.Message de WCF.  
  
 La operación de un servicio WCF se debe marcar como IsOneWay=false si un puerto de envío de BizTalk debe obtener acceso al mismo aunque no haya ningún dato para devolver. Las operaciones del contrato en el lado del cliente se deben anotar con IsOneWay=false y ReplyAction=”*”.  Además, todas las llamadas del cliente se deben marcar como IsOneWay=”false”. Una operación de servicio bidireccional puede devolver un valor de tipo de mensaje. La excepción a esto es usar el adaptador de WCF-NetMsmq, ya que ejecuta una operación unidireccional que publica un mensaje en una cola MSMQ. En este caso, el puerto de envío puede ser unidireccional y cualquier operación se marca como IsOneWay=true.  
  
 Puede llevar a confusión que también sea posible en WCF definir isOneWay=false OperationContract en un método que realmente devuelve un valor nulo. En esta situación, en realidad se devuelve un mensaje en la red creado automáticamente por el tiempo de ejecución de WCF.  
  
 Los adaptadores de WCF de BizTalk usan esta característica. Cuando se especifica un puerto de BizTalk unidireccional, en realidad se obtiene un método nulo con isOneWay=false dentro de la implementación del adaptador de WCF. El caso es que un puerto unidireccional de BizTalk, cuando usa un canal directo como HTTP o net.tcp, en realidad corresponderá a isOneWay=false OperationContract. Los canales en cola, tal como net.msmq, son diferentes en que un puerto de BizTalk unidireccional llama a isOneWay=true OperationContract. La situación es distinta, ya que el distribuidor WCF usa una transacción en el canal.  
  
## <a name="how-do-you-create-and-use-a-custom-binding-with-a-wcf-custom-adapter"></a>¿Cómo se crea y usa un enlace personalizado con un adaptador personalizado de WCF?  
 Un enlace CustomBinding de WCF consta de una colección de BindingElements. Un enlace CustomBinding se puede crear al combinar BindingElements preexistentes (por ejemplo, un transporte preexistente con un codificador preexistente de otro origen). O bien, se puede crear al combinar un BindingElement preexistente con un BindingElement personalizado que se acaba de escribir. Un enlace CustomBinding se puede crear con código a partir de estos componentes BindingElements, al agregarlos mediante programación. WCF también permite esta construcción a través de la configuración de .NET (archivos de configuración). Mediante el uso de BizTalk Server, este enlace CustomBinding puede crearse a través del adaptador personalizado de WCF de BizTalk.  
  
 El adaptador personalizado de WCF de BizTalk no solo permite crear un nuevo enlace a partir de BindingsElements, sino que también permite configurar un nuevo enlace directamente. Además permite configurar comportamientos en enlaces estándar. Esto es de particular utilidad porque escribir comportamientos personalizados es mucho más fácil que escribir nuevos objetos BindingElements.  
  
 Creación de un objeto BindingElement es un ejercicio de desarrollo complejo y la mejor fuente de referencia es los ejemplos WCF en HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=142449" \t "_blank" http://go.microsoft.com/fwlink/?LinkId=142449. Para crear un BindingElement personalizado, debe crear una clase que se derive de BindingElement. Un objeto BindingElement nuevo tendrá que estar en un ensamblado nuevo. Este ensamblado debe estar instalado en la memoria caché global de ensamblados (GAC) del equipo de administración donde están configurados el host, el puerto de envío y la ubicación de recepción de BizTalk. Para asociar un enlace personalizado con un puerto de envío específico o ubicación de recepción, primero debe agregarlo a la \<bindingElementExtensions\> sección del archivo machine.config en el mismo equipo.  
  
 Después de realizar ese cambio, a continuación, puede poner en funcionamiento la **configuración de propiedades de transporte** cuadro de diálogo para configurar el enlace.  
  
1.  En el **enlace** ficha, para el tipo de enlace, seleccione **customBinding**.  
  
2.  En el **enlace** panel, haga clic en **CustomBindingElement**y seleccione **Agregar extensión**.  
  
3.  Seleccione el elemento de enlace que especificó en el archivo machine.config y configure el enlace según se necesario. Ahora está listo para usarse en la transmisión o recepción de mensajes.  
  
 BizTalk realiza una validación muy limitada de un enlace personalizado cuando se ha agregado de esta manera. Por lo tanto, es importante asegurarse de que los elementos de enlace se enumeran en el orden correcto. El elemento de enlace que desea invocar primero en tiempo de ejecución debe estar en al final del árbol de enlace CustomBindingElement del cuadro de diálogo. La lista de BindingElements debe contener un transporte y este último debe encontrarse al final de la lista. El conjunto de BindingElements también puede contener un codificador. Para obtener más información, consulte la documentación de WCF en elementos de enlace en [ http://go.microsoft.com/fwlink/?LinkId=142449 ](http://go.microsoft.com/fwlink/?LinkId=142449).  
  
## <a name="what-is-a-wcf-custom-behavior-and-how-do-i-use-one-with-biztalk-server"></a>¿Qué es un comportamiento personalizado de WCF? y cómo se usa con BizTalk Server?  
 Una de las ventajas de usar WCF como mecanismo de comunicación de mensajes es la oportunidad de ampliar la funcionalidad de sus servicios mediante código personalizado. Las extensiones del comportamiento personalizado son una de las características que distinguen a WCF de otras tecnologías de servicios web del mercado.  
  
 Hay diferentes puntos dentro del flujo de un mensaje de WCF para interceptar y ejecutar el procesamiento personalizado antes de que un mensaje alcance su destino final. Las extensiones de comportamiento personalizado de WCF son uno de estos tipos de mecanismos de interceptación y se pueden usar para ampliar el Servicio WCF o la funcionalidad de cliente en niveles de granularidad diferentes. Las extensiones de comportamiento personalizado pueden existir en los niveles de servicio y cliente WCF. La configuración de un comportamiento en la pila de llamada para un Servicio WCF no influye en el enlace de comunicación que se usa para realizar la llamada. De hecho, los comportamientos suelen ser invisibles para el cliente porque no se muestran en los metadatos que un servicio publica. El cliente normalmente no tiene ni idea que los comportamientos se están ejecutando durante una llamada a una operación de WCF.  
  
 La capacidad de implementar el procesamiento personalizado en una llamada a un Servicio WCF es una de las principales razones por las que WCF es un paradigma de programación tan eficaz en comparación con otras maneras de comunicación entre aplicaciones web. Este procesamiento personalizado puede tomar cualquier forma según impongan los requisitos de extensibilidad dentro de una aplicación web. Los programadores pueden crear extensiones personalizadas que inspeccionen y validen la configuración del servicio o modifiquen el comportamiento de tiempo de ejecución en las aplicaciones de cliente y Servicio WCF. Comportamientos pueden complementar el procesamiento normal de mensajes, modificar el mensaje durante el procesamiento, inspeccionar determinados criterios de configuración y tome las medidas adecuadas, validar las identidades del llamador y pasar el mensaje si es correcto, etcetera. Implementar independientemente de la extensibilidad del mecanismo de procesamiento porque se trata realmente de un personalizado debe la aplicación.  
  
 Para usar un comportamiento personalizado de WCF en BizTalk Server, configura mediante el uso de la **comportamiento** pestaña para el adaptador de WCF-Custom o WCF-CustomIsolated para una ubicación de recepción o un puerto de envío.