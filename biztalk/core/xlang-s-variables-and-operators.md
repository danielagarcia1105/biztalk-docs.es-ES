---
title: Operadores y Variables de XLANG-s | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f47ee6f69c1a69d0686bdb75b5dcaffc4a7c60a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023850"
---
# <a name="xlang-s-variables-and-operators"></a><span data-ttu-id="259c8-102">Operadores y Variables de XLANG / s</span><span class="sxs-lookup"><span data-stu-id="259c8-102">XLANG-s Variables and Operators</span></span>
<span data-ttu-id="259c8-103">En esta sección se tratan las variables y los operadores utilizados en el lenguaje XLANG/s.</span><span class="sxs-lookup"><span data-stu-id="259c8-103">This section discusses the variables and operators used in the XLANG/s language.</span></span>  
  
## <a name="xlangs-variables"></a><span data-ttu-id="259c8-104">Variables de XLANG/s</span><span class="sxs-lookup"><span data-stu-id="259c8-104">XLANG/s Variables</span></span>  
 <span data-ttu-id="259c8-105">Las variables representan ubicaciones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="259c8-105">Variables represent storage locations.</span></span> <span data-ttu-id="259c8-106">Cada variable tiene un tipo que determina qué valores se pueden almacenar en ella.</span><span class="sxs-lookup"><span data-stu-id="259c8-106">Every variable has a type that determines what values can be stored in that variable.</span></span> <span data-ttu-id="259c8-107">XLANG/s implementa la seguridad de tipos y su compilador garantiza que los valores almacenados en las variables siempre sean del tipo apropiado.</span><span class="sxs-lookup"><span data-stu-id="259c8-107">XLANG/s is type-safe, and its compiler guarantees that values stored in variables are always of the appropriate type.</span></span> <span data-ttu-id="259c8-108">XLANG/s admite lo siguientes tipos de variables:</span><span class="sxs-lookup"><span data-stu-id="259c8-108">XLANG/s supports the following variable types:</span></span>  
  
- <span data-ttu-id="259c8-109">Mensajes</span><span class="sxs-lookup"><span data-stu-id="259c8-109">Messages</span></span>  
  
- <span data-ttu-id="259c8-110">Conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="259c8-110">Correlation sets</span></span>  
  
- <span data-ttu-id="259c8-111">Vínculos de servicios</span><span class="sxs-lookup"><span data-stu-id="259c8-111">Service links</span></span>  
  
- <span data-ttu-id="259c8-112">Puertos</span><span class="sxs-lookup"><span data-stu-id="259c8-112">Ports</span></span>  
  
- <span data-ttu-id="259c8-113">Distinguen tipos de valor integrados: **booleano**, **bytes**, **Char**, **Decimal**, **doble**,  **Int16**, **Int32**, **Int64**, **SByte**, **único**, **cadena**, **UInt16**, **UInt32**, y **UInt64**</span><span class="sxs-lookup"><span data-stu-id="259c8-113">Distinguished built-in value types: **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**</span></span>  
  
- <span data-ttu-id="259c8-114">Objetos</span><span class="sxs-lookup"><span data-stu-id="259c8-114">Objects</span></span>  
  
- <span data-ttu-id="259c8-115">Tipos de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="259c8-115">Enumeration types</span></span>  
  
  <span data-ttu-id="259c8-116">XLANG/s proporciona una semántica de inicialización para cada uno de los tipos anteriores.</span><span class="sxs-lookup"><span data-stu-id="259c8-116">XLANG/s provides initialization semantics for each of the preceding types.</span></span> <span data-ttu-id="259c8-117">Esta inicialización se puede considerar como la asignación del tipo a una variable.</span><span class="sxs-lookup"><span data-stu-id="259c8-117">Such initialization can be viewed as an assignment to a variable of that type.</span></span> <span data-ttu-id="259c8-118">En XLANG/s, una variable tiene que estar asignada con carácter definitivo antes de que se pueda obtener o usar su valor.</span><span class="sxs-lookup"><span data-stu-id="259c8-118">In XLANG/s, a variable must be definitely assigned before its value can be obtained or used.</span></span>  
  
