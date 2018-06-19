---
title: El intercambio contenía un error estructural. Una causa probable es el terminador de segmento no es válido porque falta un retorno de carro y- o separadores de avance de línea | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035e37d5-d4a8-49d0-8d75-3bcf2426cac7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e983e44b1284bf16e06dbfc90159afc0ed5608c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241748"
---
# <a name="the-interchange-had-structural-error-a-likely-cause-is-invalid-segment-terminator-due-to-missing-carriage-line-and-or-line-feed-seperators"></a><span data-ttu-id="9303e-103">El intercambio contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="9303e-103">The interchange had structural error.</span></span> <span data-ttu-id="9303e-104">Una causa probable es el terminador de segmento no es válido porque falta un retorno de carro y- o separadores de avance de línea</span><span class="sxs-lookup"><span data-stu-id="9303e-104">A likely cause is invalid segment terminator due to missing Carriage Line and-or Line Feed seperators</span></span>
## <a name="details"></a><span data-ttu-id="9303e-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="9303e-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9303e-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9303e-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9303e-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9303e-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9303e-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9303e-108">Event ID</span></span>|-|  
|<span data-ttu-id="9303e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9303e-109">Event Source</span></span>|<span data-ttu-id="9303e-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9303e-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="9303e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9303e-111">Component</span></span>|<span data-ttu-id="9303e-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="9303e-112">EDI Engine</span></span>|  
|<span data-ttu-id="9303e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9303e-113">Symbolic Name</span></span>|<span data-ttu-id="9303e-114">EfactInterchangeStructuralErrorAfterUnb</span><span class="sxs-lookup"><span data-stu-id="9303e-114">EfactInterchangeStructuralErrorAfterUnb</span></span>|  
|<span data-ttu-id="9303e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9303e-115">Message Text</span></span>|<span data-ttu-id="9303e-116">El intercambio con el identificador '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural.</span><span class="sxs-lookup"><span data-stu-id="9303e-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="9303e-117">La causa probable podría ser un finalizador de segmento no válido debido a la ausencia de separadores de retorno de carro o avance de línea.</span><span class="sxs-lookup"><span data-stu-id="9303e-117">A likely cause is invalid segment terminator due to missing Carriage Line and/or Line Feed seperators.</span></span> <span data-ttu-id="9303e-118">La parte situada después del error se está suspendiendo. Consulte Cola de suspensión para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="9303e-118">The part after the error is being suspended, refer to Suspended Queue for details</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9303e-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="9303e-119">Explanation</span></span>  
 <span data-ttu-id="9303e-120">Este evento de error,  indica que la canalización de recepción, la canalización de envío o la orquestación por lotes no pudo procesar el intercambio EDIFACT porque un segmento del intercambio no tenía el terminador de segmento requerido.</span><span class="sxs-lookup"><span data-stu-id="9303e-120">This Error/Warning/Information event indicates that the receive pipeline, send pipeline, or batching orchestration could not process the EDIFACT interchange, because a segment in the interchange did not have the required segment terminator.</span></span> <span data-ttu-id="9303e-121">Para un intercambio entrante, los separadores se identifican en el segmento UNA o, si no está presente el segmento UNA, en la propiedad de canalización EfactDelimiters.</span><span class="sxs-lookup"><span data-stu-id="9303e-121">For an incoming interchange, the separators are identified in the UNA Segment, or if the UNA segment is not present, the EfactDelimiters pipeline property.</span></span> <span data-ttu-id="9303e-122">Para un intercambio saliente, los separadores se identifican en la página Definición de segmento UNA del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="9303e-122">For an outgoing interchange, the separators are identified in the UNA Segment Definition page of the EDI Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9303e-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9303e-123">User Action</span></span>  
 <span data-ttu-id="9303e-124">Para solucionar este error, asegúrese de que todos los segmentos del intercambio tengan el terminador de segmento requerido y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="9303e-124">To resolve this error, ensure that all segments in the interchange have the required segment terminator, and then have the interchange resent.</span></span>