---
title: "El procesamiento en la orquestación OrderBroker | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, nested scopes
- nested scopes, performance
- processing, examples
- nested scopes, orchestrations
- orchestrations, performance
- performance, orchestrations
- performance, nested scopes
- examples, orchestration processing [process management solution]
- scopes, nesting
ms.assetid: c296e00c-b3ad-4161-baf7-258899185c34
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6a6571ece3190b6195b207b4c45969ce25ddec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-orderbroker-orchestration"></a>Procesamiento en la orquestación OrderBroker
Esta sección se describe cómo el **OrderBroker** orquestación recibe pedidos y prepararlos para un administrador de procesos. La sección empieza con una descripción del funcionamiento general de la orquestación. A continuación, se explica cómo la orquestación procesa un mensaje. Por último, se indica cómo la orquestación usa una transacción atómica para mejorar el rendimiento.  
  
> [!NOTE]
>  Debido a la longitud de la longitud de la **OrderBroker** código, puede que desee leer esta sección con la orquestación abierta en Microsoft® Visual Studio.  
  
## <a name="why-an-order-broker"></a>¿Por qué utilizar un agente de pedido?  
 El propósito de la **OrderBroker** orquestación es preprocesar un pedido y enrutarlo al administrador de procesos correcto. El preprocesamiento conlleva crear mensajes informativos para la base de datos de historial y el sistema de servicio, así como para confirmar la recepción del pedido. El **OrderBroker** también crea un mensaje de pedido genérico de la solicitud de atención al cliente. Esta normalización del pedido permite que los elementos del proceso empresarial consuman de forma genérica el pedido.  
  
 El mensaje de pedido es un mensaje de varias partes en el que la información de enrutamiento está separada de la información de pedido. La información de enrutamiento también es genérica y está diseñada para que la consuma cualquier administrador de pedidos. Esto a su vez facilita la ampliación de la solución. Para obtener información acerca de los mensajes de varias partes, vea [cómo usar tipos de mensaje de varias partes](../core/how-to-use-multi-part-message-types.md).  
  
 El aislamiento de la función de agente también le permite moverla a otro grupo de BizTalk. Porque el **OrderBroker** publica en la base de datos de cuadro de mensajes, es decir, enlace directo, también resulta más fácil para colocar el agente en otro grupo, puede mover el agente sin cambiar la orquestación. Para obtener más información acerca de cómo colocar el **OrderBroker** en otro grupo, consulte [comunicación entre OrderBroker y OrderManager](../core/communication-between-orderbroker-and-ordermanager.md).  
  
> [!NOTE]
>  El **OrderBroker** orquestación, dado que sólo tiene un **OrderManager** para comunicarse con, asigna simplemente una constante de cadena para el **OrderMgrType** campo en el orden mensaje de administrador. Normalmente, en una aplicación en la que haya varios administradores de pedidos, la aplicación utilizará el motor de reglas de negocios para determinar el valor adecuado para este cambio y el enrutamiento del pedido. Para obtener más información sobre el motor de reglas de negocios, vea [crear y usar las reglas de negocios](../core/creating-and-using-business-rules.md).  
  
## <a name="order-processing"></a>Procesamiento de pedidos  
 El **OrderBroker** orquestación comienza con dos **recepción** formas dentro de un **escuchar** forma. Una **recepción** forma toma mensajes desde el sistema de soporte al cliente; la otra, mensajes del sistema del proveedor. Los mensajes tienen el mismo esquema ya procedan de uno u otro origen.  
  
 La orquestación extrae el remite del mensaje y lo usa para establecer la dirección del puerto dinámico, **CSRPort**. La orquestación usa este puerto para enviar mensajes de confirmación y error.  
  
 Pasos siguientes de la **OrderBroker** orquestación crear el mensaje de historial, el mensaje del servicio, el mensaje de confirmación y el mensaje de pedido para enviar a la **OrderManager** orquestación. La orquestación utiliza la **InsertOrderBody** función de utilidad para agregar el mensaje de pedido al mensaje de historial.  
  
