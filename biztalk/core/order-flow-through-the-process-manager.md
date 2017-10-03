---
title: Ordenar por el Administrador de procesos de flujo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: e2b51eff-44b5-440f-a7d1-0872543e5f27
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8556bce43ba4a951d0045d22f76d4bd222fcd8f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="order-flow-through-the-process-manager"></a>Flujo de pedidos a través del Administrador de proceso
Esta sección describe cómo el Administrador de procesos, los pedidos de Southridge Video el **OrderManager** orquestación, procesa pedidos. Esta sección sigue un pedido nuevo a través de la orquestación. Además, aborda cómo controla la orquestación las actualizaciones de los pedidos.  
  
> [!NOTE]
>  La solución de administrador de procesos empresariales incluye sólo un administrador de procesos, pese a que esté diseñado para utilizar más de un tipo.  
  
 El **OrderManager** orquestación coordina orquestaciones subordinadas que implementan el proceso empresarial para controlar el orden. El **OrderManager** envía el pedido a través de dos fases que, combinados, validar el pedido, la información de envío para el grupo de instalaciones, enviar el pedido al sistema de pedidos a través de los componentes de comunicación remota y actualizar el historial de pedidos. Puede agregar, eliminar o modificar estas fases sin tener que cambiar la **OrderManager**.  
  
> [!NOTE]
>  Debido al tamaño y el ámbito de la **OrderManager** orquestación, puede que desee leer esta sección con la orquestación abierta en Microsoft Visual Studio.  
  
## <a name="order-manager-structure"></a>Estructura del administrador de pedidos  
 El **OrderManager** orquestación comienza con una forma recepción que activa la orquestación. El siguiente diagrama muestra la estructura general de la **OrderManager** orquestación.  
  
 ![Diagrama del Administrador de pedidos en bloques](../core/media/ordermanagerblockdiagram.gif "OrderManagerBlockDiagram")  
  
 La primera forma de recepción conduce a dos ramas principales. Una rama, la derecha, procesa pedidos nuevos. La rama izquierda, por su parte, controla las cancelaciones de pedido. Dado que acepta la entrada de usuario, es posible que el **OrderManager** para recibir una cancelación de pedido después de que un pedido ya se ha completado. Éste es el caso que controla la rama principal izquierda. La rama controla la cancelación aislada y, para ello, establece indicadores de finalización de procesamientos y agrega advertencias a los registros de sucesos. La orquestación controla las cancelaciones de pedido que recibe mientras se procesa un pedido en la rama derecha.  
  
 La rama de procesamiento de pedidos realiza algunas operaciones de inicialización y especifica dos bucles anidados. El bucle externo se ejecuta una vez en cada fase de procesamiento del pedido. El bucle interno se ejecuta durante el procesamiento de la fase. Además, el administrador de pedidos escucha las posibles actualizaciones del pedido dentro del bucle interno. Una vez que terminan los bucles, el administrador de pedidos envía un mensaje de finalización.  
  
 Las fases de procesamiento de pedidos usan puertos dinámicos, autocorrelación para comunicarse de vuelta con el **OrderManager** orquestación. Esto simplifica la correlación de la **OrderManager** con la fase de instancias ya que evita la necesidad de usar un conjunto de correlaciones. Para obtener más información acerca de los puertos de autocorrelación, consulte [enlaces de puerto](../core/port-bindings.md).  
  
## <a name="receiving-orders"></a>Recibir pedidos  
 El **OrderManager** recibe mensajes de pedidos de la **OrderBroker** orquestación a través de la **FromBrokerPort** puerto. Este puerto está vinculado directamente a la base de datos de cuadro de mensajes. La orquestación tiene dos **recepción** formas se conectan al puerto: uno para los pedidos nuevos y otro para actualizan los pedidos.  
  
 El **OrderManger** determina qué mensajes se proceso basado en una expresión de filtro. La expresión de filtro prueba el valor del campo de estado de mensaje y el campo de tipo de administrador de pedidos, **OrderMgrType**. Si el campo de estado es igual a ACCEPTED y el **OrderMgrType** está establecido en CABLEORDER, el orden es nuevo y está diseñado para este administrador de procesos.  
  
 El pedido nuevo activa una instancia nueva de la orquestación. El **OrderManager** vuelva a comprobar el tipo de la solicitud en un **decisión** forma. Si el tipo es Finalizar, la orquestación ejecuta la rama izquierda y finaliza el pedido. De lo contrario, la orquestación continúa procesando el pedido. Observe que aquí se incluye la escucha de los mensajes posteriores que estén relacionados con este pedido en concreto.  
  
