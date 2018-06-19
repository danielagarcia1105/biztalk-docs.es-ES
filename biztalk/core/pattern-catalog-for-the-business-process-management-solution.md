---
title: Patrón de catálogo para la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Canonical Message pattern [process management solutions]
- Nested Scopes pattern [process management solutions]
- Filter pattern [process management solutions]
- Per-Instance Pipeline Configuration pattern [process management solutions]
- Translator pattern, process management solutions
- patterns [process management solutions], pattern types
- Interruptible Orchestration pattern [process management solutions]
- Decoupled Orchestration pattern [process management solutions]
- Code Retry and Exception Handling pattern [process management solutions]
- Process Manager pattern [process management solutions]
- Asynchronous Reply pattern [process management solutions]
- Custom Exceptions pattern [process management solutions]
- Message Broker pattern [process management solutions]
- Coordination Using Delivery Notification pattern [process management solutions]
- Convoy pattern [process management solutions]
- Versioning pattern [process management solutions]
- Error Routing pattern [process management solutions]
- Application Reference pattern [process management solutions]
- Inverse Direct Partner Binding pattern [process management solutions]
ms.assetid: 246b109e-6006-404d-88b9-e6324ce3473c
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b352cce73e45103437407a013691e604b7b959
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266420"
---
# <a name="pattern-catalog-for-the-business-process-management-solution"></a>Catálogo de patrones de la solución de administración de procesos empresariales
Los patrones de la solución de administración de procesos empresariales incluyen patrones comunes para programar BizTalk Server, así como patrones de integración de empresas de secciones anteriores. La lista de esta sección incluye ambos tipos de patrones.  
  
## <a name="pattern-types"></a>Tipos de patrón  
 A continuación se describe brevemente el patrón y se incluyen vínculos a otros temas en los que se explica cómo la solución utiliza los patrones. En el caso de los patrones generales, como un filtro, se proporcionan vínculos a temas más generales.  
  
### <a name="application-reference-patterns"></a>Patrones de referencia de aplicaciones  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite que una aplicación utilice los artefactos en otra aplicación dentro del mismo grupo al agregar una referencia a la otra aplicación. La solución de administración de procesos empresariales utiliza referencias de aplicaciones en el diseño de la solución de prueba así como en la solución principal. Para obtener más información acerca de las referencias de la aplicación en la solución, vea [algunos principios de diseño de la solución de administración de procesos empresariales](../core/some-design-principles-in-the-business-process-management-solution.md).  
  
### <a name="asynchronous-reply-patterns"></a>Patrones de respuesta asíncrona  
 La comunicación entre el administrador de pedidos y las fases de procesamiento de pedidos es asíncrona. Es decir, el administrador sigue el procesamiento hasta que recibe la respuesta. Las fases utilizan puertos dinámicos de autocorrelación para enviar respuestas al administrador. Los puertos de autocorrelación eliminan la necesidad de que el administrador de pedidos administre un conjunto de correlaciones. El aspecto dinámico del puerto permite al administrador de pedidos enviar la dirección del puerto para la respuesta a la fase de pedido. Para obtener más información acerca de los puertos de la solución, vea [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md).  
  
### <a name="canonical-message-patterns"></a>Patrones de mensajes canónicos  
 Para simplificar el procesamiento a menudo una solución convierte mensajes externos en un formato interno. Este formato es un ejemplo de un mensaje canónico. La orquestación de agente de pedido convierte todos los mensajes de pedido en uno o más mensajes de pedidos canónicos. La orquestación de administrador de pedidos y fases de procesamiento utilizan este formato común de pedido. Para obtener más información, consulte [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md).  
  
### <a name="code-retry-and-exception-handling-patterns"></a>Reintento de código y patrones de control de excepciones  
 La solución centraliza la mayor parte del control de excepciones en el **ExceptionHandler** orquestación. La solución utiliza esta orquestación cuando hay una posibilidad de que la operación funcione si se vuelve a intentar, por ejemplo, con una conexión de red perdida. La orquestación utiliza la **Recaller** objeto que se va a volver a ejecutar el código de error. Para obtener más información sobre la orquestación, consulte [control de excepciones en la solución de administración de procesos empresariales](../core/exception-handling-in-the-business-process-management-solution.md). Consulte también [la orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md). Para obtener más información sobre el uso de la **Recaller** de objetos, consulte [el objeto Recaller](../core/the-recaller-object.md).  
  
### <a name="convoy-pattern"></a>Patrón de convoy  
 La orquestación de administrador de pedidos, OrderManager, utiliza el patrón de convoy para detectar y procesar cambios posteriores al procesamiento de un pedido. Para obtener más información sobre el patrón de convoy en el Administrador de pedidos, vea "Actualización de pedidos" en [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md).  
  
### <a name="coordination-using-delivery-notification"></a>Coordinación en el uso de notificación de entrega  
 El **OrderBroker** orquestación usa las notificaciones de entrega para asegurarse de que se realiza una entrada en la base de datos de historial antes de que el historial se actualiza con la segunda fase de procesamiento de pedidos (**CableOrder2**). Para obtener más información, vea "Coordinar con las fases" en [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md). Para obtener información general sobre la notificación de entrega, vea [confirmaciones utilizando](../core/using-acknowledgments.md).  
  
