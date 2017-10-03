---
title: "Definición de agregaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], creating
- Excel add-in [BAM], creating aggregations
- aggregations [BAM], Excel add-in
- aggregations [BAM], about aggregations
ms.assetid: d5bf22d5-f491-4b08-a604-c7158e6e282f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3412615d03fc9a9776d86fddfb062ab343c5aaeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-aggregations"></a>Definir agregaciones
Excel define **agregaciones** como resúmenes precalculados de datos que mejoran el tiempo de respuesta de consulta debido a las respuestas listo antes de que se planteen las preguntas. Por ejemplo, cuando una tabla de hechos de almacén de datos contiene cientos de miles de filas, una consulta que solicita las programaciones de envío de dos productos en concreto puede tardar en responder si la tabla de hechos se tiene que analizar para calcular la respuesta. Sin embargo, la respuesta podría ser casi inmediata si los datos de resumen para responder a esta consulta se ha calculado previamente.  
  
 En la siguiente ilustración se muestra un ejemplo de los datos de agregación precalculados.  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
Datos de agregación precalculados  
  
 En la ilustración anterior se proporciona un resumen de los números de cada producto, enviados a las ubicaciones determinadas durante un período de tiempo de dos meses. Excel normalmente define estos datos como **medida**. Los datos utilizados para el filtrado y categorización, Excel define como **dimensión**.  
  
> [!NOTE]
>  BAM no admite el uso de instancias con nombre para los servicios de análisis de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
 Para saber más acerca de la experiencia del usuario al examinar datos multidimensionales, consulte el tema sobre tablas dinámicas de la Ayuda de Excel.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo definir medidas](../core/how-to-define-measures.md)  
  
-   [Definir dimensiones](../core/defining-dimensions.md)  
  
-   [Cómo utilizar la tabla dinámica](../core/how-to-use-the-pivottable.md)  
  
-   [Definición de agregaciones en tiempo real](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a>Vea también  
 [Definir una vista de SAE](../core/defining-a-bam-view.md)