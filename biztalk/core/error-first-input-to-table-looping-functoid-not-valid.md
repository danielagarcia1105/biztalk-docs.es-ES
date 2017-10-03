---
title: "Error: primera entrada de Functoid no válida de bucle de tabla | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2cfa89175d566ed152caa852dfc7aef2b435447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a>Error: primera entrada de Functoid no válida de bucle de tabla
**Código de error**  
  
 btm1071  
  
 **Explicación**  
  
 El primer parámetro de entrada a la correspondiente **bucle de tabla** functoid no es válido. Este parámetro debe ser un vínculo desde un nodo del esquema de origen, el número de apariciones del elemento correspondiente en un mensaje de instancia de entrada controlará el número de veces que el conjunto de asociados **Extractor de tablas** functoids se invocará en tiempo de ejecución.  
  
 **Acción del usuario**  
  
 Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid > Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.  
  
|Número de parámetro de entrada de functoid de Bucle de tabla|Description|  
|---------------------------------------------------|-----------------|  
|1|Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.|  
|2|El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.|  
|3 – 100|Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.|