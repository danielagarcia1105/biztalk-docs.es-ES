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
ms.openlocfilehash: 8c1773b7af3ec029026ee884e6c1161e27a3c330
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="xlang-s-variables-and-operators"></a><span data-ttu-id="682fe-102">Operadores y Variables de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="682fe-102">XLANG-s Variables and Operators</span></span>
<span data-ttu-id="682fe-103">En esta sección se tratan las variables y los operadores utilizados en el lenguaje XLANG/s.</span><span class="sxs-lookup"><span data-stu-id="682fe-103">This section discusses the variables and operators used in the XLANG/s language.</span></span>  
  
## <a name="xlangs-variables"></a><span data-ttu-id="682fe-104">Variables de XLANG/s</span><span class="sxs-lookup"><span data-stu-id="682fe-104">XLANG/s Variables</span></span>  
 <span data-ttu-id="682fe-105">Las variables representan ubicaciones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="682fe-105">Variables represent storage locations.</span></span> <span data-ttu-id="682fe-106">Cada variable tiene un tipo que determina qué valores se pueden almacenar en ella.</span><span class="sxs-lookup"><span data-stu-id="682fe-106">Every variable has a type that determines what values can be stored in that variable.</span></span> <span data-ttu-id="682fe-107">XLANG/s implementa la seguridad de tipos y su compilador garantiza que los valores almacenados en las variables siempre sean del tipo apropiado.</span><span class="sxs-lookup"><span data-stu-id="682fe-107">XLANG/s is type-safe, and its compiler guarantees that values stored in variables are always of the appropriate type.</span></span> <span data-ttu-id="682fe-108">XLANG/s admite lo siguientes tipos de variables:</span><span class="sxs-lookup"><span data-stu-id="682fe-108">XLANG/s supports the following variable types:</span></span>  
  
-   <span data-ttu-id="682fe-109">Mensajes</span><span class="sxs-lookup"><span data-stu-id="682fe-109">Messages</span></span>  
  
-   <span data-ttu-id="682fe-110">Conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="682fe-110">Correlation sets</span></span>  
  
-   <span data-ttu-id="682fe-111">Vínculos de servicios</span><span class="sxs-lookup"><span data-stu-id="682fe-111">Service links</span></span>  
  
-   <span data-ttu-id="682fe-112">Puertos</span><span class="sxs-lookup"><span data-stu-id="682fe-112">Ports</span></span>  
  
-   <span data-ttu-id="682fe-113">Distinguen tipos de valor integrados: **booleano**, **bytes**, **Char**, **Decimal**, **doble**,  **Int16**, **Int32**, **Int64**, **SByte**, **único**, **cadena**, **UInt16**, **UInt32**, y **UInt64**</span><span class="sxs-lookup"><span data-stu-id="682fe-113">Distinguished built-in value types: **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**</span></span>  
  
-   <span data-ttu-id="682fe-114">Objetos</span><span class="sxs-lookup"><span data-stu-id="682fe-114">Objects</span></span>  
  
-   <span data-ttu-id="682fe-115">Tipos de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="682fe-115">Enumeration types</span></span>  
  
 <span data-ttu-id="682fe-116">XLANG/s proporciona una semántica de inicialización para cada uno de los tipos anteriores.</span><span class="sxs-lookup"><span data-stu-id="682fe-116">XLANG/s provides initialization semantics for each of the preceding types.</span></span> <span data-ttu-id="682fe-117">Esta inicialización se puede considerar como la asignación del tipo a una variable.</span><span class="sxs-lookup"><span data-stu-id="682fe-117">Such initialization can be viewed as an assignment to a variable of that type.</span></span> <span data-ttu-id="682fe-118">En XLANG/s, una variable tiene que estar asignada con carácter definitivo antes de que se pueda obtener o usar su valor.</span><span class="sxs-lookup"><span data-stu-id="682fe-118">In XLANG/s, a variable must be definitely assigned before its value can be obtained or used.</span></span>  
  
