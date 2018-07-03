---
title: Falta segmento obligatorio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e459a22-8de5-426a-a46a-1d0ab72b532d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2bc9775da2fcbef756774c576074b471e808484
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977093"
---
# <a name="mandatory-segment-missing"></a><span data-ttu-id="b888a-102">Falta segmento obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b888a-102">Mandatory Segment Missing</span></span>
## <a name="details"></a><span data-ttu-id="b888a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b888a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="b888a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b888a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="b888a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b888a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="b888a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b888a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="b888a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b888a-107">Event Source</span></span>   | <span data-ttu-id="b888a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b888a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="b888a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b888a-109">Component</span></span>    |                                       <span data-ttu-id="b888a-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="b888a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="b888a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b888a-111">Symbolic Name</span></span>  |                         <span data-ttu-id="b888a-112">X12MandatorySegmentMissingDescription</span><span class="sxs-lookup"><span data-stu-id="b888a-112">X12MandatorySegmentMissingDescription</span></span>                          |
|  <span data-ttu-id="b888a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b888a-113">Message Text</span></span>   |                               <span data-ttu-id="b888a-114">Falta segmento obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b888a-114">Mandatory Segment Missing</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="b888a-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="b888a-115">Explanation</span></span>  
 <span data-ttu-id="b888a-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante, pues el intercambio no contenía un segmento que requiere el esquema del mensaje (para el cual minOccurs es mayor que 0).</span><span class="sxs-lookup"><span data-stu-id="b888a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a segment that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b888a-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b888a-117">User Action</span></span>  
 <span data-ttu-id="b888a-118">Para resolver este error, asegúrese de que el intercambio contiene todos los segmentos que requiere el esquema del mensaje y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b888a-118">To resolve this error, make sure that the interchange contains all segments required by the message schema, and then have the message resent.</span></span>