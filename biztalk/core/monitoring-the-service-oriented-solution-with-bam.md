---
title: El servicio de supervisión orientada a servicios solución con BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, service solutions
- service solution tutorial, monitoring
- OrchestrationEventStream object
ms.assetid: 9b251580-9371-490e-9218-0ce3f6b00fa6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1aeaec2513ebe3c6d7fe62ef542b6f044bca56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264116"
---
# <a name="monitoring-the-service-oriented-solution-with-bam"></a>El servicio de supervisión orientada a servicios solución con BAM
La solución supervisa la actividad en todas las versiones de la **CustomerService** orquestación mediante la actividad supervisión económica (SAE) API. Más concretamente, usa el nuevo **OrchestrationEventStream** objeto.  
  
## <a name="what-is-the-orchestrationeventstream-object"></a>¿Qué es el objeto OrchestrationEventStream?  
 El nuevo **OrchestrationEventStream** objeto permite el seguimiento y supervisión de las orquestaciones. La información recopilada coincide desde el punto de vista de las transacciones con el estado de la orquestación. Por ejemplo, la instancia de host de la orquestación se reinicia a mitad de la ejecución de la orquestación, la instancia de la orquestación se reinicia desde el último punto de persistencia de la instancia. El **OrchestrationEventStream** clase garantiza que los datos capturados son transaccionalmente coherentes con el último punto de persistencia de la instancia de orquestación. Todos los **OrchestrationEventStream** métodos son estáticos, por lo que la orquestación no se necesita crear una instancia del mismo.  
  
> [!NOTE]
>  Para usar el **OrchestrationEventStream** objeto, debe agregar las referencias a la **Microsoft.BizTalk.Bam.XLANGs** y **Microsoft.BizTalk.Bam.EventObservation** ensamblados. Aunque la **OrchestrationEventStream** objeto se encuentra en la **Microsoft.BizTalk.Bam.EventObservation** espacio de nombres, reside en el **Microsoft.BizTalk.Bam.XLANGs** ensamblado.  
  
 Aunque el Editor de perfiles de seguimiento (TPE) es el modo recomendado de utilizar SAE, TPE no puede recopilar los valores de variable de la orquestación, ni tampoco puede controlar los objetos personalizados. La solución utiliza la API de SAE para solucionar estas limitaciones.  
  
 Para obtener información general acerca de BAM, consulte [usando Business Activity Monitoring](../core/using-business-activity-monitoring.md). Para obtener información sobre el Editor de perfiles de seguimiento (TPE), consulte [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md).  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>Ajustar el objeto OrchestrationEventStream  
 Ajustes de la solución orientada a servicios el **OrchestrationEventStream** clase con la **ServiceLevelTracking** clase. El **ServiceLevelTracking** clase proporciona métodos de hitos específicos de la aplicación y oculta algunos de los detalles del uso **OrchestrationEventStream**.  
  
 Como en **OrchestrationEventStream**, todos los métodos de **ServiceLevelTracking** son estáticos. Por tanto, la orquestación o componente personalizado no necesita crear una instancia de ésta. El método que empieza el seguimiento de una actividad, **TrackingBeginRequest**, devuelve un identificador de instancia de actividad único. Todos los eventos de seguimiento posteriores deben estar asociados con este Id. de instancia de actividad para capturar los datos de nivel de servicio correctamente, porque es único para la instancia de la **CustomerService** orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un servicio en la solución orientada a servicios](../core/developing-a-service-oriented-solution.md)   
 [Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md)