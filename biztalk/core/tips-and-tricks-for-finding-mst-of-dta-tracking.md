---
title: Sugerencias y trucos para encontrar MST de seguimiento de DTA | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d72e4ac-d952-4cff-9a65-491e20945d40
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9faaaf7ebb47ac7ec18d8df6d8cb7c6ebd48d7f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tips-and-tricks-for-finding-mst-of-dta-tracking"></a>Sugerencias y trucos para encontrar MST de seguimiento de DTA
Por definición, MST es una prueba comparativa para medir de forma reproducible el rendimiento del sistema mediante una carga constante. A continuación se indican las situaciones donde resulta especialmente útil conocer el MST.  
  
1.  **Cuando necesite que la latencia más baja del sistema**. Si se supera el MST se produce trabajo acumulado en el sistema, lo que ocasiona que aumente la latencia de los mensajes. Incluso si el trabajo acumulado solo es temporal, éste tiene un efecto negativo inmediato en la latencia. Por lo que, si conoce los sistemas, MST le dirá el rendimiento máximo absoluto que debería esperar conseguir antes de que la latencia del procesamiento individual de mensajes aumente de forma considerable (por ejemplo, de segundos a minutos dependiendo de la configuración).  
  
2.  **Cuando se comparan con otros sistemas**. Por ejemplo, si desea comprobar que está obteniendo el MST esperado en comparación con otro sistema (como puede ser el escenario que se describe en este tema, un caso práctico u otro sistema del entorno); al medir MST mediante una entrada continua se obtiene un estándar que puede reproducirse y que no es ambiguo para la comparación.  
  
 Sin embargo, medir MST puede ser un proceso muy lento. Por tanto, antes de realizar una operación tan extensa, debería evaluar las ventajas. La mayoría de los sistemas de producción no experimentarán una entrada continua como la que ha medido MST sino, más bien, una carga que cambia con el tiempo. Este perfil de carga es el que se debe comprobar en última instancia para certificar un sistema antes de la producción. Afortunadamente, puede usar la misma técnica que se usó para medir MST y evaluar, de este modo, la sostenibilidad del perfil de carga de producción. Solo tiene que ejecutar el perfil de carga durante el tiempo suficiente para que se incluya una o varias ventanas de retención de datos de la base de datos BizTalkDTADb y observar los indicadores clave de rendimiento (KPI).  
  
 Es importante que inicie las ejecuciones de prueba, ya sea MST o perfiles de carga, con una base de datos BizTalkDTADb vacía. Los datos que se almacenan en la base de datos BizTalkDTADb están sujetos a limitación temporal y si no se vuelven a obtener desde cero para cada ejecución de prueba, se pueden falsear los resultados. Según la ventana de retención de datos, esto puede aumentar de forma considerable el tiempo que se tarde en encontrar MST. Para reducirlo, el ajuste de la carga "sobre la marcha" durante las ejecuciones de prueba puede resultar útil a la hora de poner a cero el MST de forma más rápida.  
  
 Por ejemplo, si encuentra que ha pasado el primer tiempo de la ventana de retención y los KPI le indican que queda capacidad para un rendimiento mayor (por ejemplo, el tiempo de inactividad del disco se encuentra todavía por encima de cero), puede aumentar la carga de forma incremental y observar el efecto. Sin embargo, una vez definida de nuevo la estimación de MST de este modo, es importante que realice una ejecución de prueba comenzando por una base de datos BizTalkDTADb vacía para validar la estimación.  
  
## <a name="recommendations"></a>Recomendaciones  
 El seguimiento de la arquitectura del sistema en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es capaz de una gran variedad de información de seguimiento y que se debe administrar y supervisar con precaución. Como indica el MST, los factores que afectarán al rendimiento del sistema en mayor medida son los siguientes:  
  
-   El rendimiento deseado del sistema.  
  
-   El volumen de información sometido a seguimiento para cada mensaje e instancia de servicio del sistema. Esto determinará con qué rapidez aumenta el tamaño de la base de datos BizTalkDTADb y, en última instancia, con qué frecuencia se debe purgar la base de datos BizTalkDTADb para evitar que se retrase.  
  
