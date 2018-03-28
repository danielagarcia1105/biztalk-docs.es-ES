---
title: ¿Qué es rendimiento sostenible? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- reliability, sustainable performance
- performance, goals
- performance, sustainable performance
- planning, performance
- performance, planning
- sustainable performance
ms.assetid: 4b18b976-7714-431f-8976-f40a1016d5f3
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 276ce104d8667166d020b33b2f1fb4e7bfb98dbc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="what-is-sustainable-performance"></a>¿Qué es rendimiento sostenible?
Cuando se planea la sostenibilidad estimada de un sistema, es fundamental pensar en términos de sostenibilidad a largo plazo. Las principales consideraciones son:  
  
-   **Objetivos de rendimiento y perfiles de carga**: no puede tener muchos detalles en cuanto a los objetivos de rendimiento y perfiles de carga. Las pruebas y la certificación de aptitud estarán basadas en la capacidad para controlar estas cargas a largo plazo.  
  
-   **Otras actividades y los procesos que compiten por los recursos de servidor**: no se encuentra casi la carga de mensajes. Hay otros procesos y actividades que tienen lugar en los servidores que afectan al rendimiento, como el mantenimiento de las bases de datos y las consultas del cuadro de mensajes.  
  
-   **Planeadas y no planeadas interrupciones del suministro eléctrico y tiempo de inactividad**: eventos de control de tráfico y trabajo pendiente puede cambiar el perfil de carga efectivo de mensaje.  
  
 A la hora de pensar en la creación de sistemas sostenibles y las pruebas para certificarlos, asegúrese de tener en cuenta estos factores y planear de acuerdo con ellos.  
  
## <a name="is-your-performance-sustainable"></a>¿Es sostenible el rendimiento?  
 Al hablar de rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], definimos el rendimiento máximo sostenible del siguiente modo:  
  
-   La mayor carga de tráfico de mensajes que puede administrar un sistema indefinidamente en un entorno de producción.  
  
 Si bien esto parece sencillo, hay muchos factores que debe considerar a la hora de evaluar si una solución, ejecutándose en un conjunto de hardware concreto, podrá admitir o no la carga del día a día al pasarla a un entorno de producción.  
  
 Antes de pasar la solución a producción, considere los siguientes factores para evaluar si la solución puede administrar la carga más alta de tráfico de mensajes indefinidamente:  
  
-   Objetivos de rendimiento deseado y perfiles de producción y latencia.  
  
-   Otros procesos que se ejecutan en el mismo hardware, como:  
  
    -   Solución de problemas y supervisión habituales  
  
    -   Mantenimiento de las bases de datos, como trasvases, copias de seguridad, purga, mantenimiento de índices y actualizaciones de estadísticas.  
  
    -   Otras aplicaciones  
  
-   Interrupciones del suministro eléctrico planeadas y no planeadas, como:  
  
    -   Inactividad de sitios de asociados que bloquea el envío o la recepción de mensajes  
  
    -   Tiempo de inactividad debido al mantenimiento habitual del sistema  
  
## <a name="know-your-performance-goals"></a>Conozca sus objetivos de rendimiento  
 Para poder evaluar si la solución es sostenible, debe tener muy claros los objetivos de producción esperados. Sin un objetivo claro, no puede evaluar la aptitud. Una serie de objetivos de rendimiento bien planteados es fundamental, puesto que orientará sus estrategias a la hora de realizar las pruebas y la certificación. Los objetivos de rendimiento deben tener los siguientes elementos:  
  
-   Una curva que defina el rendimiento como una función de tiempo. Estas funciones pueden ser desde extremadamente sencillas hasta muy complejas.  
  
-   Un requisito de rendimiento asociado con la función de rendimiento.  
  
-   Una distribución de tamaños y tipos de archivo.  
  
### <a name="example-1"></a>Ejemplo 1  
  
-   cada día, los mensajes aumentan desde 0 mensajes por segundo a las 8:00 a.m. hasta 80 mensajes por segundo a las 12:00 a.m., y después vuelven a disminuir a 0 mensajes por segundo a las 9:00 p.m., aproximadamente una curva con forma de campana.  
  
-   El sistema no tiene ningún requisito de latencia específico para cada mensaje, pero debe ser capaz de procesar esta carga, además de todos los mensajes del día anterior de carga (por ejemplo, si se produce una interrupción del sistema de 24 horas) sin perder el ritmo.  
  
-   Hay tres tipos de documento: cesta de ventas, pedido en espera y petición de existencias. Los documentos de cesta de la compra varían en tamaño desde 2 hasta 10 KB y constituyen un 75% de los mensajes en cualquier momento. Los documentos de pedido en espera y petición de existencias suelen tener un tamaño aproximado de 1 KB y constituyen los restantes 10% y 15% respectivamente de los mensajes en cualquier momento.  
  
