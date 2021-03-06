---
title: Requisitos y limitaciones para expresiones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, about Expression Editor
- Expression Editor, requirements
- Orchestration Designer, Expression Editor
- Expression Editor, limitations
- Expression Editor
- Expression Editor, Orchestration Designer
ms.assetid: 1e0353d3-c2f3-4c10-86e3-8620e62dd0d5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9b3cbbd426227e21f16d5bde4186823164f1fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999693"
---
# <a name="requirements-and-limitations-for-expressions"></a>Requisitos y limitaciones para expresiones
El Editor de expresiones de BizTalk del Diseñador de orquestaciones es un editor de texto estándar de Visual Studio, lo que significa que ofrece IntelliSense. El Editor de expresiones de BizTalk se usa para escribir expresiones en formato de texto.  
  
 Use el cuadro de texto para escribir una sola expresión en formato de texto. La expresión puede contener varias líneas, pero debe finalizar por un solo punto y coma (;).  
  
 A continuación se muestra una lista de limitaciones para el uso de expresiones en el Editor de expresiones de BizTalk:  
  
- No se permite la asignación compuesta, como "+=", "-=" o "*=".  
  
- No se admite el uso de más de un operador de asignación en una instrucción.  
  
- No se admite la asignación dentro de un predicado “if” o “while”.  
  
- No se admiten los incrementos ni las reducciones. Por ejemplo, "++" ni "--".  
  
- Para las partes de mensajes, se permite el acceso de miembros en los métodos públicos, los tipos anidados, los campos de datos estáticos, las propiedades de .NET de solo lectura cuando se anotan con Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute, todos los campos de datos públicos y las propiedades de .NET que no son de solo lectura.  
  
- No se admiten los indizadores ni las propiedades de .NET con parámetros.  
  
- No se admiten los delegados ni los eventos.  
  
- No se admiten los elementos genéricos.  
  
- No se admite la sintaxis de control de flujo, tal como "foreach", "for", "do-while", "break" y "continue".  
  
- No se admiten las operaciones ternarias. Por ejemplo, "?:".  
  
- Puede agregar comentarios en la forma Expresión, pero ésta debe contener al menos una instrucción.  
  
- No se admiten las matrices.  
  
- Cuando la forma Expresión se coloca en una forma Construir mensaje, no se puede realizar ningún flujo de control. Por ejemplo, "if-then-else" ni "while".  
  
- Todas las instrucciones de expresiones válidas deben tener el formato:  
  
  -   Dotted-name = expression;  
  
  -   Dotted-name = expression;  
  
  Aunque puede usar el Editor de expresiones de BizTalk para escribir expresiones complejas con facilidad y rapidez, no se puede usar para escribir una cantidad de código arbitraria. El motivo es asegurar que el código de los procesos empresariales se mantenga independiente de su código de implementación.