-   El tiempo que desee conservar los datos en la base de datos de BizTalkDTADb, es decir, la ventana de retención de datos. Cuanto más tiempo esté la ventana, más crecerá la base de datos BizTalkDTADb, lo que afecta al rendimiento.  
  
-   Si archiva los datos de la base de datos BizTalkDTADb y los purga, o solo los purga para mantener el tamaño de la base de datos.  
  
 El proceso de encontrar el rendimiento máximo sostenible para el seguimiento en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implica tres indicadores clave de rendimiento:  
  
-   El tiempo de inactividad del disco físico para el subsistema de discos de archivos de datos DTAdb.  
  
-   La profundidad de la cola  
  
-   La profundidad de BizTalkDTADbData  
  
 Realice búsquedas en el MST de los sistemas o valide el rendimiento del perfil de producción supervisando estos tres indicadores clave de rendimiento en busca de lo siguiente:  
  
-   Profundidad de la tabla trackingdata y de cola estable  
  
-   El tiempo de inactividad del disco físico de archivos de datos de la base de datos BizTalkDTADb se aproxima, aunque no tiende continuamente a, cero.  
  
 El uso de las características de seguimiento de DTA afecta al rendimiento.  El seguimiento predeterminado puede realizar el seguimiento de más elementos de los necesarios una vez que la solución se encuentra en producción, pero puede hacer más fáciles el desarrollo, la comprobación inicial y la depuración al proporcionar una amplia información de resolución de problemas. Por tanto, se recomienda dejar activado el seguimiento predeterminado durante el desarrollo y la comprobación inicial. Una vez que una solución implementada en BizTalk está estable y lista para la certificación de la producción, incluida la comprobación del rendimiento, se recomienda que examine con cuidado la cantidad de información a la que se debe realizar el seguimiento en producción y el tiempo que debe permanecer en la base de datos BizTalkDTADb, así como que la ajuste de forma correspondiente.  
  
 Por ejemplo, si no es necesario realizar el seguimiento del cuerpo de los mensajes para evitar el rechazo y solucionar problemas, no active el seguimiento del cuerpo del mensaje. Para ilustrar este punto, en el escenario de ejemplo descrito en [escenarios de prueba para medir el rendimiento máximo Sostenible de DTA seguimiento](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md), cuando se ha eliminado el cuerpo del mensaje componente de la configuración de seguimiento de seguimiento, se duplicó el MST a 40 mensajes por segundo.  
  
 Asimismo, tenga en cuenta que incluso cuando surgen problemas, en muchos casos (aunque no en todos), los mensajes se suspenden en la base de datos de cuadro de mensajes y se pueden recuperar e inspeccionar sin necesidad de realizar un seguimiento del cuerpo de los mensajes.  
  
 Céntrese en la sostenibilidad de la carga que coloca en el sistema:  
  
-   ¿Puede el sistema mantener el perfil de carga de producción de forma indefinida incluso con actividades normales de mantenimiento?  
  
-   ¿Qué ocurre si sucede algo que provoca que el sistema mantenga trabajo acumulado, como una interrupción de la base de datos BizTalkDTADb planeada o no planeada?  
  
 Es conveniente establecer objetivos que se basen en peores escenarios de casos y comprobar estos objetivos. Por ejemplo, si sabe que hay un ciclo de mantenimiento planeado y periódico que hará que la base de datos BizTalkDTADb se quede sin conexión, simule esta interrupción durante una ejecución de prueba para evaluar la capacidad del sistema para recuperarse del trabajo acumulado resultante.  
  
## <a name="see-also"></a>Vea también  
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [Comprender el comportamiento del rendimiento de seguimiento de DTA](../core/understanding-dta-tracking-performance-behavior.md)   
 [Escenarios de prueba para medir MST de seguimiento de DTA](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [Instrucciones para ajustar el tamaño de la base de datos de seguimiento](../core/tracking-database-sizing-guidelines.md)