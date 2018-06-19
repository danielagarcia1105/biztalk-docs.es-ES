---
title: Recomendaciones para la fase implementación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04877156-cc32-480b-8410-d26eb073c327
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fce6d7df21f15b40e0312438394859f4b94b7fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257404"
---
# <a name="implementation-phase-recommendations"></a>Recomendaciones para la fase de implementación
En la fase de implementación se toman los requisitos y los productos de la fase de diseño y se implementan mediante las tecnologías apropiadas. En el caso de las pruebas de validación, es en esta fase cuando se completan y automatizan los casos de prueba en preparación de las pruebas de validación. Normalmente, gran parte de las pruebas de las versiones anteriores del sistema también se llevan a cabo durante esta fase, no solo para validar el sistema, sino también para comprobar que no existan problemas con los propios casos de prueba.  
  
## <a name="implement-performance-test-cases"></a>Implementar los casos de pruebas de rendimiento  
 Durante las fases de requisitos y diseño, se definen y diseñan casos de pruebas representativos para demostrar que el rendimiento del sistema cumple o supera los criterios de versión de rendimiento. Durante la fase de implementación, estos casos de prueba se implementan, automatizan y ejecutan inicialmente para comprobar que, a medida que se van completando las distintas partes del sistema, las pruebas están listas para comprobar su rendimiento.  
  
 Es importante automatizar lo más posible la configuración, la ejecución y el análisis de resultados de las pruebas durante la fase de implementación. La cantidad de pruebas de rendimiento puede ser muy elevada y las pruebas individuales pueden tardar mucho en ejecutarse, de modo que automatizar las pruebas aumentará la eficacia de su ejecución, ya que reduce la cantidad de recursos humanos necesarios. Además, prevea la ejecución de las pruebas de comprobación muchas veces durante una tanda de pruebas, a medida que se vayan identificando y corrigiendo los cuellos de botella. Automatizar las pruebas facilita, agiliza y sistematiza la ejecución de las comprobaciones del rendimiento entre las generaciones.  
  
## <a name="build-the-performance-test-bed"></a>Generar el entorno de pruebas de rendimiento  
 Es importantísimo que todas las pruebas de rendimiento se realicen de modo coherente y reproducible. Es fundamental utilizar exactamente el mismo hardware en el que establecer las líneas de base y ejecutar las pruebas para que se puedan comparar los resultados de dichas pruebas. Según la arquitectura de la solución, existen gran cantidad de variables de hardware que pueden afectar a los resultados de manera significativa.  
  
 Por ejemplo, hemos comprobado que la memoria caché disponible, incluso en servidores que son idénticos en todos los demás aspectos, afecta en gran medida a los resultados aunque al observar la configuración de los servidores no se note a simple vista que ambos tienen distintos niveles de caché. Asegurarse de que las pruebas se ejecuten en entornos de pruebas que no se modifican entre una ejecución y la siguiente permite eliminar el problema de la comparabilidad. Si es imprescindible cambiar la configuración del hardware, por ejemplo, para ajustarlo a una nueva estimación de tamaño, entonces deberán establecerse de nuevo las líneas de base para que se puedan efectuar comparaciones.  
  
## <a name="begin-performance-validation-testing"></a>Iniciar las pruebas de validación del rendimiento  
 Las pruebas de rendimiento casi siempre comienzan en paralelo con la implementación de prueba.  Casi nunca es demasiado pronto para empezar a validar los criterios de versión, puesto que cuando antes se empiece, antes se podrá reaccionar en caso de descubrirse algún problema.  
  
 La consideración principal al iniciar las pruebas formales es si el sistema, o una parte de él, que se somete a las pruebas, está preparado. Determinar si el sistema está o no preparado puede ser una cuestión bastante subjetiva, pero deben tenerse en cuenta los factores siguientes:  
  
 ¿Está completado el código de la ruta del sistema que se va a probar? Si todavía falta una porción importante de código por agregar a la ruta, puede ser conveniente centrar los esfuerzos en otro aspecto hasta que la "masa crítica" esté preparada.  
  
 ¿Se han ejecutado correctamente las pruebas funcionales en el sistema? Puede resultar muy pesado, además de ineficaz, configurar y comenzar las pruebas de rendimiento en un sistema o subsistema para descubrir que hay algún tipo de problema funcional que impide continuar con las pruebas de rendimiento. Asegúrese de que la ruta se haya sometido a las pruebas funcionales suficientes antes de comenzar las pruebas de rendimiento.  
  
 ¿Cuál es el nivel de riesgo del sistema o el subsistema que se va a probar? Las primeras rutas del sistema que hay que investigar son aquéllas que conllevan el mayor nivel de riesgo en relación con el cumplimiento de los criterios de versión. No nos cansaremos de insistir en la importancia de identificar los cuellos de botella del sistema en las fases más tempranas del ciclo del proyecto, a fin de contar con el tiempo suficiente para realizar las modificaciones necesarias.  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de planeación del proyecto por fases](../core/project-planning-recommendations-by-phase.md)   
 [Recomendaciones de la fase de requisitos](../core/requirements-phase-recommendations.md)   
 [Recomendaciones de la fase de diseño](../core/design-phase-recommendations.md)   
 [Recomendaciones de la fase de comprobación](../core/verification-phase-recommendations.md)   
 [Recomendaciones para la fase versión](../core/release-phase-recommendations.md)