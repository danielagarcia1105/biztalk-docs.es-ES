---
title: Cómo investigar cuellos de botella | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ca22d07-d5fe-4dfb-8b52-3be3a95b0d6f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a3cf4630bf3269516537439ed58b464589cf26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254900"
---
# <a name="how-to-investigate-bottlenecks"></a>Cómo investigar cuellos de botella
En este tema se describe un proceso recomendado para investigar cuellos de botella.  
  
## <a name="what-is-the-source-of-the-problem"></a>¿Cuál es el origen del problema?  
 El origen del problema podría estar relacionado con el hardware o el software. Cuando los recursos se infrautilizan suele ser indicativo de un cuello de botella en alguna parte del sistema. Los cuellos de botella pueden estar ocasionados por limitaciones del hardware, por una configuración del software poco eficaz, o por ambos motivos.  
  
 La identificación de cuellos de botella es un proceso incremental, donde la solución de un cuello de botella puede llevar a descubrir otro. El objetivo de este tema consiste en encontrar el modo de identificar y solucionar estos cuellos de botella. Es posible que un sistema obtenga valores máximos durante breves períodos de tiempo. Sin embargo, para un rendimiento sostenible un sistema solo podrá procesar tan rápido como su componente de realización más lento.  
  
## <a name="using-a-serial-approach"></a>Uso de un enfoque en serie  
 Los cuellos de botella se pueden producir en extremos (entrada/salida) del sistema o en cualquier otro lugar (orquestación/base de datos). Una vez que se haya aislado la ubicación del cuello de botella, se puede llevar a cabo un enfoque estructurado para identificar el origen. Cuando se hayan solucionado los cuellos de botella, es fundamental volver a medir el rendimiento para asegurarse de que no se ha producido un cuello de botella nuevo en otro lugar del sistema más abajo de la línea.  
  
 El proceso de identificar y corregir cuellos de botella debería realizarse en serie; solo se debería modificar un parámetro cada vez y, a continuación, se debería medir el rendimiento para comprobar el efecto de ese cambio. Si se modifica más de un parámetro de una vez, podría ocultarse el efecto del cambio.  
  
 Por ejemplo, si se cambia el parámetro 1 se podría mejorar el rendimiento, sin embargo, si se cambia el parámetro 2 junto con el parámetro 1 podría tener un efecto perjudicial y anular las ventajas de cambiar el parámetro 1 que llevaría a un efecto neto de cero. Sin embargo, esto provoca un negativo falso en el efecto de modificar el parámetro 1 y un positivo falso en el efecto de modificar el parámetro 2.  
  
## <a name="testing-consistency"></a>Comprobar coherencia  
 Es esencial medir las características del rendimiento después de cambiar la configuración para validar el efecto del cambio.  
  
-   Hardware: Es importante usar hardware coherente ya que modifica el hardware puede mostrar un comportamiento incoherente que produzca resultados erróneos, por ejemplo, no use un equipo portátil.  
  
-   Duración de la ejecución de pruebas: También es importante medir el rendimiento durante un período mínimo definido para asegurarse de que los resultados son sostenibles y no simplemente, valores máximos. Otra razón para llevar a cabo pruebas durante períodos más largos es que se debe asegurar que el sistema ha pasado por el período inicial de preparación donde se han rellenado todas las cachés, que las tablas de la base de datos han alcanzado los recuentos esperados y que la limitación ha contado con tiempo suficiente para activarse y regular el rendimiento una vez alcanzados los umbrales predefinidos. Este enfoque ayudará a descubrir el rendimiento óptimo sostenible.  
  
-   Los parámetros de prueba: También es necesario no modificar los parámetros de ejecución de pruebas para probar serie de pruebas. Por ejemplo, si se modifica la complejidad de asignación o el tamaño del documento, se pueden producir resultados de latencia y rendimientos distintos.  
  
