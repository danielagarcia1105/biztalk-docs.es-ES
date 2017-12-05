---
title: "Error - el Functoid de índice No tiene un índice | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0159d308c9befc90590d281351409ba571921a53
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---index-functoid-has-no-index"></a>Error - el Functoid de índice No tiene un índice
**Código de error**  
  
 btm1014  
  
 **Explicación**  
  
 Se ha proporcionado ningún valor o valores de índice para el functoid **índice** functoid.  
  
 **Acción del usuario**  
  
 Proporcione un número apropiado de parámetros de entrada de índice para el functoid **índice** functoid, donde el número apropiado viene determinado por el número de bucle **registro** nodos dentro del cual el **Campo** está anidado el nodo del esquema de origen. Para crear parámetros de entrada de índice, seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, después, use la ![ ] (../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert") botón dentro de la **configurar \<Functoid\> Functoid** cuadro de diálogo para agregar uno o más parámetros de entrada constantes, donde la primera de ellas representa un índice en el elemento primario inmediato bucle **registro** parámetros representan antecesor remoto bucle de entrada de nodo e índice siguientes **registro** nodos.