## <a name="xlangs-operators"></a><span data-ttu-id="259c8-119">Operadores de XLANG/s</span><span class="sxs-lookup"><span data-stu-id="259c8-119">XLANG/s Operators</span></span>  
 <span data-ttu-id="259c8-120">XLANG/s admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="259c8-120">XLANG/s supports the following operators.</span></span> <span data-ttu-id="259c8-121">Cumplen estrictamente con las funciones de los operadores correspondientes en C#.</span><span class="sxs-lookup"><span data-stu-id="259c8-121">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="259c8-122">Operador</span><span class="sxs-lookup"><span data-stu-id="259c8-122">Operator</span></span>|<span data-ttu-id="259c8-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="259c8-123">Description</span></span>|<span data-ttu-id="259c8-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="259c8-124">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="259c8-125">activado</span><span class="sxs-lookup"><span data-stu-id="259c8-125">checked</span></span>|<span data-ttu-id="259c8-126">Genera un error al producirse un desbordamiento aritmético</span><span class="sxs-lookup"><span data-stu-id="259c8-126">Raises error on arithmetic overflow</span></span>|<span data-ttu-id="259c8-127">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="259c8-127">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="259c8-128">desactivada</span><span class="sxs-lookup"><span data-stu-id="259c8-128">unchecked</span></span>|<span data-ttu-id="259c8-129">Hace caso omiso del desbordamiento aritmético.</span><span class="sxs-lookup"><span data-stu-id="259c8-129">Ignores arithmetic overflow</span></span>|<span data-ttu-id="259c8-130">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="259c8-130">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="259c8-131">nuevo</span><span class="sxs-lookup"><span data-stu-id="259c8-131">new</span></span>|<span data-ttu-id="259c8-132">Crea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="259c8-132">Creates an instance of a class</span></span>|<span data-ttu-id="259c8-133">myObject = new MyClass;</span><span class="sxs-lookup"><span data-stu-id="259c8-133">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="259c8-134">typeof</span><span class="sxs-lookup"><span data-stu-id="259c8-134">typeof</span></span>|<span data-ttu-id="259c8-135">Recupera un tipo</span><span class="sxs-lookup"><span data-stu-id="259c8-135">Retrieves a type</span></span>|<span data-ttu-id="259c8-136">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="259c8-136">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="259c8-137">succeeded</span><span class="sxs-lookup"><span data-stu-id="259c8-137">succeeded</span></span>|<span data-ttu-id="259c8-138">Comprueba la finalización correcta de ámbito transaccional u orquestación</span><span class="sxs-lookup"><span data-stu-id="259c8-138">Tests for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="259c8-139">se ha realizado correctamente (\<Id. de transacción para transacción secundaria de ámbito o servicio actual\>)</span><span class="sxs-lookup"><span data-stu-id="259c8-139">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="259c8-140">exists</span><span class="sxs-lookup"><span data-stu-id="259c8-140">exists</span></span>|<span data-ttu-id="259c8-141">Comprueba la existencia de una propiedad de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="259c8-141">Tests for the existence of a message context property</span></span>|<span data-ttu-id="259c8-142">BTS.RetryCount exists Message_In</span><span class="sxs-lookup"><span data-stu-id="259c8-142">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="259c8-143">Suma unaria</span><span class="sxs-lookup"><span data-stu-id="259c8-143">Unary plus</span></span>|<span data-ttu-id="259c8-144">+(int x)</span><span class="sxs-lookup"><span data-stu-id="259c8-144">+(int x)</span></span>|  
