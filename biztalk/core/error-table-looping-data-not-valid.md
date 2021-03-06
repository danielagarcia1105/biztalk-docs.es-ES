---
title: 'Error: datos no válidos de bucle de tabla | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9478026980ecaf3e2049773737250c56d18262c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968556"
---
# <a name="error---table-looping-data-not-valid"></a>Error: datos no válidos de bucle de tabla
**Código de error**  
  
 btm1065  
  
 **Explicación**  
  
 La tabla de datos asociados con la correspondiente **bucle de tabla** functoid no es válido, probablemente porque no está configurado correctamente segundo parámetro de entrada del functoid o a una cuadrícula de bucle de tabla no está configurada correctamente.  
  
 **Acción del usuario**  
  
 Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid\> Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.  
  
|Número de parámetro de entrada de functoid de Bucle de tabla|Description|  
|---------------------------------------------------|-----------------|  
|1|Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.|  
|2|El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.|  
|3 – 100|Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.|  
  
 Además, asegúrese de configurar correctamente la cuadrícula de bucle de tabla que se obtiene acceso a través de la **cuadrícula de bucle de tabla** propiedad y el **configuración de bucle de tabla** cuadro de diálogo. Se debe elegir un valor constante o un vínculo para cada celda que vayan a tener acceso por un asociado **Extractor de tablas** functoid.