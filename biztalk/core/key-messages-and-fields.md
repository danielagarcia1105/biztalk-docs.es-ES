---
title: Mensajes y campos clave | Documentos de Microsoft
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
ms.assetid: 77db0706-dfdc-48b0-8ca4-bae7ab2d7641
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 524b5f361495d9509809a9229362d28a18712239
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="key-messages-and-fields"></a>Campos y los mensajes de teclado
Esta sección describen brevemente los mensajes de teclado y campos controladas el **OrderBroker** y **OrderManager** orquestaciones. Para obtener una lista completa de mensajes de la aplicación, consulte [referencia de mensaje para la solución de administración de procesos empresariales](../core/message-reference-for-the-business-process-management-solution.md).  
  
## <a name="order-messages"></a>Mensajes de pedido  
 Mensajes de pedido de la **OrderBroker** son mensajes de varias partes. Una parte contiene la información de enrutamiento y la otra parte contiene la información de pedido. La clase .NET que define la parte de enrutamiento de mensaje convierte todos sus campos en campos distintivos para que una orquestación pueda tener acceso a todos los miembros de la clase como propiedades de mensaje. Las clases también incluyen campos promocionados en la clase de enrutamiento para que los mensajes sean enrutables. Todos los campos promocionados también son campos distintivos para que se puedan programar y hacer referencia a estos con notaciones menos complejas.  
  
 Para obtener más información sobre cómo usar las clases de .NET para definir mensajes, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
## <a name="identifying-orders"></a>Identificar pedidos  
 La solución utiliza tres campos en la información de enrutamiento para identificar un pedido. De estos tres, dos identifican el orden: el identificador de pedido (**OrderID**) y el identificador del cliente (**CustomerID**). Sin embargo, aunque estos dos campos identifican un pedido, puede haber más de una instancia de un pedido. Por ejemplo, un cliente podría solicitar una instalación de cable estándar nueva y llamar después para modificar el pedido a una instalación de cable deluxe. Es poco probable que se haya finalizado el pedido original antes de que se reciba el pedido actualizado. De esta forma se crean dos instancias del pedido.  
  
 Para distinguir entre las instancias de los pedidos, la solución utiliza un número de secuencia de pedido único (**SeqNum**). Los tres campos **OrderID**, **CustomerID**, y **SeqNum** identificar de forma exclusiva una instancia de un pedido.  
  
 Por último, dado que la solución utiliza números incrementales para la **SeqNum**, la solución puede distinguir una actualización del pedido original, la actualización tiene un valor superior **SeqNum**.  
  
> [!NOTE]
>  La solución se basa en los sistemas que crean solicitudes de pedidos para asignar valores ascendentes a **SeqNum**. Vea el código subyacente de la página ASP para el servicio web de entrada, **CSRMainForm.aspx.cs**y la asignación que convierte la solicitud a un pedido, **CSR_OrderRequest_To_Order.btm** para los nombres de los campos implicados.  
  
## <a name="status"></a>Estado  
 El **OrderBroker**, **OrderManager**, y sus orquestaciones satélite utilizan dos campos en la parte de enrutamiento del mensaje de orden para realizar el seguimiento de estado: **estado**y **Fase**. El **estado** campo realiza un seguimiento del estado de la orden. En la tabla siguiente se describe los valores para la **estado** campo.  
  
|Valor|Donde se establece|Description|  
|-----------|---------------|-----------------|  
|ACCEPTED|OrderBroker|El pedido puede pasar a OrderManager.|  
|COMPLETED|OrderManager|El procesamiento del pedido completo ha finalizado sin errores.|  
|ERROR|OrderManager|Se ha detectado un error en el pedido.|  
|ORDERMANAGER-EXCEPTION|OrderManager|Se ha producido una excepción en OrderManager al procesar el pedido.|  
|STAGE_n_COMPLETED|OrderManager|Indica que la fase n, donde n es un número, ha finalizado sin errores.|  
|STARTED|OrderManager|Se ha iniciado el procesamiento del pedido.|  
|TERMINATED|OrderManager|Se ha detenido el procesamiento del pedido debido a una cancelación.|  
  
## <a name="stage"></a>Fase  
 El **OrderManager** utiliza la **fase** campo en la parte de enrutamiento para indicar la fase del procesamiento de un mensaje. El campo se usa en filtros que determinan qué orquestación satélite procesa el mensaje. El **OrderManager** establece inicialmente **fase** a uno (1). Cuando finaliza el orden o se completa, el **OrderManager** establece **fase** en el valor de una variable de orquestación **detener**.  
  
## <a name="requesttype"></a>RequestType  
 El **OrderManager** también usa el **RequestType** campo del mensaje del pedido. Si el valor del campo es TERMINATE, finaliza el pedido. La orquestación omite todos los demás valores de la **RequestType** campo y se basa en los números de secuencia de orden para que reconozca las actualizaciones y duplicados. En caso contrario, el **OrderBroker** establece la **RequestType** campo en el valor de la **estado** campo en el mensaje del sistema de servicio de proveedor o cliente.  
  
## <a name="ordertypecode-ordertype-and-serviceclass"></a>OrderTypeCode, OrderType y ServiceClass  
 El tipo del pedido está en el **OrderTypeCode** campo del mensaje del pedido. El **OrderBroker** establece su valor en el valor de la **OrdTypeCode** campo en el mensaje procedente de sistema del servicio de cliente o de sistema del proveedor. En la tabla siguiente se muestra los valores posibles para **OrderTypeCode**:  
  
|Valor|Description|  
|-----------|-----------------|  
|NS|Instalación de cable estándar nueva.|  
|ND|Instalación de cable deluxe nueva.|  
|XS|Cancelar instalación de cable estándar.|  
|XD|Cancelar instalación de cable deluxe.|  
|CS|Cambiar instalación de cable estándar.|  
|CD|Cambiar instalación de cable deluxe.|  
|UNKNOWN|Desconocido.|  
  
 Más adelante, el **validar** orquestación utiliza el motor de reglas de negocio para traducir estos valores en dos campos distintos, **OrderType** y **ServiceClass**. El **validar** orquestación llama a la primera fase, de procesamiento de pedidos **CableOrder1**.  
  
 En la tabla siguiente se proporciona los valores para la **OrderType**:  
  
|Valores de OrderTypeCode|Valores de OrderType|  
|--------------------------|---------------------|  
|NS, ND|ACTIVATE|  
|XS, XD|CANCEL|  
|CS, CD|CHANGE|  
|Combinación no válida.|INVALID|  
  
 Los valores de **ServiceClass** son las letras individuales correspondientes, **S** estándar, o **d.** para deluxe.  
  
## <a name="additional-identifiers"></a>Identificadores adicionales  
 La solución también utiliza un identificador para cada pedido específico. Este identificador, **RequestId**, debe ser único en todos los pedidos. El servicio Web de entrada le asigna automáticamente un GUID. Los mensajes enviados mediante la entrada por lotes deben incluir un valor para el campo. El campo es **RequestID** en el esquema del pedido. El **OrderBroker**, sin embargo, utiliza el **CSR_OrderRequest** esquema para procesar los pedidos. El campo aparece como **ReqId** en este esquema y es una propiedad distintiva.  
  
 La solución utiliza la **RequestId** para formar el identificador de actividad utilizado en el sistema de seguimiento de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Lógica del Administrador de procesos](../core/process-manager-logic.md)   
 [Flujo de pedidos a través del Administrador de proceso](../core/order-flow-through-the-process-manager.md)   
 [Construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md)   
 [Referencia de mensajes para la solución de administración de procesos empresariales](../core/message-reference-for-the-business-process-management-solution.md)