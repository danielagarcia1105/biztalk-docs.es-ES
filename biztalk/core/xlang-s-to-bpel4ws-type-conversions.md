---
title: Conversiones de tipos de XLANG-s a BPEL4WS | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XLANG/s
- XLANG/s, warning
- XLANG/s, BPEL4WS
- XLANG/s, converting
ms.assetid: a35d4dba-9344-43c8-86e6-a373a4452579
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a9451d1f156bf98b3e8fd7da177937cd4492b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a><span data-ttu-id="43780-102">XLANG-s para las conversiones de tipo de BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="43780-102">XLANG-s to BPEL4WS Type Conversions</span></span>
<span data-ttu-id="43780-103">En las siguientes tablas se detallan las conversiones entre varias construcciones XLANG/s y BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="43780-103">The following tables detail the conversions between various XLANG/s constructs and BPEL4WS constructs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="43780-104">XPath 1.1 no es compatible con números exponenciales o dobles formatos.</span><span class="sxs-lookup"><span data-stu-id="43780-104">XPath 1.1 does not support numbers in exponential or double formats.</span></span> <span data-ttu-id="43780-105">Los valores literales de estos formatos en orquestaciones XLANG/s se exportan a BPEL4WS mediante el formato %f  y puede que se produzca una pérdida de precisión.</span><span class="sxs-lookup"><span data-stu-id="43780-105">Literal values in these formats in XLANG/s orchestrations are exported to BPEL4WS using the %f format, and a loss of precision might result.</span></span>  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a><span data-ttu-id="43780-106">Literales (si el literal es parte de una expresión)</span><span class="sxs-lookup"><span data-stu-id="43780-106">Literals (if the literal is part of an expression)</span></span>  
  
|<span data-ttu-id="43780-107">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="43780-107">XLANG/s</span></span>|<span data-ttu-id="43780-108">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="43780-108">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="43780-109">Cadena, carácter</span><span class="sxs-lookup"><span data-stu-id="43780-109">String, character</span></span>|<span data-ttu-id="43780-110">Cadena XPath</span><span class="sxs-lookup"><span data-stu-id="43780-110">XPath string</span></span>|  
|<span data-ttu-id="43780-111">Entero, real</span><span class="sxs-lookup"><span data-stu-id="43780-111">Integer, real</span></span>|<span data-ttu-id="43780-112">Número XPath</span><span class="sxs-lookup"><span data-stu-id="43780-112">XPath number</span></span>|  
|<span data-ttu-id="43780-113">Booleano "true", "false"</span><span class="sxs-lookup"><span data-stu-id="43780-113">Boolean "true", "false"</span></span>|<span data-ttu-id="43780-114">Funciones XPath true(), false()</span><span class="sxs-lookup"><span data-stu-id="43780-114">XPath true(), false() functions</span></span>|  
  
## <a name="literals-standalone-assignment"></a><span data-ttu-id="43780-115">Literales (asignación independiente)</span><span class="sxs-lookup"><span data-stu-id="43780-115">Literals (standalone assignment)</span></span>  
  
|<span data-ttu-id="43780-116">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="43780-116">XLANG/s</span></span>|<span data-ttu-id="43780-117">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="43780-117">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="43780-118">Constante literal</span><span class="sxs-lookup"><span data-stu-id="43780-118">Literal constant</span></span>|<span data-ttu-id="43780-119">Equivalente XSD</span><span class="sxs-lookup"><span data-stu-id="43780-119">XSD equivalent</span></span>|  
  
## <a name="variables"></a><span data-ttu-id="43780-120">Variables</span><span class="sxs-lookup"><span data-stu-id="43780-120">Variables</span></span>  
  
