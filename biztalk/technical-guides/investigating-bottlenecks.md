---
title: Investigación de cuellos de botella | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ab8e485-ffe5-4f71-9ce2-f72c0c939e5d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e34d01bbfafd1a05f87fff5cda2b21764d43f42b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298844"
---
# <a name="investigating-bottlenecks"></a>Investigación de cuellos de botella
Este tema describe un proceso recomendado para investigar los cuellos de botella.  
  
## <a name="what-is-the-source-of-the-problem"></a>¿Cuál es el origen del problema?  
 Podría ser el origen del cuello de botella de hardware o software relacionado con. Cuando los recursos están infrautilizados, suele ser una indicación de un cuello de botella. Cuellos de botella pueden deberse a limitaciones de hardware, por las configuraciones de software poco eficaz o por ambos.  
  
 La identificación de cuellos de botella es un proceso incremental, donde la solución de un cuello de botella puede llevar a descubrir otro. El objetivo de este tema consiste en encontrar el modo de identificar y solucionar estos cuellos de botella. Es posible que un sistema obtenga valores máximos durante breves períodos de tiempo. Sin embargo, para un rendimiento sostenible un sistema solo podrá procesar tan rápido como su componente de realización más lento.  
  
## <a name="using-an-iterative-approach-to-testing"></a>Si aplica un enfoque iterativo a las pruebas  
 Pueden producirse cuellos de botella en los puntos de conexión (entrada/salida) del sistema o en el medio (orquestación/base de datos). Después de que el cuello de botella se ha aislado, use un enfoque estructurado para identificar el origen. Después de que el cuello de botella se ve facilitado, es importante medir el rendimiento para asegurarse de que un cuello de botella nuevo no se ha introducido en otro lugar en el sistema.  
  
 El proceso de identificar y corregir cuellos de botella debería realizarse de forma iterativa. Variar solo un parámetro a la vez, repetir exactamente los mismos pasos durante cada ejecución de pruebas y, a continuación, medir el rendimiento para comprobar el impacto de la modificación único. Si se modifica más de un parámetro de una vez, podría ocultarse el efecto del cambio.  
  
 Por ejemplo, cambiar el parámetro 1 podría mejorar el rendimiento. Sin embargo, el cambio de parámetro 2 junto con el parámetro 1 podría tener un efecto negativo y anular las ventajas de cambiar el parámetro 1. Esto conduce a una red de cero efecto y da como resultado un falso negativo en el efecto de modificar el parámetro 1 y un falso positivo en el efecto de modificar el parámetro 2.  
  
## <a name="testing-consistency"></a>Comprobar coherencia  
 Medir las características de rendimiento después de cambiar la configuración debe realizarse para validar el efecto del cambio.  
  
-   **Hardware -** usar hardware coherente ya que modifica el hardware puede producir un comportamiento incoherente y generar resultados engañosos. Por ejemplo, no utilizaría un equipo portátil para probar el rendimiento de una solución de BizTalk.  
  
-   **Probar la duración de ejecución -** medir el rendimiento durante un período mínimo definido para asegurarse de que los resultados son sostenibles. Ejecutar pruebas durante períodos más largos también garantiza que el sistema ha pasado a través de la preparación inicial período donde se rellenan todas las memorias caché, las tablas de base de datos han alcanzado los recuentos esperados y limitación debido a un tiempo suficiente para regular el rendimiento una vez predefinida se alcanzan los umbrales. Este enfoque ayudará a descubrir el rendimiento óptimo sostenible.  
  
-   **Probar los parámetros –** no varían los parámetros de prueba de la ejecución de pruebas para la ejecución de pruebas. Por ejemplo, si se modifica la complejidad de asignación o el tamaño del documento, se pueden producir resultados de latencia y rendimientos distintos.  
  
