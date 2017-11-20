---
title: Operadores y Variables de XLANG-s | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1affe6ebdebac515782ec9ecb82b0c6085341bfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-variables-and-operators"></a><span data-ttu-id="0c565-102">Operadores y Variables de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="0c565-102">XLANG-s Variables and Operators</span></span>
<span data-ttu-id="0c565-103">En esta sección se tratan las variables y los operadores utilizados en el lenguaje XLANG/s.</span><span class="sxs-lookup"><span data-stu-id="0c565-103">This section discusses the variables and operators used in the XLANG/s language.</span></span>  
  
## <a name="xlangs-variables"></a><span data-ttu-id="0c565-104">Variables de XLANG/s</span><span class="sxs-lookup"><span data-stu-id="0c565-104">XLANG/s Variables</span></span>  
 <span data-ttu-id="0c565-105">Las variables representan ubicaciones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0c565-105">Variables represent storage locations.</span></span> <span data-ttu-id="0c565-106">Cada variable tiene un tipo que determina qué valores se pueden almacenar en ella.</span><span class="sxs-lookup"><span data-stu-id="0c565-106">Every variable has a type that determines what values can be stored in that variable.</span></span> <span data-ttu-id="0c565-107">XLANG/s implementa la seguridad de tipos y su compilador garantiza que los valores almacenados en las variables siempre sean del tipo apropiado.</span><span class="sxs-lookup"><span data-stu-id="0c565-107">XLANG/s is type-safe, and its compiler guarantees that values stored in variables are always of the appropriate type.</span></span> <span data-ttu-id="0c565-108">XLANG/s admite lo siguientes tipos de variables:</span><span class="sxs-lookup"><span data-stu-id="0c565-108">XLANG/s supports the following variable types:</span></span>  
  
-   <span data-ttu-id="0c565-109">Mensajes</span><span class="sxs-lookup"><span data-stu-id="0c565-109">Messages</span></span>  
  
-   <span data-ttu-id="0c565-110">Conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="0c565-110">Correlation sets</span></span>  
  
-   <span data-ttu-id="0c565-111">Vínculos de servicios</span><span class="sxs-lookup"><span data-stu-id="0c565-111">Service links</span></span>  
  
-   <span data-ttu-id="0c565-112">Puertos</span><span class="sxs-lookup"><span data-stu-id="0c565-112">Ports</span></span>  
  
-   <span data-ttu-id="0c565-113">Distinguen tipos de valor integrados: **booleano**, **bytes**, **Char**, **Decimal**, **doble**,  **Int16**, **Int32**, **Int64**, **SByte**, **único**, **cadena**, **UInt16**, **UInt32**, y **UInt64**</span><span class="sxs-lookup"><span data-stu-id="0c565-113">Distinguished built-in value types: **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**</span></span>  
  
-   <span data-ttu-id="0c565-114">Objetos</span><span class="sxs-lookup"><span data-stu-id="0c565-114">Objects</span></span>  
  
-   <span data-ttu-id="0c565-115">Tipos de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="0c565-115">Enumeration types</span></span>  
  
 <span data-ttu-id="0c565-116">XLANG/s proporciona una semántica de inicialización para cada uno de los tipos anteriores.</span><span class="sxs-lookup"><span data-stu-id="0c565-116">XLANG/s provides initialization semantics for each of the preceding types.</span></span> <span data-ttu-id="0c565-117">Esta inicialización se puede considerar como la asignación del tipo a una variable.</span><span class="sxs-lookup"><span data-stu-id="0c565-117">Such initialization can be viewed as an assignment to a variable of that type.</span></span> <span data-ttu-id="0c565-118">En XLANG/s, una variable tiene que estar asignada con carácter definitivo antes de que se pueda obtener o usar su valor.</span><span class="sxs-lookup"><span data-stu-id="0c565-118">In XLANG/s, a variable must be definitely assigned before its value can be obtained or used.</span></span>  
  
