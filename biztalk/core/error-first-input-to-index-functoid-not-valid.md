---
title: 'Error: primera entrada de Functoid de índice no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToIndexNotValid
ms.assetid: f7dbe9cc-9cfa-4fc7-af3e-1241cb2b50a9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 163de330945cc085648188dffcb75821c11ec5d6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969650"
---
# <a name="error---first-input-to-index-functoid-not-valid"></a>Error: primera entrada de Functoid de índice no válida
**Código de error**  
  
 btm1015  
  
 **Explicación**  
  
 El primer parámetro de entrada para el functoid **índice** functoid no es de un **campo** nodo dentro de un bucle **registro** nodo del esquema de origen.  
  
 **Acción del usuario**  
  
 Crear el vínculo de entrada correspondiente arrastrando de un **campo** nodo dentro de un bucle **registro** nodo en el esquema de origen y el functoid **índice** functoid. Puede que sea necesario abrir el **configurar \<Functoid\> Functoid** cuadro de diálogo, seleccione el functoid **índice** functoid y haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades para asegurarse de que el vínculo recién creado constituye el primer parámetro de entrada para el functoid **Índice** functoid.