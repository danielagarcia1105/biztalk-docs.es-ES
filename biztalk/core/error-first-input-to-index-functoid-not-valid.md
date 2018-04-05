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
---
# <a name="error---first-input-to-index-functoid-not-valid"></a><span data-ttu-id="005fd-102">Error: primera entrada de Functoid de índice no válida</span><span class="sxs-lookup"><span data-stu-id="005fd-102">Error - First Input to Index Functoid Not Valid</span></span>
<span data-ttu-id="005fd-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="005fd-103">**Error Code**</span></span>  
  
 <span data-ttu-id="005fd-104">btm1015</span><span class="sxs-lookup"><span data-stu-id="005fd-104">btm1015</span></span>  
  
 <span data-ttu-id="005fd-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="005fd-105">**Explanation**</span></span>  
  
 <span data-ttu-id="005fd-106">El primer parámetro de entrada para el functoid **índice** functoid no es de un **campo** nodo dentro de un bucle **registro** nodo del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="005fd-106">The first input parameter to the indicated **Index** functoid is not from a **Field** node within a looping **Record** node in the source schema.</span></span>  
  
 <span data-ttu-id="005fd-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="005fd-107">**User Action**</span></span>  
  
 <span data-ttu-id="005fd-108">Crear el vínculo de entrada correspondiente arrastrando de un **campo** nodo dentro de un bucle **registro** nodo en el esquema de origen y el functoid **índice** functoid.</span><span class="sxs-lookup"><span data-stu-id="005fd-108">Create the appropriate input link by dragging between a **Field** node within a looping **Record** node in the source schema and the indicated **Index** functoid.</span></span> <span data-ttu-id="005fd-109">Puede que sea necesario abrir el **configurar \<Functoid\> Functoid** cuadro de diálogo, seleccione el functoid **índice** functoid y haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades para asegurarse de que el vínculo recién creado constituye el primer parámetro de entrada para el functoid **Índice** functoid.</span><span class="sxs-lookup"><span data-stu-id="005fd-109">It may be necessary to open the **Configure \<Functoid\> Functoid** dialog box by selecting the indicated **Index** functoid and clicking the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window in order to ensure that the newly created link is the first input parameter to the indicated **Index** functoid.</span></span>