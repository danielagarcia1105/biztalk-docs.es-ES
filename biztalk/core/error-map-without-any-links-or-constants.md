---
title: "Error - la asignación carece de vínculos o constantes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.mapWithoutAnyLinksOrConstants
ms.assetid: 8d1cdbcd-4bd0-4ddc-9e94-746e82b6ec48
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d697d6d053f2c0a36d0f5cb45002dca28a92f005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---map-without-any-links-or-constants"></a><span data-ttu-id="8f356-102">Error - la asignación carece de vínculos o constantes</span><span class="sxs-lookup"><span data-stu-id="8f356-102">Error - Map Without Any Links or Constants</span></span>
<span data-ttu-id="8f356-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="8f356-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8f356-104">btm1000</span><span class="sxs-lookup"><span data-stu-id="8f356-104">btm1000</span></span>  
  
 <span data-ttu-id="8f356-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="8f356-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8f356-106">La asignación carece de vínculos entre los esquemas o de valores constantes en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8f356-106">The map does not contain any links between the schemas, or constant values in the destination schema.</span></span> <span data-ttu-id="8f356-107">Por lo tanto, esta asignación no puede generar ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="8f356-107">Therefore, no output can be created from this map.</span></span>  
  
 <span data-ttu-id="8f356-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="8f356-108">**User Action**</span></span>  
  
 <span data-ttu-id="8f356-109">Agregue los vínculos correspondientes y, si es necesario, los functoids a la cuadrícula de asignación o las constantes al esquema de destino para especificar cómo se deben transformar los mensajes de instancia que se ajustan al esquema de origen en mensajes de instancia que se ajusten al esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8f356-109">Add the appropriate links and, if appropriate, functoids to the map grid, or constants to the destination schema, to specify how instance messages conforming to the source schema should be transformed into instance messages conforming to the destination schema.</span></span>