---
title: 'Error: primera entrada de Functoid de extractor de tablas no válida de valor | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputValueExtractorNotValid
ms.assetid: 7703ca5f-21aa-441f-8c28-b02da72c25c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68b143cea7e1d7e99c1d5b378bd9d6619270fb70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-value-extractor-functoid-not-valid"></a>Error: primera entrada de Functoid de extractor de tablas no válida de valor
**Código de error**  
  
 btm1002  
  
 **Explicación**  
  
 El primer parámetro de entrada para el functoid **Extractor de valor** functoid debe ser el resultado (un conjunto de registros ADO) desde el **base de datos de búsqueda** functoid.  
  
 **Acción del usuario**  
  
 Asegúrese de que la primera entrada a todos los **Extractor de valor** functoids es un vínculo de un **base de datos de búsqueda** functoid a la izquierda de una página de cuadrícula de asignación.