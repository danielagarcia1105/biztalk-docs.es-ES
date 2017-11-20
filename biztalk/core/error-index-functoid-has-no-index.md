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
ms.openlocfilehash: 8143442b9d77d6881efe2b64dfb7f5888ab2d466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---index-functoid-has-no-index"></a>Error - el Functoid de índice No tiene un índice
**Código de error**  
  
 btm1014  
  
 **Explicación**  
  
 Se ha proporcionado ningún valor o valores de índice para el functoid **índice** functoid.  
  
 **Acción del usuario**  
  
 Proporcione un número apropiado de parámetros de entrada de índice para el functoid **índice** functoid, donde el número apropiado viene determinado por el número de bucle **registro** nodos dentro del cual el **Campo** está anidado el nodo del esquema de origen. Para crear parámetros de entrada de índice, seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) botón asociado a la **parámetros de entrada** propiedad Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, utilice la ![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert") botón dentro de la **configurar \< Functoid > Functoid** cuadro de diálogo para agregar uno o más parámetros de entrada constantes, donde la primera de ellas representa un índice en el bucle principal inmediato **registro** nodo y parámetros de entrada de índice siguientes representar antecesor remoto bucle **registro** nodos.