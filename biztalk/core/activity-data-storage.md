---
title: Almacenamiento de datos de actividad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- databases [BAM], performance
- activities [BAM], peformance
- databases [BAM], partitioning
- BAM, performance
ms.assetid: 1f736599-3d16-496e-a459-8b0507d57fcb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0139e76512eb9ca60089cb3c5f1e71b4f5524690
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="activity-data-storage"></a>Almacenamiento de datos de actividad
Este tema describe el almacenamiento de datos de actividad, los problemas de rendimiento provocados con el tiempo por el crecimiento de las tablas de actividad y cómo BAM soluciona estos problemas de rendimiento con tablas diferentes de las actividades en ejecución y las completadas. Este tema también describe la ventana en línea para la realización de consultas de datos y la forma en la que puede realizar particiones en BAM para obtener una mejora del rendimiento.  
  
 La idea básica del almacenamiento de datos de actividad es tener tablas diferentes de cada tipo de actividad, en las que cada registro representa un instancia de actividad diferente (por ejemplo, en ejecución o completadas).  
  
 En este ejemplo, si la actividad fuera Pedidos, la tabla tendría la siguiente apariencia:  
  
|PO#|RecvTime|City|Cantidad|ShipTime|DeliveryTime|  
|----------|--------------|----------|--------------|--------------|------------------|  
|123|8:00 a.m.|Seattle|150|8:24 am|12:45pm|  
|124|8:30 a.m.|Seattle|234|8:45 a.m.|1:20 p.m.|  
|125|8:35 am|Redmond|87|9:05 a.m.|2:30 p.m.|  
|126|8:45 a.m.|Seattle|450|9:20 a.m.|3:10 p.m.|  
|127|8:55 a. m.|Redmond|200|9:30 a.m.|\<NULL\>|  
|128|8:57 a.m.|Seattle|340|9:20 a.m.|3:05 p.m.|  
|129|9:12 am|Seattle|120|9:45 a.m.|\<NULL\>|  
|130|9:30 a.m.|Redmond|25|10:15 a.m.|\<NULL\>|  
|131|9:45|Seattle|250|10:35 am|\<NULL\>|  
|132|10:00 a.m.|Redmond|100|\<NULL\>|\<NULL\>|  
|133|10:15 a.m.|Seattle|230|\<NULL\>|\<NULL\>|  
|134|10:25 a. m.|Redmond|45|\<NULL\>|\<NULL\>|  
  
 En esta tabla, cuando BAM recibe un pedido nuevo, se inserta una fila nueva y algunos conjuntos de algunas columnas con valores que no son nulos (RecvTime, City, Quantity, etc.). Más adelante, cuando apruebe y envíe este pedido, BAM establece el ShipTime para valores que no son nulos Finalmente, cuando recibe y confirma el envío, BAM establece DeliveryTime para valores que no son nulos.  
  
 El rendimiento de esta implementación simplista empeora rápidamente con el tiempo. Al principio, el rendimiento está limitado al número de transacciones que el servidor SQL Server puede realizar (básicamente, enlazadas a la CPU), pero con el tiempo, disminuye drásticamente. A la misma vez, la longitud promedio de la cola para E/S de disco aumenta más allá de los límites aceptables:  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig4.gif "ebiz_prog_bam_data_maint_fig4")  
Rendimiento de escritura de BAM frente a la longitud de la cola de disco  
  
 El motivo de que suceda esto es que el tamaño de la tabla crece a medida que se completan más instancias del proceso empresarial. Por ejemplo, la primera vez, la instrucción ACTUALIZAR del procedimiento almacenado produce una búsqueda del índice agrupado del número de pedidos y lee algunas páginas en memoria. Ya que las instancias del proceso de pedido son independientes (algunas tardan tiempo pero otras son rápidas), puede que la siguiente llamada al procedimiento almacenado sea para cualquier otra instancia de pedido y, por lo tanto, necesite que se lean páginas de datos diferentes en la memoria. Siempre que el número total de registros de pedidos sea bajo, el servidor SQL Server guardará en caché todas las páginas de datos en la memoria. Cuando el número de registros aumenta suficientemente, la frecuencia de aciertos de caché disminuye y cada operación requiere que se lea el disco físicamente. Aparentemente, en esta situación no es posible ninguna actividad de consulta en la tabla.  
  
