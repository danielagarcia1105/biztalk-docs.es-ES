---
title: Functoids lógicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 873e2b0ea1189586f9cabfbcb43c6ef276f34e0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007597"
---
# <a name="logical-functoids"></a><span data-ttu-id="5267f-102">Functoids lógicos</span><span class="sxs-lookup"><span data-stu-id="5267f-102">Logical Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="5267f-103">Información general</span><span class="sxs-lookup"><span data-stu-id="5267f-103">Overview</span></span>
<span data-ttu-id="5267f-104">**Lógico** functoids se utilizan para realizar los siguientes tipos de operaciones:</span><span class="sxs-lookup"><span data-stu-id="5267f-104">**Logical** functoids are used to perform the following types of operations:</span></span>  

- <span data-ttu-id="5267f-105">Realizar pruebas lógicas específicas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5267f-105">Perform specific logical tests at run time.</span></span> <span data-ttu-id="5267f-106">El **o lógico**, **NOT lógico** y **lógico y** functoids puede usarse para determinar si se crea un registro en un mensaje de instancia de destino, como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5267f-106">The **Logical OR**, **Logical NOT** and **Logical AND** functoids can be used to determine whether a record is created in a destination instance message, such as the following:</span></span>  

   <span data-ttu-id="5267f-107">Si ShipTo **o** OrderedBy están presentes, cree el registro de dirección BillTo.</span><span class="sxs-lookup"><span data-stu-id="5267f-107">If ShipTo **OR** OrderedBy are present, create BillTo address record.</span></span>  

   <span data-ttu-id="5267f-108">También puede usar estos functoids junto con el **bucle** functoid para configurar el número de veces que un registro bucles.</span><span class="sxs-lookup"><span data-stu-id="5267f-108">You can also use these functoids in conjunction with the **Looping** functoid to configure how many times a record loops.</span></span>  

- <span data-ttu-id="5267f-109">Controlar si un registro específico se crea en un mensaje de instancia de destino en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5267f-109">Control whether a specific record is created in a destination instance message at run time.</span></span> <span data-ttu-id="5267f-110">Functoids como **IsNil**, **numérico lógico**, **menor**, y **mayor** puede utilizarse para controlar si se crea un registro.</span><span class="sxs-lookup"><span data-stu-id="5267f-110">Functoids such as **IsNil**, **Logical Numeric**, **Less Than**, and **Greater Than** can be used to control whether a record is created.</span></span>  

   <span data-ttu-id="5267f-111">Si el resultado de uno de estos functoids lógicos es **True**, se genera el registro correspondiente en el mensaje de instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="5267f-111">If the result of one of these logical functoids is **True**, the corresponding record in the destination instance message is generated.</span></span> <span data-ttu-id="5267f-112">Si el resultado es **False**, no se genera el registro correspondiente en el mensaje de instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="5267f-112">If the result is **False**, the corresponding record in the destination instance message is not generated.</span></span>  

  <span data-ttu-id="5267f-113">Los functoids **IsNil**, **fecha lógica**, **existencia lógica**, **NOT lógico**, **numérico lógico**, y **cadena lógica** solo aceptan un parámetro.</span><span class="sxs-lookup"><span data-stu-id="5267f-113">The functoids **IsNil**, **Logical Date**, **Logical Existence**, **Logical NOT**, **Logical Numeric**, and **Logical String** accept only one parameter.</span></span> <span data-ttu-id="5267f-114">Los functoids **igual**, **mayor**, **mayor o igual que**, **menor**, **menor o igual que**, y **distinto** acepta dos parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="5267f-114">The functoids **Equal**, **Greater Than**, **Greater Than or Equal To**, **Less Than**, **Less Than or Equal To**, and **Not Equal** accept two input parameters.</span></span> <span data-ttu-id="5267f-115">Mientras que, el **lógico y** y **o lógico** functoids aceptan parámetros de entrada entre 2 y 100.</span><span class="sxs-lookup"><span data-stu-id="5267f-115">Whereas, the **Logical AND** and **Logical OR** functoids accept input parameters between 2 and 100.</span></span>  

  <span data-ttu-id="5267f-116">La salida de un **lógicos** functoid también se puede aceptar como entrada para otro functoid en un mapa.</span><span class="sxs-lookup"><span data-stu-id="5267f-116">The output of a **Logical** functoid can also be accepted as input to other functoids in a map.</span></span> <span data-ttu-id="5267f-117">Si ambos un **lógicos** functoid un functoid de bucle están vinculados entre sí y, a continuación, vinculados a un registro en el esquema de destino, se usa el functoid de bucle solo cuando el **lógicos** salida del functoid es  **True**.</span><span class="sxs-lookup"><span data-stu-id="5267f-117">If both a **Logical** functoid and a looping functoid are linked together, and then linked to a record in the destination schema, the looping functoid is used only when the **Logical** functoid output is **True**.</span></span>  

  <span data-ttu-id="5267f-118">También puede usar **lógicos** functoids con los **Value Mapping** o **asignación de valores (sin formato)** functoids para controlar si un registro en el mensaje de instancia de destino se crea.</span><span class="sxs-lookup"><span data-stu-id="5267f-118">You can also use **Logical** functoids with the **Value Mapping** or **Value Mapping (Flattening)** functoids to control whether a record in the destination instance message is created.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="5267f-119">Si vincula dos registros o campos del esquema de origen a dos diferentes **lógicos** functoids y, a continuación, vincula cada uno de los **lógicos** functoids en el mismo registro en el esquema de destino, la primera  **Lógico** functoid se usa en el generado Extensible Stylesheet Language Transformations (XSLT).</span><span class="sxs-lookup"><span data-stu-id="5267f-119">If you link two records or fields in the source schema to two different **Logical** functoids, and then link each of the **Logical** functoids to the same record in the destination schema, only the first **Logical** functoid is used in the generated Extensible Stylesheet Language Transformations (XSLT).</span></span> <span data-ttu-id="5267f-120">El segundo vínculo, en la segunda **lógicos** functoid, se omite.</span><span class="sxs-lookup"><span data-stu-id="5267f-120">The second link, from the second **Logical** functoid, is ignored.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5267f-121">Cuando se comparan las dos cadenas, los functoids lógicos distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5267f-121">Logical functoids are case-sensitive when comparing two strings.</span></span> <span data-ttu-id="5267f-122">Por ejemplo, "Abc" y "abc" no son iguales.</span><span class="sxs-lookup"><span data-stu-id="5267f-122">For example, "Abc" and "abc" are not equal.</span></span> <span data-ttu-id="5267f-123">La excepción a esta regla es cuando **lógicos** functoids comparan cadenas que representan los valores booleanos **True** y **False**.</span><span class="sxs-lookup"><span data-stu-id="5267f-123">The exception to this rule is when **Logical** functoids compare strings that represent the Boolean values **True** and **False**.</span></span> <span data-ttu-id="5267f-124">Por ejemplo, "True" y "true" son iguales.</span><span class="sxs-lookup"><span data-stu-id="5267f-124">For example, "True" and "true" are equal.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="5267f-125">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="5267f-125">Available functoids</span></span>  
 <span data-ttu-id="5267f-126">El **lógicos** functoids son:</span><span class="sxs-lookup"><span data-stu-id="5267f-126">The **Logical** functoids are:</span></span> 

