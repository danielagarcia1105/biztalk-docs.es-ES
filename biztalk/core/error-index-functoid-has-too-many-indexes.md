---
title: "Error - el Functoid de índice tiene demasiados índices | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.indexFunctoidHasTooManyIndices
ms.assetid: 5dd2d5b4-3f7a-45be-b6f4-708b0a76805a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a22b49a921b957c0fb36f9e6b6925c991cc3cf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---index-functoid-has-too-many-indexes"></a>Error - el Functoid de índice tiene demasiados índices
**Código de error**  
  
 btm1016  
  
 **Explicación**  
  
 El functoid **índice** el functoid tiene demasiados parámetros de entrada de índice especificados. El número de parámetros de entrada de índice no debe superar el número de bucle antecesor **registro** nodos dentro del cual el **campo** nodo especificado como primer parámetro de entrada está anidado.  
  
 **Acción del usuario**  
  
 Seleccione el functoid **índice** functoid, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, en la **configurar \<Functoid\> Functoid** cuadro de diálogo, elimine el índice exceso los parámetros de entrada seleccionando y haciendo clic en el ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") botón para cada uno de ellos.