---
title: Se repite más de las necesarias | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac4649ea88756ba63393155ca8910437567fbd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024042"
---
# <a name="repeats-more-than-required"></a><span data-ttu-id="c018d-102">Más repeticiones de las necesarias.</span><span class="sxs-lookup"><span data-stu-id="c018d-102">Repeats more than required</span></span>
## <a name="details"></a><span data-ttu-id="c018d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c018d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c018d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c018d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c018d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c018d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c018d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c018d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c018d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c018d-107">Event Source</span></span>   | <span data-ttu-id="c018d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c018d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="c018d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c018d-109">Component</span></span>    |                                       <span data-ttu-id="c018d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c018d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c018d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c018d-111">Symbolic Name</span></span>  |                        <span data-ttu-id="c018d-112">X12FeRepeatsMoreThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="c018d-112">X12FeRepeatsMoreThanRequiredDescription</span></span>                         |
|  <span data-ttu-id="c018d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c018d-113">Message Text</span></span>   |                               <span data-ttu-id="c018d-114">Más repeticiones de las necesarias.</span><span class="sxs-lookup"><span data-stu-id="c018d-114">Repeats more than required</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="c018d-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c018d-115">Explanation</span></span>  
 <span data-ttu-id="c018d-116">Este evento de error, advertencia o información indica que los segmentos de un intercambio X12 entrante que se encuentran dentro o fuera de un bucle se repiten más veces que las que requiere el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="c018d-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated more times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c018d-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c018d-117">User Action</span></span>  
 <span data-ttu-id="c018d-118">Para resolver este error, asegúrese de que los segmentos que se encuentran dentro o fuera de un bucle del intercambio se repiten el número de veces especificado en el esquema y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="c018d-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>