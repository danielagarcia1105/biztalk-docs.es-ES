---
title: 'Error: número máximo de coincidencias de propiedad promocionada se produce | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c8395757d19eff5241d47c31b15409a00b6faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239868"
---
# <a name="error---promoted-property-max-occurs"></a><span data-ttu-id="474ca-102">Error: número máximo de coincidencias de propiedad promocionada se produce</span><span class="sxs-lookup"><span data-stu-id="474ca-102">Error - Promoted Property Max Occurs</span></span>
<span data-ttu-id="474ca-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="474ca-103">**Error Code**</span></span>  
  
 <span data-ttu-id="474ca-104">BEC2002</span><span class="sxs-lookup"><span data-stu-id="474ca-104">BEC2002</span></span>  
  
 <span data-ttu-id="474ca-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="474ca-105">**Explanation**</span></span>  
  
 <span data-ttu-id="474ca-106">La configuración de la **Max Occurs** propiedad del nodo promocionado, o de uno de sus nodos antecesores, es incompatible con la promoción de propiedades.</span><span class="sxs-lookup"><span data-stu-id="474ca-106">The setting of the **Max Occurs** property of the node being promoted, or of one of its ancestor nodes, is incompatible with property promotion.</span></span> <span data-ttu-id="474ca-107">La promoción de propiedades se deshabilita para nodos que puedan aparecer más de una vez en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="474ca-107">Property promotion is disallowed for nodes that can occur more than once in an instance message.</span></span> <span data-ttu-id="474ca-108">Por lo tanto, la **Max Occurs** propiedades de todos los nodos del nodo promocionado al nodo raíz deben establecerse en 1.</span><span class="sxs-lookup"><span data-stu-id="474ca-108">Therefore, the **Max Occurs** properties of all nodes from the node being promoted back to the root node must be set to 1.</span></span>  
  
 <span data-ttu-id="474ca-109">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="474ca-109">**User Action**</span></span>  
  
 <span data-ttu-id="474ca-110">Asegúrese de que el **Max Occurs** propiedad del nodo promocionado y todos sus nodos antecesores está establecida en uno (1).</span><span class="sxs-lookup"><span data-stu-id="474ca-110">Ensure that the **Max Occurs** property of the node being promoted and all of its ancestor nodes is set to one (1).</span></span>