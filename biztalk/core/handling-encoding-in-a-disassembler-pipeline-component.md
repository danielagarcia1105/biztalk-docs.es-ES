---
title: "Controlar la codificación en un componente de canalización de desensamblador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcbfb8f86847668436fae04db7bee1703dfb60ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a><span data-ttu-id="6d34a-102">Controlar la codificación en un componente de canalización de desensamblador</span><span class="sxs-lookup"><span data-stu-id="6d34a-102">Handling Encoding in a Disassembler Pipeline Component</span></span>
<span data-ttu-id="6d34a-103">Asegúrese de que su componente de desensamblador personalizado codifica los documentos de salida en uno de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d34a-103">Ensure that your custom disassembler component encodes outbound documents in one of the following formats:</span></span>  
  
-   <span data-ttu-id="6d34a-104">UTF-8</span><span class="sxs-lookup"><span data-stu-id="6d34a-104">UTF-8</span></span>  
  
-   <span data-ttu-id="6d34a-105">UTF-16</span><span class="sxs-lookup"><span data-stu-id="6d34a-105">UTF-16</span></span>  
  
-   <span data-ttu-id="6d34a-106">UTF-32</span><span class="sxs-lookup"><span data-stu-id="6d34a-106">UTF-32</span></span>  
  
-   <span data-ttu-id="6d34a-107">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="6d34a-107">UTF-16LE</span></span>  
  
-   <span data-ttu-id="6d34a-108">UTF-16BE</span><span class="sxs-lookup"><span data-stu-id="6d34a-108">UTF-16BE</span></span>  
  
 <span data-ttu-id="6d34a-109">Si se usan otros formatos de codificación, puede que el motor de orquestaciones no pueda procesar los documentos.</span><span class="sxs-lookup"><span data-stu-id="6d34a-109">The orchestration engine may not be able to process documents with other encoding formats.</span></span>  
  
 <span data-ttu-id="6d34a-110">UTF-32LE y UTF-32BE no son compatibles con .NET Framework; por ello, para usar estos formatos, debe crear una implementación de codificación personalizada.</span><span class="sxs-lookup"><span data-stu-id="6d34a-110">UTF-32LE and UTF-32BE are not supported by the .NET Framework; to use these formats, you must create a custom encoding implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d34a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d34a-111">See Also</span></span>  
 [<span data-ttu-id="6d34a-112">Desarrollar un componente de canalización de desensamblado</span><span class="sxs-lookup"><span data-stu-id="6d34a-112">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)