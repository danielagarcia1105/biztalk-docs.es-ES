---
title: Error - el Functoid de índice tiene demasiados índices | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasTooManyIndices
ms.assetid: 5dd2d5b4-3f7a-45be-b6f4-708b0a76805a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a22b49a921b957c0fb36f9e6b6925c991cc3cf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968946"
---
# <a name="error---index-functoid-has-too-many-indexes"></a><span data-ttu-id="23eb0-102">Error - el Functoid de índice tiene demasiados índices</span><span class="sxs-lookup"><span data-stu-id="23eb0-102">Error - Index Functoid Has Too Many Indexes</span></span>
<span data-ttu-id="23eb0-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="23eb0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="23eb0-104">btm1016</span><span class="sxs-lookup"><span data-stu-id="23eb0-104">btm1016</span></span>  
  
 <span data-ttu-id="23eb0-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="23eb0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="23eb0-106">El functoid **índice** el functoid tiene demasiados parámetros de entrada de índice especificados.</span><span class="sxs-lookup"><span data-stu-id="23eb0-106">The indicated **Index** functoid has too many index input parameters specified.</span></span> <span data-ttu-id="23eb0-107">El número de parámetros de entrada de índice no debe superar el número de bucle antecesor **registro** nodos dentro del cual el **campo** nodo especificado como primer parámetro de entrada está anidado.</span><span class="sxs-lookup"><span data-stu-id="23eb0-107">The number of index input parameters must not exceed the number of ancestor looping **Record** nodes within which the **Field** node specified as the first input parameter is nested.</span></span>  
  
 <span data-ttu-id="23eb0-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="23eb0-108">**User Action**</span></span>  
  
 <span data-ttu-id="23eb0-109">Seleccione el functoid **índice** functoid, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, en la **configurar \<Functoid\> Functoid** cuadro de diálogo, elimine el índice exceso los parámetros de entrada seleccionando y haciendo clic en el ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") botón para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="23eb0-109">Select the indicated **Index** functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete the excess index input parameters by selecting and clicking the  ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span>