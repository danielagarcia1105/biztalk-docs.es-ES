---
title: "Error: segunda entrada de Functoid acumulativo no válida | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.secondInputToCumulativeNotValid
ms.assetid: e41a58a7-e0a2-4284-bd19-279578a8915d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a288bdaa9427cd26191571d180d39ad2dde9f9f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---second-input-to-cumulative-functoid-not-valid"></a><span data-ttu-id="991b2-102">Error: segunda entrada de Functoid acumulativo no válida</span><span class="sxs-lookup"><span data-stu-id="991b2-102">Error - Second Input to Cumulative Functoid Not Valid</span></span>
<span data-ttu-id="991b2-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="991b2-103">**Error Code**</span></span>  
  
 <span data-ttu-id="991b2-104">btm1031</span><span class="sxs-lookup"><span data-stu-id="991b2-104">btm1031</span></span>  
  
 <span data-ttu-id="991b2-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="991b2-105">**Explanation**</span></span>  
  
 <span data-ttu-id="991b2-106">El functoid **acumulativa** el functoid tiene un segundo parámetro de entrada que no es válido.</span><span class="sxs-lookup"><span data-stu-id="991b2-106">The indicated **Cumulative** functoid has a second input parameter that is not valid.</span></span> <span data-ttu-id="991b2-107">El segundo parámetro de entrada de los functoids acumulativos debe ser un número entero positivo que indique el intervalo dentro del esquema de origen en el que tendrá lugar la acumulación.</span><span class="sxs-lookup"><span data-stu-id="991b2-107">The second input parameter to cumulative functoids must be a positive integer that indicates the range within the source schema over which the accumulation will be performed.</span></span>  
  
 <span data-ttu-id="991b2-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="991b2-108">**User Action**</span></span>  
  
 <span data-ttu-id="991b2-109">Seleccione el functoid **acumulativa** functoid, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **entradas de Functoid de orden** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, en la **configurar \<Functoid > Functoid** diálogo cuadro, asegúrese de que el segundo parámetro de entrada, si existe, es un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="991b2-109">Select the indicated **Cumulative** functoid, click the ellipsis (**...**) button associated with the **Order Functoid Inputs** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid> Functoid** dialog box, ensure that the second input parameter, if any, is a positive integer.</span></span>