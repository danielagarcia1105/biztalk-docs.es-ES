---
title: Escenarios de prueba para medir MST de seguimiento de DTA | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 303dc1d8-baac-4b54-92c8-95c0ce640a76
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28a1cee9de5a97ac7430cebbee8b5e2a253a1ceb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="test-scenarios-for-measuring-mst-of-dta-tracking"></a>Escenarios de prueba para medir MST de seguimiento de DTA
Para mostrar el funcionamiento de todo esto en la práctica y para presentar una técnica sencilla de medir el rendimiento máximo sostenible (MST) para seguimiento, presentamos ahora un escenario de prueba en el que se ha medido el MST de seguimiento. Además de las técnicas proporcionadas, también puede usar los datos presentados como punto de inicio para calcular el rendimiento de seguimiento para otros sistemas.  
  
> [!IMPORTANT]
>  El lector debería tener en cuenta que la información contenida en este tema representa la visión actual de Microsoft acerca de los asuntos tratados desde la fecha de publicación. Puesto que debemos responder a condiciones de mercado y tecnologías variables, no debe interpretarse como un compromiso por parte de Microsoft, y Microsoft no puede garantizar la precisión de la información que se presenta después de la fecha de publicación.  
  
## <a name="test-scenario-topology-and-configuration"></a>Topología y configuración del escenario de prueba  
 En la ilustración siguiente se muestran la topología y la configuración del escenario de prueba.  Es una considerable compilación horizontal con cuatro servidores de base de datos de cuadro de mensajes, un servidor de base de datos de BizTalkDTADb dedicado y un total de siete servidores que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Tenga en cuenta que el servidor de BAM reflejado en la ilustración no estaba en uso para este escenario de prueba.  
  
 **Rendimiento sostenible de BizTalkDTADb**  
  
 ![Seguimiento de topología](../core/media/trackingperformancetopology.gif "TrackingPerformanceTopology")  
  
 **Especificación de hardware (BizTalk Server)**  
  
-   CPU: Dual 3 GHz (caché: L2: 512 KB/L3: 1 MB)  
  
-   Memoria: 2 GB de RAM  
  
-   DISCO DURO: 2 X 32 GB / 15 K  
  
 **Especificación de hardware (SQL Server)**  
  
-   CPU: Cuatro 2 GHz (nivel 2: 512 KB/L3: 1 MB)  
  
-   Memoria: 4 GB de RAM  
  
-   DISCO DURO: 2 X 32 GB/15 K + SAN  
  
 En la ilustración siguiente se proporciona información general de la arquitectura del escenario de prueba, donde  
  
-   **TP** = punto de seguimiento, un punto en el que algunos elementos se realiza un seguimiento como eventos o propiedades del mensaje.  
  
-   **MB** = cuerpo del mensaje, un punto en el que se realiza el seguimiento de un cuerpo del mensaje.  
  
 En la siguiente arquitectura de solución se muestra una configuración de seguimiento con tres componentes de configuración principales:  
  
-   **Seguimiento de DTA predeterminado**. Todos los puntos de seguimiento de eventos en la ilustración están activadas de forma predeterminada cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado.  
  
-   **Propiedades de mensaje**. El punto de seguimiento asociado con el desensamblador (DA) en la canalización de entrada representa el seguimiento de 10 propiedades del mensaje de entrada. Para obtener más información acerca de cómo promocionar propiedades para el seguimiento, vea [promocionar propiedades](../core/promoting-properties.md).  
  
-   **Cuerpo del mensaje**. En la ilustración, los dos puntos de cuerpo del mensaje (MB) representan los puntos en los que se realiza el seguimiento de los cuerpos de mensaje. Para obtener más información sobre cómo configurar el seguimiento de cuerpos de mensaje, consulte [configuración de seguimiento mediante la consola de administración de BizTalk Server](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef).  
  
 **Arquitectura del escenario de prueba**  
  
 ![Escenarios de rendimiento](../core/media/performancescenarios.gif "PerformanceScenarios")  
  
