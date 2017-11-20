---
title: Analizar esquemas de archivo sin formato con registros posicionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], flat file documents
- pipeline components [custom], parsing
ms.assetid: 1ceb8c06-ac21-490e-b3d5-54e5035e5f6a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4a6a1d5d6c263c0f794d1b703eff256f15c43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="parsing-flat-file-schemas-with-positional-records"></a><span data-ttu-id="504f3-102">Analizar esquemas de archivo sin formato con registros posicionales</span><span class="sxs-lookup"><span data-stu-id="504f3-102">Parsing Flat File Schemas with Positional Records</span></span>
<span data-ttu-id="504f3-103">Al analizar un esquema de archivo sin formato con registros posicionales de tamaños desiguales, debe incluir una etiqueta en cada registro del esquema, o bien el finalizador, para indicar el tamaño de cada registro posicional.</span><span class="sxs-lookup"><span data-stu-id="504f3-103">When parsing a flat file schema with positional records of unequal size, you must include a tag within each schema record or the trailer to indicate the size of each positional record.</span></span> <span data-ttu-id="504f3-104">De lo contrario, el motor de análisis devuelve el tamaño de registro más largo.</span><span class="sxs-lookup"><span data-stu-id="504f3-104">Otherwise, the parsing engine returns the longest record size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504f3-105">Vea también</span><span class="sxs-lookup"><span data-stu-id="504f3-105">See Also</span></span>  
 [<span data-ttu-id="504f3-106">Usar el motor de análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="504f3-106">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)