## <a name="initialization-for-new-orders"></a>Inicialización de pedidos nuevos  
 Después de la **OrderManager** orquestación recibe un mensaje inicial y comienza la bifurcación main derecha, obtiene su información de configuración de la **SSOConfigStore**. Esto lo hace a través de un objeto singleton, definido en el **utilidades** ensamblado. Los valores de configuración son propiedades del objeto. El objeto administra una caché local de los valores de configuración parecida a la solución de arquitectura orientada a servicios. Para obtener más información sobre el objeto singleton, vea [usar SSO de forma eficaz en la solución de administración de procesos empresariales](../core/using-sso-efficiently-in-the-business-process-management-solution.md).  
  
 Al igual que ocurre con la solución orientada a servicios, la solución de administración de procesos empresariales utiliza el almacén de secreto (puesto que aparece siempre que BizTalk está instalado) y SSO almacena en caché la información de configuración para que todos los valores estén disponibles con facilidad; además, puede proteger información como, por ejemplo, cadenas y contraseñas de conexión de bases de datos. Por todo ello, el almacén secreto se convierte en la ubicación idónea para la información de configuración, aunque no se esté utilizando el inicio de sesión único para administrar las conexiones a las aplicaciones de servidor.  
  
> [!NOTE]
>  La orquestación recupera información de configuración antes de iniciar el procesamiento. De esta manera, se garantiza que la orquestación utilice la misma configuración en caso de que se deshidrate y recupere la hidratación. Para obtener más información acerca de la deshidratación, vea [orquestación deshidratación y rehidratación](../core/orchestration-dehydration-and-rehydration.md).  
  
 El Administrador de pedidos utiliza un valor de los datos de configuración: **TotalStages**, el número total de fases en el proceso de administración de pedidos. El administrador asigna este valor a una variable local, **numStages**. También establece dos variables más conectadas al bucle externo, **fase** y **detener**. El **fase** indica la fase actual y representa el contador del bucle externo; **detener** el valor de detención.  
  
 Por último, el administrador establece la **orderStatus** variable Started y especifica el bucle de procesamiento externo.  
  
## <a name="new-order-processing-loops"></a>Nuevos bucles de procesamiento de pedidos  
 El bucle externo se ejecuta siempre que el valor de la **fase** variable es menor que el valor de la **numStages** variable. Los bucles externos dirigen el procesamiento de cada fase. El bucle interno se ejecuta siempre que se esté procesando una fase. También escucha los cambios posibles del pedido.  
  
### <a name="outer-loop"></a>Bucle externo  
 La orquestación inicia el bucle externo mediante la asignación del mensaje recibido (**NewOrderMgrMsg**) a una variable, **OrderMgrMsg**. A continuación, copia la fase y el estado a la parte de enrutamiento del mensaje. La orquestación también establece la dirección del remitente en el mensaje a la dirección de la **StageCompletionPort**:  
  
```  
OrderMgrMsg.RoutingPart.OrderMgrReturnAddress =   
       StageCompletionPort(Microsoft.XLANGs.BaseTypes.Address);  
```  
  
 La orquestación, a continuación, envía el pedido a la **StagePort**, un puerto de petición-respuesta. La orquestación espera la confirmación de la fase que ha iniciado el procesamiento del pedido. La fase envía un **OrderAck** cuando se inicia el orden de procesamiento de mensajes.  
  
> [!NOTE]
>  El **OrderAck** mensaje es uno de varios en la solución definida por las clases. NET, en lugar de un esquema. Para obtener más información sobre cómo usar las clases de .NET para definir mensajes, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
 Cuando la orquestación recibe la confirmación, asigna la fase a la **currentStage** variable y entra en el bucle interno.  
  
### <a name="inner-loop"></a>Bucle interno  
 El bucle interno se ejecuta siempre que el **currentStage** variable es igual a la **fase** variable; que sea, siempre que se está procesando la fase actual. El cuerpo del bucle es un **escuchar** forma con tres **recepción** formas. La forma situada en la orquestación, **solicitud de pedido**, forma parte del mecanismo de actualización de orden, se describe en la sección siguiente.  
  
 Cuando un pedido finaliza la fase de procesamiento, envía un mensaje a la **StageCompletion** puerto de la **OrderManager** orquestación. Si la fase finaliza de forma repentina debido a un error, envía una **TerminatedMessage**. En este caso, el **OrderManager** produce una excepción. El controlador de excepciones exterior detecta la excepción y envía un mensaje de error para la **OperatorPort**.  
  
 Si la fase envía un **OrderMgrMsg**, **OrderManager** incrementos la **fase** variable. Si existen más fases (fase menor o igual a numStages), la orquestación establece el estado del pedido **OrderMgrMsg** como stage_n_completed, donde n es el número de la fase actual. Si no hubiera más fases, establece el estado del pedido como COMPLETED y sale de los bucles.  
  
