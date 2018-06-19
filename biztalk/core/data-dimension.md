---
title: Dimensión de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data dimension [BAM]
- aggregations [BAM], data dimensions
ms.assetid: 07b5e56a-4fd5-4c88-a98a-758e514d0621
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7138cf31a9cb86a9ba949142129ac5c906754b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238356"
---
# <a name="data-dimension"></a>Dimensión de datos
La definición de una dimensión de datos permite usar el valor de ciertos elementos de texto de la actividad de BAM en filas o columnas. Por ejemplo, puede usarse una dimensión de datos llamada Productos para crear la tabla siguiente:  
  
|Product|Count|  
|-------------|-----------|  
|Raquetas de tenis|100|  
|Balones de fútbol|200|  
  
 Asimismo, es posible definir más de una dimensión de datos en el Asistente para vistas de BAM. Por ejemplo, definir una dimensión de datos llamada **ubicación** con niveles para **estado** y **City** puede usarse para crear la tabla siguiente:  
  
|||||  
|-|-|-|-|  
||California||Washington|  
||Los Angeles|San Francisco|Seattle|  
|Raquetas de tenis|50|20|30|  
|Balones de fútbol|130|50|20|  
  
 En esta tabla se usó la dimensión Producto para las filas y la dimensión Ubicación para las columnas.  
  
## <a name="see-also"></a>Vea también  
 [Dimensión de tiempo](../core/time-dimension.md)   
 [Dimensión de progreso](../core/progress-dimension.md)   
 [Dimensión de rango numérico](../core/numeric-range-dimension.md)   
 [Definir dimensiones](../core/defining-dimensions.md)