## <a name="xlangs-operators"></a><span data-ttu-id="0c565-119">Operadores de XLANG/s</span><span class="sxs-lookup"><span data-stu-id="0c565-119">XLANG/s Operators</span></span>  
 <span data-ttu-id="0c565-120">XLANG/s admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="0c565-120">XLANG/s supports the following operators.</span></span> <span data-ttu-id="0c565-121">Cumplen estrictamente con las funciones de los operadores correspondientes en C#.</span><span class="sxs-lookup"><span data-stu-id="0c565-121">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="0c565-122">Operador</span><span class="sxs-lookup"><span data-stu-id="0c565-122">Operator</span></span>|<span data-ttu-id="0c565-123">Description</span><span class="sxs-lookup"><span data-stu-id="0c565-123">Description</span></span>|<span data-ttu-id="0c565-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c565-124">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="0c565-125">activado</span><span class="sxs-lookup"><span data-stu-id="0c565-125">checked</span></span>|<span data-ttu-id="0c565-126">Genera un error al producirse un desbordamiento aritmético</span><span class="sxs-lookup"><span data-stu-id="0c565-126">Raises error on arithmetic overflow</span></span>|<span data-ttu-id="0c565-127">checked(x = y * 1000)</span><span class="sxs-lookup"><span data-stu-id="0c565-127">checked(x = y * 1000)</span></span>|  
