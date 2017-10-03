---
title: "Control de interrupciones en la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, pausing
- process management solution tutorial, pausing processing
ms.assetid: 23ce7617-f705-4b7d-8447-221dec9fb196
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b98eae8ee9cbb43354c1cfc48710c70969a929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interrupt-handling-in-the-business-process-management-solution"></a>Control de interrupciones en la solución de administración de procesos empresariales
En esta sección se describe el mecanismo de control de interrupciones utilizado en la solución de administración de procesos empresariales. Mediante el mecanismo de interrupción le permite detener el procesamiento de pedidos cuando se actualiza o se cancela un pedido.  
  
## <a name="interrupt-handling"></a>Control de interrupciones  
 Las orquestaciones que implementan las fases de procesamiento llaman a una orquestación, **CheckInterrupt**, que comprueba una solicitud de interrupción de otra parte del proceso. El **CheckInterrupt** orquestación consta de un **escuchar** forma. Una rama de la **escuchar** forma busca un mensaje con el mismo identificador de correlación que el pedido actual. Si no hay este tipo de mensaje, el **CheckInterrupt** orquestación envía un mensaje de confirmación y ejecuta un **Throw** forma. Dado que las bifurcaciones en un **escuchar** forma se ejecutan de izquierda a derecha, el retraso aparece en la rama derecha. Observe que el retraso es cero (0).  
  
 La combinación de la **escuchar** forma, una rama de recepción y una rama de retraso permite que la orquestación comprobar si hay mensajes. Si hay un mensaje de interrupción, se ejecuta la rama izquierda. Si no hay ningún mensaje, se ejecuta la rama derecha y vuelve a la orquestación de llamada. Se puede enviar un mensaje de interrupción en cualquier momento. Dado que la **CheckInterrupt** orquestación se ejecuta sólo en algunas ocasiones, puede haber un mensaje de interrupción en espera.  
  
 El **OrderManager** establece las interrupciones mediante una llamada a la **Interrupter** orquestación. El **Interrupter** orquestación envía un mensaje de interrupción a la **InterruptPort** y espera una respuesta. La orquestación utiliza la **tiempo de espera** propiedad de los **ámbito** forma que se va a reiniciar el bucle si no se recibe una respuesta. La orquestación continúa enviando el mensaje de interrupción siempre que el ámbito exceda el tiempo de espera antes de recibir una respuesta. Un tiempo de espera indica que la solicitud coincidió con una suscripción pero que no ha habido tiempo para una respuesta. El bucle finaliza si hay una respuesta o si no hay ninguna suscripción a la **InterruptPort**.  
  
 El patrón de respuesta de solicitud de finalización el **OrderManager** utiliza con las fases de proceso es una parte fundamental de la administración de interrupción. Dado que la **OrderManager** espera una respuesta: una confirmación, desde la fase, sabe que la fase ha empezado a ejecutarse antes de continuar. De este modo se garantiza que una fase no puede recibir una interrupción antes de iniciarse. Esto también permite la **OrderManager** saber que, si no hay ninguna suscripción a una interrupción, se ha completado la fase.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento en la solución de administración de procesos empresariales](../core/processing-in-the-business-process-management-solution.md)   
 [Lógica del Administrador de procesos](../core/process-manager-logic.md)   
 [La orquestación de ExceptionHandler](../core/the-exceptionhandler-orchestration.md)