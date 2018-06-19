---
title: Dimensión de tiempo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Time dimension [BAM]
- aggregations [BAM], Time dimension
ms.assetid: 8f83b758-09a1-4efb-ae0e-32753f56c4e4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 418afdc5b7507aba9a564628341c10495b2a740a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279452"
---
# <a name="time-dimension"></a>Dimensión de tiempo
La dimensión de tiempo permite crear agregaciones con respecto al tiempo. Por ejemplo, puede usar una dimensión de tiempo para crear la tabla siguiente:  
  
|Year|Month|Count|  
|----------|-----------|-----------|  
|2003|January|120|  
||February|230|  
||March|350|  
||April|280|  
  
 La dimensión de tiempo puede combinarse con cualquier otra dimensión. Por ejemplo, puede usar la dimensión de tiempo en filas y la dimensión de datos en columnas para crear la tabla siguiente:  
  
|||Raquetas de tenis|Balones de fútbol|  
|------|------|---------------------|------------------|  
||January|50|70|  
||February|120|110|  
||March|300|50|  
||April|220|60|  
  
## <a name="see-also"></a>Vea también  
 [Dimensión de rango numérico](../core/numeric-range-dimension.md)   
 [Dimensión de progreso](../core/progress-dimension.md)   
 [Dimensión de datos](../core/data-dimension.md)   
 [Definir dimensiones](../core/defining-dimensions.md)