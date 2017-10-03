---
title: Recomendaciones de la fase de requisitos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b510313-c3a7-42bc-9c9b-336c927a5d4a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d945e50d9c7b8f0a9feae5e0f93a4766d108c695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-phase-recommendations"></a>Recomendaciones para la fase de requisitos
La principal entrega relacionada con la fase de requisitos es una especificación de requisitos, o una especificación funcional con los requisitos que incluyen objetivos de rendimiento. Al determinar estos objetivos, es muy importante que participen los usuarios finales y los propietarios empresariales del sistema, a fin de garantizar la obtención de un perfil preciso del rendimiento.  
  
## <a name="establish-performance-criteria"></a>Establecer los criterios de rendimiento  
 Desde la perspectiva del rendimiento, la parte más importante de la especificación funcional que se crea durante esta fase es la definición de objetivos de rendimiento detallados para el proyecto y el establecimiento de los criterios de versión para ese rendimiento. Existen tres componentes vitales para definir los criterios de rendimiento:  
  
-   Una curva que defina el rendimiento como una función de tiempo.  
  
-   Un requisito de rendimiento asociado con la función de rendimiento.  
  
-   Una distribución de tamaños y tipos de archivo.  
  
 Estos criterios se abordan en [¿qué es rendimiento sostenible?](../core/what-is-sustainable-performance.md)  
  
 Los criterios de versión para el rendimiento de una aplicación se extraen a partir de los objetivos de rendimiento. Estos criterios representan un comportamiento conseguible y medible que se puede demostrar con pruebas. La aplicación no pasará a la fase de versión hasta que se cumplan todos los criterios de versión o, en caso de que no sea posible, se hayan identificado todas las excepciones a los criterios de versión.  
  
 Es muy importante establecer los criterios de versión durante las primeras fases del ciclo del producto. De este modo, todos los afectados sabrán cuáles son los objetivos y cuáles las consecuencias de no alcanzarlos antes de la aprobación del diseño y la implementación.  
  
 Además, los casos de las pruebas de rendimiento se basarán en cómo hay que medir los criterios de versión, de modo que el grado de detalle de estos últimos debe ser suficiente para evitar cualquier confusión. Por ejemplo, al establecer un rendimiento concreto que debe lograrse, se debe incluir:  
  
-   El hardware en el que se ejecutará, por ejemplo: el número y tipo de servidores, el tipo y la velocidad del disco, etc.  
  
-   Qué escenario se va a probar, por ejemplo: qué ruta seguirán los mensajes dentro de la aplicación.  
  
-   Cómo se va a medir, por ejemplo: contadores de rendimiento, código personalizado, medición de los momentos de llegada de los mensajes en un recurso compartido, etc.  
  
 Para juzgar si un criterio de versión está bien constituido, cualquier persona debe ser capaz de leerlo tal y como esté documentado y entender cómo crear un caso de prueba que demuestre si se cumple.  
  
## <a name="identify-performance-risks"></a>Identificar riesgos para el rendimiento  
 Una vez establecidos con el detalle suficiente los objetivos de rendimiento y los criterios de versión correspondientes, se puede efectuar una evaluación inicial de las áreas de riesgo para el rendimiento. La finalidad de este análisis es identificar partes de la aplicación que puedan requerir una atención de diseño especial, soluciones alternativas o incluso su eliminación, para cumplir los criterios deseados.  
  
 Por ejemplo, cada tipo de adaptador de transporte tiene sus propias características de rendimiento y escala. Si el rendimiento deseado supera la capacidad de uno o varios tipos de adaptadores (ya sea de recepción o envío), es posible que deban investigarse alternativas para escalar el adaptador.  
  
## <a name="estimate-sizing"></a>Estimar el tamaño del hardware  
 Según los criterios y objetivos establecidos, nunca es pronto para iniciar el proceso de estimación del tamaño del hardware que se necesitará para cumplir los objetivos. Al igual que con cualquier esfuerzo de estimación del tamaño, las estimaciones deben basarse en los resultados reales de las pruebas. Durante las fases iniciales de un proyecto, estos resultados deben proceder de fuentes externas. Puede leer casos prácticos en BizTalk Server Developer Center en [http://go.microsoft.com/fwlink/?LinkId=49339](http://go.microsoft.com/fwlink/?LinkId=49339). En los casos de estudio se proporcionan detalles sobre los escenarios probados, el hardware en que se realizaron las pruebas y la configuración utilizada para ellas. Puede extrapolar a partir del rendimiento alcanzado en estos casos de prueba para obtener una estimación de tamaño inicial para el sistema.  
  
 Tenga en cuenta que no hay ningún modelo predictivo ni simulación que permita calcular con precisión tamaño del sistema de cualquier aplicación arbitraria que se ejecutan en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]es una plataforma en la que se puede implementar gran variedad de soluciones de aplicaciones, cada uno con su propio rendimiento. En consecuencia, aunque una estimación basada en los resultados de los casos de estudio ofrece un punto de partida adecuado con fines de planeamiento, es prácticamente seguro que será preciso ajustar el tamaño definitivo del sistema para todas las aplicaciones, con exclusión, quizás, de aquéllas con las arquitecturas más simples.  
  
## <a name="plan-for-sufficient-testing"></a>Planear pruebas suficientes  
 Como hemos indicado antes, en la actualidad no existe ningún modelo ni simulación que permita calcular con precisión el hardware necesario para cumplir los objetivos de rendimiento. Esto significa que la única manera de comprobar realmente si un sistema es capaz de cumplir los objetivos es probarlo en un hardware de nivel de producción. Es decir, llevar a cabo casos de prueba en un hardware lo más parecido posible a la configuración de producción.  
  
 Esta parte del planeamiento es vital, y combina los principios de rendimiento sostenible, una comprensión en profundidad de los perfiles de rendimiento y el conocimiento de los criterios de versión para el rendimiento. Usando los perfiles de rendimiento obtenidos mediante la extrapolación a partir de datos existentes, deben derivarse casos de prueba que midan de manera sistemática los criterios de versión. Los casos de prueba deben ejecutarse teniendo siempre presente la sostenibilidad. Para obtener ejemplos sobre pruebas de sostenibilidad, consulte los temas siguientes:  
  
-   [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)  
  
-   [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de planeación del proyecto por fases](../core/project-planning-recommendations-by-phase.md)   
 [Recomendaciones de la fase de diseño](../core/design-phase-recommendations.md)   
 [Recomendaciones de la fase de implementación](../core/implementation-phase-recommendations.md)   
 [Recomendaciones de la fase de comprobación](../core/verification-phase-recommendations.md)   
 [Recomendaciones para la fase versión](../core/release-phase-recommendations.md)