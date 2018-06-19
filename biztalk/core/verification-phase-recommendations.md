---
title: Recomendaciones de la fase de comprobación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00663354-ce5d-4391-b835-89940c92c1ce
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25344eafc37f492474b3f0bb36318afaf566829a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288140"
---
# <a name="verification-phase-recommendations"></a>Recomendaciones para la fase de comprobación
Una vez finalizado el código del sistema, está preparado para su plena estabilización y es posible comprobar los criterios de versión. Esta fase se denomina con frecuencia la fase de estabilización. El objetivo definitivo de esta fase es identificar y corregir los errores y demostrar que el sistema está preparado para la producción. Esta fase, pues, conlleva una tanda de pruebas finales en un candidato de versión del sistema.  
  
 Un candidato de versión es una versión del sistema (normalmente, la más reciente) que se considera completa y lo bastante estable para convertirse en la versión de lanzamiento si se superan todas las pruebas de comprobación. Para demostrarlo, es preciso completar correctamente una serie de pruebas funcionales, de rendimiento y de esfuerzo que comprueben que está preparada realmente.  
  
## <a name="test-to-verify-sustainable-throughput-and-latency"></a>Prueba para comprobar el rendimiento sostenible y la latencia  
 Las pruebas de comprobación del rendimiento se han iniciado en paralelo con la fase de implementación, pero es preciso finalizarlas en un candidato de versión que haya demostrado soportar correctamente el conjunto completo de pruebas de los criterios de versión. Lo óptimo es que no se realicen cambios en el candidato de versión durante la última tanda de pruebas, de modo que se pueda confiar en que no se han incluido regresiones. En la práctica, es algo bastante difícil y, a medida que se protegen cambios en la generación, debe evaluarse el riesgo de que exista alguna regresión.  
  
 Por ejemplo, si se incluye un cambio fundamental en un artefacto del sistema como una canalización o una orquestación, es probable que sea preciso volver a ejecutar las pruebas de rendimiento para validar este nuevo candidato de versión.  
  
 Para garantizar que el sistema esté listo para producción, debe comprobar que se ha probado de manera sostenible de extremo a extremo. Esto significa que todas las actividades de operaciones como mantenimiento de base de datos, deben probar las operaciones de consulta y planeado e interrupciones imprevistas, tal como se define en el tema [¿qué es rendimiento sostenible?](../core/what-is-sustainable-performance.md) Ésta es la última oportunidad para certificar está listo para el sistema, por lo que es importante combinar el conjunto completo de pruebas de rendimiento sostenible en la última tanda de pruebas.  
  
## <a name="identify-bottlenecks-and-adjust-hardware-or-solution-to-remove-goal-blockers"></a>Identificar cuellos de botella y ajustar el hardware o la solución para eliminar los obstáculos para la consecución de objetivos  
 En la práctica, es habitual que el banco de pruebas para la última tanda de pruebas está más cercano en producción con respecto a hardware que el desarrollo de las bases de prueba.  Es importante, por lo tanto, para utilizar la oportunidad de durante la última tanda de pruebas para identificar los cuellos de botella nuevos o existentes en el sistema y decidir si su magnitud es suficiente para requerir ajustes en el hardware. Aunque no haya que ajustar el hardware de manera inmediata, identificar los cuellos de botella más notables del sistema proporcionará información valiosa sobre planeamiento y operaciones.  
  
 Por ejemplo, si el sistema soporta el perfil de carga de producción pero se observa que el tiempo de inactividad del disco físico del servidor de cuadro de mensajes es bajo (por ejemplo, inferior al 20%), podrá identificarse como indicador clave del estado de funcionamiento la supervisión de este disco durante la producción. Además, cualquier plan de aumentar la capacidad de carga del sistema podrá incluir el conocimiento de que va a ser necesario mejorar el subsistema de disco.  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de planeación del proyecto por fases](../core/project-planning-recommendations-by-phase.md)   
 [Recomendaciones de la fase de requisitos](../core/requirements-phase-recommendations.md)   
 [Recomendaciones de la fase de diseño](../core/design-phase-recommendations.md)   
 [Recomendaciones de la fase de implementación](../core/implementation-phase-recommendations.md)   
 [Recomendaciones para la fase versión](../core/release-phase-recommendations.md)