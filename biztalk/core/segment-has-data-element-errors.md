---
title: Segmento contiene errores de elementos de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 469622e2-6500-4f55-ab53-f8d89ee0a978
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c8c9e43bfe0a733a3e95b7812195a0b7f3990c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="segment-has-data-element-errors"></a><span data-ttu-id="3e449-102">El segmento contiene errores de elementos de datos</span><span class="sxs-lookup"><span data-stu-id="3e449-102">Segment has data element errors</span></span>
## <a name="details"></a><span data-ttu-id="3e449-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e449-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e449-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3e449-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3e449-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3e449-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3e449-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3e449-106">Event ID</span></span>|-|  
|<span data-ttu-id="3e449-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3e449-107">Event Source</span></span>|<span data-ttu-id="3e449-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e449-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="3e449-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3e449-109">Component</span></span>|<span data-ttu-id="3e449-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="3e449-110">EDI Engine</span></span>|  
|<span data-ttu-id="3e449-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3e449-111">Symbolic Name</span></span>|<span data-ttu-id="3e449-112">X12SegmentHasDataElementErrorsDescription</span><span class="sxs-lookup"><span data-stu-id="3e449-112">X12SegmentHasDataElementErrorsDescription</span></span>|  
|<span data-ttu-id="3e449-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3e449-113">Message Text</span></span>|<span data-ttu-id="3e449-114">El segmento contiene errores de elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="3e449-114">Segment Has Data Element Errors</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3e449-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="3e449-115">Explanation</span></span>  
 <span data-ttu-id="3e449-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio contenía segmentos que incluían elementos de datos que no se ajustaban al esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="3e449-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained segments that included data elements that did not conform to the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e449-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3e449-117">User Action</span></span>  
 <span data-ttu-id="3e449-118">Para resolver este error, asegúrese de que los elementos de datos del intercambio se ajustan al esquema del documento y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="3e449-118">To resolve this error, make sure that the data elements in the interchange conform to the document schema, and then resend the interchange.</span></span>