|<span data-ttu-id="0c565-128">No está activada</span><span class="sxs-lookup"><span data-stu-id="0c565-128">unchecked</span></span>|<span data-ttu-id="0c565-129">Hace caso omiso del desbordamiento aritmético.</span><span class="sxs-lookup"><span data-stu-id="0c565-129">Ignores arithmetic overflow</span></span>|<span data-ttu-id="0c565-130">unchecked(x = y * 1000)</span><span class="sxs-lookup"><span data-stu-id="0c565-130">unchecked(x = y * 1000)</span></span>|  
|<span data-ttu-id="0c565-131">nuevo</span><span class="sxs-lookup"><span data-stu-id="0c565-131">new</span></span>|<span data-ttu-id="0c565-132">Crea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="0c565-132">Creates an instance of a class</span></span>|<span data-ttu-id="0c565-133">myObject = new MyClass;</span><span class="sxs-lookup"><span data-stu-id="0c565-133">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="0c565-134">typeof</span><span class="sxs-lookup"><span data-stu-id="0c565-134">typeof</span></span>|<span data-ttu-id="0c565-135">Recupera un tipo</span><span class="sxs-lookup"><span data-stu-id="0c565-135">Retrieves a type</span></span>|<span data-ttu-id="0c565-136">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="0c565-136">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="0c565-137">succeeded</span><span class="sxs-lookup"><span data-stu-id="0c565-137">succeeded</span></span>|<span data-ttu-id="0c565-138">Comprueba la finalización correcta de ámbito transaccional u orquestación</span><span class="sxs-lookup"><span data-stu-id="0c565-138">Tests for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="0c565-139">se ha realizado correctamente (\<Id. de transacción para transacción secundaria de ámbito o servicio actual >)</span><span class="sxs-lookup"><span data-stu-id="0c565-139">succeeded(\<transaction ID for child transaction of current scope or service>)</span></span>|  
|<span data-ttu-id="0c565-140">exists</span><span class="sxs-lookup"><span data-stu-id="0c565-140">exists</span></span>|<span data-ttu-id="0c565-141">Comprueba la existencia de una propiedad de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="0c565-141">Tests for the existence of a message context property</span></span>|<span data-ttu-id="0c565-142">BTS.RetryCount exists Message_In</span><span class="sxs-lookup"><span data-stu-id="0c565-142">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="0c565-143">Suma unaria</span><span class="sxs-lookup"><span data-stu-id="0c565-143">Unary plus</span></span>|<span data-ttu-id="0c565-144">+(int x)</span><span class="sxs-lookup"><span data-stu-id="0c565-144">+(int x)</span></span>|  
|-|<span data-ttu-id="0c565-145">Resta unaria</span><span class="sxs-lookup"><span data-stu-id="0c565-145">Unary minus</span></span>|<span data-ttu-id="0c565-146">-(int x)</span><span class="sxs-lookup"><span data-stu-id="0c565-146">-(int x)</span></span>|  
|<span data-ttu-id="0c565-147">!</span><span class="sxs-lookup"><span data-stu-id="0c565-147">!</span></span>|<span data-ttu-id="0c565-148">Negación lógica</span><span class="sxs-lookup"><span data-stu-id="0c565-148">Logical negation</span></span>|<span data-ttu-id="0c565-149">!myBool</span><span class="sxs-lookup"><span data-stu-id="0c565-149">!myBool</span></span>|  
|~|<span data-ttu-id="0c565-150">Complemento bit a bit</span><span class="sxs-lookup"><span data-stu-id="0c565-150">Bitwise complement</span></span>|<span data-ttu-id="0c565-151">x = ~y</span><span class="sxs-lookup"><span data-stu-id="0c565-151">x = ~y</span></span>|  
|<span data-ttu-id="0c565-152">()</span><span class="sxs-lookup"><span data-stu-id="0c565-152">()</span></span>|<span data-ttu-id="0c565-153">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="0c565-153">Cast</span></span>|<span data-ttu-id="0c565-154">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="0c565-154">(bool) myInt</span></span>|  
|*|<span data-ttu-id="0c565-155">Veces</span><span class="sxs-lookup"><span data-stu-id="0c565-155">Times</span></span>|<span data-ttu-id="0c565-156">Weight = MyMsg.numOrders * 20</span><span class="sxs-lookup"><span data-stu-id="0c565-156">Weight = MyMsg.numOrders * 20</span></span>|  
|/|<span data-ttu-id="0c565-157">Dividido por</span><span class="sxs-lookup"><span data-stu-id="0c565-157">Divided by</span></span>|<span data-ttu-id="0c565-158">x / y</span><span class="sxs-lookup"><span data-stu-id="0c565-158">x / y</span></span>|  
|+|<span data-ttu-id="0c565-159">signo más</span><span class="sxs-lookup"><span data-stu-id="0c565-159">Plus</span></span>|<span data-ttu-id="0c565-160">x + y</span><span class="sxs-lookup"><span data-stu-id="0c565-160">x + y</span></span>|  
|-|<span data-ttu-id="0c565-161">Resta</span><span class="sxs-lookup"><span data-stu-id="0c565-161">Minus</span></span>|<span data-ttu-id="0c565-162">x - y</span><span class="sxs-lookup"><span data-stu-id="0c565-162">x - y</span></span>|  
|<<|<span data-ttu-id="0c565-163">Desplazamiento a la izquierda</span><span class="sxs-lookup"><span data-stu-id="0c565-163">Shift left</span></span>|<span data-ttu-id="0c565-164">x <\< 2</span><span class="sxs-lookup"><span data-stu-id="0c565-164">x <\< 2</span></span>|  
|>>|<span data-ttu-id="0c565-165">Desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="0c565-165">Shift right</span></span>|<span data-ttu-id="0c565-166">x >> 2</span><span class="sxs-lookup"><span data-stu-id="0c565-166">x >> 2</span></span>|  
|<|<span data-ttu-id="0c565-167">Menor que</span><span class="sxs-lookup"><span data-stu-id="0c565-167">Less than</span></span>|<span data-ttu-id="0c565-168">Si (MyMsg.numOrders \< 10)...</span><span class="sxs-lookup"><span data-stu-id="0c565-168">If (MyMsg.numOrders \< 10)...</span></span>|  
|>|<span data-ttu-id="0c565-169">Mayor que</span><span class="sxs-lookup"><span data-stu-id="0c565-169">Greater than</span></span>|<span data-ttu-id="0c565-170">Si (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="0c565-170">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="0c565-171">Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="0c565-171">Less than or equal to</span></span>|<span data-ttu-id="0c565-172">Si (MyMsg.numOrders \<= 10)...</span><span class="sxs-lookup"><span data-stu-id="0c565-172">If (MyMsg.numOrders \<= 10)...</span></span>|  
|>=|<span data-ttu-id="0c565-173">Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="0c565-173">Greater than or equal to</span></span>|<span data-ttu-id="0c565-174">Si (MyMsg.numOrders > = 10)...</span><span class="sxs-lookup"><span data-stu-id="0c565-174">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="0c565-175">Igual a</span><span class="sxs-lookup"><span data-stu-id="0c565-175">Equal to</span></span>|<span data-ttu-id="0c565-176">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="0c565-176">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="0c565-177">!=</span><span class="sxs-lookup"><span data-stu-id="0c565-177">!=</span></span>|<span data-ttu-id="0c565-178">No es igual a</span><span class="sxs-lookup"><span data-stu-id="0c565-178">Not equal to</span></span>|<span data-ttu-id="0c565-179">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="0c565-179">If (MyMsg.numOrders != 10)...</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c565-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c565-180">See Also</span></span>  
 <span data-ttu-id="0c565-181">[Tipos de datos de XLANG-s](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0c565-181">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="0c565-182">[Instrucciones de XLANG-s](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="0c565-182">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="0c565-183">[Expresiones de XLANG-s](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="0c565-183">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="0c565-184">[Palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="0c565-184">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="0c565-185">XLANG-s para las conversiones de tipo de BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="0c565-185">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)