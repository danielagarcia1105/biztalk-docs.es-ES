---
title: "Error: los elementos secundarios del Functoid de secuencia de comandos XSLT generan código | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.xsltScriptingChildrenGenCode
ms.assetid: 9cdac362-177f-445e-904b-aa6a9b1eb46f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810fe9befecd9bbd1a15468ca714177900450cb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a><span data-ttu-id="1d97d-102">Error: los elementos secundarios del Functoid de secuencia de comandos XSLT generan código</span><span class="sxs-lookup"><span data-stu-id="1d97d-102">Error - Children of XSLT Scripting Functoid Generate Code</span></span>
<span data-ttu-id="1d97d-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="1d97d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="1d97d-104">btm1063</span><span class="sxs-lookup"><span data-stu-id="1d97d-104">btm1063</span></span>  
  
 <span data-ttu-id="1d97d-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="1d97d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="1d97d-106">Un escenario que contradice el uso de un **secuencias de comandos** functoid que está configurado para usar una plantilla de llamada XSLT o XSLT en línea se encontró en la asignación.</span><span class="sxs-lookup"><span data-stu-id="1d97d-106">A scenario that contradicts the use of a **Scripting** functoid that is configured to use inline XSLT or an XSLT Call Template was found in the map.</span></span> <span data-ttu-id="1d97d-107">En el esquema de destino, los nodos descendientes de un nodo que está vinculado a la salida de estos un **secuencias de comandos** functoid están intentado generar código XSLT propio.</span><span class="sxs-lookup"><span data-stu-id="1d97d-107">In the destination schema, descendent nodes of a node that is linked to the output of such a **Scripting** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="1d97d-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="1d97d-108">**User Action**</span></span>  
  
 <span data-ttu-id="1d97d-109">Elimine la incompatibilidad cambiando el uso de la correspondiente **secuencias de comandos** functoid o cambiando los nodos secundarios de modo que ya no generen código XSLT propio.</span><span class="sxs-lookup"><span data-stu-id="1d97d-109">Remove the incompatibility by changing the usage of the relevant **Scripting** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>