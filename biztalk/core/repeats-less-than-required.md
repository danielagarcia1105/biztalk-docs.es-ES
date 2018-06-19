---
title: Se repite menor que el necesario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5bebc13-0e70-4f73-99c0-fed917d79fba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d88fe1868a91bce7208c0da557f20211cde23109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268532"
---
# <a name="repeats-less-than-required"></a><span data-ttu-id="c767c-102">Menos repeticiones de las necesarias.</span><span class="sxs-lookup"><span data-stu-id="c767c-102">Repeats less than required</span></span>
## <a name="details"></a><span data-ttu-id="c767c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c767c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c767c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c767c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c767c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c767c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c767c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c767c-106">Event ID</span></span>|-|  
|<span data-ttu-id="c767c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c767c-107">Event Source</span></span>|<span data-ttu-id="c767c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c767c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c767c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c767c-109">Component</span></span>|<span data-ttu-id="c767c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c767c-110">EDI Engine</span></span>|  
|<span data-ttu-id="c767c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c767c-111">Symbolic Name</span></span>|<span data-ttu-id="c767c-112">X12FeRepeatsLessThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="c767c-112">X12FeRepeatsLessThanRequiredDescription</span></span>|  
|<span data-ttu-id="c767c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c767c-113">Message Text</span></span>|<span data-ttu-id="c767c-114">Menos repeticiones de las necesarias.</span><span class="sxs-lookup"><span data-stu-id="c767c-114">Repeats less than required</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c767c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c767c-115">Explanation</span></span>  
 <span data-ttu-id="c767c-116">Este evento de error,  indica que los segmentos de un intercambio X12 entrante que se encuentran dentro o fuera de un bucle se repiten menos veces que las que requiere el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="c767c-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated fewer times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c767c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c767c-117">User Action</span></span>  
 <span data-ttu-id="c767c-118">Para resolver este error, asegúrese de que los segmentos que se encuentran dentro o fuera de un bucle del intercambio se repiten el número de veces especificado en el esquema y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="c767c-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>