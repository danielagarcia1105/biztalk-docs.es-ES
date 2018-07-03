---
title: El segmento contiene errores de elementos de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469622e2-6500-4f55-ab53-f8d89ee0a978
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30b000f670e4329c68540b51f291097f5bbd4dc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998893"
---
# <a name="segment-has-data-element-errors"></a><span data-ttu-id="5ff5b-102">El segmento contiene errores de elementos de datos</span><span class="sxs-lookup"><span data-stu-id="5ff5b-102">Segment has data element errors</span></span>
## <a name="details"></a><span data-ttu-id="5ff5b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5ff5b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5ff5b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5ff5b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5ff5b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5ff5b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5ff5b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5ff5b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5ff5b-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5ff5b-107">Event Source</span></span>   | <span data-ttu-id="5ff5b-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff5b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="5ff5b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5ff5b-109">Component</span></span>    |                                       <span data-ttu-id="5ff5b-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="5ff5b-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5ff5b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5ff5b-111">Symbolic Name</span></span>  |                       <span data-ttu-id="5ff5b-112">X12SegmentHasDataElementErrorsDescription</span><span class="sxs-lookup"><span data-stu-id="5ff5b-112">X12SegmentHasDataElementErrorsDescription</span></span>                        |
|  <span data-ttu-id="5ff5b-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5ff5b-113">Message Text</span></span>   |                            <span data-ttu-id="5ff5b-114">El segmento contiene errores de elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="5ff5b-114">Segment Has Data Element Errors</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="5ff5b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="5ff5b-115">Explanation</span></span>  
 <span data-ttu-id="5ff5b-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio contenía segmentos que incluían elementos de datos que no se ajustaban al esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="5ff5b-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained segments that included data elements that did not conform to the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5ff5b-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5ff5b-117">User Action</span></span>  
 <span data-ttu-id="5ff5b-118">Para resolver este error, asegúrese de que los elementos de datos del intercambio se ajustan al esquema del documento y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="5ff5b-118">To resolve this error, make sure that the data elements in the interchange conform to the document schema, and then resend the interchange.</span></span>