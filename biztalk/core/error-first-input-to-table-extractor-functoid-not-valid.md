---
title: 'Error: primera entrada de Functoid de Extractor de tablas no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d501c18bf104a0f538ef90d10510e7d9ec0f02
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969018"
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a><span data-ttu-id="2c3a8-102">Error: primera entrada de Functoid de Extractor de tablas no válida</span><span class="sxs-lookup"><span data-stu-id="2c3a8-102">Error - First Input to Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="2c3a8-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="2c3a8-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2c3a8-104">btm1019</span><span class="sxs-lookup"><span data-stu-id="2c3a8-104">btm1019</span></span>  
  
 <span data-ttu-id="2c3a8-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="2c3a8-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2c3a8-106">El primer parámetro de entrada para el functoid **Extractor de tablas** functoid no es un vínculo de un **bucle de tabla** functoid, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2c3a8-106">The first input parameter to the indicated **Table Extractor** functoid is not a link from a **Table Looping** functoid, as required.</span></span>  
  
 <span data-ttu-id="2c3a8-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="2c3a8-107">**User Action**</span></span>  
  
 <span data-ttu-id="2c3a8-108">Crear un vínculo entre el functoid **Extractor de tablas** functoid y los respectivos **bucle de tabla** functoid arrastrando uno de ellos al otro.</span><span class="sxs-lookup"><span data-stu-id="2c3a8-108">Create a link between the indicated **Table Extractor** functoid and the appropriate **Table Looping** functoid by dragging one of them to the other.</span></span> <span data-ttu-id="2c3a8-109">El primer functoid debe estar ubicado a la derecha del segundo en una página de cuadrícula de asignación.</span><span class="sxs-lookup"><span data-stu-id="2c3a8-109">The former functoid must be located to the right of the latter functoid in a map grid page.</span></span> <span data-ttu-id="2c3a8-110">Además, al usar el **configurar \<Functoid\> Functoid** diálogo cuadro, asegúrese de que el vínculo recién creado es el primer parámetro de entrada para el functoid **Extractor de tablas** functoid.</span><span class="sxs-lookup"><span data-stu-id="2c3a8-110">Also, using the **Configure \<Functoid\> Functoid** dialog box, ensure that the newly created link is the first input parameter to the indicated **Table Extractor** functoid.</span></span>