## <a name="order-updates"></a>Actualizaciones de pedido  
 El **OrderManager** orquestación escucha las actualizaciones de pedido dentro del bucle de procesamiento interno. Tenga en cuenta que la **recepción** forma utiliza para ello, **OrderRequest**, también se utiliza la **FromBrokerPort**. El empleo de una segunda forma de recepción en el mismo puerto de un bucle, junto con los conjuntos de correlaciones, constituyen un patrón habitual de BizTalk Server, el patrón de convoy. El patrón de convoy se utiliza para garantizar que la misma instancia de una orquestación procesa todos los mensajes conectados con una operación determinada.  
  
 Cuando el administrador de pedidos recibe el primer mensaje conectado a un pedido, inicializa dos conjuntos de correlaciones. La primera, **OrderCorrelation**, usa el identificador de cliente (**CustID**) y el Id. de pedido (**OrderID**). El administrador de pedidos utiliza esta correlación con las fases de procesamiento de pedidos. La correlación de la segunda es la correlación de convoy, **OrderConvoyCorrelation**, que utiliza el estado del pedido (**estado**) además de los Id. de cliente y el ID de pedido. El **OrderRequestReceive** forma usa **OrderConvoyCorrelation** como un conjunto de correlaciones siguientes. Esta configuración de la correlación garantiza que la instancia del administrador de pedidos reciba cambios para el pedido que está procesando.  
  
> [!NOTE]
>  Recuerde que un conjunto de correlaciones es una agrupación de propiedades de mensaje utilizadas para determinar si un mensaje pertenece a una instancia determinada de una orquestación. Para obtener más información, consulte [usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md).  
  
 Cuando el **OrderManager** recibe un mensaje posterior para un pedido, en primer lugar comprueba el tipo de solicitud. Si TERMINATE es el tipo de solicitud, la forma Decisión ejecuta la rama de finalización. De lo contrario, la orquestación realiza una prueba en el mensaje nuevo para ver si se trata de una actualización. Un mensaje de actualización tiene un número de secuencia superior (**SeqNum**) a la solicitud original. Si el número de secuencia del mensaje nuevo es superior, la orquestación comienza el procesamiento del pedido con el mensaje nuevo. Si el mensaje de actualización y el original cuentan con el mismo número de secuencia o el número de secuencia del mensaje de actualización es inferior, existe un error de secuencia. Si los números de secuencia coinciden, el pedido está duplicado y se marca como un error de duplicado.  
  
 Para obtener más información acerca de **SeqNum**, consulte [clave mensajes y campos](../core/key-messages-and-fields.md).  
  
## <a name="final-steps"></a>Pasos finales  
 Después de salir de los bucles, el Administrador de pedidos asigna la dirección de respuesta para el puerto dinámico **CSRCompletionPort**. Seguidamente, el administrador construye el mensaje de estado de finalización, lo envía y prueba si se ha producido un error. En caso de que exista un error, la orquestación ejecuta una forma Finalizar; de lo contrario, simplemente termina.  
  
## <a name="coordinating-with-the-stages"></a>Coordinar con las fases  
 Tanto el **OrderBroker** orquestación y la segunda orquestación de la fase de procesamiento (**CableOrder2**) crea entradas en la base de datos de historial. La orquestación CableOrder2 actualiza la información de historial especificada por el **OrderBroker** orquestación. Para asegurarse de que hay una entrada en la base de datos para actualizar, el **OrderBroker** utiliza la notificación de entrega en el puerto que utiliza la base de datos.  
  
 Configuración asigna el **OrderBroker** puerto de envío para la base de datos de historial para un grupo de puertos de envío que contiene dos puertos: un puerto para la configuración de pruebas (**HistoryInsert-Test-SP**), uno para regular configuración (**HistoryInsert-SP**). Si mantiene los dos puertos del grupo activos, la solución envía mensajes en ambos puertos. Por consiguiente, solicita dos notificaciones de entrega, pero solamente procesa una.  
  
 Para evitar esta situación, dar de baja el puerto de prueba (**HistoryInsert-Test-SP**), o detener la versión de prueba de la aplicación. Para obtener más información acerca de la notificación de entrega, vea [confirmaciones utilizando](../core/using-acknowledgments.md).  
  
## <a name="errors-and-routing-repaired-messagesdesign-choices"></a>Errores y el enrutamiento de mensajes reparados: opciones de diseño  
 La orquestación de controlador de excepción y las orquestaciones utilizadas por las fases de procesamiento de pedido utilizan una orquestación de control de errores (**ErrorHandlerOrch**) para enrutar los pedidos defectuosos para su reparación. El diseño supone que existe un departamento o grupo que arreglará los errores del pedido como sea necesario. El pedido reparado no vuelve a enviarse a través de la orquestación orderbroker (**OrderBroker**). En su lugar, el pedido normalizado se repara en la forma normalizada. En el diseño actual de la solución, la orquestación de controlador enruta el mensaje de error al origen del pedido original. Sin embargo, los pedidos reparados deben enrutarse a un puerto MSMQ en la orquestación de control de errores. (La versión de prueba de la solución utiliza una carpeta de archivos.) El control de errores devuelve el mensaje reparado a una orquestación de llamada.  
  
 Esta solución utiliza este diseño, pues el agente de pedido realiza una normalización y validación significativa del mensaje de pedido. A su vez, el mensaje de pedido que necesita reparación también se encuentra en la forma normalizada. El mantenimiento de la forma normalizada del mensaje impide tener que tratar la diferencia existente entre las formas enviada y normalizada de los mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Lógica del Administrador de procesos](../core/process-manager-logic.md)   
 [Campos y los mensajes de teclado](../core/key-messages-and-fields.md)