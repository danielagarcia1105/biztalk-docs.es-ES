---
title: 'Error: el destino necesario con origen opcional | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.reqdTargetWithOptionalSource
ms.assetid: 3f342011-4577-4682-8324-8296615d5194
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76dd96f61766a475db6385e306bc64bc36db4fcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-with-optional-source"></a><span data-ttu-id="20c8d-102">Error: el destino necesario con origen opcional</span><span class="sxs-lookup"><span data-stu-id="20c8d-102">Error - Required Target with Optional Source</span></span>
<span data-ttu-id="20c8d-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="20c8d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="20c8d-104">btm1001</span><span class="sxs-lookup"><span data-stu-id="20c8d-104">btm1001</span></span>  
  
 <span data-ttu-id="20c8d-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="20c8d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="20c8d-106">Los datos del nodo necesario indicado en el esquema de destino proceden de un nodo opcional del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="20c8d-106">The data for the indicated required node in the destination schema comes from an optional node in the source schema.</span></span> <span data-ttu-id="20c8d-107">Por tanto, es probable que haya mensajes de instancia válidos para los que la asignación no se produzca correctamente.</span><span class="sxs-lookup"><span data-stu-id="20c8d-107">Therefore, there may be valid instance messages for which mapping will fail.</span></span>  
  
 <span data-ttu-id="20c8d-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="20c8d-108">**User Action**</span></span>  
  
 <span data-ttu-id="20c8d-109">Confirme las características opcionales y necesarias de los nodos especificados de origen y de destino respectivamente, e intente que estas características coincidan.</span><span class="sxs-lookup"><span data-stu-id="20c8d-109">Confirm the optional and required characteristics of the specified source and destination nodes, respectively, and consider making these characteristics match.</span></span>