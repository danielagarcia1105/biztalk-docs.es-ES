---
title: 'Error: primera entrada de Functoid de extractor de tablas no válida de valor | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputValueExtractorNotValid
ms.assetid: 7703ca5f-21aa-441f-8c28-b02da72c25c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68b143cea7e1d7e99c1d5b378bd9d6619270fb70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-value-extractor-functoid-not-valid"></a><span data-ttu-id="d337a-102">Error: primera entrada de Functoid de extractor de tablas no válida de valor</span><span class="sxs-lookup"><span data-stu-id="d337a-102">Error - First Input to Value Extractor Functoid Not Valid</span></span>
<span data-ttu-id="d337a-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="d337a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d337a-104">btm1002</span><span class="sxs-lookup"><span data-stu-id="d337a-104">btm1002</span></span>  
  
 <span data-ttu-id="d337a-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="d337a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d337a-106">El primer parámetro de entrada para el functoid **Extractor de valor** functoid debe ser el resultado (un conjunto de registros ADO) desde el **base de datos de búsqueda** functoid.</span><span class="sxs-lookup"><span data-stu-id="d337a-106">The first input parameter to the indicated **Value Extractor** functoid must be the output (an ADO recordset) from the **Database Lookup** functoid.</span></span>  
  
 <span data-ttu-id="d337a-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="d337a-107">**User Action**</span></span>  
  
 <span data-ttu-id="d337a-108">Asegúrese de que la primera entrada a todos los **Extractor de valor** functoids es un vínculo de un **base de datos de búsqueda** functoid a la izquierda de una página de cuadrícula de asignación.</span><span class="sxs-lookup"><span data-stu-id="d337a-108">Ensure that the first input to all **Value Extractor** functoids is a link from a **Database Lookup** functoid to their left in a map grid page.</span></span>