-   Un estado limpio: Una vez completada una prueba es importante para realizar la limpieza ejecutar todo el estado antes de ejecutar la prueba siguiente. Por ejemplo, los datos históricos pueden acumularse en la base de datos, lo que influye en el rendimiento del tiempo de ejecución. Si se reciclan las instancias de servicio, se liberan los recursos almacenados en caché como la memoria, las conexiones de la base de datos y los subprocesos.  
  
## <a name="expectations-throughput-versus-latency"></a>Expectativas: Rendimiento frente a latencia  
 Es razonable esperar una determinada cantidad de rendimiento o latencia del sistema implementado. Esperar obtener un alto rendimiento y una latencia baja es como tirar en direcciones opuestas. Sin embargo, es realista esperar un rendimiento óptimo con una latencia razonable. Cuando mejora el rendimiento, el sistema sufre más sobrecarga (mayor consumo de la CPU, mayor contención para E/S de disco, consumo excesivo de la memoria, mayor contención de bloqueo) lo que puede llevar a un efecto negativo en la latencia. Para descubrir la capacidad óptima de un sistema, es necesario identificar y solucionar cualquier cuello de botella que se presente.  
  
 Los cuellos de botella pueden estar ocasionados por los datos heredados (instancias completadas) que se encuentran en la base de datos que no se ha vaciado. Cuando sucede esto, puede reducirse el rendimiento. Si se le da al sistema tiempo suficiente para que se purgue, será más fácil solucionar el problema. Sin embargo, es importante descubrir la razón de la acumulación de datos para solucionar el problema.  
  
 Para descubrir la razón de la acumulación, es importante analizar los datos históricos, supervisar los contadores Monitor de rendimiento (para descubrir patrones de uso y diagnosticar el origen de la acumulación). Esta es una situación frecuente cuando se procesan grandes volúmenes de datos por lotes todas las noches. Descubrir la capacidad del sistema y la posibilidad de recuperarse de una acumulación puede ser útil a la hora de tener en cuenta los requisitos de hardware para controlar casos de sobrecarga y la cantidad de espacio del búfer para almacenamiento dentro de un sistema para controlar, de este modo, picos imprevistos en el rendimiento.  
  
 Ajustar el sistema para un rendimiento sostenible y óptimo requiere un conocimiento en profundidad de la aplicación que se implementa, de los puntos fuertes y débiles del sistema, así como de los patrones de uso del caso específico. El único modo de descubrir cuellos de botella y prever un rendimiento sostenible y óptimo con seguridad consiste en realizar comprobaciones exhaustivas en una topología que se aproxime a la que se usará en la producción.  
  
 En otros temas de esta sección se le indica cómo definir esa topología, cómo solucionar cuellos de botella y, con un poco de suerte, cómo evitarlos.  
  
## <a name="scaling"></a>Ampliación  
 Los cuellos de botella se pueden producir en diferentes fases de la topología implementada. Algunos pueden solucionarse mediante la actualización del hardware. El hardware puede actualizarse si se escala verticalmente (más CPU, memorias o cachés) o si se escala horizontalmente (otros servidores). La decisión de escalar vertical u horizontalmente depende del tipo de cuello de botella que se ha encontrado y de la aplicación que se va a configurar. A continuación se presentan unas indicaciones que ayudarán a cambiar las topologías de implementación de hardware que se basan en los cuellos de botella que se han encontrado. Una aplicación debe generarse a partir de cero para que pueda aprovechar las ventajas de escalarse vertical u horizontalmente. Por ejemplo:  
  
-   Si la aplicación está serializada y depende de un único subproceso de ejecución, es posible que no ayude a solucionar el problema el hecho de escalar verticalmente un servidor con otras CPU y memorias.  
  
-   Es posible que el escalamiento horizontal con otros servidores no sea de ayuda si éstos simplemente agregan contención a un recurso común que no se pueda escalar. Sin embargo, el escalonamiento horizontal proporciona otras ventajas. Implementar dos servidores de procesadores dobles en lugar de un servidor de procesador cuádruple ayuda a proporcionar un servidor redundante que cumple el doble propósito de escalar para controlar el rendimiento adicional y proporcionar una topología con una alta disponibilidad.