### <a name="custom-exceptions-pattern"></a>Patrón de excepciones personalizadas  
 Para las excepciones que no se pueden reintentar, la solución utiliza el control de excepción habitual del servidor BizTalk Server junto con el control de excepciones personalizadas. El control de excepciones personalizadas proporciona un control de excepciones más específico. También sirve como indicador entre ámbitos anidados para garantizar que se deshacen todas las partes de una operación. Para obtener más información sobre el uso de la solución de excepciones personalizadas, vea [excepciones personalizadas](../core/custom-exceptions.md). Para obtener más información sobre los ámbitos, consulte [cómo configurar la forma ámbito](../core/how-to-configure-the-scope-shape.md).  
  
### <a name="decoupled-orchestration-patterns"></a>Patrones separados de orquestación  
 El diseño de la solución de administración de procesos empresariales separa las orquestaciones en la máxima medida de lo posible. Separar las orquestaciones facilita la creación de versiones de partes de la solución y simplifica el traslado de partes de la solución a otros servidores o grupos. Para obtener más información sobre la relación entre el agente de pedido y el Administrador de pedidos, consulte [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md) y [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md).  
  
### <a name="error-routing-pattern"></a>Patrón de enrutamiento de error  
 La solución utiliza la nueva característica de informes de errores de BizTalk Server. Esta característica enruta los mensajes que fallaron a un puerto de suscripción para elaborar un informe o procesarlos. Para obtener información general sobre informes de errores, vea [enrutamiento de mensajes de error utilizando](../core/using-failed-message-routing.md).  
  
### <a name="filter-pattern"></a>Patrón de filtro  
 El patrón de filtro selecciona mensajes que cumplen determinados criterios para el procesamiento. En BizTalk, el patrón de filtro casi siempre se convierte en una expresión de filtro en un puerto. Para obtener más información sobre los filtros de puertos, consulte [utilizando filtros con el mensaje de forma recepción](../core/using-filters-with-the-receive-message-shape.md).  
  
### <a name="interruptible-orchestration-pattern"></a>Patrón interrumpible de orquestación  
 El modo que tiene la solución de controlar actualizaciones o cancelaciones de pedidos es interrumpir el pedido actual en primer lugar. Las orquestaciones de la solución utilizan la orquestación de interrupción para procesar las interrupciones. Para obtener más información, consulte [de interrupción de control en la solución de administración de procesos empresariales](../core/interrupt-handling-in-the-business-process-management-solution.md).  
  
### <a name="inverse-direct-partner-binding-pattern"></a>Patrón de inversión de enlace directo de socio  
 La solución invierte el uso de enlace directo para separar las fases de procesamiento de pedidos del administrador de pedidos. Para obtener más información sobre el enlace directo inverso, consulte [enlace de socio directo inverso](../core/inverse-direct-partner-binding.md).  
  
### <a name="message-broker-pattern"></a>Patrón de agente de mensajes  
 El patrón de agente de mensajes permite que la solución determine el destino de un mensaje para que no sea necesario que el remitente conozca el destino. La solución de administración de procesos empresariales implementa un agente de mensajes con el **OrderBroker** orquestación. El **OrderBroker** orquestación toma un pedido, determina el tipo de servicio solicitado y enruta el pedido al administrador de pedidos correspondiente. Para obtener más información acerca de agentes de mensajes en el **OrderBroker**, consulte [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md).  
  
### <a name="nested-scopes-pattern"></a>Patrón de ámbitos anidados  
 El **OrderBroker** orquestación utiliza ámbitos anidados para minimizar los puntos de persistencia y, por lo tanto, para mejorar la eficacia. Para obtener más información, vea "Mejorar el rendimiento con ámbitos anidados" en [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md).  
  
### <a name="per-instance-pipeline-configuration"></a>Configuración de canalización por instancia  
 Aunque la solución utiliza canalizaciones predeterminadas, hace un gran uso de la nueva configuración de canalización por instancia para especificar un sobre para mensajes. Para obtener más información, consulte [cómo implementar canalizaciones](../core/how-to-deploy-pipelines.md) y [componentes de la solución de administración de procesos empresariales](../core/components-of-the-business-process-management-solution.md).  
  
### <a name="process-manager-pattern"></a>Patrón de administrador de procesos  
 La solución utiliza un administrador de pedidos relativamente genérico para controlar el flujo mediante las fases de procesamiento de pedidos. Esto ayuda a separar la lógica empresarial de la administración del proceso de pedidos. Para obtener más información acerca de cómo funciona la orquestación OrderManager como administrador de procesos, vea [lógica del Administrador de procesos](../core/process-manager-logic.md).  
  
### <a name="terminate-shape-at-end-of-orchestration"></a>Forma Finalizar para terminar una orquestación  
 Varias orquestaciones utilizan una forma Finalizar para terminar en un error incluso si la orquestación hubiera finalizado de forma normal en ese momento. La forma Finalizar permite errores e instancias fallidas de seguimiento. Para obtener más información, consulte [personalizado excepciones](../core/custom-exceptions.md).  
  
### <a name="translator-pattern"></a>Patrón de traductor  
 El patrón de empresa de un traductor, es decir, la conversión de un mensaje de un formulario a otro formato, a menudo se traduce en una asignación de BizTalk. Para obtener información general acerca de las asignaciones de BizTalk, consulte [crear asigna utilizando el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).  
  
### <a name="versioning-patterns"></a>Patrones de control de versiones  
 La solución de administración de procesos empresariales está diseñada para simplificar el control de las versiones de los componentes de la solución a través de la separación de orquestaciones y el uso de la numeración de versiones en espacios de nombres de esquema. Para obtener más información, consulte [control de versiones de la solución de administración de procesos empresariales](../core/versioning-the-business-process-management-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Patrones de la solución de administración de procesos empresariales](../core/patterns-in-the-business-process-management-solution.md)