### <a name="example-2"></a>Ejemplo 2  
  
-   cada noche a las 12:00 p.m. llega un lote de 500.000 mensajes para procesarlos.  
  
-   todos los mensajes del lote se deben procesar en 8 horas.  
  
-   todos los mensajes son del mismo tipo y se distribuyen de forma equitativa entre 10 y 50 KB, inclusive. Además, el lote siempre contiene 10 mensajes de tipo de catálogo que tienen 10 MB cada uno y se deben subdividir en entradas de catálogo individuales para procesarlos.  
  
### <a name="example-3"></a>Ejemplo 3  
  
-   Cada mañana a las 8:00 a.m. 4.000 representantes de atención al cliente inician sesión en el sistema interactivo y realizan una media de 4 consultas por representante y por minuto hasta que se cierra a las 5:00 p.m., los siete días de la semana.  
  
-   todas las consultas deben devolver resultados en menos de 2 segundos.  
  
-   todas las consultas son del mismo tipo y su tamaño se distribuye equitativamente entre 500 y 1.000 bytes, inclusive.  
  
#### <a name="a-performance-requirement-associated-with-the-performance-function"></a>Un requisito de rendimiento asociado con la función de rendimiento  
 Continuando con los ejemplos anteriores:  
  
-   **Ejemplo 1 (continuado)**: el sistema no tiene ningún requisito de latencia específico para cada mensaje, pero debe ser capaz de procesar esta carga, además de todos los mensajes del día anterior de carga (por ejemplo, si se produce una interrupción del sistema de 24 horas) sin perder el ritmo.  
  
-   **Ejemplo 2 (continuado)**: todos los mensajes en el lote se deben procesar en 8 horas.  
  
-   **Ejemplo 3 (continuado)**: todas las consultas deben devolver resultados en menos de 2 segundos.  
  
#### <a name="a-distribution-of-file-sizes-and-types"></a>Una distribución de tamaños y tipos de archivo  
  
-   **Ejemplo 1 (continuado)**: hay tres tipos de documento: cesta de ventas, pedido en espera y petición de existencias. Los documentos de cesta de la compra varían en tamaño desde 2 hasta 10 KB y constituyen un 75% de los mensajes en cualquier momento. Los documentos de pedido en espera y petición de existencias suelen tener un tamaño aproximado de 1 KB y constituyen los restantes 10% y 15% respectivamente de los mensajes en cualquier momento.  
  
-   **Ejemplo 2 (continuado)**: todos los mensajes son del mismo tipo y se distribuyen uniformemente entre 10 y 50 KB, inclusive. Además, el lote siempre contiene 10 mensajes de tipo de catálogo que tienen 10 MB cada uno y se deben subdividir en entradas de catálogo individuales para procesarlos.  
  
-   **Ejemplo 3 (continuado)**: todas las consultas son del mismo tipo y se distribuye equitativamente entre 500 y 1.000 bytes de tamaño, ambos inclusive.  
  
## <a name="accounting-for-other-processes"></a>Contabilizar otros procesos  
 Además de los perfiles de carga que pasan directamente a través del motor de BizTalk, hay siempre otros procesos que compiten por recursos del mismo hardware.  Estos otros procesos reducen la capacidad global de rendimiento sostenible del sistema. El mantenimiento de las bases de datos es probablemente el ejemplo más común de este tipo de procesos.  
  
 Cada base de datos, grande o pequeña, requiere mantenimiento periódico, como trasvases, copias de seguridad, archivo y purga. La supervisión y la solución de problemas son otros ejemplos de operaciones que se deben tener en cuenta a la hora de definir y certificar lo que es sostenible. Por ejemplo, consultar el cuadro de mensajes (por ejemplo, desde la página Concentrador de grupo de la consola de administración) para ver cuántos mensajes de un tipo dado se han suspendido en las pasadas 24 horas requiere recursos de SQL Server que, de otro modo, se habrían podido usar para procesar mensajes.  
  
 La siguiente es una lista de actividades que suelen tener el mayor efecto en la sostenibilidad global en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   **Trasvase de registros y copia de seguridad**. Como parte de la mayoría de los planes de recuperación después de errores que implican SQL Server, debe realizar trasvases y copias de seguridad periódicamente de todas las bases de datos del grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md). Consulte también [trasvase de registros](../core/log-shipping.md).  
  
