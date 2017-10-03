---
title: "Error: segunda entrada de tabla no es válido el Functoid de bucle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.secondInputForTableLoopingNotValid
ms.assetid: 22771f36-5969-40b1-a957-3ca67e19c3fd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caab1e1cac77dda276398fcc0331b2bfac2bcbd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a>Error: segunda entrada de tabla no es válido el Functoid de bucle
**Código de error**  
  
 btm1072  
  
 **Explicación**  
  
 El segundo parámetro a la correspondiente de entrada **bucle de tabla** functoid no es válido. Este parámetro debe ser un número entero positivo que indique el número de columnas de la cuadrícula de bucle de tabla asociada.  
  
 **Acción del usuario**  
  
 Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid > Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.  
  
|Número de parámetro de entrada de functoid de Bucle de tabla|Description|  
|---------------------------------------------------|-----------------|  
|1|Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.|  
|2|El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.|  
|3 – 100|Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.|