-   **Limpiar el estado -** una vez completada una prueba, asegúrese de que el estado del entorno de prueba está limpio antes de ejecutar la prueba siguiente. Por ejemplo, los datos históricos pueden acumular en la base de datos que afectan a rendimiento en tiempo de ejecución. Reciclar las instancias de servicio ayuda a los recursos almacenados en caché como subprocesos, memoria y las conexiones de base de datos de la versión. En el entorno de prueba, puede que desee crear y ejecutar el procedimiento almacenado bts_CleanupMsgbox tal y como se describe en [cómo purgar datos manualmente desde la base de datos de cuadro de mensajes en un entorno de prueba](http://go.microsoft.com/fwlink/?LinkId=158064) (http://go.microsoft.com/fwlink/?LinkId=158064). Esta secuencia de comandos está diseñada para devolver el entorno de prueba de BizTalk Server a un nuevo estado en relación con el cuadro de mensaje entre ejecuciones. La secuencia de comandos elimina todas las instancias en ejecución y toda la información acerca de esas instancias como estado, mensajes y las suscripciones, pero deja todas las suscripciones de activación de modo que no es necesario volver a dar de alta las orquestaciones o puertos de envío. Tenga en cuenta que esta herramienta no se admite en sistemas de producción.  
  
-   **Pruebas de rendimiento y optimización -** el objetivo de esta categoría de prueba es maximizar el rendimiento y la capacidad de la aplicación y busque el rendimiento sostenible máximo (MST) del sistema.  Para obtener más información sobre cómo planear y medir el rendimiento máximo sostenible vea [planear el rendimiento sostenido de](http://go.microsoft.com/fwlink/?LinkId=158065) (http://go.microsoft.com/fwlink/?LinkId=158065) y [¿qué es rendimiento sostenible?](http://go.microsoft.com/fwlink/?LinkId=132304) (http://go.microsoft.com/fwlink/?LinkId=132304).  
  
     El MST es la mayor carga de tráfico de mensajes que puede administrar un sistema indefinidamente en un entorno de producción. Todas las aplicaciones de BizTalk deben probarse para rendimiento y antes de pasar a producción. Como mínimo, debe ejecutar un conjunto representativo de los casos de prueba que representan los escenarios de uso más comunes. Se recomienda realizar pruebas en cargas esperadas y picos de carga en un entorno independiente que coincida con las características del entorno de producción. Este entorno debe tener todos los servicios corporativos estándares instalado y en ejecución, como agentes de supervisión y el software antivirus.  
  
-   También le recomendamos que pruebe nuevas aplicaciones de BizTalk en el mismo hardware en producción junto con las demás aplicaciones de BizTalk que se ejecutan. Estas otras aplicaciones de BizTalk colocan una carga adicional en BizTalk Server, SQL Server, E/S de red y E/S de disco. Además, una aplicación de BizTalk podría producir otro limitar (cuando la profundidad de cola de impresión es demasiado grande, por ejemplo). Todas las aplicaciones de BizTalk deben ser rendimiento / esfuerzo probarse antes de pasar a producción. Además, debe determinar el tiempo que tarda el sistema para recuperarse de las cargas máximas. Si el sistema no debe recuperar completamente desde un pico de carga antes de que se produce la siguiente carga máxima, tienes un problema. El sistema obtendrá aún más y más subyacente y que nunca podrá recuperar completamente.  
  
## <a name="expectations-throughput-vs-latency"></a>Expectativas: rendimiento frente a latencia  
 Puede esperar una determinada cantidad de rendimiento o latencia del sistema implementado. Intenta lograr un alto rendimiento y baja latencia simultáneamente coloca opuestas demandas en el sistema. Puede esperar un rendimiento óptimo con una latencia razonable. Cuando mejora el rendimiento, resalte (por ejemplo, mayor consumo de CPU, mayor contención de disco de e/s, presión de memoria y mayor contención de bloqueo) en el sistema aumenta. Esta situación puede tener un impacto negativo en la latencia. Para descubrir la capacidad óptima de un sistema, se recomienda que se identifican y minimizar los cuellos de botella.  
  
 Instancias completadas que residen en la base de datos pueden producir cuellos de botella. Cuando se producen cuellos de botella, puede degradar el rendimiento. Lo que proporciona al sistema tiempo suficiente para purgar puede ayudar a solucionar el problema. Son importante descubrir la causa de la acumulación y ayudar a solucionar el problema.  
  
 Para descubrir la causa del trabajo pendiente, puede analizar datos históricos y supervisar los contadores de rendimiento (para detectar patrones de uso y diagnosticar el origen del trabajo pendiente). Normalmente, trabajos pendientes pueden producirse cuando se procesan grandes volúmenes de datos en un modo por lotes noches. Puede que le resulte útil para detectar la capacidad del sistema y su capacidad para recuperarse de un trabajo pendiente. Esta información puede ayudarle a estimar los requisitos de hardware para controlar casos de sobrecarga y la cantidad de espacio en el búfer para dar cabida a dentro de un sistema para atender los picos imprevistos en el rendimiento.  
  
 Supervisión de los contadores de rendimiento puede ayudar a individuate posibles cuellos de botella que podrían surgir en tiempo de ejecución. Sin embargo, cuando se sospecha que la causa del cuello de botella de CPU o memoria puede ser uno de los componentes personalizados que componen la solución, se recomienda encarecidamente que utilice herramientas de generación de perfiles tales el generador de perfiles de Visual Studio o el generador de perfiles de rendimiento de las HORMIGAS durante una prueba de rendimiento para descubrir y individuate con exactitud la clase que genera el problema. Obviamente, la generación de perfiles de una aplicación interfiere con el rendimiento. Por lo tanto, estas pruebas deben centrarse individuating esos componentes que provocan el consumo de memoria, el uso de CPU o la latencia y se deberían descartar cifras durante estas pruebas.  
  
 Ajustar el sistema para el rendimiento óptimo sostenible requiere una profundidad de descripción de la aplicación implementada, los puntos fuertes y débiles del sistema y patrones de uso del escenario específico. El único modo de descubrir cuellos de botella y prever un rendimiento sostenible y óptimo con seguridad consiste en realizar comprobaciones exhaustivas en una topología que se aproxime a la que se usará en la producción. Al ejecutar pruebas de carga y esfuerzo en un determinado caso de uso, aislar únicos artefactos (ubicaciones de recepción, puertos de envío, orquestaciones) en instancias de host independientes y la configuración de los contadores de derecho dentro de la herramienta monitor de rendimiento son fundamental para reducir el causa de un cuello de botella.  
  
 Otros temas de esta sección le guían a través del proceso de definir esa topología y ofrecen orientación sobre cómo reducir y evitar los cuellos de botella.  
  
## <a name="scaling"></a>Ampliación  
 Los cuellos de botella pueden producirse en distintas fases de una topología de implementada. Algunos cuellos de botella pueden tratarse por parte de escalamiento vertical o el escalado del entorno. El escalado es el proceso de actualizar el equipo existente. Por ejemplo, puede actualizar un equipo de servidor BizTalk Server desde un equipo con cuatro procesadores a un equipo con ocho procesadores, así como para sustituir las CPU existentes y agregar más RAM. De esta manera, puede acelerar las tareas que consumen muchos recursos como documento de análisis y la asignación. La ampliación horizontal es el proceso de agregar servidores a la implementación. La decisión de escalar vertical u horizontalmente depende del tipo de cuello de botella y la aplicación que se está configurando. Una aplicación necesita que se crea desde el principio para ser capaces de sacar partido de ajuste de escala vertical u horizontalmente. Las instrucciones siguientes explican cómo cambiar las topologías de implementación de hardware en función de los cuellos de botella que se encontró.  
  
 **El escalado** significa que la ejecución de una solución de BizTalk actualiza el hardware (por ejemplo, adición de CPU y memoria). Debe considerar cómo ampliar cuando (1) el escalado horizontal es demasiado caro o (2) el escalado no ayudará a solucionar un cuello de botella. Por ejemplo, puede reducir significativamente el tiempo empleado transformar y procesar un mensaje grande si ejecuta la tarea en un equipo más rápido.  
  
 **La ampliación horizontal** consta de la plataforma de aplicaciones de agregar nodos de BizTalk al grupo de BizTalk Server y lo utiliza para ejecutar una o más partes de la solución. Debe mirar escalado horizontal cuando (1) necesita aislar el envío, recepción, procesamiento, hosts de seguimiento o (2) cuando la memoria, se sobrepasa los recursos de E/S o de E/S de red para un único servidor. La carga se puede distribuir en varios servidores; Sin embargo, la adición de nuevos nodos en el grupo de BizTalk Server puede aumentar la contención de bloqueo en la base de datos de cuadro de mensajes.  
  
 ¿Por lo que debe aumentar o escalar horizontalmente? Cómo ampliar la plataforma puede reducir la latencia de una solución de BizTalk porque dificulta la tareas únicas (por ejemplo, asignación de mensajes) ejecutarse con mayor rapidez. Escalado horizontal puede mejorar el rendimiento sostenible máximo del sistema y la escalabilidad de la solución de BizTalk porque permite distribuir la carga de trabajo en varios equipos.  
  
## <a name="see-also"></a>Vea también  
 [Buscar y eliminar los cuellos de botella](../technical-guides/finding-and-eliminating-bottlenecks.md)