---
title: Advanced Functoids | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bf2547-5e44-45f8-b577-97e5760a0339
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5002b639df79ece1019c2d013c128f615517ae5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230396"
---
# <a name="advanced-functoids"></a><span data-ttu-id="047c3-102">Functoids avanzados</span><span class="sxs-lookup"><span data-stu-id="047c3-102">Advanced Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="047c3-103">Información general</span><span class="sxs-lookup"><span data-stu-id="047c3-103">Overview</span></span>
<span data-ttu-id="047c3-104">Los functoids avanzados se dividen en cinco grupos según su uso:</span><span class="sxs-lookup"><span data-stu-id="047c3-104">Advanced functoids fall into five groups, according to their use:</span></span>  
  
-   <span data-ttu-id="047c3-105">**Administrar registros de bucle.**</span><span class="sxs-lookup"><span data-stu-id="047c3-105">**Managing looping records.**</span></span> <span data-ttu-id="047c3-106">El **índice**, **iteración**, **bucle**, **valor nulo**, **número de registros**, **tabla Extractor de tablas**, y **bucle de tabla** los functoids se utilizan en diversas combinaciones cuando el mensaje de instancia de entrada contiene secciones con un impredecible número de elementos, que se repiten como se representa mediante un bucle registros del esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="047c3-106">The **Index**, **Iteration**, **Looping**, **Nil Value**, **Record Count**, **Table Extractor**, and **Table Looping** functoids are used in various combinations when the input instance message contains sections with an unpredictable number of repeating elements, as represented by looping records in the source schema.</span></span>  
  
-   <span data-ttu-id="047c3-107">**Asignación condicional.**</span><span class="sxs-lookup"><span data-stu-id="047c3-107">**Conditional mapping.**</span></span> <span data-ttu-id="047c3-108">El **asignación de valores** y **asignación de valores (sin formato)** functoids se utilizan para proporcionar asignación condicional de un mensaje de instancia de entrada a un mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="047c3-108">The **Value Mapping** and **Value Mapping (Flattening)** functoids are used to provide conditional mapping from an input instance message to an output instance message.</span></span> <span data-ttu-id="047c3-109">Cuando el primer parámetro de entrada tiene el valor True, el segundo parámetro de entrada se coloca en el elemento o atributo especificado del mensaje de instancia de salida; en caso contrario, no se crea ese elemento o atributo en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="047c3-109">When their first input parameter is true, the second input parameter is put into the specified element or attribute in the output instance message; otherwise, that element or attribute is not created in the output instance message.</span></span>  
  
-   <span data-ttu-id="047c3-110">**Secuencias de comandos arbitrarias.**</span><span class="sxs-lookup"><span data-stu-id="047c3-110">**Arbitrary scripting.**</span></span> <span data-ttu-id="047c3-111">El **secuencias de comandos** functoid se utiliza para ejecutar secuencias de comandos arbitrarias o código compilado cuando se asigna un mensaje de instancia de entrada a un mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="047c3-111">The **Scripting** functoid is used to run arbitrary script or compiled code when an input instance message is being mapped to an output instance message.</span></span> <span data-ttu-id="047c3-112">La secuencia de comandos o el código compilado pueden crearse de forma que acepten parámetros de entrada del mensaje de instancia de origen, de valores constantes configurados, de la salida de otro functoid o de alguna combinación de los anteriores.</span><span class="sxs-lookup"><span data-stu-id="047c3-112">Such script or compiled code can be created so that it accepts input parameters from the source instance message, from configured constant values, from the output of another functoid, or some combination thereof.</span></span>  
  
-   <span data-ttu-id="047c3-113">**Asignación simple.**</span><span class="sxs-lookup"><span data-stu-id="047c3-113">**Simple mapping.**</span></span> <span data-ttu-id="047c3-114">El **copia masiva** functoid puede utilizarse para copiar un elemento entero, incluidos sus subelementos hasta una profundidad arbitraria, de un mensaje de instancia de entrada a un mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="047c3-114">The **Mass Copy** functoid can be used to copy an entire element, including its subelements to an arbitrary depth, from an input instance message to an output instance message.</span></span>  
  
-   <span data-ttu-id="047c3-115">**Solución de problemas de**.</span><span class="sxs-lookup"><span data-stu-id="047c3-115">**Troubleshooting**.</span></span> <span data-ttu-id="047c3-116">El **Assert** functoid puede utilizarse para probar sus suposiciones acerca de los valores de elemento.</span><span class="sxs-lookup"><span data-stu-id="047c3-116">The **Assert** functoid can be used to test your assumptions about element values.</span></span>  
  
