---
title: Estructura de mensaje EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c9a0447-447f-483c-825d-547c06ad691e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9395ed5e0b03bda48e19d6413f95ca2e74a3f1e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-structure"></a><span data-ttu-id="7b9dd-102">Estructura de los mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="7b9dd-102">EDI Message Structure</span></span>
<span data-ttu-id="7b9dd-103">Los mensajes EDI constan de un sobre y series jerárquicas de elementos estructurales.</span><span class="sxs-lookup"><span data-stu-id="7b9dd-103">EDI messages consist of an envelope and a hierarchical series of structural elements.</span></span> <span data-ttu-id="7b9dd-104">El sobre contiene un conjunto de encabezados y finalizadores, cada conjunto de éstos describe y contiene un elemento estructural.</span><span class="sxs-lookup"><span data-stu-id="7b9dd-104">The envelope contains a set of headers and trailers, each set of which describes and contains a structural element.</span></span> <span data-ttu-id="7b9dd-105">Estos elementos estructurales son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b9dd-105">These structural elements are as follows:</span></span>  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 <span data-ttu-id="7b9dd-106">La estructura jerárquica de un mensaje EDI habilita los conjuntos de transacciones/mensajes y grupos que se van a procesar por lotes.</span><span class="sxs-lookup"><span data-stu-id="7b9dd-106">The hierarchical structure of an EDI message enables transaction sets/messages and groups to be batched.</span></span> <span data-ttu-id="7b9dd-107">Incluso si un intercambio contiene sólo un conjunto de transacciones/mensaje y sólo un grupo, ese intercambio se estructura con los mismos elementos estructurales básicos que tendría si se procesara por lotes, con la excepción de que no sería un conjunto de varias transacciones/mensajes o elementos de grupo.</span><span class="sxs-lookup"><span data-stu-id="7b9dd-107">Even if an interchange contains only one transaction set/message and only one group, that interchange is structured with the same basic structural elements that it would have if it were batched, with the exception that there would not be multiple transaction set/message or group elements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b9dd-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7b9dd-108">In This Section</span></span>  
  
-   [<span data-ttu-id="7b9dd-109">Encabezados y finalizadores EDI</span><span class="sxs-lookup"><span data-stu-id="7b9dd-109">EDI Headers and Trailers</span></span>](../core/edi-headers-and-trailers.md)  
  
-   [<span data-ttu-id="7b9dd-110">Elemento estructural de intercambio EDI</span><span class="sxs-lookup"><span data-stu-id="7b9dd-110">EDI Interchange Structural Element</span></span>](../core/edi-interchange-structural-element.md)  
  
-   [<span data-ttu-id="7b9dd-111">Elemento estructural de grupo EDI</span><span class="sxs-lookup"><span data-stu-id="7b9dd-111">EDI Group Structural Element</span></span>](../core/edi-group-structural-element.md)  
  
-   [<span data-ttu-id="7b9dd-112">Elemento estructural de mensajes de conjunto de transacciones de EDI</span><span class="sxs-lookup"><span data-stu-id="7b9dd-112">EDI Transaction Set-Message Structural Element</span></span>](../core/edi-transaction-set-message-structural-element.md)  
  
-   [<span data-ttu-id="7b9dd-113">Elemento estructural de segmento EDI</span><span class="sxs-lookup"><span data-stu-id="7b9dd-113">EDI Segment Structural Element</span></span>](../core/edi-segment-structural-element.md)  
  
-   [<span data-ttu-id="7b9dd-114">Elemento estructural de elemento de datos EDI</span><span class="sxs-lookup"><span data-stu-id="7b9dd-114">EDI Data Element Structural Element</span></span>](../core/edi-data-element-structural-element.md)