|-|<span data-ttu-id="259c8-145">Resta unaria</span><span class="sxs-lookup"><span data-stu-id="259c8-145">Unary minus</span></span>|<span data-ttu-id="259c8-146">-(int x)</span><span class="sxs-lookup"><span data-stu-id="259c8-146">-(int x)</span></span>|  
|<span data-ttu-id="259c8-147">!</span><span class="sxs-lookup"><span data-stu-id="259c8-147">!</span></span>|<span data-ttu-id="259c8-148">Negación lógica</span><span class="sxs-lookup"><span data-stu-id="259c8-148">Logical negation</span></span>|<span data-ttu-id="259c8-149">!myBool</span><span class="sxs-lookup"><span data-stu-id="259c8-149">!myBool</span></span>|  
|~|<span data-ttu-id="259c8-150">Complemento bit a bit</span><span class="sxs-lookup"><span data-stu-id="259c8-150">Bitwise complement</span></span>|<span data-ttu-id="259c8-151">x = ~y</span><span class="sxs-lookup"><span data-stu-id="259c8-151">x = ~y</span></span>|  
|<span data-ttu-id="259c8-152">()</span><span class="sxs-lookup"><span data-stu-id="259c8-152">()</span></span>|<span data-ttu-id="259c8-153">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="259c8-153">Cast</span></span>|<span data-ttu-id="259c8-154">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="259c8-154">(bool) myInt</span></span>|  
|*|<span data-ttu-id="259c8-155">Veces</span><span class="sxs-lookup"><span data-stu-id="259c8-155">Times</span></span>|<span data-ttu-id="259c8-156">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="259c8-156">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="259c8-157">Dividido por</span><span class="sxs-lookup"><span data-stu-id="259c8-157">Divided by</span></span>|<span data-ttu-id="259c8-158">x / y</span><span class="sxs-lookup"><span data-stu-id="259c8-158">x / y</span></span>|  
|+|<span data-ttu-id="259c8-159">Signo más</span><span class="sxs-lookup"><span data-stu-id="259c8-159">Plus</span></span>|<span data-ttu-id="259c8-160">x + y</span><span class="sxs-lookup"><span data-stu-id="259c8-160">x + y</span></span>|  
|-|<span data-ttu-id="259c8-161">Resta</span><span class="sxs-lookup"><span data-stu-id="259c8-161">Minus</span></span>|<span data-ttu-id="259c8-162">x - y</span><span class="sxs-lookup"><span data-stu-id="259c8-162">x - y</span></span>|  
|<<|<span data-ttu-id="259c8-163">Desplazamiento a la izquierda</span><span class="sxs-lookup"><span data-stu-id="259c8-163">Shift left</span></span>|<span data-ttu-id="259c8-164">x << 2</span><span class="sxs-lookup"><span data-stu-id="259c8-164">x << 2</span></span>|  
|>>|<span data-ttu-id="259c8-165">Desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="259c8-165">Shift right</span></span>|<span data-ttu-id="259c8-166">x >> 2</span><span class="sxs-lookup"><span data-stu-id="259c8-166">x >> 2</span></span>|  
|<|<span data-ttu-id="259c8-167">Menor que</span><span class="sxs-lookup"><span data-stu-id="259c8-167">Less than</span></span>|<span data-ttu-id="259c8-168">Si (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="259c8-168">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="259c8-169">Mayor que</span><span class="sxs-lookup"><span data-stu-id="259c8-169">Greater than</span></span>|<span data-ttu-id="259c8-170">Si (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="259c8-170">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="259c8-171">Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="259c8-171">Less than or equal to</span></span>|<span data-ttu-id="259c8-172">Si (MyMsg.numOrders < = 10)...</span><span class="sxs-lookup"><span data-stu-id="259c8-172">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="259c8-173">Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="259c8-173">Greater than or equal to</span></span>|<span data-ttu-id="259c8-174">Si (MyMsg.numOrders > = 10)...</span><span class="sxs-lookup"><span data-stu-id="259c8-174">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="259c8-175">Igual a</span><span class="sxs-lookup"><span data-stu-id="259c8-175">Equal to</span></span>|<span data-ttu-id="259c8-176">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="259c8-176">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="259c8-177">!=</span><span class="sxs-lookup"><span data-stu-id="259c8-177">!=</span></span>|<span data-ttu-id="259c8-178">No es igual a</span><span class="sxs-lookup"><span data-stu-id="259c8-178">Not equal to</span></span>|<span data-ttu-id="259c8-179">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="259c8-179">If (MyMsg.numOrders != 10)...</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="259c8-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="259c8-180">See Also</span></span>  
 <span data-ttu-id="259c8-181">[Tipos de datos de XLANG / s](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="259c8-181">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="259c8-182">[Instrucciones de XLANG / s](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="259c8-182">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="259c8-183">[Expresiones de XLANG / s](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="259c8-183">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="259c8-184">[Palabras reservadas de XLANG / s](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="259c8-184">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="259c8-185">Conversiones de tipos de XLANG/s a BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="259c8-185">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)