---
title: Excepciones personalizadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, compensation blocks
- compensation blocks, process management solutions
- process management solution tutorial, custom exceptions
- Terminate shape [Orchestration Designer], called orchestrations
- process management solution tutorial, errors
ms.assetid: 0c923303-82ad-4a20-9c7c-5e38c477993a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfead2aadc237d27e0fb8ed28a776dd1e4f5c6f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240140"
---
# <a name="custom-exceptions"></a>Excepciones personalizadas
En situaciones donde hay un error irrecuperable, la solución Administración de procesos empresariales utiliza una combinación de controladores de excepción y de excepciones personalizadas.  
  
## <a name="handling-exceptions"></a>Control de excepciones  
 En lugar de usar **Terminate** formas en orquestaciones solicitadas se puede usar el patrón de producir excepciones controladas por la orquestación raíz. Esto permite a la orquestación tomar la decisión de controlar la excepción teniendo el mayor conocimiento posible del contexto. Cuando las orquestaciones subordinadas inician excepciones personalizadas, es posible comunicar más información específica a la orquestación raíz.  
  
 La solución Administración de procesos empresariales sigue este patrón. Hay cuatro raíz, o, las orquestaciones de la solución: **OrderBroker**, **OrderManager**, **CableOrder1**, y **CableOrder2**. Tres de las orquestaciones raíz reciben y controlan excepciones personalizadas: **OrderManager**, **CableOrder1**, y **CableOrder2**.  
  
 Tenga en cuenta que algunas de las orquestaciones raíz utilizan la **Terminate** forma y que la **Terminate** forma aparece justo antes del punto final normal de la orquestación. La orquestación también utiliza el **Terminate** forma si se produce un error para que la orquestación se registre como finalizada, en lugar de como completada, pero con un mensaje de error. Esto permite que la solución haga fácilmente un seguimiento de instancias erróneas además de registrar el error.  
  
 Para obtener más información sobre la **Terminate** forma, consulte [cómo configurar la forma finalizar](../core/how-to-configure-the-terminate-shape.md). Para obtener más información sobre la **ThrowException** forma, consulte [cómo configurar la forma de excepción Throw](../core/how-to-configure-the-throw-exception-shape.md).  
  
## <a name="the-custom-exceptions"></a>Excepciones personalizadas  
 Cada una de las siguientes tres excepciones personalizadas tienen el mismo patrón. Disponer de tipos diferenciados permite que el código distinga excepciones diferentes.  
  
|Exception|Iniciada por (orquestación)|  
|---------------|---------------------------------|  
|**ActivateException**|**Cambio**|  
|**CableOrderException**|**Activar**, **CableOrder1**|  
|**InterruptException**|**CableOrder1**, **CheckInterrupt**, **ErrorHandlerOrch**|  
  
 Todas las excepciones personalizadas están definidas en el **utilidades** ensamblado. Todas las excepciones personalizadas son clases .NET. Todas las clases de excepción personalizada de heredan de .NET **ApplicationException** clase que a su vez hereda de la **System.Exception** clase. Dado que existe una posibilidad de que la excepción pueda estar deshidratada (serializada y almacenada en la base de datos), las excepciones deben implementar un constructor de deserialización. Un constructor de deserialización es un constructor que toma dos argumentos: un objeto SerializationInfo y un objeto StreamingContext. Se utilizará el constructor de deserialización durante la rehidratación de la excepción. Dado que la **ApplicationException** clase ya implementa un constructor de deserialización, el constructor para la excepción personalizada invoca simplemente al constructor de deserialización base (ApplicationException). Por ejemplo, el **InterruptException** incluye el siguiente constructor:  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 Para obtener información más detallada acerca de la serialización personalizada, consulte Serialización personalizada en la Guía del programador de [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)].  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a>Bloques de compensación y controladores de excepción anidados  
 Además de servir como excepciones especializadas, las excepciones personalizadas también sirven en varios lugares como un indicador de ordenación. En el **cambio** orquestación, hay dos lugares en que se debe deshacer la operación de cancelación.  
  
> [!NOTE]
>  Puede que desee leer esta sección con la **cambio** orquestación abierta en Visual Studio.  
  
 En la parte superior de la orquestación, si la llamada a la **cancelar** orquestación se produce un error, el **CancelCompensation** bloque se ejecuta y deshace la **cancelar** transacciones. Si todo funciona correctamente, la orquestación, a continuación, llama a la **activar** orquestación.  
  
 Si el **activar** se produce un error de operación, el **cancelar** transacciones también se deben deshacer. Sin embargo, el controlador de excepciones de la llamada a **activar** no sabe nada sobre la **cancelar** transacciones. Para controlar esto, existe un controlador de excepción para toda la orquestación. Este controlador, porque contiene la **cancelar** ámbito, conozca la **cancelar** transacciones. El controlador detecta la excepción iniciada en el **activar** ámbito (el **ActivateException**), se revierte el **cancelar** transacciones y, a continuación, inicia la excepción de nuevo para que la orquestación que llamó la **cambio** orquestación puede realizar cualquier procesamiento adicional.  
  
 Tenga en cuenta que este diseño sólo compensa el **cancelar** si la **activar** se produce un error. Si el **cancelar** se produce un error y produce una excepción, el **cancelar** nunca habrá tenido lugar y no se debería compensar.  
  
 Para obtener más información acerca de los bloques de compensación y la **compensar** forma, consulte [cómo configurar la forma compensar](../core/how-to-configure-the-compensate-shape.md).  
  
## <a name="see-also"></a>Vea también  
 [Control de excepciones en la solución de administración de procesos empresariales](../core/exception-handling-in-the-business-process-management-solution.md)   
 [La orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md)