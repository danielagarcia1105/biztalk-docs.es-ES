---
title: Functoid de bucle de tabla | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5e5f2967fb48bfe896c26246db1630266812f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="table-looping-functoid"></a>Functoid de bucle de tabla
El **bucle de tabla** functoid le permite crear una tabla de valores de salida que se usará al crear el mensaje de instancia de salida. Los datos de la tabla pueden constar de vínculos y constantes. El primer parámetro de entrada a la **bucle de tabla** functoid configura el ámbito o cuántos bucles realizará el registro. El segundo parámetro de entrada el **bucle de tabla** functoid determina cuántas columnas se encuentran en la tabla y las restantes entradas definen posibles valores de celdas de la tabla, sin ningún orden determinado. Para obtener más información sobre cómo trabajar con estas propiedades, vea [configuración de bucle de Table-Driven](../core/table-driven-looping-configuration.md). Consulte también [Table-Driven bucle ejemplo](../core/table-driven-looping-example.md).  
  
> [!NOTE]
>  El **bucle de tabla** functoid se repite con el registro de bucle está conectado a. Dentro de cada iteración, recorre una vez cada fila en la cuadrícula de bucle de tabla y produce múltiples bucles de salida.  
  
## <a name="see-also"></a>Vea también  
 [Functoid de Extractor de tablas](../core/table-extractor-functoid.md)   
 [Cómo agregar el bucle de tabla y Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoid de índice](../core/index-functoid.md)   
 [Functoid de iteración](../core/iteration-functoid.md)   
 [Functoid de bucle](../core/looping-functoid.md)   
 [Functoid de número de registros](../core/record-count-functoid.md)