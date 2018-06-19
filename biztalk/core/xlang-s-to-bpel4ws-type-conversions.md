---
title: Conversiones de tipos de XLANG-s a BPEL4WS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XLANG/s
- XLANG/s, warning
- XLANG/s, BPEL4WS
- XLANG/s, converting
ms.assetid: a35d4dba-9344-43c8-86e6-a373a4452579
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02412b86b8649b73cadb4715793f085682a1de74
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973746"
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a>XLANG-s para las conversiones de tipo de BPEL4WS
En las siguientes tablas se detallan las conversiones entre varias construcciones XLANG/s y BPEL4WS.  
  
> [!CAUTION]
>  XPath 1.1 no es compatible con números exponenciales o dobles formatos. Los valores literales de estos formatos en orquestaciones XLANG/s se exportan a BPEL4WS mediante el formato %f  y puede que se produzca una pérdida de precisión.  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a>Literales (si el literal es parte de una expresión)  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|Cadena, carácter|Cadena XPath|  
|Entero, real|Número XPath|  
|Booleano "true", "false"|Funciones XPath true(), false()|  
  
## <a name="literals-standalone-assignment"></a>Literales (asignación independiente)  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|Constante literal|Equivalente XSD|  
  
## <a name="variables"></a>Variables  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|Referencia de variable|bpws:getContainerData(%varName%,  part, %locationPath%)|  
|Referencia de mensajes (de tipo .NET)|bpws:getContainerData(%msgName%, part, %locationPath%)|  
|Referencia de parte-de-mensaje|bpws:getContainerData(%msgName%, %locationPath%)|  
|Referencia de campo-distintivo|bpws:getContainerData(%msgName%, %partName%, %locationPath%)|  
|Referencia de propiedad-de-datos de mensaje|bpws:getContainerProperty(%msgName%, %propertyQName%)|  
  
## <a name="operators"></a>Operadores  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|Unario +|Pasa por alto|  
|- unario|Unario - de XPath|  
|Unario !|not() function de XPath|  
|Binario & &,&#124;&#124;|Operadores de XPath 'and', 'or' |  
|Binarios ==,! =, < =, <>, =, >|XPath '=', '! =', ' < =', ' <', ' > =', ' >' operadores|  
|Binarios +, -, *, % con ambos operandos de tipo entero|Operadores '+', '-', '*', 'mod' de XPath|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a>Construcciones XLANG/s que no se permiten en BPEL4WS  
  
-   Referencia de propiedad-de-contexto de mensaje  
  
-   Referencia de propiedad-de-servicio  
  
-   Referencia de propiedad-de-puerto  
  
-   Referencia de propiedad-de-vínculo de servicio  
  
-   Unario - con tipo no entero  
  
-   Unario ~  
  
-   Operador de conversión  
  
-   Binario / con operandos de tipo entero  
  
-   Binarios +, -, *, %, / con operandos de tipo no entero  
  
-   Binarios < =, <>, =, > con operandos no es una cadena  
  
-   Operadores bit a bit &, ^,&#124;  
  
-   Operadores de desplazamiento <<>>,  
  
-   Expresión comprobada  
  
-   Expresión intrínseca  
  
-   Incrementos y reducciones previos y posteriores ++, --.  
  
-   Llamada a objeto (con o sin los parámetros de referencia and/or)  
  
-   Operador 'new'