## <a name="xlangs-operators"></a><span data-ttu-id="682fe-119">Operadores de XLANG/s</span><span class="sxs-lookup"><span data-stu-id="682fe-119">XLANG/s Operators</span></span>  
 <span data-ttu-id="682fe-120">XLANG/s admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="682fe-120">XLANG/s supports the following operators.</span></span> <span data-ttu-id="682fe-121">Cumplen estrictamente con las funciones de los operadores correspondientes en C#.</span><span class="sxs-lookup"><span data-stu-id="682fe-121">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="682fe-122">Operador</span><span class="sxs-lookup"><span data-stu-id="682fe-122">Operator</span></span>|<span data-ttu-id="682fe-123">Description</span><span class="sxs-lookup"><span data-stu-id="682fe-123">Description</span></span>|<span data-ttu-id="682fe-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="682fe-124">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="682fe-125">activado</span><span class="sxs-lookup"><span data-stu-id="682fe-125">checked</span></span>|<span data-ttu-id="682fe-126">Genera un error al producirse un desbordamiento aritmético</span><span class="sxs-lookup"><span data-stu-id="682fe-126">Raises error on arithmetic overflow</span></span>|<span data-ttu-id="682fe-127">checked(x = y * 1000)</span><span class="sxs-lookup"><span data-stu-id="682fe-127">checked(x = y * 1000)</span></span>|  
