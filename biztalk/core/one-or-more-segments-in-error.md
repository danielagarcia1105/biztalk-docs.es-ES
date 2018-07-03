---
title: Error en uno o más segmentos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c364af2691767ac55a52afb52b77f09d39ef6d2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005076"
---
# <a name="one-or-more-segments-in-error"></a><span data-ttu-id="5e024-102">Error en uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="5e024-102">One or more segments in error</span></span>
## <a name="details"></a><span data-ttu-id="5e024-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5e024-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5e024-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5e024-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5e024-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5e024-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5e024-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5e024-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5e024-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5e024-107">Event Source</span></span>   | <span data-ttu-id="5e024-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e024-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="5e024-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5e024-109">Component</span></span>    |                                       <span data-ttu-id="5e024-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="5e024-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5e024-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5e024-111">Symbolic Name</span></span>  |                        <span data-ttu-id="5e024-112">X12TsOneOrMoreSegmentsInErrorDescription</span><span class="sxs-lookup"><span data-stu-id="5e024-112">X12TsOneOrMoreSegmentsInErrorDescription</span></span>                        |
|  <span data-ttu-id="5e024-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5e024-113">Message Text</span></span>   |                             <span data-ttu-id="5e024-114">Error en uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="5e024-114">One or more segments in error</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="5e024-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="5e024-115">Explanation</span></span>  
 <span data-ttu-id="5e024-116">Este evento de error,  indica que uno o varios segmentos del intercambio no se ajustan al esquema que los controla.</span><span class="sxs-lookup"><span data-stu-id="5e024-116">This Error/Warning/Information event indicates that one or more segments in the interchange did not conform to the schema governing them.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e024-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5e024-117">User Action</span></span>  
 <span data-ttu-id="5e024-118">Para resolver este error, determine qué segmento tiene un error, abra el esquema que controla dicho segmento y determine a partir de dicho esquema por qué el segmento tiene un error.</span><span class="sxs-lookup"><span data-stu-id="5e024-118">To resolve this error, determine which segment is in error, open the schema governing that segment, and determine from that schema why the segment is in error.</span></span>