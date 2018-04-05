---
title: 'Error: primera entrada de Functoid de Extractor de tablas no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d501c18bf104a0f538ef90d10510e7d9ec0f02
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a>Error: primera entrada de Functoid de Extractor de tablas no válida
**Código de error**  
  
 btm1019  
  
 **Explicación**  
  
 El primer parámetro de entrada para el functoid **Extractor de tablas** functoid no es un vínculo de un **bucle de tabla** functoid, según sea necesario.  
  
 **Acción del usuario**  
  
 Crear un vínculo entre el functoid **Extractor de tablas** functoid y los respectivos **bucle de tabla** functoid arrastrando uno de ellos al otro. El primer functoid debe estar ubicado a la derecha del segundo en una página de cuadrícula de asignación. Además, al usar el **configurar \<Functoid\> Functoid** diálogo cuadro, asegúrese de que el vínculo recién creado es el primer parámetro de entrada para el functoid **Extractor de tablas** functoid.