## <a name="bam-tables"></a>Tablas de BAM  
 Para evitar este problema, BAM utiliza dos tablas diferentes: una para las actividades en ejecución, y otra para las completadas en la figura siguiente:  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig5.gif "ebiz_prog_bam_data_maint_fig5")  
Tablas de BAM  
  
 En esta figura, la idea es conservar una tabla relativamente pequeña donde se produzcan las actualizaciones, y otra que se agrande pero a la que se tenga acceso de forma incremental. En este ejemplo, solo estarán en la tabla activa los pedidos que se hayan procesado en ese momento, mientras que los pedidos que ya se han entregado irán a la tabla completada.  
  
 Debido al desencadenador, esta estructura de tablas es más lenta que una estructura INSERTAR/ACTUALIZAR de una tabla única del principio, pero conserva un rendimiento de escritura estable en el tiempo.  
  
## <a name="online-window-for-activity-data"></a>Ventana en línea para datos de actividad  
 El almacenamiento de la actividad controla principalmente consultas de actividades en ejecución o recién completadas. BAM archiva y luego purga las actividades completadas y antiguas desde la base de datos de importación principal de BAM. Por lo tanto, los datos de actividad pasan a través de BAM y están disponibles para las consultas mediante una ventana en línea configurable.  
  
## <a name="bam-partitioning"></a>Particiones de BAM  
 Para obtener un mayor rendimiento y evitar tiempo de inactividad, el almacenamiento de actividad utiliza particiones según la marca de tiempo cuando la actividad se haya completado. BAM consigue esto intercambiando con regularidad la tabla completada con otra tabla vacía de idéntico formato. Una vez que BAM hace esto, las demás actividades completadas pasan a la nueva tabla mientras que BAM mantiene la partición antigua para consultas, como se muestra en la figura siguiente:  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig8.gif "ebiz_prog_bam_data_maint_fig8")  
Intercambio de particiones de BAM  
  
 Una vez que una partición esté completamente fuera de la ventana en línea, BAM la archiva y luego la quita. Para minimizarle esta complejidad al usuario, BAM también conserva una vista con particiones de la forma:  
  
```  
SELECT * FROM Active   
UNION ALL   
SELECT * FROM Completed   
UNION ALL  
  
```  
  
 BAM vuelve a crear automáticamente esta vista cada vez que crea o quita una partición.  
  
 Tenga en cuenta lo siguiente sobre la creación de particiones de BAM:  
  
-   El nombre de la vista con particiones es **bam_\<ActivityName\>_AllInstances**. Esta vista no es para consultas directas, pero puede ser útil para solucionar problemas de la instrumentación de BAM. Debería consultar los datos de vistas determinadas para cada categoría de usuarios empresariales que crea en la parte superior de esta vista. Para obtener más información, consulte [consultar datos de instancia](../core/querying-instance-data.md).  
  
-   Establecer la ventana en línea mediante la modificación de los valores de **OnlineWindowTimeUnit** y **OnlineWindowLength** en el registro para la actividad actual en la tabla **bam_Metadata_Activities** en la base de datos de importación principal.  
  
-   El paquete DTS, **BAM_DM_\<ActivityName\>**, lleva a cabo la creación de particiones y el archivo y la purga. Cada vez que se ejecuta este paquete, trunca otra partición y archiva y quita todas las particiones que están fuera de la ventana en línea.  
  
-   Si no está configurada la base de datos de archivo, BAM quita la actividad antigua sin archivar.  
  
## <a name="see-also"></a>Vea también  
 [Infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md)