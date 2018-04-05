---
title: 'Error: segunda entrada de Functoid de tabla extractor de tablas no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e674ad6777ebff53fefe053e1b6af46ebc54ef3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a>Error: segunda entrada de Functoid de tabla extractor de tablas no válida
**Código de error**  
  
 btm1073  
  
 **Explicación**  
  
 El segundo parámetro a la correspondiente de entrada **Extractor de tablas** functoid no es válido. Este parámetro debe ser una constante de número entero positivo que indica una columna válida de la tabla configurada para cuadrícula de bucle la **bucle de tabla** functoid indicado por el primer parámetro de entrada.  
  
 **Acción del usuario**  
  
 Asegúrese de que los parámetros de entrada a la correspondiente **Extractor de tablas** functoid, que se obtiene acceso a través de su **parámetros de entrada** propiedad y el **configurar \<Functoid\> Functoid** cuadro de diálogo, son como se muestra en la tabla siguiente.  
  
|Número de parámetro de entrada del functoid de Extractor de tablas|Description|  
|-----------------------------------------------------|-----------------|  
|1|Vincular desde el **bucle de tabla** functoid a partir del cual **Extractor de tablas** functoid extraerá los datos de la columna tal y como indica su segundo parámetro.|  
|2|El número de una columna válida de la tabla de datos que se configura a través de la **cuadrícula de bucle de tabla** propiedad de la **bucle de tabla** especificado por el primer parámetro de entrada de functoid.|