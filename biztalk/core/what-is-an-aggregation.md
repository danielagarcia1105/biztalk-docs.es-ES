---
title: ¿Qué es una agregación? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OLAP cubes, BAM
- BAM, aggregations
- BAM, OLAP cubes
- aggregations [BAM], OLAP cubes
- aggregations [BAM], about aggregations
- aggregations [BAM]
ms.assetid: 77d40602-ef56-4a5b-a18f-56ccbff573a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24dced4d7075e85b8b002bf90b821ce745f91e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289164"
---
# <a name="what-is-an-aggregation"></a>¿Qué es una agregación?
Excel define las agregaciones como resúmenes de datos precalculados que mejoran el tiempo de respuesta de consultas al tener preparadas las respuestas antes de que se planteen las preguntas. Por ejemplo, cuando una tabla de hechos de almacén de datos contiene cientos de miles de filas, una consulta que solicita las programaciones de envío de dos productos en concreto puede tardar en responder si la tabla de hechos se tiene que analizar para calcular la respuesta. Sin embargo, la respuesta podría ser casi inmediata si los datos de resumen para responder a esta consulta se ha calculado previamente.  
  
 En la siguiente ilustración se muestra un ejemplo de los datos de agregación precalculados.  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
Cubo OLAP de BAM  
  
 En la ilustración anterior se proporciona un resumen de los números de cada producto, enviados a las ubicaciones determinadas durante un período de tiempo de dos meses. Excel normalmente define estos datos como medida. Excel define como dimensión los datos que se usan para el filtrado y la categorización.  
  
 Para saber más acerca de la experiencia del usuario cuando examina datos multidimensionales, consulte el tema relativo a las tablas dinámicas en la Ayuda de Excel.  
  
 Puede crear agregaciones de actividad multidimensionales que estén basadas en los datos disponibles en una vista específica. Aquellas agregaciones contienen medidas (datos que se van a agregar, como la cantidad de dólares) y dimensiones (que se utilizan para filtrar o agrupar, como Estado y Ciudad).  
  
 Puede crear las agregaciones en forma de cubos de procesamiento analítico en línea (OLAP) que representen una instantánea del negocio a una hora determinada o como agregaciones en tiempo real, que determinan el escenario empresarial y que puede ver si utiliza la estructura multidimensional en tiempo real.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Agregaciones programadas](../core/scheduled-aggregations.md)  
  
-   [Agregaciones en tiempo real](../core/real-time-aggregations.md)