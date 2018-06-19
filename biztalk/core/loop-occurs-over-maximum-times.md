---
title: Se produce un bucle superior al máximo permitido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 827ab88a2676cd052ee1ea3ba3a4bd7bd80f1912
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261884"
---
# <a name="loop-occurs-over-maximum-times"></a><span data-ttu-id="46153-102">Repetición de bucles superior al máximo permitido</span><span class="sxs-lookup"><span data-stu-id="46153-102">Loop Occurs Over Maximum Times</span></span>
## <a name="details"></a><span data-ttu-id="46153-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="46153-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46153-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="46153-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="46153-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="46153-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="46153-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="46153-106">Event ID</span></span>|-|  
|<span data-ttu-id="46153-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="46153-107">Event Source</span></span>|<span data-ttu-id="46153-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46153-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="46153-109">Componente</span><span class="sxs-lookup"><span data-stu-id="46153-109">Component</span></span>|<span data-ttu-id="46153-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="46153-110">EDI Engine</span></span>|  
|<span data-ttu-id="46153-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="46153-111">Symbolic Name</span></span>|<span data-ttu-id="46153-112">X12LoopOccursOverMaximumTimesDescription</span><span class="sxs-lookup"><span data-stu-id="46153-112">X12LoopOccursOverMaximumTimesDescription</span></span>|  
|<span data-ttu-id="46153-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="46153-113">Message Text</span></span>|<span data-ttu-id="46153-114">Repetición de bucles superior al máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="46153-114">Loops Occurs Over Maximum Times</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46153-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="46153-115">Explanation</span></span>  
 <span data-ttu-id="46153-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un bucle que se repetía más veces que el número máximo que requiere el esquema del mensaje.</span><span class="sxs-lookup"><span data-stu-id="46153-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated more times than the maximum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46153-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="46153-117">User Action</span></span>  
 <span data-ttu-id="46153-118">Para resolver este error, asegúrese de que el bucle no se repita en el intercambio más del número de veces que indica la propiedad MaxOccurs especificada para el bucle en el esquema del mensaje y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="46153-118">To resolve this error, make sure that the loop repeats in the interchange no more than the number of times in the maxOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>