-   **Archivar y purgar datos de seguimiento**. Además de registro envío y copia de seguridad plan general, la base de datos de seguimiento de BizTalk (BizTalkDTADb) tiene su propio archivo y purga regímenes; Para obtener más información, consulte [archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md). La velocidad a la que se pueden archivar y purgar los datos de la base de datos de seguimiento de BizTalk es especialmente importante, puesto que los procesos de archivo y purga de la base de datos de seguimiento de BizTalk suelen ser un cuello de botella cuando está activo el seguimiento.  
  
-   **Consultas del sistema**. Uso de API o la interfaz de usuario de consola de administración de BizTalk Server para ejecutar varios tipos de consultas en el sistema afecta al rendimiento sostenible.  
  
-   **Mantenimiento de cuadro de mensajes**. Hay una serie de trabajos de SQL que son parte de la funcionalidad principal de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que mantiene la base de datos de cuadro de mensajes limpiando los mensajes y las instancias cuyo procesamiento ha terminado. Como parte del motor principal, la velocidad a la que se pueden realizar estos trabajos es un factor clave a la hora de evaluar la sostenibilidad. Para obtener más información acerca de estos trabajos y su rol, consulte [mantener BizTalk Server1](../core/maintaining-biztalk-server1.md).  
  
-   **Actividades de implementación de solución**. Cuando se implementan, enlazan e inician nuevas aplicaciones o nuevas versiones de aplicaciones existentes, se produce una carga adicional en BizTalk, como la creación de nuevas suscripciones en las bases de datos de cuadro de mensajes. Tras implementar las aplicaciones, los mensajes que se procesan compiten por los recursos y, por tanto, afectan al rendimiento de las aplicaciones existentes.  
  
 Para cada una de estas áreas, debe preguntar: ¿cuál es su recomendación para minimizar el impacto de estas actividades? Por ejemplo, ¿se debería planear ejecutarlas a las 3:00 a.m.?  
  
## <a name="considering-planned-and-unplanned-outages"></a>Considerar interrupciones del suministro eléctrico planeadas y no planeadas  
 Los efectos que tienen las interrupciones del suministro eléctrico en el rendimiento del sistema varían en función del sistema que experimenta la interrupción. No obstante, las consecuencias más comunes son:  
  
-   **Eventos de control de tráfico**. Cuando los sistemas están inactivos por un tiempo, los mensajes se pueden acumular y llegar todos de golpe para procesarlos una vez que el sistema vuelve a funcionar.  Por ejemplo, si una aplicación que se ejecuta en BizTalk recibe mensajes a través de MSMQ y esa aplicación está inactiva durante algún tiempo, los mensajes se acumulan en las colas a la espera de que los recojan. Cuando se inicia de nuevo la aplicación, es como si un gran número de mensajes llegara "todos de golpe".  
  
-   **Trabajo pendiente de mensajes**. Si los sistemas a los que se envían mensajes están inactivos, suele haber un ciclo de reintentos que utiliza recursos adicionales. Tras el ciclo de reintentos, los mensajes se suspenden. A continuación, los sistemas inactivos vuelven a estar en línea y tiene lugar un tipo de evento de control de tráfico (floodgate) donde grandes cantidades de mensajes se pueden reanudar o enviar correctamente.  
  
 Por supuesto, las interrupciones de suministro eléctrico planeadas (por ejemplo, las debidas al mantenimiento programado) se deben tener en cuenta a la hora de diseñar y certificar un sistema. También se recomienda considerar un análisis de las interrupciones de suministro eléctrico no planeadas y sus efectos.  
  
 Identificar los tipos de interrupciones de suministro eléctrico que se pueden producir, clasificándolos por el nivel de riesgo estimado (es decir, probabilidad por gravedad) y estimar la duración y el efecto (por ejemplo, eventos de control del tráfico (floodgate), volumen de mensajes suspendidos, registro, etc.) de las interrupciones de mayor riesgo indicarán la capacidad deseada de un sistema en el caso de que se produzcan interrupciones del suministro eléctrico. Cualquier sistema asincrónico basado en mensajería de almacenamiento y reenvío, como [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se debe diseñar con una capacidad de procesamiento suficiente para hacer frente a interrupciones del suministro eléctrico planeadas y no planeadas.  
  
## <a name="see-also"></a>Vea también  
 [Durabilidad y persistencia de motor](../core/engine-persistence-and-durability.md)   
 [Recomendaciones de planeación del proyecto por fases](../core/project-planning-recommendations-by-phase.md)   
 [Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [Escalar soluciones](../core/scaling-your-solutions.md)   
 [Identificar cuellos de botella de rendimiento](../core/identifying-performance-bottlenecks.md)   
 [Capacidad y rendimiento del motor](../core/engine-performance-and-capacity.md)