* <span data-ttu-id="5267f-127">Igual</span><span class="sxs-lookup"><span data-stu-id="5267f-127">Equal</span></span>
* <span data-ttu-id="5267f-128">Mayor que</span><span class="sxs-lookup"><span data-stu-id="5267f-128">Greater Than</span></span>
* <span data-ttu-id="5267f-129">Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="5267f-129">Greater Than or Equal To</span></span>
* <span data-ttu-id="5267f-130">IsNil</span><span class="sxs-lookup"><span data-stu-id="5267f-130">IsNil</span></span>
* <span data-ttu-id="5267f-131">Menor que</span><span class="sxs-lookup"><span data-stu-id="5267f-131">Less Than</span></span>
* <span data-ttu-id="5267f-132">Menor o igual a</span><span class="sxs-lookup"><span data-stu-id="5267f-132">Less Than or Equal To</span></span>
* <span data-ttu-id="5267f-133">Y lógico</span><span class="sxs-lookup"><span data-stu-id="5267f-133">Logical AND</span></span>
* <span data-ttu-id="5267f-134">Fecha lógica</span><span class="sxs-lookup"><span data-stu-id="5267f-134">Logical Date</span></span>
* <span data-ttu-id="5267f-135">Existencia lógica</span><span class="sxs-lookup"><span data-stu-id="5267f-135">Logical Existence</span></span>
* <span data-ttu-id="5267f-136">NOT lógico</span><span class="sxs-lookup"><span data-stu-id="5267f-136">Logical NOT</span></span>
* <span data-ttu-id="5267f-137">Valor numérico lógico</span><span class="sxs-lookup"><span data-stu-id="5267f-137">Logical Numeric</span></span>
* <span data-ttu-id="5267f-138">O lógico</span><span class="sxs-lookup"><span data-stu-id="5267f-138">Logical OR</span></span>
* <span data-ttu-id="5267f-139">Cadena lógica</span><span class="sxs-lookup"><span data-stu-id="5267f-139">Logical String</span></span>
* <span data-ttu-id="5267f-140">No igual</span><span class="sxs-lookup"><span data-stu-id="5267f-140">Not Equal</span></span>

<span data-ttu-id="5267f-141">Encontrará más detalles sobre estas funciones [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="5267f-141">More details on these functions are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="5267f-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5267f-142">See Also</span></span>  
- [<span data-ttu-id="5267f-143">Cómo agregar Functoids básicos a una asignación</span><span class="sxs-lookup"><span data-stu-id="5267f-143">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="5267f-144">**Referencia a Functoids lógicos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5267f-144">**Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
