---
title: 'Error: se generan varios elementos secundarios equivalentes | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.couldGenMultipleEquivChildren
ms.assetid: ef3ea6db-6759-4f38-804c-e32a1f24d758
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686899c2871ded25f6901e919e9283694b9bacf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---could-generate-multiple-equivalent-children"></a><span data-ttu-id="9dbfe-102">Error: se generan varios elementos secundarios equivalentes</span><span class="sxs-lookup"><span data-stu-id="9dbfe-102">Error - Could Generate Multiple Equivalent Children</span></span>
<span data-ttu-id="9dbfe-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="9dbfe-103">**Error Code**</span></span>  
  
 <span data-ttu-id="9dbfe-104">btm1026</span><span class="sxs-lookup"><span data-stu-id="9dbfe-104">btm1026</span></span>  
  
 <span data-ttu-id="9dbfe-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="9dbfe-105">**Explanation**</span></span>  
  
 <span data-ttu-id="9dbfe-106">Vínculos al esquema de destino habilitan, indebidamente varios nodos dentro de un **equivalente** nodo de grupo que se genere.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-106">Links to the destination schema inappropriately enable multiple nodes within an **Equivalent** group node to be generated.</span></span>  
  
 <span data-ttu-id="9dbfe-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="9dbfe-107">**User Action**</span></span>  
  
 <span data-ttu-id="9dbfe-108">Cambie los vínculos del esquema de destino, utilizan potencialmente functoids lógicos, por lo que es un único nodo dentro de la **equivalente** nodo de grupo puede generarse durante la asignación.</span><span class="sxs-lookup"><span data-stu-id="9dbfe-108">Rework the links into the destination schema, potentially using logical functoids, so that only a single node within the **Equivalent** group node can be generated during mapping.</span></span>