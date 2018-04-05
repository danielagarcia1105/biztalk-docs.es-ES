---
title: 'Error: los elementos secundarios del Functoid de copia masiva generan código | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.massCopyChildtenGenCode
ms.assetid: c791009b-241b-4004-b0c6-f1536bb119c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68183a90be46b176d13100b02cbed2798fe24b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a><span data-ttu-id="182bb-102">Error: los elementos secundarios del Functoid de copia masiva generan código</span><span class="sxs-lookup"><span data-stu-id="182bb-102">Error - Children of Mass Copy Functoid Generate Code</span></span>
<span data-ttu-id="182bb-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="182bb-103">**Error Code**</span></span>  
  
 <span data-ttu-id="182bb-104">btm1068</span><span class="sxs-lookup"><span data-stu-id="182bb-104">btm1068</span></span>  
  
 <span data-ttu-id="182bb-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="182bb-105">**Explanation**</span></span>  
  
 <span data-ttu-id="182bb-106">Un escenario que contradice la funcionalidad de la **copia masiva** functoid se encontró en la asignación.</span><span class="sxs-lookup"><span data-stu-id="182bb-106">A scenario that contradicts the functionality of the **Mass Copy** functoid was found in the map.</span></span> <span data-ttu-id="182bb-107">En el esquema de destino, los nodos descendientes de un nodo que está vinculado a la salida de un **copia masiva** functoid están intentado generar código XSLT propio.</span><span class="sxs-lookup"><span data-stu-id="182bb-107">In the destination schema, descendent nodes of a node that is linked to the output of a **Mass Copy** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="182bb-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="182bb-108">**User Action**</span></span>  
  
 <span data-ttu-id="182bb-109">Elimine la incompatibilidad cambiando el uso de la correspondiente **copia masiva** functoid o cambiando los nodos secundarios de modo que ya no generen código XSLT propio.</span><span class="sxs-lookup"><span data-stu-id="182bb-109">Remove the incompatibility by changing the usage of the relevant **Mass Copy** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>