## <a name="available-functoids"></a><span data-ttu-id="047c3-117">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="047c3-117">Available functoids</span></span>
  
 <span data-ttu-id="047c3-118">El **avanzadas** functoids son:</span><span class="sxs-lookup"><span data-stu-id="047c3-118">The **Advanced** functoids are:</span></span> 

* <span data-ttu-id="047c3-119">Functoid de aserción</span><span class="sxs-lookup"><span data-stu-id="047c3-119">Assert Functoid</span></span>
* <span data-ttu-id="047c3-120">Índice (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-120">Index Functoid</span></span> 
* <span data-ttu-id="047c3-121">Iteración (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-121">Iteration Functoid</span></span> 
* <span data-ttu-id="047c3-122">Bucle (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-122">Looping Functoid</span></span> 
* <span data-ttu-id="047c3-123">Copia masiva (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-123">Mass Copy Functoid</span></span> 
* <span data-ttu-id="047c3-124">Valor nulo (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-124">Nil Value Functoid</span></span>
* <span data-ttu-id="047c3-125">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="047c3-125">Record Count Functoid</span></span> 
* <span data-ttu-id="047c3-126">Secuencias de comandos (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-126">Scripting Functoid</span></span> 
* <span data-ttu-id="047c3-127">Bucle de tabla y Functoids de Extractor de tabla</span><span class="sxs-lookup"><span data-stu-id="047c3-127">Table Looping and Table Extractor Functoids</span></span>
* <span data-ttu-id="047c3-128">Asignación de valores (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-128">Value Mapping Functoid</span></span>
* <span data-ttu-id="047c3-129">Asignación de valores (sin formato) (functoid)</span><span class="sxs-lookup"><span data-stu-id="047c3-129">Value Mapping (Flattening) Functoid</span></span>

<span data-ttu-id="047c3-130">Obtener más detalles sobre estos functoids están en el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="047c3-130">More details on these functoids are in the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="047c3-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="047c3-131">Next steps</span></span>
  
-   [<span data-ttu-id="047c3-132">Functoid de aserción</span><span class="sxs-lookup"><span data-stu-id="047c3-132">Assert Functoid</span></span>](../core/assert-functoid.md)  
  
-   [<span data-ttu-id="047c3-133">Functoid de índice</span><span class="sxs-lookup"><span data-stu-id="047c3-133">Index Functoid</span></span>](../core/index-functoid.md)  
  
-   [<span data-ttu-id="047c3-134">Functoid de iteración</span><span class="sxs-lookup"><span data-stu-id="047c3-134">Iteration Functoid</span></span>](../core/iteration-functoid.md)  
  
-   [<span data-ttu-id="047c3-135">Functoid de bucle</span><span class="sxs-lookup"><span data-stu-id="047c3-135">Looping Functoid</span></span>](../core/looping-functoid.md)  
  
-   [<span data-ttu-id="047c3-136">Functoid de copia masiva</span><span class="sxs-lookup"><span data-stu-id="047c3-136">Mass Copy Functoid</span></span>](../core/mass-copy-functoid.md)  
  
-   [<span data-ttu-id="047c3-137">Functoid de valor nulo</span><span class="sxs-lookup"><span data-stu-id="047c3-137">Nil Value Functoid</span></span>](../core/nil-value-functoid.md)  
  
-   [<span data-ttu-id="047c3-138">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="047c3-138">Record Count Functoid</span></span>](../core/record-count-functoid.md)  
  
-   [<span data-ttu-id="047c3-139">Bucle de tabla y Functoids de Extractor de tabla</span><span class="sxs-lookup"><span data-stu-id="047c3-139">Table Looping and Table Extractor Functoids</span></span>](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="047c3-140">El Functoid de asignación de valores</span><span class="sxs-lookup"><span data-stu-id="047c3-140">Value Mapping Functoid</span></span>](../core/value-mapping-functoid.md)  
  
-   [<span data-ttu-id="047c3-141">Valor de asignación de Functoid (sin formato)</span><span class="sxs-lookup"><span data-stu-id="047c3-141">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)  
  
-   [<span data-ttu-id="047c3-142">Secuencias de comandos de Functoid</span><span class="sxs-lookup"><span data-stu-id="047c3-142">Scripting Functoid</span></span>](../core/scripting-functoid.md)