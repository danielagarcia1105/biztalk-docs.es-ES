---
title: Terminador de segmento no válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 508dac21-4731-439d-bf4a-a50858f1ffa0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47d5a79af0616baed6d401b4df7b68f5f596ef07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257252"
---
# <a name="invalid-segment-terminator"></a><span data-ttu-id="e58fa-102">Terminador de segmento no válido.</span><span class="sxs-lookup"><span data-stu-id="e58fa-102">Invalid Segment Terminator</span></span>
## <a name="details"></a><span data-ttu-id="e58fa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e58fa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e58fa-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e58fa-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e58fa-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e58fa-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e58fa-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e58fa-106">Event ID</span></span>|-|  
|<span data-ttu-id="e58fa-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e58fa-107">Event Source</span></span>|<span data-ttu-id="e58fa-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e58fa-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="e58fa-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e58fa-109">Component</span></span>|<span data-ttu-id="e58fa-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e58fa-110">EDI Engine</span></span>|  
|<span data-ttu-id="e58fa-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e58fa-111">Symbolic Name</span></span>|<span data-ttu-id="e58fa-112">X12Ta1InvalidSegmentTerminatorDescription</span><span class="sxs-lookup"><span data-stu-id="e58fa-112">X12Ta1InvalidSegmentTerminatorDescription</span></span>|  
|<span data-ttu-id="e58fa-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e58fa-113">Message Text</span></span>|<span data-ttu-id="e58fa-114">Terminador de segmento no válido.</span><span class="sxs-lookup"><span data-stu-id="e58fa-114">Invalid Segment Terminator</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e58fa-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e58fa-115">Explanation</span></span>  
 <span data-ttu-id="e58fa-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del terminador de segmento del intercambio no estaba limitado a los caracteres del juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="e58fa-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="e58fa-117">En X12, el terminador de segmento se define como el último carácter del segmento ISA.</span><span class="sxs-lookup"><span data-stu-id="e58fa-117">In X12, the segment terminator is defined as the last character in the ISA segment.</span></span> <span data-ttu-id="e58fa-118">En EDIFACT, el terminador de segmento es el campo UNA6.</span><span class="sxs-lookup"><span data-stu-id="e58fa-118">In EDIFACT, the segment terminator is the UNA6 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e58fa-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e58fa-119">User Action</span></span>  
 <span data-ttu-id="e58fa-120">Para resolver este error, asegúrese de que el terminador de segmento (el último carácter del segmento ISA de un intercambio X12 o el campo UNA6 en un intercambio EDIFACT) está limitado a los caracteres del juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="e58fa-120">To resolve this error, make sure that the segment terminator (the last character of the ISA segment in an X12 interchange or the UNA6 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="e58fa-121">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e58fa-121">Have the interchange resent.</span></span>