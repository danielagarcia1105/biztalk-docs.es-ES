---
title: Menor que el mínimo permitido de número de veces que un bucle se repite | Documentos de Microsoft
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
ms.openlocfilehash: 00d9b38712d8b8336daa9357bd20eb34148691b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261988"
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="fa7be-102">El bucle se repite un número de veces inferior al mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="fa7be-102">Loop repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="fa7be-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa7be-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa7be-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fa7be-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fa7be-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fa7be-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="fa7be-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fa7be-106">Event ID</span></span>|-|  
|<span data-ttu-id="fa7be-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fa7be-107">Event Source</span></span>|<span data-ttu-id="fa7be-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa7be-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="fa7be-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fa7be-109">Component</span></span>|<span data-ttu-id="fa7be-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fa7be-110">EDI Engine</span></span>|  
|<span data-ttu-id="fa7be-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fa7be-111">Symbolic Name</span></span>|<span data-ttu-id="fa7be-112">X12SeLoopRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="fa7be-112">X12SeLoopRepeatsLessTimesDescription</span></span>|  
|<span data-ttu-id="fa7be-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa7be-113">Message Text</span></span>|<span data-ttu-id="fa7be-114">El bucle se repite un número de veces inferior al mínimo permitido.</span><span class="sxs-lookup"><span data-stu-id="fa7be-114">Loop repeats less than the minimum allowed number of times</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa7be-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="fa7be-115">Explanation</span></span>  
 <span data-ttu-id="fa7be-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un bucle que se repetía menos veces que el número mínimo que requiere el esquema del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa7be-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated fewer times than the minimum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa7be-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fa7be-117">User Action</span></span>  
 <span data-ttu-id="fa7be-118">Para resolver este error, asegúrese de que el bucle se repite en el intercambio al menos el número de veces que indica la propiedad MinOccurs especificada para el bucle en el esquema del mensaje y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa7be-118">To resolve this error, make sure that the loop repeats in the interchange at least the number of times in the minOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>