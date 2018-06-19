---
title: Las agregaciones del Portal de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, pivot tables
- BAM, data analysis
- pivot tables [BAM portal]
- BAM portal, charts
- data, analysis [BAM]
- data, OLAP cubes
- aggregations [BAM], BAM portal
- charts, BAM portal
- BAM portal, aggregations
ms.assetid: 1c689563-714b-4573-9c18-a5b0efe97fb8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43ef0adfacea0a29ea47584ed545884ffb8fa8bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230548"
---
# <a name="aggregations-in-the-bam-portal"></a>Agregaciones en el portal de BAM
Las agregaciones son tablas de datos precalculados que puede usar para realizar el procesamiento analítico con un cubo OLAP. Las agregaciones facilitan la realización de consultas eficaces en un contexto de bases de datos multidimensionales. Al crear e implementar el modelo de observación (la definición de alto nivel de los datos económicos) mediante el complemento BAM para Excel, se crean agregaciones que puede usar para evaluar rápidamente las colecciones de datos que hacen referencia a los indicadores clave de rendimiento (KPI).  
  
## <a name="types-of-aggregations"></a>Tipos de agregaciones  
 Las agregaciones pueden ser programadas o en tiempo real. Las agregaciones programadas son cubos OLAP que representan una instantánea de sus datos económicos en el momento que determine. Las agregaciones en tiempo real permiten ver los datos económicos de su negocio en función de los factores desencadenantes que determine. De esta manera, el sistema de BAM le notifica mediante una alerta en cuanto se alcanza el indicador clave de rendimiento.  
  
## <a name="pivottable-view"></a>Vista de tabla dinámica  
 El área Vista de tabla dinámica muestra el informe de tabla dinámica que se diseña mediante el complemento de BAM para Excel. Office Web Components permite manipular el informe de PivotTable para presentar la vista de los datos que mejor se ajuste a sus necesidades.  
  
> [!NOTE]
>  Al ver un informe de tabla dinámica, es posible que algunas filas contengan datos nulos tanto en las agregaciones en tiempo real (ATR) como en las agregaciones precalculadas (una implementación OLAP) si se han alcanzado los hitos de la actividad pero no se han utilizado en una dimensión de progreso. Asimismo, se pueden encontrar filas con datos nulos si se usa la dimensión de tiempo en un contexto de dimensión de progreso y está delimitada con relación a un hito, como "confirmado" en lugar de "recibido". En este caso, se recibe una instancia de actividad y se desencadena el hito recibido, pero la actividad todavía no ha desencadenado el hito de confirmación y aparecerá el valor cero en la fila de la dimensión de tiempo.  Para evitar esta situación, vincule la dimensión de tiempo con el hito recibido.  
  
 ![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")  
  
 Recuerde estas consideraciones cuando utilice Office Web Components en el portal de BAM para modificar su informe de tabla dinámica.  
  
-   Los informes de tabla dinámica en Excel incluyen un campo Página, donde puede ubicar una dimensión de intervalo de tiempo. Los Office Web Components que utiliza el portal de BAM no incluyen un campo Página. Si su informe de tabla dinámica de Excel usa el campo Página para cualquier dimensión, los datos de este campo no se muestran en su informe de tabla dinámica en el portal de BAM.  
  
-   Office Web Components muestra los datos en el marco Contenido del portal de BAM. Debido a las limitaciones espaciales de este marco, al agregar dimensiones desde la lista de campos al área de las columnas, podría provocar que la tabla dinámica desplazara parcial o totalmente los nombres de las dimensiones fuera de la vista.  
  
 Para obtener más información acerca de las tablas dinámicas, vea "Terminología de tablas dinámicas" en [http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416).  
  
## <a name="chart-view"></a>Vista de gráfico  
 El área Vista de diagrama muestra la agregación gráficamente. Office Web Components permite manipular los detalles de la agregación mediante la Vista de diagrama para ajustar los datos registrados según sea necesario. Si arrastra y coloca los elementos de datos de la lista de campos de diagrama para ajustar la agregación, el informe de tabla dinámica de la agregación se actualiza automáticamente para reflejar los cambios. Puede obtener detalles de la tabla dinámica para crear una alerta en la vista Agregación nueva.  
  
 ![](../core/media/aggregationchartview.gif "AggregationChartView")  
  
## <a name="more"></a>Más  
  
-   [Cómo establecer una alerta](../core/how-to-set-an-alert.md)  
  
-   [Cómo ver los resultados de una búsqueda de actividad](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [Cómo modificar una agregación](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es una agregación?](../core/what-is-an-aggregation.md)