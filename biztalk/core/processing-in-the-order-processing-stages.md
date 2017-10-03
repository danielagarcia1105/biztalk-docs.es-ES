---
title: En las fases de procesamiento de orden de procesamiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 698005da-1ba8-4972-83db-f5ae45fd6a83
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a8eae6b814af36d0ea07065726ca66518984703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-order-processing-stages"></a>Procesar en las fases de procesamiento de pedidos
La solución de administración de procesos empresariales incluye dos fases, la **CableOrder1** y **CableOrder2** orquestaciones, que llevan a cabo las acciones de procesamiento de pedidos. Para obtener más información acerca de cómo se dividió el proceso de pedido en fases, vea [número de fases de procesamiento](../core/number-of-processing-stages.md).  
  
 Ambas fases de procesamiento comienzan cuando reciben un mensaje de pedido y responden con un mensaje de estado para la **OrderManager** orquestación una vez que se ha iniciado. De forma similar, ambos devuelven un mensaje a la **OrderManager** para indicar si la fase completó o finalizó con un error. Para obtener más información acerca de la conexión entre el **OrderManager** orquestación y las fases de procesamiento, vea [enlace directo de socio inverso](../core/inverse-direct-partner-binding.md).  
  
 Las dos fases de procesamiento usan la autocorrelación, puertos dinámicos para devolver información de nuevo a la **OrderManger**. Con puertos dinámicos, las orquestaciones copian la dirección del puerto del mensaje al puerto de envío.  
  
 Todos los mensajes de pedido las fases de procesamiento de recepción son los mensajes de pedido normalizado, canónica creados en el **OrderBroker**.  
  
> [!NOTE]
>  Debido a la longitud de la **CableOrder1** y **CableOrder2** orquestaciones, puede que desee leer esta sección con las orquestaciones abiertas en Microsoft Visual Studio.  
  
## <a name="the-cableorder1-orchestration"></a>La orquestación CableOrder1  
 El **CableOrder1** orquestación empieza cuando se recibe un mensaje de pedido. Copia la dirección de respuesta del mensaje al puerto de finalización de la fase. A continuación, genera un mensaje de confirmación y lo envía como respuesta a la **BeginStagePort** de puerto y, a continuación, guarda la información de enrutamiento en una variable local.  
  
 A continuación, la orquestación obtiene la información de configuración de SSO. Para obtener más información acerca de cómo la solución usa SSO, vea [usar SSO de forma eficaz en la solución de administración de procesos empresariales](../core/using-sso-efficiently-in-the-business-process-management-solution.md).  
  
 La orquestación, a continuación, crea una instancia de la **OrderHandler** de objeto para comunicarse con los procesos de back-end, comprueba la validez del mensaje, analiza el mensaje, determina el tipo de servicio y qué acción se debe realizar. Dependiendo de la acción que se va a realizar, llama a una de las orquestaciones de acción de pedido **activar**, **cambio**, o **cancelar** y pasa el **OrderHandler** objeto a la orquestación.  
  
 El **CableOrder1** orquestación, a continuación, vuelve una interrupción, envía un mensaje para el grupo de instalaciones y espera recibir. Si la orquestación recibe un mensaje de respuesta del grupo de instalaciones, continúa el procesamiento. De lo contrario, si se produce una interrupción, la orquestación inicia una excepción de interrupción.  
  
 Finaliza la orquestación mediante la construcción de un mensaje de finalización y enviarlo a través de la **StageCompletion** puerto.  
  
## <a name="the-cableorder2-orchestration"></a>La orquestación CableOrder2  
 La orquestación CableOrder2 realiza los mismos pasos iniciales que la orquestación CableOrder1 para la información de enrutamiento, información de configuración de SSO y la creación de una instancia de la **OrderHandler** objeto.  
  
 La orquestación, a continuación, busca una interrupción y pasa el **OrderHandler** objeto en una llamada a la **completar** orquestación. A continuación, la orquestación crea un mensaje de estado de pedido, actualiza el historial de pedidos y envía un mensaje de finalización a través de la **StageCompletion** puerto.  
  
## <a name="see-also"></a>Vea también  
 [Control de versiones de la solución de administración de procesos empresariales](../core/versioning-the-business-process-management-solution.md)   
 [Procesamiento en la solución de administración de procesos empresariales](../core/processing-in-the-business-process-management-solution.md)