|<span data-ttu-id="43780-121">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="43780-121">XLANG/s</span></span>|<span data-ttu-id="43780-122">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="43780-122">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="43780-123">Referencia de variable</span><span class="sxs-lookup"><span data-stu-id="43780-123">Variable reference</span></span>|<span data-ttu-id="43780-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="43780-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span></span>|  
|<span data-ttu-id="43780-125">Referencia de mensajes (de tipo .NET)</span><span class="sxs-lookup"><span data-stu-id="43780-125">Message reference (.NET type)</span></span>|<span data-ttu-id="43780-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="43780-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span></span>|  
|<span data-ttu-id="43780-127">Referencia de parte-de-mensaje</span><span class="sxs-lookup"><span data-stu-id="43780-127">Message-part reference</span></span>|<span data-ttu-id="43780-128">bpws:getContainerData(%msgName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="43780-128">bpws:getContainerData(%msgName%, %locationPath%)</span></span>|  
|<span data-ttu-id="43780-129">Referencia de campo-distintivo</span><span class="sxs-lookup"><span data-stu-id="43780-129">Distinguished-field reference</span></span>|<span data-ttu-id="43780-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="43780-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span></span>|  
|<span data-ttu-id="43780-131">Referencia de propiedad-de-datos de mensaje</span><span class="sxs-lookup"><span data-stu-id="43780-131">Message data-property reference</span></span>|<span data-ttu-id="43780-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span><span class="sxs-lookup"><span data-stu-id="43780-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span></span>|  
  
## <a name="operators"></a><span data-ttu-id="43780-133">Operadores</span><span class="sxs-lookup"><span data-stu-id="43780-133">Operators</span></span>  
  
|<span data-ttu-id="43780-134">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="43780-134">XLANG/s</span></span>|<span data-ttu-id="43780-135">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="43780-135">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="43780-136">Unario +</span><span class="sxs-lookup"><span data-stu-id="43780-136">Unary +</span></span>|<span data-ttu-id="43780-137">Pasa por alto</span><span class="sxs-lookup"><span data-stu-id="43780-137">Ignored</span></span>|  
|<span data-ttu-id="43780-138">- unario</span><span class="sxs-lookup"><span data-stu-id="43780-138">Unary -</span></span>|<span data-ttu-id="43780-139">Unario - de XPath</span><span class="sxs-lookup"><span data-stu-id="43780-139">XPath unary -</span></span>|  
|<span data-ttu-id="43780-140">Unario !</span><span class="sxs-lookup"><span data-stu-id="43780-140">Unary !</span></span>|<span data-ttu-id="43780-141">not() function de XPath</span><span class="sxs-lookup"><span data-stu-id="43780-141">XPath not() function</span></span>|  
|<span data-ttu-id="43780-142">Binario & &, &#124; &#124;</span><span class="sxs-lookup"><span data-stu-id="43780-142">Binary &&, &#124;&#124;</span></span>|<span data-ttu-id="43780-143">Operadores de XPath 'and', 'or' </span><span class="sxs-lookup"><span data-stu-id="43780-143">XPath 'and', 'or' operators</span></span>|  
|<span data-ttu-id="43780-144">Binarios ==,! =, < =, \<, > =, ></span><span class="sxs-lookup"><span data-stu-id="43780-144">Binary ==, !=, <=, \<, >=, ></span></span>|<span data-ttu-id="43780-145">XPath '=', '!</span><span class="sxs-lookup"><span data-stu-id="43780-145">XPath '=', '!</span></span> <span data-ttu-id="43780-146">=', ' < = ','\<', ' > =', ' >' operadores</span><span class="sxs-lookup"><span data-stu-id="43780-146">=', '<=', '\<', '>=', '>' operators</span></span>|  
|<span data-ttu-id="43780-147">Binarios +, -, *, % con ambos operandos de tipo entero</span><span class="sxs-lookup"><span data-stu-id="43780-147">Binary +, -, *, % with both integral operands</span></span>|<span data-ttu-id="43780-148">Operadores '+', '-', '*', 'mod' de XPath</span><span class="sxs-lookup"><span data-stu-id="43780-148">XPath '+', '-', '*', 'mod' operators</span></span>|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a><span data-ttu-id="43780-149">Construcciones XLANG/s que no se permiten en BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="43780-149">XLANG/s constructs that are disallowed in BPEL4WS</span></span>  
  
-   <span data-ttu-id="43780-150">Referencia de propiedad-de-contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="43780-150">Message context-property reference</span></span>  
  
-   <span data-ttu-id="43780-151">Referencia de propiedad-de-servicio</span><span class="sxs-lookup"><span data-stu-id="43780-151">Service-property reference</span></span>  
  
-   <span data-ttu-id="43780-152">Referencia de propiedad-de-puerto</span><span class="sxs-lookup"><span data-stu-id="43780-152">Port-property reference</span></span>  
  
-   <span data-ttu-id="43780-153">Referencia de propiedad-de-vínculo de servicio</span><span class="sxs-lookup"><span data-stu-id="43780-153">Service link-property reference</span></span>  
  
-   <span data-ttu-id="43780-154">Unario - con tipo no entero</span><span class="sxs-lookup"><span data-stu-id="43780-154">Unary – with non-integral type</span></span>  
  
-   <span data-ttu-id="43780-155">Unario ~</span><span class="sxs-lookup"><span data-stu-id="43780-155">Unary ~</span></span>  
  
-   <span data-ttu-id="43780-156">Operador de conversión</span><span class="sxs-lookup"><span data-stu-id="43780-156">Cast operator</span></span>  
  
-   <span data-ttu-id="43780-157">Binario / con operandos de tipo entero</span><span class="sxs-lookup"><span data-stu-id="43780-157">Binary / with integral operands</span></span>  
  
-   <span data-ttu-id="43780-158">Binarios +, -, *, %, / con operandos de tipo no entero</span><span class="sxs-lookup"><span data-stu-id="43780-158">Binary +, -, *, %, / with non-integral operands</span></span>  
  
-   <span data-ttu-id="43780-159">Binarios < =, \<, > =, > con operandos no es una cadena</span><span class="sxs-lookup"><span data-stu-id="43780-159">Binary <=, \<, >=, > with non-string operands</span></span>  
  
-   <span data-ttu-id="43780-160">Operadores bit a bit &, ^, &#124;</span><span class="sxs-lookup"><span data-stu-id="43780-160">Bitwise operators &, ^, &#124;</span></span>  
  
-   <span data-ttu-id="43780-161">Operadores de desplazamiento <\<, >></span><span class="sxs-lookup"><span data-stu-id="43780-161">Shift operators <\<, >></span></span>  
  
-   <span data-ttu-id="43780-162">Expresión comprobada</span><span class="sxs-lookup"><span data-stu-id="43780-162">Checked expression</span></span>  
  
-   <span data-ttu-id="43780-163">Expresión intrínseca</span><span class="sxs-lookup"><span data-stu-id="43780-163">Intrinsic expression</span></span>  
  
-   <span data-ttu-id="43780-164">Incrementos y reducciones previos y posteriores ++, --.</span><span class="sxs-lookup"><span data-stu-id="43780-164">Pre- and post- increment and decrement ++, --</span></span>  
  
-   <span data-ttu-id="43780-165">Llamada a objeto (con o sin los parámetros de referencia and/or)</span><span class="sxs-lookup"><span data-stu-id="43780-165">Object invocation (with our without out and/or ref params)</span></span>  
  
-   <span data-ttu-id="43780-166">Operador 'new'</span><span class="sxs-lookup"><span data-stu-id="43780-166">'new' operator</span></span>