---
title: Mediante el Type1 MATH_NUMERIC | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4a5df2d15f489d52c8e3d6dfc575f9e644c646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288516"
---
# <a name="using-the-mathnumeric-type"></a>Uso del tipo MATH_NUMERIC
En este tema se describe el tipo MATH_NUMERIC y se detalla cómo se gestionan los exponentes, el número máximo de dígitos y el número máximo de dígitos decimales. También incluye una explicación sobre:  
  
-   Exponentes  
  
-   Valores no válidos  
  
-   Precisión para las operaciones  
  
-   Moneda  
  
 El tipo MATH_NUMERIC es un tipo de cadena numérica. Para usarlo, introduzca valores de parámetros del siguiente formato:  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 Where  
  
 `<OptionalSign>`puede ser `+` o `-`. `+`es el valor predeterminado.  
  
 `<IntegerAndFractionalPart>` es un máximo de 32 dígitos significativos, sin contar el símbolo decimal. El símbolo decimal depende de la configuración regional en la instalación de JD Edwards EnterpriseOne; normalmente es un punto (.) o una coma (,). Los dígitos pueden ser todos enteros, todos fraccionarios o una parte entera y otra fraccionaria, pero no pueden ser mayores de 32.  
  
 `<OptionalExponentPart>` equivale a:  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 Where  
  
 `<OptionalSign>`puede ser `+` o `-`. `+`es el valor predeterminado.  
  
 `<ExponentDigits>` tienen como máximo dos dígitos. Se permiten valores entre 63 y-63 excluyendo el cero.  
  
## <a name="valid-values"></a>Valores válidos  
 Ejemplos de **válido** valores de MATH_NUMERIC:  
  
-   123.045  
  
-   4089 (observe que no hay coma ni punto para miles)  
  
-   -9084  
  
-   -230.75  
  
-   0.010503  
  
-   1.023e-10, que equivale a 0,0000000001023  
  
-   0.097e5 o 0.097e+5, que equivale a 9700  
  
-   1.0e-32, que equivale a 0.00000000000000000000000000000001 (Es válido porque, en este caso, el 0 de la parte entera se ignora; hay 32 dígitos fraccionarios significativos.)  
  
## <a name="invalid-values"></a>Valores no válidos  
 Los valores no válidos dependen del tipo de valor. Una fracción decimal demasiado pequeña se interpreta como cero (se pierden todos los dígitos significativos). Un entero con demasiados dígitos significativos produce resultados inesperados. JD Edwards EnterpriseOne no siempre provoca una condición de error en este caso. Un exponente demasiado grande o demasiado pequeño también se devuelve como valor no válido.  
  
 Ejemplos de **válido** valores de MATH_NUMERIC:  
  
-   1034.00000000000000000000000000001023 - demasiados dígitos significativos  
  
-   1.023e - 64 - exponente demasiado pequeño  
  
-   0.00317e64 - exponente demasiado grande  
  
 Los caracteres no numéricos diferentes a los adecuados para signos y símbolos decimales originan valores no válidos.  
  
## <a name="exponents"></a>Exponentes  
 Los exponentes los proporciona MATH_NUMERIC de JD Edwards EnterpriseOne como comodidad para introducir valores. Sin embargo, la mayoría de los valores se devuelven sin exponentes (con los 32 dígitos significativos visibles).  
  
## <a name="precision-for-operations"></a>Precisión para las operaciones  
 Si una operación produce una pérdida de precisión, se produce redondeo. Por ejemplo:  
  
 1.9e-31 / 10.0 = 0.00000000000000000000000000000002.  
  
 1.9e-31 / 100.0 = 0.00000000000000000000000000000000  
  
 En otros casos se producen resultados impredecibles, como cuando un valor positivo muy grande se multiplica por otro. 1.01e32 * 2.053e32 no produce resultados fiables y no genera un error. Para la mayoría de las situaciones empresariales, no se superan estos intervalos.  
  
## <a name="currency"></a>Moneda  
 Cuando una función empresarial de JD Edwards EnterpriseOne espera un valor de divisa, dicha función siempre tiene un parámetro independiente para un código de divisa de cuatro caracteres. No es necesario escribir este código salvo que use una divisa distinta a la configurada de manera predeterminada para el sistema JD Edwards EnterpriseOne.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice B: tipos de datos](../core/appendix-b-data-types.md)