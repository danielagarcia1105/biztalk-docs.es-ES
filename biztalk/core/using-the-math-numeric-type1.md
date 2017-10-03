---
title: Mediante el Type1 MATH_NUMERIC | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards EnterpriseOne adapters], currency
- JD Edwards EnterpriseOne adapters, exponents
- adapters [JD Edwards EnterpriseOne adapters], exponents
- MATH_NUMERIC type
- currency, values [JD Edwards EnterpriseOne adapters]
- JD Edwards EnterpriseOne adapters, currency
- exponents, values [JD Edwards EnterpriseOne adapters]
ms.assetid: 2a302216-f0a6-4afb-8f7d-bb1475ea1c57
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4a5df2d15f489d52c8e3d6dfc575f9e644c646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="3de2c-102">Uso del tipo MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="3de2c-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="3de2c-103">En este tema se describe el tipo MATH_NUMERIC y se detalla cómo se gestionan los exponentes, el número máximo de dígitos y el número máximo de dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="3de2c-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="3de2c-104">También incluye una explicación sobre:</span><span class="sxs-lookup"><span data-stu-id="3de2c-104">It also includes a discussion on:</span></span>  
  
-   <span data-ttu-id="3de2c-105">Exponentes</span><span class="sxs-lookup"><span data-stu-id="3de2c-105">Exponents</span></span>  
  
-   <span data-ttu-id="3de2c-106">Valores no válidos</span><span class="sxs-lookup"><span data-stu-id="3de2c-106">Invalid Values</span></span>  
  
-   <span data-ttu-id="3de2c-107">Precisión para las operaciones</span><span class="sxs-lookup"><span data-stu-id="3de2c-107">Precision for Operations</span></span>  
  
-   <span data-ttu-id="3de2c-108">Moneda</span><span class="sxs-lookup"><span data-stu-id="3de2c-108">Currency</span></span>  
  
 <span data-ttu-id="3de2c-109">El tipo MATH_NUMERIC es un tipo de cadena numérica.</span><span class="sxs-lookup"><span data-stu-id="3de2c-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="3de2c-110">Para usarlo, introduzca valores de parámetros del siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="3de2c-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 <span data-ttu-id="3de2c-111">Where</span><span class="sxs-lookup"><span data-stu-id="3de2c-111">Where</span></span>  
  
 <span data-ttu-id="3de2c-112">`<OptionalSign>`puede ser `+` o `-`.</span><span class="sxs-lookup"><span data-stu-id="3de2c-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="3de2c-113">`+`es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3de2c-113">`+` is the default.</span></span>  
  
 <span data-ttu-id="3de2c-114">`<IntegerAndFractionalPart>` es un máximo de 32 dígitos significativos, sin contar el símbolo decimal.</span><span class="sxs-lookup"><span data-stu-id="3de2c-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="3de2c-115">El símbolo decimal depende de la configuración regional en la instalación de JD Edwards EnterpriseOne; normalmente es un punto (.) o una coma (,).</span><span class="sxs-lookup"><span data-stu-id="3de2c-115">The decimal symbol is locale-specific to the JD Edwards EnterpriseOne installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="3de2c-116">Los dígitos pueden ser todos enteros, todos fraccionarios o una parte entera y otra fraccionaria, pero no pueden ser mayores de 32.</span><span class="sxs-lookup"><span data-stu-id="3de2c-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
 <span data-ttu-id="3de2c-117">`<OptionalExponentPart>` equivale a:</span><span class="sxs-lookup"><span data-stu-id="3de2c-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 <span data-ttu-id="3de2c-118">Where</span><span class="sxs-lookup"><span data-stu-id="3de2c-118">Where</span></span>  
  
 <span data-ttu-id="3de2c-119">`<OptionalSign>`puede ser `+` o `-`.</span><span class="sxs-lookup"><span data-stu-id="3de2c-119">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="3de2c-120">`+`es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3de2c-120">`+` is the default.</span></span>  
  
 <span data-ttu-id="3de2c-121">`<ExponentDigits>` tienen como máximo dos dígitos.</span><span class="sxs-lookup"><span data-stu-id="3de2c-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="3de2c-122">Se permiten valores entre 63 y-63 excluyendo el cero.</span><span class="sxs-lookup"><span data-stu-id="3de2c-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="3de2c-123">Valores válidos</span><span class="sxs-lookup"><span data-stu-id="3de2c-123">Valid Values</span></span>  
 <span data-ttu-id="3de2c-124">Ejemplos de **válido** valores de MATH_NUMERIC:</span><span class="sxs-lookup"><span data-stu-id="3de2c-124">Examples of **valid** MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="3de2c-125">123.045</span><span class="sxs-lookup"><span data-stu-id="3de2c-125">123.045</span></span>  
  
-   <span data-ttu-id="3de2c-126">4089 (observe que no hay coma ni punto para miles)</span><span class="sxs-lookup"><span data-stu-id="3de2c-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="3de2c-127">-9084</span><span class="sxs-lookup"><span data-stu-id="3de2c-127">-9084</span></span>  
  
-   <span data-ttu-id="3de2c-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="3de2c-128">-230.75</span></span>  
  
-   <span data-ttu-id="3de2c-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="3de2c-129">0.010503</span></span>  
  
