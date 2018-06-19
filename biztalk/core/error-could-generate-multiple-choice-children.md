---
title: 'Error: se generan varios secundarios de elección | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.couldGenMultipleChoiceChildren
ms.assetid: 64e69ebb-781f-4ecb-9d91-6fdcca949d4b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9322897f6fab9bc4b9c3e098214c19fb339b58d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240692"
---
# <a name="error---could-generate-multiple-choice-children"></a><span data-ttu-id="2e79a-102">Error: se generan varios secundarios de elección</span><span class="sxs-lookup"><span data-stu-id="2e79a-102">Error - Could Generate Multiple Choice Children</span></span>
<span data-ttu-id="2e79a-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="2e79a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2e79a-104">btm1027</span><span class="sxs-lookup"><span data-stu-id="2e79a-104">btm1027</span></span>  
  
 <span data-ttu-id="2e79a-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="2e79a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2e79a-106">Vínculos al esquema de destino habilitan, indebidamente varios nodos dentro de un **elección** nodo de grupo que se genere.</span><span class="sxs-lookup"><span data-stu-id="2e79a-106">Links to the destination schema inappropriately enable multiple nodes within a **Choice** group node to be generated.</span></span>  
  
 <span data-ttu-id="2e79a-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="2e79a-107">**User Action**</span></span>  
  
 <span data-ttu-id="2e79a-108">Cambie los vínculos en el esquema de destino, por lo tanto que solo un único nodo dentro del **elección** se puede generar el nodo de grupo.</span><span class="sxs-lookup"><span data-stu-id="2e79a-108">Rework the links into the destination schema so that only a single node within the **Choice** group node can be generated.</span></span>