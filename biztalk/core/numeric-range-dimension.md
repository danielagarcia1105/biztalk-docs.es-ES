---
title: Dimensión de rango numérico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], Numeric Range dimension
- Numeric Range dimension [BAM]
ms.assetid: a874ce44-b034-498f-ba58-114028dbef2c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fb6d4c21e0a207cfeec3e592569ca0f48f3badf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263404"
---
# <a name="numeric-range-dimension"></a>Dimensión de rango numérico
La dimensión de rango numérico permite clasificar las agregaciones según los nombres descriptivos de distintos rangos especificados. Por ejemplo, un analista de negocios puede definir una dimensión de rango numérico llamada Tamaño de pedido de compra con los rangos Pequeño para pedidos de entre 0 y 100 USD, Mediano para pedidos de entre 100 y 1.000 USD, y Grande para pedidos de más de 1.000 USD.  
  
> [!NOTE]
>  Si una cantidad de pedido de compra no está en los intervalos definidos, por ejemplo, una cantidad de pedido de compra es menor que 0 y, a continuación, una fila "fuera del intervalo" se crearán automáticamente por BAM para dar cabida a los datos fuera del intervalo.  
  
> [!NOTE]
>  No puede crear dos dimensiones de rango numérico que hagan referencia al mismo alias de datos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo utilizar la tabla dinámica](../core/how-to-use-the-pivottable.md)   
 [Dimensión de progreso](../core/progress-dimension.md)   
 [Dimensión de datos](../core/data-dimension.md)   
 [Dimensión de tiempo](../core/time-dimension.md)   
 [Definir dimensiones](../core/defining-dimensions.md)