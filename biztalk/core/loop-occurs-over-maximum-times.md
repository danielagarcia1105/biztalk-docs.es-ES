---
title: Repetición de bucles superior al máximo permitido | Microsoft Docs
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
ms.openlocfilehash: 6587e5b5dcef641f37f24005fe594a084e5de12d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979605"
---
# <a name="loop-occurs-over-maximum-times"></a><span data-ttu-id="7e2ee-102">Repetición de bucles superior al máximo permitido</span><span class="sxs-lookup"><span data-stu-id="7e2ee-102">Loop Occurs Over Maximum Times</span></span>
## <a name="details"></a><span data-ttu-id="7e2ee-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e2ee-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7e2ee-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7e2ee-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7e2ee-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7e2ee-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7e2ee-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7e2ee-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7e2ee-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7e2ee-107">Event Source</span></span>   | <span data-ttu-id="7e2ee-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e2ee-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="7e2ee-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7e2ee-109">Component</span></span>    |                                       <span data-ttu-id="7e2ee-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7e2ee-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7e2ee-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7e2ee-111">Symbolic Name</span></span>  |                        <span data-ttu-id="7e2ee-112">X12LoopOccursOverMaximumTimesDescription</span><span class="sxs-lookup"><span data-stu-id="7e2ee-112">X12LoopOccursOverMaximumTimesDescription</span></span>                        |
|  <span data-ttu-id="7e2ee-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7e2ee-113">Message Text</span></span>   |                            <span data-ttu-id="7e2ee-114">Repetición de bucles superior al máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="7e2ee-114">Loops Occurs Over Maximum Times</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="7e2ee-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="7e2ee-115">Explanation</span></span>  
 <span data-ttu-id="7e2ee-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un bucle que se repetía más veces que el número máximo que requiere el esquema del mensaje.</span><span class="sxs-lookup"><span data-stu-id="7e2ee-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated more times than the maximum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e2ee-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7e2ee-117">User Action</span></span>  
 <span data-ttu-id="7e2ee-118">Para resolver este error, asegúrese de que el bucle no se repita en el intercambio más del número de veces que indica la propiedad MaxOccurs especificada para el bucle en el esquema del mensaje y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7e2ee-118">To resolve this error, make sure that the loop repeats in the interchange no more than the number of times in the maxOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>