## <a name="test-techniques"></a>Técnicas de la prueba  
 El adaptador de archivo se usó para la recepción y para el envío. Usamos la herramienta para la generación de cargas, LoadGen 2007, para entregar los mensajes al recurso compartido de archivos de entrada. Esta herramienta se configuró para entregar archivos a un ritmo específico de modo que se pudiera variar la carga mientras buscábamos nuestro nivel de MST de seguimiento. Para obtener más información acerca de la herramienta LoadGen, consulte [mediante la herramienta Microsoft BizTalk LoadGen 2007](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md).  
  
 Para nuestras pruebas, asumimos un requisito de retención de 24 horas en la base de datos BizTalkDTADb. Esto es, todo lo que fuera más antiguo de 24 horas se purgó de la base de datos. El trabajo de SQL de archivo y purga está diseñado para que únicamente los datos que se han archivado se purguen, de modo que no se pierdan datos durante el proceso.  
  
 Para probar por completo el sistema con este requisito, fue necesario ejecutar la carga durante al menos 25 horas para que se incluyera al menos un ciclo de archivo y purga. Decidimos ejecutarla durante un tiempo completo de 48 horas para supervisar el sistema durante las 24 horas posteriores al primer archivo con el fin de asegurarnos de que era sostenible. Las primeras 24 horas eran necesarias para crear datos con la antigüedad suficiente para su archivo (cada 24 horas) con el fin de simular un estado fijo. Después, durante las siguientes 24 horas, el sistema se supervisó para determinar que todos los procesos (por ejemplo, TDDS, archivado y purga) podían mantener el rendimiento.  
  
 A partir de nuestra comprensión del comportamiento del seguimiento, solo hay unos pocos indicadores clave de rendimiento (KPI) que suele ser necesario supervisar para determinar la sostenibilidad:  
  
-   **El disco físico de tiempo de inactividad para el archivo de datos de base de datos de BizTalkDTADb**. Si el tiempo de inactividad del disco físico se acerca a 0, es un buen signo de que la base de datos BizTalkDTADb está saturada con la llegada de datos en los que se ha efectuado un seguimiento, la actividad de archivo o de purga.  
  
-   **La profundidad de la tabla trackingdata**. Si la tabla trackingdata comienza a aumentar ininterrumpidamente, es decir que continúa aumentando sin enlaces, es un claro signo de que, a la velocidad de rendimiento actual, TDDS no puede insertar datos en la base de datos BizTalkDTADb con la velocidad suficiente para mantener el rendimiento.  
  
-   **La profundidad de cola de impresión**. Hay varias causas de que la cola de impresión aumente. Una de las situaciones que causan este crecimiento es si se queda atrás el trabajo de SQL que copia los cuerpos de mensajes en los que se ha efectuado el seguimiento de la base de datos de cuadro de mensajes a la base de datos BizTalkDTADb. Debido a que los mensajes en los que es necesario efectuar un seguimiento no se pueden quitar de la base de datos de cuadro de mensajes (mediante los trabajos de limpieza del cuadro de mensajes) hasta que se hayan copiado correctamente a la base de datos BizTalkDTADb, si el trabajo de copia se queda atrás, la cola de impresión aumenta de tamaño.  
  
 Para la mayoría de los sistemas, la supervisión solo de estos tres indicadores de rendimiento bajo carga proporciona la información suficiente para determinar si la carga es sostenible o no.  
  
 **Indicadores clave de rendimiento bajo carga sostenible**  
  
 ![Supervisión del rendimiento de la base de datos de seguimiento](../core/media/perf-monitor-tracking-db.gif "Perf_Monitor_Tracking_db")  
  
 Con el escenario de ejemplo y una carga de 20 mensajes recibidos por segundo, obtuvimos datos de 48 horas de indicadores clave de rendimiento, tal y como se muestra en el gráfico de monitor de rendimiento generado. Observe en el gráfico las siguientes tendencias que indican sostenibilidad:  
  
-   **La profundidad de BizTalkDTADbdata (líneas negras)**. Con nuestras tres bases de datos de cuadro de mensajes de publicación podemos observar que, incluso después del primer archivo a las 24 horas, la profundidad de la tabla trackingdata se estabiliza y no continúa creciendo.  
  
-   **Profundidad (líneas azules) de la cola**. La profundidad de la cola de impresión es muy estable durante la ejecución, lo que indica que, incluso con los recursos empleados para el archivo y la purga, los mensajes en los que se efectuó el seguimiento, de 10 kilobytes de tamaño cada uno, se copian a la base de datos BizTalkDTADb sin que se queden atrás.  
  
