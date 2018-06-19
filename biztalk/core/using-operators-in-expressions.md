---
title: Usar operadores en expresiones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aec9ed6ebecb0b151dbfe9d5c09707b954fdf45
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974306"
---
# <a name="using-operators-in-expressions"></a><span data-ttu-id="67947-102">Usar operadores en expresiones</span><span class="sxs-lookup"><span data-stu-id="67947-102">Using Operators in Expressions</span></span>
<span data-ttu-id="67947-103">Los siguientes operadores XLAN/s están disponibles para su uso en expresiones de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="67947-103">The following XLANG/s operators are available for use in orchestration expressions.</span></span> <span data-ttu-id="67947-104">Cumplen estrictamente con las funciones de los operadores correspondientes en C#.</span><span class="sxs-lookup"><span data-stu-id="67947-104">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="67947-105">Operador</span><span class="sxs-lookup"><span data-stu-id="67947-105">Operator</span></span>|<span data-ttu-id="67947-106">Description</span><span class="sxs-lookup"><span data-stu-id="67947-106">Description</span></span>|<span data-ttu-id="67947-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67947-107">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="67947-108">checked()</span><span class="sxs-lookup"><span data-stu-id="67947-108">checked()</span></span>|<span data-ttu-id="67947-109">genera error al producirse un desbordamiento aritmético</span><span class="sxs-lookup"><span data-stu-id="67947-109">raise error on arithmetic overflow</span></span>|<span data-ttu-id="67947-110">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="67947-110">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="67947-111">unchecked()</span><span class="sxs-lookup"><span data-stu-id="67947-111">unchecked()</span></span>|<span data-ttu-id="67947-112">omite el desbordamiento aritmético.</span><span class="sxs-lookup"><span data-stu-id="67947-112">ignore arithmetic overflow</span></span>|<span data-ttu-id="67947-113">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="67947-113">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="67947-114">nuevo</span><span class="sxs-lookup"><span data-stu-id="67947-114">new</span></span>|<span data-ttu-id="67947-115">crea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="67947-115">create an instance of a class</span></span>|<span data-ttu-id="67947-116">myObject = new MyClass;</span><span class="sxs-lookup"><span data-stu-id="67947-116">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="67947-117">typeof</span><span class="sxs-lookup"><span data-stu-id="67947-117">typeof</span></span>|<span data-ttu-id="67947-118">recuperación de tipo</span><span class="sxs-lookup"><span data-stu-id="67947-118">Type retrieval</span></span>|<span data-ttu-id="67947-119">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="67947-119">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="67947-120">succeeded()</span><span class="sxs-lookup"><span data-stu-id="67947-120">succeeded()</span></span>|<span data-ttu-id="67947-121">prueba para la finalización correcta de ámbito transaccional u orquestación</span><span class="sxs-lookup"><span data-stu-id="67947-121">test for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="67947-122">se ha realizado correctamente (\<identificador de transacción de secundarios del ámbito actual o servicio\>)</span><span class="sxs-lookup"><span data-stu-id="67947-122">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="67947-123">exists</span><span class="sxs-lookup"><span data-stu-id="67947-123">exists</span></span>|<span data-ttu-id="67947-124">prueba para la existencia de una propiedad de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="67947-124">test for the existence of a message context property</span></span>|<span data-ttu-id="67947-125">BTS.RetryCount exists Message_In</span><span class="sxs-lookup"><span data-stu-id="67947-125">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="67947-126">más unario</span><span class="sxs-lookup"><span data-stu-id="67947-126">unary plus</span></span>|<span data-ttu-id="67947-127">+(int x)</span><span class="sxs-lookup"><span data-stu-id="67947-127">+(int x)</span></span>|  
|-|<span data-ttu-id="67947-128">menos unario</span><span class="sxs-lookup"><span data-stu-id="67947-128">unary minus</span></span>|<span data-ttu-id="67947-129">-(int x)</span><span class="sxs-lookup"><span data-stu-id="67947-129">-(int x)</span></span>|  
|<span data-ttu-id="67947-130">!</span><span class="sxs-lookup"><span data-stu-id="67947-130">!</span></span>|<span data-ttu-id="67947-131">negación lógica</span><span class="sxs-lookup"><span data-stu-id="67947-131">logical negation</span></span>|<span data-ttu-id="67947-132">!myBool</span><span class="sxs-lookup"><span data-stu-id="67947-132">!myBool</span></span>|  
|~|<span data-ttu-id="67947-133">complemento bit a bit</span><span class="sxs-lookup"><span data-stu-id="67947-133">bitwise complement</span></span>|<span data-ttu-id="67947-134">x = ~y</span><span class="sxs-lookup"><span data-stu-id="67947-134">x = ~y</span></span>|  
|<span data-ttu-id="67947-135">()</span><span class="sxs-lookup"><span data-stu-id="67947-135">()</span></span>|<span data-ttu-id="67947-136">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="67947-136">cast</span></span>|<span data-ttu-id="67947-137">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="67947-137">(bool) myInt</span></span>|  
|*|<span data-ttu-id="67947-138">times</span><span class="sxs-lookup"><span data-stu-id="67947-138">times</span></span>|<span data-ttu-id="67947-139">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="67947-139">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="67947-140">dividido por</span><span class="sxs-lookup"><span data-stu-id="67947-140">divided by</span></span>|<span data-ttu-id="67947-141">x / y</span><span class="sxs-lookup"><span data-stu-id="67947-141">x / y</span></span>|  
|+|<span data-ttu-id="67947-142">más</span><span class="sxs-lookup"><span data-stu-id="67947-142">plus</span></span>|<span data-ttu-id="67947-143">x + y</span><span class="sxs-lookup"><span data-stu-id="67947-143">x + y</span></span>|  
|-|<span data-ttu-id="67947-144">menos</span><span class="sxs-lookup"><span data-stu-id="67947-144">minus</span></span>|<span data-ttu-id="67947-145">x - y</span><span class="sxs-lookup"><span data-stu-id="67947-145">x - y</span></span>|  
|<<|<span data-ttu-id="67947-146">desplazar a la izquierda</span><span class="sxs-lookup"><span data-stu-id="67947-146">shift left</span></span>|<span data-ttu-id="67947-147">x << 2</span><span class="sxs-lookup"><span data-stu-id="67947-147">x << 2</span></span>|  
|>>|<span data-ttu-id="67947-148">desplazar a la derecha</span><span class="sxs-lookup"><span data-stu-id="67947-148">shift right</span></span>|<span data-ttu-id="67947-149">x >> 2</span><span class="sxs-lookup"><span data-stu-id="67947-149">x >> 2</span></span>|  
|<|<span data-ttu-id="67947-150">menor que</span><span class="sxs-lookup"><span data-stu-id="67947-150">less than</span></span>|<span data-ttu-id="67947-151">Si (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="67947-151">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="67947-152">mayor que</span><span class="sxs-lookup"><span data-stu-id="67947-152">greater than</span></span>|<span data-ttu-id="67947-153">Si (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="67947-153">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="67947-154">menor que o igual a</span><span class="sxs-lookup"><span data-stu-id="67947-154">less than or equal to</span></span>|<span data-ttu-id="67947-155">Si (MyMsg.numOrders < = 10)...</span><span class="sxs-lookup"><span data-stu-id="67947-155">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="67947-156">mayor que o igual a</span><span class="sxs-lookup"><span data-stu-id="67947-156">greater than or equal to</span></span>|<span data-ttu-id="67947-157">Si (MyMsg.numOrders > = 10)...</span><span class="sxs-lookup"><span data-stu-id="67947-157">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="67947-158">igual a</span><span class="sxs-lookup"><span data-stu-id="67947-158">equal to</span></span>|<span data-ttu-id="67947-159">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="67947-159">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="67947-160">!=</span><span class="sxs-lookup"><span data-stu-id="67947-160">!=</span></span>|<span data-ttu-id="67947-161">no es igual a</span><span class="sxs-lookup"><span data-stu-id="67947-161">not equal to</span></span>|<span data-ttu-id="67947-162">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="67947-162">If (MyMsg.numOrders != 10)...</span></span>|  
|&|<span data-ttu-id="67947-163">y</span><span class="sxs-lookup"><span data-stu-id="67947-163">and</span></span>|<span data-ttu-id="67947-164">Si (myByte & 255)...</span><span class="sxs-lookup"><span data-stu-id="67947-164">If (myByte & 255)...</span></span>|  
|^|<span data-ttu-id="67947-165">exclusivo o</span><span class="sxs-lookup"><span data-stu-id="67947-165">exclusive or</span></span>|<span data-ttu-id="67947-166">If (myByte ^ 1)...</span><span class="sxs-lookup"><span data-stu-id="67947-166">If (myByte ^ 1)...</span></span>|  
|<span data-ttu-id="67947-167">&#124;</span><span class="sxs-lookup"><span data-stu-id="67947-167">&#124;</span></span>|<span data-ttu-id="67947-168">o bien</span><span class="sxs-lookup"><span data-stu-id="67947-168">or</span></span>|<span data-ttu-id="67947-169">Si (myByte &#124; 1)...</span><span class="sxs-lookup"><span data-stu-id="67947-169">If (myByte &#124; 1)...</span></span>|  
|&&|<span data-ttu-id="67947-170">condicional y</span><span class="sxs-lookup"><span data-stu-id="67947-170">conditional and</span></span>|<span data-ttu-id="67947-171">Si (MyMsg.numOrders > 10) & & (MyMsg.numOrders < 100)</span><span class="sxs-lookup"><span data-stu-id="67947-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span></span>|  
|<span data-ttu-id="67947-172">&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="67947-172">&#124;&#124;</span></span>|<span data-ttu-id="67947-173">condicional o</span><span class="sxs-lookup"><span data-stu-id="67947-173">conditional or</span></span>|<span data-ttu-id="67947-174">Si (MyMsg.numOrders < 10) &#124; &#124; (MyMsg.numOrders > 100)</span><span class="sxs-lookup"><span data-stu-id="67947-174">If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)</span></span>|  
|//|<span data-ttu-id="67947-175">comentario</span><span class="sxs-lookup"><span data-stu-id="67947-175">commenting</span></span>|<span data-ttu-id="67947-176">//Éste es el comentario</span><span class="sxs-lookup"><span data-stu-id="67947-176">//This is the comment</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="67947-177">Las reglas difieren entre las expresiones generales y las expresiones de filtro que se usan con la **recepción** forma.</span><span class="sxs-lookup"><span data-stu-id="67947-177">The rules differ between general expressions and filter expressions that are used with the **Receive** shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67947-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="67947-178">See Also</span></span>  
 [<span data-ttu-id="67947-179">Uso de filtros con la forma Recibir mensaje</span><span class="sxs-lookup"><span data-stu-id="67947-179">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)