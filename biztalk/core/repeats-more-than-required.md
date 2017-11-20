---
title: "Se repite más de necesario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cb8f9e324c9d09e09649719c98e3f684b0d81f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="repeats-more-than-required"></a><span data-ttu-id="c6247-102">Más repeticiones de las necesarias.</span><span class="sxs-lookup"><span data-stu-id="c6247-102">Repeats more than required</span></span>
## <a name="details"></a><span data-ttu-id="c6247-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c6247-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6247-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c6247-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c6247-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c6247-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c6247-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c6247-106">Event ID</span></span>|-|  
|<span data-ttu-id="c6247-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c6247-107">Event Source</span></span>|<span data-ttu-id="c6247-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6247-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c6247-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c6247-109">Component</span></span>|<span data-ttu-id="c6247-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c6247-110">EDI Engine</span></span>|  
|<span data-ttu-id="c6247-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c6247-111">Symbolic Name</span></span>|<span data-ttu-id="c6247-112">X12FeRepeatsMoreThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="c6247-112">X12FeRepeatsMoreThanRequiredDescription</span></span>|  
|<span data-ttu-id="c6247-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c6247-113">Message Text</span></span>|<span data-ttu-id="c6247-114">Más repeticiones de las necesarias.</span><span class="sxs-lookup"><span data-stu-id="c6247-114">Repeats more than required</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c6247-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c6247-115">Explanation</span></span>  
 <span data-ttu-id="c6247-116">Este evento de error, advertencia o información indica que los segmentos de un intercambio X12 entrante que se encuentran dentro o fuera de un bucle se repiten más veces que las que requiere el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="c6247-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated more times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6247-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c6247-117">User Action</span></span>  
 <span data-ttu-id="c6247-118">Para resolver este error, asegúrese de que los segmentos que se encuentran dentro o fuera de un bucle del intercambio se repiten el número de veces especificado en el esquema y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="c6247-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>