-   <span data-ttu-id="3de2c-130">1.023e-10, que equivale a 0,0000000001023</span><span class="sxs-lookup"><span data-stu-id="3de2c-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="3de2c-131">0.097e5 o 0.097e+5, que equivale a 9700</span><span class="sxs-lookup"><span data-stu-id="3de2c-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="3de2c-132">1.0e-32, que equivale a 0.00000000000000000000000000000001 (Es válido porque, en este caso, el 0 de la parte entera se ignora; hay 32 dígitos fraccionarios significativos.)</span><span class="sxs-lookup"><span data-stu-id="3de2c-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001 (This is valid because in this case, the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="3de2c-133">Valores no válidos</span><span class="sxs-lookup"><span data-stu-id="3de2c-133">Invalid Values</span></span>  
 <span data-ttu-id="3de2c-134">Los valores no válidos dependen del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="3de2c-134">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="3de2c-135">Una fracción decimal demasiado pequeña se interpreta como cero (se pierden todos los dígitos significativos).</span><span class="sxs-lookup"><span data-stu-id="3de2c-135">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="3de2c-136">Un entero con demasiados dígitos significativos produce resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="3de2c-136">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="3de2c-137">JD Edwards EnterpriseOne no siempre provoca una condición de error en este caso.</span><span class="sxs-lookup"><span data-stu-id="3de2c-137">JD Edwards EnterpriseOne does not always raise an error condition in this case.</span></span> <span data-ttu-id="3de2c-138">Un exponente demasiado grande o demasiado pequeño también se devuelve como valor no válido.</span><span class="sxs-lookup"><span data-stu-id="3de2c-138">An exponent that is too large or too small also returns as an invalid value.</span></span>  
  
 <span data-ttu-id="3de2c-139">Ejemplos de **válido** valores de MATH_NUMERIC:</span><span class="sxs-lookup"><span data-stu-id="3de2c-139">Examples of **invalid** MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="3de2c-140">1034.00000000000000000000000000001023 - demasiados dígitos significativos</span><span class="sxs-lookup"><span data-stu-id="3de2c-140">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
-   <span data-ttu-id="3de2c-141">1.023e - 64 - exponente demasiado pequeño</span><span class="sxs-lookup"><span data-stu-id="3de2c-141">1.023e-64 - exponent too small</span></span>  
  
-   <span data-ttu-id="3de2c-142">0.00317e64 - exponente demasiado grande</span><span class="sxs-lookup"><span data-stu-id="3de2c-142">0.00317e64 - exponent too large</span></span>  
  
 <span data-ttu-id="3de2c-143">Los caracteres no numéricos diferentes a los adecuados para signos y símbolos decimales originan valores no válidos.</span><span class="sxs-lookup"><span data-stu-id="3de2c-143">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="3de2c-144">Exponentes</span><span class="sxs-lookup"><span data-stu-id="3de2c-144">Exponents</span></span>  
 <span data-ttu-id="3de2c-145">Los exponentes los proporciona MATH_NUMERIC de JD Edwards EnterpriseOne como comodidad para introducir valores.</span><span class="sxs-lookup"><span data-stu-id="3de2c-145">Exponents are provided by the JD Edwards EnterpriseOne MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="3de2c-146">Sin embargo, la mayoría de los valores se devuelven sin exponentes (con los 32 dígitos significativos visibles).</span><span class="sxs-lookup"><span data-stu-id="3de2c-146">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="3de2c-147">Precisión para las operaciones</span><span class="sxs-lookup"><span data-stu-id="3de2c-147">Precision for Operations</span></span>  
 <span data-ttu-id="3de2c-148">Si una operación produce una pérdida de precisión, se produce redondeo.</span><span class="sxs-lookup"><span data-stu-id="3de2c-148">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="3de2c-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3de2c-149">For example:</span></span>  
  
 <span data-ttu-id="3de2c-150">1.9e-31 / 10.0 = 0.00000000000000000000000000000002.</span><span class="sxs-lookup"><span data-stu-id="3de2c-150">1.9e-31 / 10.0 = 0.00000000000000000000000000000002.</span></span>  
  
 <span data-ttu-id="3de2c-151">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="3de2c-151">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="3de2c-152">En otros casos se producen resultados impredecibles, como cuando un valor positivo muy grande se multiplica por otro.</span><span class="sxs-lookup"><span data-stu-id="3de2c-152">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span> <span data-ttu-id="3de2c-153">1.01e32 * 2.053e32 no produce resultados fiables y no genera un error.</span><span class="sxs-lookup"><span data-stu-id="3de2c-153">1.01e32 * 2.053e32 does not yield reliable results and does not raise an error.</span></span> <span data-ttu-id="3de2c-154">Para la mayoría de las situaciones empresariales, no se superan estos intervalos.</span><span class="sxs-lookup"><span data-stu-id="3de2c-154">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="3de2c-155">Moneda</span><span class="sxs-lookup"><span data-stu-id="3de2c-155">Currency</span></span>  
 <span data-ttu-id="3de2c-156">Cuando una función empresarial de JD Edwards EnterpriseOne espera un valor de divisa, dicha función siempre tiene un parámetro independiente para un código de divisa de cuatro caracteres.</span><span class="sxs-lookup"><span data-stu-id="3de2c-156">When a JD Edwards EnterpriseOne business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="3de2c-157">No es necesario escribir este código salvo que use una divisa distinta a la configurada de manera predeterminada para el sistema JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="3de2c-157">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards EnterpriseOne system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de2c-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="3de2c-158">See Also</span></span>  
 [<span data-ttu-id="3de2c-159">Apéndice B: tipos de datos</span><span class="sxs-lookup"><span data-stu-id="3de2c-159">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)