-   **Tiempo de inactividad de disco (línea roja) físico del archivo de datos de la base de datos de BizTalkDTADb**. Durante las primeras 24 horas antes de que el archivo y la purga entren en acción, la base de datos BizTalkDTADb va acumulando más y más datos, lo que produce más y más E/S del disco a medida que TDDS inserta datos. Esto se considera claramente un descenso fijo en el tiempo de inactividad del disco físico.  
  
     A las 24 horas en la ejecución, se observa una clara caída en tiempo de inactividad de E/S, que coincide con la primera vez que el archivo y purga tienen trabajo para hacer. Después del primer archivo purga tiene trabajo que realizar cada minuto para purgar datos antigüedad superior a 24 horas (Recuerde, hay todavía se cargan en el sistema), que da como resultado un cercano a cero el tiempo de inactividad.  
  
     Aquí el punto clave es que, después de haber realizado el primer archivo, es decir, que el sistema ha superado la primera ventana de “retención de datos de la base de datos BizTalkDTADb activa”, el tiempo de inactividad del disco se acercará mucho al valor cero cuando el sistema se encuentra en el MST o cerca de éste. Esto se debe a que el cuello de botella de la base de datos BizTalkDTADb es casi siempre la velocidad del subsistema de E/S del disco.  
  
 En muchos casos, puede resultar beneficioso medir el MST con el seguimiento desactivado a modo de línea de base del sistema. En nuestro caso, por ejemplo, el MST con todo el seguimiento desactivado fue de 290 mensajes por segundo, lo que representa el MST multiplicado varias veces obtenido cuando el sistema tiene el seguimiento activado con las características y la ventana de retención de datos de DTA indicadas anteriormente. Esto nos indica que el sistema se infrautiliza de forma significativa cuando el seguimiento está activado. Esto significa que no necesitamos crear un sistema con capacidad para 290 mensajes/s cuando el seguimiento que necesitamos efectuar en algunos aspectos solo permitirá un MST de 20 mensajes/s. Dicho de otro modo, suponiendo que el hardware de la base de datos BizTalkDTADb no cambie, serían necesarios muchos menos servidores de base de datos de cuadro de mensajes y de BizTalk para alcanzar un rendimiento de 20 mensajes por segundo que los que tenemos en nuestro escenario.  
  
## <a name="searching-for-maximum-sustainable-throughput"></a>Buscar el rendimiento máximo sostenible  
 Ahora que ya hemos visto el aspecto del KPI en un sistema que se ejecuta a MST, recopilemos y conozcamos cómo hemos llegado a la conclusión de nuestro MST de 20 mensajes/s para el escenario de ejemplo. Se trata de un enfoque iterativo sencillo y de "búsqueda binaria", como se describe a continuación:  
  
-   **Elegir un punto de partida**. A menos que ya tenga experiencia con las pruebas de rendimiento en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tendrá que aprovechar la información disponible sobre lo que se ha conseguido en otros sistemas.  
  
     Por ejemplo, se ha proporcionado todo el hardware, la configuración y la arquitectura de la solución para el escenario de ejemplo en este tema. Con ello, el tipo de seguimiento que habíamos activado (predeterminado + 10 propiedades + cuerpos de mensaje de 10KB) y el MST alcanzado (20 mensajes/s) con una ventana de retención de datos de DTA de 24 horas, compárelo con su configuración y sus requisitos.  
  
     Al menos debería ser capaz de estimar si el MST de su solución será superior o inferior al que obtuvimos nosotros. También puede encontrar varios estudios de casos técnicos disponibles con los que pueda comparar su sistema. Para obtener ejemplos, vea los casos de estudio disponibles en el centro de desarrollo de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=49339](http://go.microsoft.com/fwlink/?LinkId=49339).  
  
-   **Ejecute el sistema bajo la carga de MST estimada y supervise el KPI**. Normalmente, comenzar por los valores elevados del MST que espera puede reducir el tiempo que se tarda en encontrar el MST. Al comenzar en estos valores, empujará el KPI a la saturación (especialmente la E/S del disco) en menos tiempo de lo que duraría descubrir que se encuentra por debajo del MST (esto es, al menos una ventana de retención de datos completos).  
  
-   **Refinar la estimación del MST y repita**. Con los resultados obtenidos en la ejecución de prueba, perfeccione la estimación del MST y repita la prueba con la nueva estimación.  
  
## <a name="see-also"></a>Vea también  
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [Comprender el comportamiento del rendimiento de seguimiento de DTA](../core/understanding-dta-tracking-performance-behavior.md)   
 [Sugerencias y trucos para encontrar MST de seguimiento de DTA](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [Instrucciones para ajustar el tamaño de la base de datos de seguimiento](../core/tracking-database-sizing-guidelines.md)