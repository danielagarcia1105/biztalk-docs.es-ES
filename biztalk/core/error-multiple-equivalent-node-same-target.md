---
title: Error - varios nodos equivalente mismo destino | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.multipleEquivNodeSameTarget
ms.assetid: d8ca9f94-1d87-41bb-9479-6a01a5b6702d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12df4f7a68bb1eceaa3211c6aad6e9a581f17a4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-equivalent-node-same-target"></a><span data-ttu-id="51c64-102">Error - varios nodos equivalente mismo destino</span><span class="sxs-lookup"><span data-stu-id="51c64-102">Error - Multiple Equivalent Node Same Target</span></span>
<span data-ttu-id="51c64-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="51c64-103">**Error Code**</span></span>  
  
 <span data-ttu-id="51c64-104">btm1025</span><span class="sxs-lookup"><span data-stu-id="51c64-104">btm1025</span></span>  
  
 <span data-ttu-id="51c64-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="51c64-105">**Explanation**</span></span>  
  
 <span data-ttu-id="51c64-106">Los nodos indicados en el esquema de origen, que son nodos secundarios en conflicto de un **equivalente** nodo de grupo, están vinculados al nodo indicado del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="51c64-106">The indicated nodes in the source schema, which are conflicting child nodes of an **Equivalent** group node, are both linked to the indicated node in the destination schema.</span></span> <span data-ttu-id="51c64-107">Solo puede aparecer uno de estos nodos en el esquema de origen de un mensaje de instancia determinado.</span><span class="sxs-lookup"><span data-stu-id="51c64-107">Only one of these nodes in the source schema can occur in a given instance message.</span></span>  
  
 <span data-ttu-id="51c64-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="51c64-108">**User Action**</span></span>  
  
 <span data-ttu-id="51c64-109">Asegúrese de que solo uno de los secundarios nodos de la **equivalente** nodo de grupo está conectado a un nodo determinado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="51c64-109">Ensure that only one of the child nodes of the **Equivalent** group node is connected to a given node in the destination schema.</span></span>