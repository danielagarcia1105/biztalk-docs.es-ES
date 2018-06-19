---
title: 'Error: número de parámetros de entrada no es válido el Functoid de bucle de tabla | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.badParamCountForTableLooping
ms.assetid: 616e54aa-f6e3-4a49-afe2-278a0724e226
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2df0a6780485b91fc89356aecb73823643276be1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968466"
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a>Error: número de parámetros de entrada no es válido el Functoid de bucle de tabla
**Código de error**  
  
 btm1070  
  
 **Explicación**  
  
 El número de parámetros de entrada especificados para la correspondiente **bucle de tabla** functoid no es válido.  
  
 **Acción del usuario**  
  
 Asegúrese de que los parámetros de entrada para el **bucle de tabla** functoid, que se obtiene acceso a través de la **parámetros de entrada** propiedad y el **configurar \<Functoid\> Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.  
  
|Número de parámetro de entrada de functoid de Bucle de tabla|Description|  
|---------------------------------------------------|-----------------|  
|1|Vínculo de un registro o campo del esquema de origen, el número de repeticiones de los cuales un mensaje de instancia de entrada controla el número de veces que el conjunto de asociados **Extractor de tablas** functoids se ejecutan.|  
|2|El número de columnas en la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la correspondiente **bucle de tabla** functoid.|  
|3 – 100|Constantes y vínculos (del esquema de origen o de salida de otros functoids) que se convertirán en orígenes posibles de datos con la cuadrícula de bucle de tabla.|