---
title: El segmento excede la descripción de uso máximo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1704a-5d49-4549-af50-d1a89a1e70f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62a52f7589dc42d3af6b07db6fcbeb926a3d5dbc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985325"
---
# <a name="segment-exceeds-maximum-use-description"></a><span data-ttu-id="d5c05-102">El segmento excede la descripción de uso máximo.</span><span class="sxs-lookup"><span data-stu-id="d5c05-102">Segment Exceeds Maximum Use Description</span></span>
## <a name="details"></a><span data-ttu-id="d5c05-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d5c05-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d5c05-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d5c05-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d5c05-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d5c05-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d5c05-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d5c05-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d5c05-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d5c05-107">Event Source</span></span>   | <span data-ttu-id="d5c05-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c05-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="d5c05-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d5c05-109">Component</span></span>    |                                       <span data-ttu-id="d5c05-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="d5c05-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d5c05-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d5c05-111">Symbolic Name</span></span>  |                         <span data-ttu-id="d5c05-112">X12SegmentExceedsMaximumUseDescription</span><span class="sxs-lookup"><span data-stu-id="d5c05-112">X12SegmentExceedsMaximumUseDescription</span></span>                         |
|  <span data-ttu-id="d5c05-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d5c05-113">Message Text</span></span>   |                        <span data-ttu-id="d5c05-114">El segmento excede la descripción de uso máximo.</span><span class="sxs-lookup"><span data-stu-id="d5c05-114">Segment Exceeds Maximum Use Description</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="d5c05-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d5c05-115">Explanation</span></span>  
 <span data-ttu-id="d5c05-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía más instancias de un segmento de lo que permitía el esquema.</span><span class="sxs-lookup"><span data-stu-id="d5c05-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained more instances of a segment than allowed by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5c05-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d5c05-117">User Action</span></span>  
 <span data-ttu-id="d5c05-118">Para resolver este error, asegúrese de que el intercambio no contiene más del número máximo permitido de segmentos y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="d5c05-118">To resolve this error, make sure that the interchange does not have more than the maximum allowed number of segments, and then resend the interchange.</span></span>