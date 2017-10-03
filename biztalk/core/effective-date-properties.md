---
title: Propiedades de fecha de vigencia | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f1c4cf3579a3381c846ddbb9896b2e5be26f6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="effective-date-properties"></a><span data-ttu-id="3e392-102">Propiedades de fecha efectiva</span><span class="sxs-lookup"><span data-stu-id="3e392-102">Effective Date Properties</span></span>
<span data-ttu-id="3e392-103">PeopleSoft Enterprise permite programar y realizar un seguimiento de los elementos planificados usando una propiedad especial denominada Fecha de vigencia (abreviada como EFFDT por sus siglas en inglés).</span><span class="sxs-lookup"><span data-stu-id="3e392-103">PeopleSoft Enterprise provides the ability to schedule and keep track of planned items by using a special property called Effective Date (abbreviated EFFDT).</span></span> <span data-ttu-id="3e392-104">Tales elementos están en vigor o meramente planificados, en función de si su fecha es anterior o posterior a la fecha actual de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="3e392-104">Such items are either in effect or merely planned, depending on whether their date is before or after the PeopleSoft current date.</span></span>  
  
 <span data-ttu-id="3e392-105">Si las propiedades de una interfaz de componente contienen tales elementos con fecha de vigencia (es decir, un campo con el nombre EFFDT), el adaptador permite que quienes realizan llamadas recuperen el conjunto de valores completo o únicamente los valores que aún no están en vigor (los que aún pueden modificarse).</span><span class="sxs-lookup"><span data-stu-id="3e392-105">If the properties of a component interface contain such effective-dated items (that is, a field with a name of EFFDT), the adapter makes it possible for callers to retrieve the complete set of values or only those values not yet effective—those that can still be changed.</span></span>  
  
## <a name="gethistoryitems-parameter"></a><span data-ttu-id="3e392-106">Parámetro getHistoryItems</span><span class="sxs-lookup"><span data-stu-id="3e392-106">getHistoryItems Parameter</span></span>  
 <span data-ttu-id="3e392-107">Para las interfaces de componentes con propiedades que incluyan una fecha de vigencia, el adaptador proporciona un parámetro adicional, denominado `getHistoryItems`, a las operaciones Get.</span><span class="sxs-lookup"><span data-stu-id="3e392-107">For component interfaces with properties that include an effective date, the adapter provides an additional parameter, called `getHistoryItems`, to the Get operations.</span></span> <span data-ttu-id="3e392-108">Este parámetro es del tipo booleano, y, si está configurado como True, se devolverán todos los elementos con fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="3e392-108">This parameter is of type Boolean, and if it is set to True, all effective-dated items are returned.</span></span> <span data-ttu-id="3e392-109">Entre ellos se incluyen todos los elementos pasados, actuales y futuros con fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="3e392-109">These include all past, current, and future effective-dated items.</span></span>  
  
 <span data-ttu-id="3e392-110">Si el parámetro `getHistoryItems` está configurado como False, solamente se devolverán los elementos actuales y futuros con fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="3e392-110">If the `getHistoryItems` parameter is set to False, only the current and future effective-dated items are returned.</span></span> <span data-ttu-id="3e392-111">Elija False si su intención es agregar o cambiar estos elementos (porque no se puedan cambiar los elementos antiguos).</span><span class="sxs-lookup"><span data-stu-id="3e392-111">Choose False if your intention is to add or change these items (because past items cannot be changed).</span></span>  
  
 <span data-ttu-id="3e392-112">También es posible tener varios elementos con fecha de vigencia que tengan la misma fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="3e392-112">It is also possible to have multiple effective-dated items having the same effective date.</span></span> <span data-ttu-id="3e392-113">En tal caso, deberá proporcionarse asimismo una propiedad adicional, Secuencia de vigencia (EFFSEQ, por sus siglas en inglés).</span><span class="sxs-lookup"><span data-stu-id="3e392-113">In this situation, an additional property, Effective Sequence (EFFSEQ), must also be provided.</span></span> <span data-ttu-id="3e392-114">Los valores de EFFSEQ deben ser únicos para diferenciar elementos que tengan la misma fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="3e392-114">The values of the EFFSEQ must be unique to differentiate items with the same effective date.</span></span> <span data-ttu-id="3e392-115">Consulte la documentación de PeopleSoft para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3e392-115">See the PeopleSoft documentation for more information.</span></span>  
  
## <a name="modifying-past-effective-dated-items"></a><span data-ttu-id="3e392-116">Modificación de los elementos cuya fecha de vigencia ya haya pasado</span><span class="sxs-lookup"><span data-stu-id="3e392-116">Modifying Past Effective-Dated Items</span></span>  
 <span data-ttu-id="3e392-117">El `correctionMode` argumento tanto en el [UpdateEx](../core/updateex-method.md) y [DeleteOnly](../core/deleteonly-method.md) métodos controlan si se pueden modificar los últimos elementos con fecha efectivos.</span><span class="sxs-lookup"><span data-stu-id="3e392-117">The `correctionMode` argument in both the [UpdateEx](../core/updateex-method.md) and [DeleteOnly](../core/deleteonly-method.md) methods control whether past effective dated items can be modified.</span></span> <span data-ttu-id="3e392-118">Si se establece en true, todos los elementos se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="3e392-118">If it is set to true, all items can be modified.</span></span> <span data-ttu-id="3e392-119">En caso contrario, la modificación de los elementos con fecha de vigencia que ya haya pasado genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="3e392-119">Otherwise, modifying past effective dated item generates an exception.</span></span>  
  
 <span data-ttu-id="3e392-120">Cuando se llama al obsoleto método `Update` en una interfaz de componente con elementos con fecha de vigencia, deberá tener cuidado de no incluir ninguna fecha de vigencia con valor anterior a la fecha de vigencia actual de PeopleSoft, para evitar que la llamada falle con una excepción.</span><span class="sxs-lookup"><span data-stu-id="3e392-120">When calling the deprecated `Update` method on a component interface that has effective-dated items, you must take care not to include any effective dates of a value earlier than the PeopleSoft current effective date, or the call fails with an exception.</span></span> <span data-ttu-id="3e392-121">Sin embargo, se puede incluir el elemento con fecha de vigencia actual, pues se omite al configurar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="3e392-121">However, the current effective-dated item can be included as it is bypassed when setting properties.</span></span> <span data-ttu-id="3e392-122">Si existe la Secuencia de vigencia, todos los elementos con fecha de vigencia actual cuyas Secuencias de vigencia coincidan en el servidor se omitirán al configurar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="3e392-122">If Effective Sequence exists, then all current effective-dated items with matching Effective Sequences in the server are skipped when setting properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e392-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e392-123">See Also</span></span>  
 [<span data-ttu-id="3e392-124">Apéndice A: métodos de interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="3e392-124">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)