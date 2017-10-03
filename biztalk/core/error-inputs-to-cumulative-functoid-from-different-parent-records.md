---
title: Error - entradas al Functoid acumulado de distintos registros primarios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.inputsToCumulativeFromDiffParents
ms.assetid: a2dcfe6f-0cd4-41ed-a69f-e510a74760a9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3c919001e05ca99383ffce72c8d450f6d04624b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---inputs-to-cumulative-functoid-from-different-parent-records"></a><span data-ttu-id="f14f6-102">Error - entradas de Functoid acumulado procedentes de distintos registros primarios</span><span class="sxs-lookup"><span data-stu-id="f14f6-102">Error - Inputs to Cumulative Functoid from Different Parent Records</span></span>
<span data-ttu-id="f14f6-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="f14f6-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f14f6-104">btm1032</span><span class="sxs-lookup"><span data-stu-id="f14f6-104">btm1032</span></span>  
  
 <span data-ttu-id="f14f6-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="f14f6-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f14f6-106">Para el functoid **acumulativa** functoid, el segundo parámetro de entrada (el ámbito de acumulación) procede de una parte distinta del esquema de origen que el nodo que actúa como el primer parámetro de entrada (el nodo a acumular).</span><span class="sxs-lookup"><span data-stu-id="f14f6-106">For the indicated **Cumulative** functoid, the second input parameter (the accumulation scope) is from a different part of the source schema than the node serving as the first input parameter (the node to accumulate).</span></span>  
  
 <span data-ttu-id="f14f6-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="f14f6-107">**User Action**</span></span>  
  
 <span data-ttu-id="f14f6-108">Asegúrese de que ambos parámetros de entrada que el indicado **acumulativa** functoid comparten el mismo registro primario, o que el segundo parámetro de entrada (el ámbito de acumulación) proporcionan tiene un parámetro de entrada constante.</span><span class="sxs-lookup"><span data-stu-id="f14f6-108">Ensure that both input parameters to the indicated **Cumulative** functoid share the same parent record, or that the second input parameter (the accumulation scope) you provide has a constant input parameter.</span></span>