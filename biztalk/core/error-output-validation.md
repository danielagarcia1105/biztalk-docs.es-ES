---
title: "Error: validación de salida | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.outputValidation
ms.assetid: 18a251a9-6bd4-4fd1-a774-2ea1b7870891
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7410fba7cebbf5183a02e79aa3c179eb86cd8395
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---output-validation"></a><span data-ttu-id="687d3-102">Error: validación de salida</span><span class="sxs-lookup"><span data-stu-id="687d3-102">Error - Output Validation</span></span>
<span data-ttu-id="687d3-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="687d3-103">**Error Code**</span></span>  
  
 <span data-ttu-id="687d3-104">btm1046</span><span class="sxs-lookup"><span data-stu-id="687d3-104">btm1046</span></span>  
  
 <span data-ttu-id="687d3-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="687d3-105">**Explanation**</span></span>  
  
 <span data-ttu-id="687d3-106">El archivo de mensaje de instancia de salida que creó la operación Comprobar asignación no se pudo validar con respecto al esquema de destino por la razón indicada.</span><span class="sxs-lookup"><span data-stu-id="687d3-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for the indicated reason.</span></span>  
  
 <span data-ttu-id="687d3-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="687d3-107">**User Action**</span></span>  
  
 <span data-ttu-id="687d3-108">En función de la razón indicada, haga las correcciones correspondientes en las transformaciones especificadas en la asignación, en el esquema de destino o en ambos.</span><span class="sxs-lookup"><span data-stu-id="687d3-108">Based on the indicated reason, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="687d3-109">Puede resultar útil abrir el esquema de destino en el Editor de BizTalk y utilice la **Validar esquema**, **Validar instancia**, y **generar instancia** comandos disponibles cuando Haga un esquema en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="687d3-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>