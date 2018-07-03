---
title: Functoids de fecha y hora | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e2d49f5-1aaf-4e4d-8da1-e8605304dccb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5224c409a6d705806cccc493009ce2c32062f0a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010669"
---
# <a name="date-and-time-functoids"></a><span data-ttu-id="fc2c7-102">Functoids de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="fc2c7-102">Date and Time Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="fc2c7-103">Información general</span><span class="sxs-lookup"><span data-stu-id="fc2c7-103">Overview</span></span>
<span data-ttu-id="fc2c7-104">**Fecha / hora** functoids pueden dividirse en dos categorías.</span><span class="sxs-lookup"><span data-stu-id="fc2c7-104">**Date / Time** functoids can be divided into two categories.</span></span> <span data-ttu-id="fc2c7-105">La primera categoría contiene un único functoid, **agregar días**, que se usa para agregar un número de días especificado a un valor de hora y fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="fc2c7-105">The first category contains a single functoid, **Add Days**, which is used to add a specified number of days to a specified date and time value.</span></span> <span data-ttu-id="fc2c7-106">Esto puede ser útil cuando se supone que un campo del mensaje de instancia de salida incluye una estimación de fecha y hora en el futuro.</span><span class="sxs-lookup"><span data-stu-id="fc2c7-106">This can be useful when a field in the output instance message is supposed to include a date and time estimate in the future.</span></span> <span data-ttu-id="fc2c7-107">Por ejemplo, el **agregar días** functoid puede utilizarse para generar un estimado fecha de envío en función de una diferencia fija de la fecha en que se recibió un pedido.</span><span class="sxs-lookup"><span data-stu-id="fc2c7-107">For example, the **Add Days** functoid can be used to generate an estimated shipping date based a fixed delta from the date that an order was received.</span></span>  

 <span data-ttu-id="fc2c7-108">La segunda categoría incluye todos los functoids restantes en el **fecha y hora** categoría.</span><span class="sxs-lookup"><span data-stu-id="fc2c7-108">The second category includes all of the remaining functoids in the **Date and Time** category.</span></span> <span data-ttu-id="fc2c7-109">Se usan para proporcionar una marca de hora en tiempo de ejecución, de modo que la fecha y la hora en las que se lleva a cabo la transformación del mensaje pueden incluirse en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="fc2c7-109">They are used to provide a timestamp at run time, so that the date and time at which message transformation is being performed can be included in the output instance message.</span></span>  

 <span data-ttu-id="fc2c7-110">El **agregar días** functoid acepta dos parámetros de entrada, mientras que el **fecha**, **fecha y hora**, y **tiempo** los functoids no tienen ninguna entrada parámetros.</span><span class="sxs-lookup"><span data-stu-id="fc2c7-110">The **Add Days** functoid accepts two input parameters, whereas the **Date**, **Date and Time**, and **Time** functoids have no input parameters.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="fc2c7-111">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="fc2c7-111">Available functoids</span></span>  
 <span data-ttu-id="fc2c7-112">El **fecha / hora** functoids son:</span><span class="sxs-lookup"><span data-stu-id="fc2c7-112">The **Date / Time** functoids are:</span></span> 

* <span data-ttu-id="fc2c7-113">Agregar días</span><span class="sxs-lookup"><span data-stu-id="fc2c7-113">Add Days</span></span>
* <span data-ttu-id="fc2c7-114">date</span><span class="sxs-lookup"><span data-stu-id="fc2c7-114">Date</span></span>
* <span data-ttu-id="fc2c7-115">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="fc2c7-115">Date and Time</span></span>
* <span data-ttu-id="fc2c7-116">Time</span><span class="sxs-lookup"><span data-stu-id="fc2c7-116">Time</span></span>

<span data-ttu-id="fc2c7-117">Encontrará más detalles sobre estos functoids **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="fc2c7-117">More details on these functoids are available **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="fc2c7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc2c7-118">See Also</span></span>  
- [<span data-ttu-id="fc2c7-119">Cómo agregar Functoids básicos a una asignación</span><span class="sxs-lookup"><span data-stu-id="fc2c7-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="fc2c7-120">**Referencia de Functoids de fecha y hora** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="fc2c7-120">**Date and Time Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
