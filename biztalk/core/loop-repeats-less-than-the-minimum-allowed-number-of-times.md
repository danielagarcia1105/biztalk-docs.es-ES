---
title: Menor que el mínimo permitido de número de veces que un bucle se repite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0be21d1d-86da-456b-83e6-c91f1dc9fb48
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5457110830a2e38e592ff58e7da672373a139d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012317"
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="81ad1-102">El bucle se repite un número de veces inferior al mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="81ad1-102">Loop repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="81ad1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="81ad1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="81ad1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="81ad1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="81ad1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="81ad1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="81ad1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="81ad1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="81ad1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="81ad1-107">Event Source</span></span>   | <span data-ttu-id="81ad1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ad1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="81ad1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="81ad1-109">Component</span></span>    |                                       <span data-ttu-id="81ad1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="81ad1-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="81ad1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="81ad1-111">Symbolic Name</span></span>  |                          <span data-ttu-id="81ad1-112">X12SeLoopRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="81ad1-112">X12SeLoopRepeatsLessTimesDescription</span></span>                          |
|  <span data-ttu-id="81ad1-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="81ad1-113">Message Text</span></span>   |               <span data-ttu-id="81ad1-114">El bucle se repite un número de veces inferior al mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="81ad1-114">Loop repeats less than the minimum allowed number of times</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="81ad1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="81ad1-115">Explanation</span></span>  
 <span data-ttu-id="81ad1-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un bucle que se repetía menos veces que el número mínimo que requiere el esquema del mensaje.</span><span class="sxs-lookup"><span data-stu-id="81ad1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated fewer times than the minimum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81ad1-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="81ad1-117">User Action</span></span>  
 <span data-ttu-id="81ad1-118">Para resolver este error, asegúrese de que el bucle se repite en el intercambio al menos el número de veces que indica la propiedad MinOccurs especificada para el bucle en el esquema del mensaje y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="81ad1-118">To resolve this error, make sure that the loop repeats in the interchange at least the number of times in the minOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>