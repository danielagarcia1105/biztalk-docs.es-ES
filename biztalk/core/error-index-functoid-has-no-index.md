---
title: Error - el Functoid de índice No tiene un índice | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0159d308c9befc90590d281351409ba571921a53
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968442"
---
# <a name="error---index-functoid-has-no-index"></a><span data-ttu-id="fb183-102">Error - el Functoid de índice No tiene un índice</span><span class="sxs-lookup"><span data-stu-id="fb183-102">Error - Index Functoid Has No Index</span></span>
<span data-ttu-id="fb183-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="fb183-103">**Error Code**</span></span>  
  
 <span data-ttu-id="fb183-104">btm1014</span><span class="sxs-lookup"><span data-stu-id="fb183-104">btm1014</span></span>  
  
 <span data-ttu-id="fb183-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="fb183-105">**Explanation**</span></span>  
  
 <span data-ttu-id="fb183-106">Se ha proporcionado ningún valor o valores de índice para el functoid **índice** functoid.</span><span class="sxs-lookup"><span data-stu-id="fb183-106">No index value(s) have been provided for the indicated **Index** functoid.</span></span>  
  
 <span data-ttu-id="fb183-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="fb183-107">**User Action**</span></span>  
  
 <span data-ttu-id="fb183-108">Proporcione un número apropiado de parámetros de entrada de índice para el functoid **índice** functoid, donde el número apropiado viene determinado por el número de bucle **registro** nodos dentro del cual el **Campo** está anidado el nodo del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="fb183-108">Provide an appropriate number of index input parameters for the indicated **Index** functoid, where the appropriate number is determined by the number of looping **Record** nodes within which the **Field** node in the source schema is nested.</span></span> <span data-ttu-id="fb183-109">Para crear parámetros de entrada de índice, seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, después, use la ![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert") botón dentro de la **configurar \<Functoid\> Functoid** cuadro de diálogo para agregar uno o más parámetros de entrada constantes, donde la primera de ellas representa un índice en el elemento primario inmediato bucle **registro** parámetros representan antecesor remoto bucle de entrada de nodo e índice siguientes **registro** nodos.</span><span class="sxs-lookup"><span data-stu-id="fb183-109">To created index input parameters, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then use the  ![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert") button within the **Configure \<Functoid\> Functoid** dialog box to add one or more constant input parameters, where the first one represents an index into the immediate parent looping **Record** node, and subsequent index input parameters represent increasingly remote ancestor looping **Record** nodes.</span></span>