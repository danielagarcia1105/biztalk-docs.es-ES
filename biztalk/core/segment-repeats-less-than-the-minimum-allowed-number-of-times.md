---
title: "Segmento se repite menor que el mínimo permitido de veces | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8ca6c3d-f923-49bc-b5d9-65dc2d7adab1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee7aeb488fb2f8634fba73e7ddf3f44cd02a6529
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="segment-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="d2e33-102">El segmento se repite un número de veces inferior al mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="d2e33-102">Segment repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="d2e33-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d2e33-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2e33-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d2e33-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d2e33-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d2e33-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d2e33-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d2e33-106">Event ID</span></span>|-|  
|<span data-ttu-id="d2e33-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d2e33-107">Event Source</span></span>|<span data-ttu-id="d2e33-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2e33-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="d2e33-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d2e33-109">Component</span></span>|<span data-ttu-id="d2e33-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="d2e33-110">EDI Engine</span></span>|  
|<span data-ttu-id="d2e33-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d2e33-111">Symbolic Name</span></span>|<span data-ttu-id="d2e33-112">X12SeSegmentRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="d2e33-112">X12SeSegmentRepeatsLessTimesDescription</span></span>|  
|<span data-ttu-id="d2e33-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d2e33-113">Message Text</span></span>|<span data-ttu-id="d2e33-114">El segmento se repite un número de veces inferior al mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="d2e33-114">Segment repeats less than the minimum allowed number of times</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d2e33-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d2e33-115">Explanation</span></span>  
 <span data-ttu-id="d2e33-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante, pues un segmento del intercambio no se repite el número mínimo de veces que requiere el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="d2e33-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange does not repeat the minimum number of times required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2e33-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d2e33-117">User Action</span></span>  
 <span data-ttu-id="d2e33-118">Para resolver este error, pida al remitente del intercambio que repita el segmento de modo que se repita al menos el número mínimo de veces que requiere el esquema del documento y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="d2e33-118">To resolve this error, have the sender of the interchange as repetition of the segment so that it repeats at least the minimum number of times required by the document schema, and then resend the interchange.</span></span>