|<span data-ttu-id="682fe-128">No está activada</span><span class="sxs-lookup"><span data-stu-id="682fe-128">unchecked</span></span>|<span data-ttu-id="682fe-129">Hace caso omiso del desbordamiento aritmético.</span><span class="sxs-lookup"><span data-stu-id="682fe-129">Ignores arithmetic overflow</span></span>|<span data-ttu-id="682fe-130">unchecked(x = y * 1000)</span><span class="sxs-lookup"><span data-stu-id="682fe-130">unchecked(x = y * 1000)</span></span>|  
|<span data-ttu-id="682fe-131">nuevo</span><span class="sxs-lookup"><span data-stu-id="682fe-131">new</span></span>|<span data-ttu-id="682fe-132">Crea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="682fe-132">Creates an instance of a class</span></span>|<span data-ttu-id="682fe-133">myObject = new MyClass;</span><span class="sxs-lookup"><span data-stu-id="682fe-133">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="682fe-134">typeof</span><span class="sxs-lookup"><span data-stu-id="682fe-134">typeof</span></span>|<span data-ttu-id="682fe-135">Recupera un tipo</span><span class="sxs-lookup"><span data-stu-id="682fe-135">Retrieves a type</span></span>|<span data-ttu-id="682fe-136">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="682fe-136">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="682fe-137">succeeded</span><span class="sxs-lookup"><span data-stu-id="682fe-137">succeeded</span></span>|<span data-ttu-id="682fe-138">Comprueba la finalización correcta de ámbito transaccional u orquestación</span><span class="sxs-lookup"><span data-stu-id="682fe-138">Tests for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="682fe-139">se ha realizado correctamente (\<identificador de transacción de secundarios del ámbito actual o servicio\>)</span><span class="sxs-lookup"><span data-stu-id="682fe-139">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="682fe-140">exists</span><span class="sxs-lookup"><span data-stu-id="682fe-140">exists</span></span>|<span data-ttu-id="682fe-141">Comprueba la existencia de una propiedad de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="682fe-141">Tests for the existence of a message context property</span></span>|<span data-ttu-id="682fe-142">BTS.RetryCount exists Message_In</span><span class="sxs-lookup"><span data-stu-id="682fe-142">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="682fe-143">Suma unaria</span><span class="sxs-lookup"><span data-stu-id="682fe-143">Unary plus</span></span>|<span data-ttu-id="682fe-144">+(int x)</span><span class="sxs-lookup"><span data-stu-id="682fe-144">+(int x)</span></span>|  
|-|<span data-ttu-id="682fe-145">Resta unaria</span><span class="sxs-lookup"><span data-stu-id="682fe-145">Unary minus</span></span>|<span data-ttu-id="682fe-146">-(int x)</span><span class="sxs-lookup"><span data-stu-id="682fe-146">-(int x)</span></span>|  
|<span data-ttu-id="682fe-147">!</span><span class="sxs-lookup"><span data-stu-id="682fe-147">!</span></span>|<span data-ttu-id="682fe-148">Negación lógica</span><span class="sxs-lookup"><span data-stu-id="682fe-148">Logical negation</span></span>|<span data-ttu-id="682fe-149">!myBool</span><span class="sxs-lookup"><span data-stu-id="682fe-149">!myBool</span></span>|  
|~|<span data-ttu-id="682fe-150">Complemento bit a bit</span><span class="sxs-lookup"><span data-stu-id="682fe-150">Bitwise complement</span></span>|<span data-ttu-id="682fe-151">x = ~y</span><span class="sxs-lookup"><span data-stu-id="682fe-151">x = ~y</span></span>|  
|<span data-ttu-id="682fe-152">()</span><span class="sxs-lookup"><span data-stu-id="682fe-152">()</span></span>|<span data-ttu-id="682fe-153">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="682fe-153">Cast</span></span>|<span data-ttu-id="682fe-154">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="682fe-154">(bool) myInt</span></span>|  
|*|<span data-ttu-id="682fe-155">Veces</span><span class="sxs-lookup"><span data-stu-id="682fe-155">Times</span></span>|<span data-ttu-id="682fe-156">Weight = MyMsg.numOrders * 20</span><span class="sxs-lookup"><span data-stu-id="682fe-156">Weight = MyMsg.numOrders * 20</span></span>|  
|/|<span data-ttu-id="682fe-157">Dividido por</span><span class="sxs-lookup"><span data-stu-id="682fe-157">Divided by</span></span>|<span data-ttu-id="682fe-158">x / y</span><span class="sxs-lookup"><span data-stu-id="682fe-158">x / y</span></span>|  
|+|<span data-ttu-id="682fe-159">signo más</span><span class="sxs-lookup"><span data-stu-id="682fe-159">Plus</span></span>|<span data-ttu-id="682fe-160">x + y</span><span class="sxs-lookup"><span data-stu-id="682fe-160">x + y</span></span>|  
|-|<span data-ttu-id="682fe-161">Resta</span><span class="sxs-lookup"><span data-stu-id="682fe-161">Minus</span></span>|<span data-ttu-id="682fe-162">x - y</span><span class="sxs-lookup"><span data-stu-id="682fe-162">x - y</span></span>|  
|<<|<span data-ttu-id="682fe-163">Desplazamiento a la izquierda</span><span class="sxs-lookup"><span data-stu-id="682fe-163">Shift left</span></span>|<span data-ttu-id="682fe-164">x << 2</span><span class="sxs-lookup"><span data-stu-id="682fe-164">x << 2</span></span>|  
|>>|<span data-ttu-id="682fe-165">Desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="682fe-165">Shift right</span></span>|<span data-ttu-id="682fe-166">x >> 2</span><span class="sxs-lookup"><span data-stu-id="682fe-166">x >> 2</span></span>|  
|<|<span data-ttu-id="682fe-167">Menor que</span><span class="sxs-lookup"><span data-stu-id="682fe-167">Less than</span></span>|<span data-ttu-id="682fe-168">Si (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="682fe-168">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="682fe-169">Mayor que</span><span class="sxs-lookup"><span data-stu-id="682fe-169">Greater than</span></span>|<span data-ttu-id="682fe-170">Si (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="682fe-170">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="682fe-171">Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="682fe-171">Less than or equal to</span></span>|<span data-ttu-id="682fe-172">Si (MyMsg.numOrders < = 10)...</span><span class="sxs-lookup"><span data-stu-id="682fe-172">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="682fe-173">Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="682fe-173">Greater than or equal to</span></span>|<span data-ttu-id="682fe-174">Si (MyMsg.numOrders > = 10)...</span><span class="sxs-lookup"><span data-stu-id="682fe-174">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="682fe-175">Igual a</span><span class="sxs-lookup"><span data-stu-id="682fe-175">Equal to</span></span>|<span data-ttu-id="682fe-176">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="682fe-176">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="682fe-177">!=</span><span class="sxs-lookup"><span data-stu-id="682fe-177">!=</span></span>|<span data-ttu-id="682fe-178">No es igual a</span><span class="sxs-lookup"><span data-stu-id="682fe-178">Not equal to</span></span>|<span data-ttu-id="682fe-179">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="682fe-179">If (MyMsg.numOrders != 10)...</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="682fe-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="682fe-180">See Also</span></span>  
 <span data-ttu-id="682fe-181">[Tipos de datos de XLANG-s](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="682fe-181">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="682fe-182">[Instrucciones de XLANG-s](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="682fe-182">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="682fe-183">[Expresiones de XLANG-s](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="682fe-183">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="682fe-184">[Palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="682fe-184">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="682fe-185">Conversiones de tipos de XLANG/s a BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="682fe-185">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)