> [!NOTE]
>  En algunas situaciones, la solución puede producir mensajes que se entregan pero que no se consumen. La orquestación OrderBroker utiliza un puerto de envío para insertar información en la base de datos de historial. Este puerto de envío usa la característica de notificación de entrega. Configuración asigna el puerto de envío a un grupo de puertos de envío que contiene dos puertos: un puerto para la configuración de pruebas (**HistoryInsert-Test-SP**), uno para la configuración normal (**HistoryInsert-SP**). Si deja ejecutando los dos puertos del grupo, la solución envía mensajes en los dos puertos. Por consiguiente, solicita dos notificaciones de entrega, pero solamente procesa una.  
>   
>  Para evitar esta situación, dar de baja el puerto de prueba (**HistoryInsert-Test-SP**), o detener la versión de prueba de la aplicación, **BTSScn.BPM.OrderBrokerApp.Test**. Para obtener más información acerca de las notificaciones de entrega, vea [confirmaciones utilizando](../core/using-acknowledgments.md).  
  
 Al construir el mensaje para enviarlo a la **OrderManager** orquestación, el **OrderBroker** orquestación crea un mensaje de varias partes con dos partes. Una parte contiene la información de enrutamiento y la otra parte incluye el propio pedido. La parte de enrutamiento del mensaje, **OrderMgrMsg.Routing**, utiliza un esquema definido por una clase de C# en el **SchemaClasses** ensamblado. El agente trata la orden de partes del mensaje como un tipo genérico o de tipo independiente, el documento XML (**System.Xml.XmlDocument**) y lo asigna a **OrderMgrMsg.Order**.  
  
 Hay dos campos en la información de enrutamiento que son especialmente importantes para el Administrador de pedidos, **OrderMgrMsg.Routing.OrderMgrType** y **OrderMgrMsg.Routing.Status**. El agente establece la **OrderMgrType** para el tipo de administrador de pedidos que va a controlar el orden. En la solución, sólo hay un administrador de pedidos y el campo está establecido en CABLEORDER. El agente también establece la **estado** campo aceptado. Éste es el valor que indica al administrador de pedidos que el mensaje es un nuevo pedido. El Administrador de pedidos en la solución, **OrderManager** orquestación, utiliza un **recepción** forma que los filtros para el tipo de orden igual a CABLEORDER y cuyo estado es igual a ACCEPTED.  
  
 Los pasos restantes de la **OrderBroker** orquestación enviar los mensajes de diferentes a los puertos correspondientes.  
  
## <a name="improving-performance-with-nested-scopes"></a>Mejorar el rendimiento con ámbitos anidados  
 Una de las características más notorias el **OrderBroker** orquestación es el uso de ámbitos anidados. Uno de los objetivos de los ámbitos anidados es mejorar el rendimiento a través de la limitación de los puntos de persistencia.  
  
 El motor de orquestaciones guarda periódicamente el estado de toda la orquestación en puntos de ejecución que se denominan puntos de persistencia. El motor de orquestaciones trata automáticamente varias formas de orquestación, incluidos los **enviar** formas, como puntos de persistencia. Para obtener una lista de puntos de persistencia y obtener más información acerca de ellos, consulte [persistencia y el motor de orquestaciones](../core/persistence-and-the-orchestration-engine.md).  
  
 Con cinco **enviar** formas, el **OrderBroker** orquestación debe tener cinco puntos de persistencia. Sin embargo, al agrupar **enviar** formas dentro de un ámbito de transacción atómica, el motor reconoce solo necesita un punto de persistencia para el ámbito. Dado que cuatro de las **enviar** formas **OrderBroker** orquestación no forman parte de controladores de excepciones y nada debe hacerse después del envío, pueden incluirse en un ámbito de transacción atómica. Esto reduce el número de puntos de persistencia. Para obtener más información acerca de las transacciones atómicas, vea [transacciones atómicas](../core/atomic-transactions.md).  
  
 Además, el motor de orquestaciones utilizará un único punto de persistencia para las transacciones anidadas si todas las transacciones finalizan al mismo tiempo. Por lo tanto, la forma **OrderBroker** orquestación anida las transacciones reduce adicionalmente los puntos de persistencia: la orquestación tiene una persistencia única punto debido al uso de **ámbito** formas.  
  
> [!TIP]
>  Se puede mejorar el rendimiento si se reduce al mínimo el número de puntos de persistencia de una orquestación. Puede agrupar **enviar** formas en una transacción atómica para producir una persistencia única punto para todos los **enviar** formas. Si se finalizan a la vez los ámbitos de transacciones anidadas, se creará un único punto de persistencia para las transacciones.  
  
 Un ámbito de transacción atómica no puede tener un controlador de la excepción. Por ello, la orquestación anida el ámbito atómico dentro de una transacción de larga ejecución. Esta transacción externa puede tener un controlador de excepciones y es este controlador que procesa una excepción de la **enviar** formas.  
  
> [!TIP]
>  El anidamiento de una transacción atómica dentro de una transacción de larga ejecución es un patrón habitual para permitir para el control de excepciones.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento en la solución de administración de procesos empresariales](../core/processing-in-the-business-process-management-solution.md)   
 [Lógica del Administrador de procesos](../core/process-manager-logic.md)   
 [Control de interrupciones en la solución de administración de procesos empresariales](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [La orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md)