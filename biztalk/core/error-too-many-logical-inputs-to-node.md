---
title: "Error: demasiadas entradas lógicas en el nodo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tooManyLogicalInputsToNode
ms.assetid: 9295d6a2-702d-4cf3-8f5d-26ba63b9fce0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e363d79a2b013b8e90533c4e6e36cff5b5798b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---too-many-logical-inputs-to-node"></a><span data-ttu-id="fc4a4-102">Error: demasiadas entradas lógicas en el nodo</span><span class="sxs-lookup"><span data-stu-id="fc4a4-102">Error - Too Many Logical Inputs to Node</span></span>
<span data-ttu-id="fc4a4-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="fc4a4-103">**Error Code**</span></span>  
  
 <span data-ttu-id="fc4a4-104">btm1006</span><span class="sxs-lookup"><span data-stu-id="fc4a4-104">btm1006</span></span>  
  
 <span data-ttu-id="fc4a4-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="fc4a4-105">**Explanation**</span></span>  
  
 <span data-ttu-id="fc4a4-106">Hay un mayor número de vínculos lógicos conectados al nodo indicado en el esquema de destino que el número de vínculos de entrada a la **bucle** functoid que esté conectado al nodo antecesor del nodo indicado.</span><span class="sxs-lookup"><span data-stu-id="fc4a4-106">There are a greater number of logical links connected to the indicated node in the destination schema than the number of input links to the **Looping** functoid that is connected to an ancestor node of the indicated node.</span></span> <span data-ttu-id="fc4a4-107">El número de vínculos, tanto del primer tipo como del segundo, debe coincidir.</span><span class="sxs-lookup"><span data-stu-id="fc4a4-107">The number of links of the former and latter types should match.</span></span>  
  
 <span data-ttu-id="fc4a4-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="fc4a4-108">**User Action**</span></span>  
  
 <span data-ttu-id="fc4a4-109">Repetición del trabajo el número de vínculos conectados al nodo indicado y a la **bucle** functoid conectado al nodo antecesor para que coincidan.</span><span class="sxs-lookup"><span data-stu-id="fc4a4-109">Rework the number of links connected to the indicated node and to the **Looping** functoid connected to the ancestor node so that they match.</span></span>