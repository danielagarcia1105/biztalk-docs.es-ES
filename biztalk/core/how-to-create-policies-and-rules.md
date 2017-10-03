---
title: "Cómo crear directivas y reglas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, business rules
- policies, rules
- policies, predicates
- business rules, creating
- creating, policies
- policies, logical operators
- policies, examples
- policies, default actions
- policies
- policies, arguments
- policies, creating
ms.assetid: 59f06a67-edde-443b-9fbb-55ec4429837a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52fb3d835b39a4059fc7a4a1644d7653257ea3dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-policies-and-rules"></a>Cómo crear directivas y reglas
Puede crear reglas con condiciones que son agrupaciones lógicas de operadores lógicos (**AND**, **OR**, y **no**) aplicadas a predicados (funciones integrados o definidos por el usuario u operadores) que toman argumentos (referencias de hechos integrados o definidos por el usuario). También puede hacer clic **condiciones** o en operadores lógicos y seleccionar un operador lógico o predicado integrado en el menú contextual.  
  
 Puede definir acciones (funciones integradas o definidas por el usuario) que se ejecutarán si la condición de regla se evalúa como **true**.  
  
> [!NOTE]
>  Si incluye más de un predicado en una regla, todos los predicados deben aparecer como argumentos para un operador lógico. (El nivel superior puede ser un miembro .NET único, una columna de base de datos o un campo/atributo XML que sea de tipo booleano.)  
  
### <a name="to-create-a-policy"></a>Para crear una directiva  
  
1.  En el panel Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.  
  
     Una nueva carpeta, **Policy1**, se crea en **directivas**. De forma predeterminada, se crea la versión 1 de una nueva directiva.  
  
2.  Haga clic en **Policy1**.  
  
3.  En el panel de la propiedad Nombre, escriba un nombre.  
  
### <a name="to-add-a-rule-to-a-policy-version"></a>Para agregar una regla a una versión de directiva  
  
-   En el panel Explorador de directivas, expanda [**la directiva de**], haga clic en **versión 1.0 (sin guardar)**y, a continuación, seleccione **agregar nueva regla**.  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a>Para agregar un operador lógico a una condición de regla  
  
-   En la ventana de definición de la regla, haga clic en **condiciones**y, a continuación, haga clic en uno de **Agregar operador lógico AND**, **Agregar operador lógico OR**, o **Agregar operador lógico NOT**.  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a>Para agregar un predicado integrado a una condición de regla o a un operador lógico  
  
1.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha y, a continuación, haga clic en el **predicados** carpeta.  
  
2.  Expanda una versión publicada de un vocabulario de predicados y haga clic en el predicado que desee.  
  
3.  Arrastre el predicado en el operador lógico, o bien **condiciones** si la regla contiene sólo un predicado.  
  
    > [!NOTE]
    >  También puede agregar un predicado directamente desde un origen de datos, siempre que el elemento de datos actúa como un predicado (se evalúa como **true** o **false**).  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a>Para agregar una acción integrada a una regla  
  
1.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha y, a continuación, haga clic en el **funciones** carpeta.  
  
2.  Expanda una versión publicada de un vocabulario de funciones y haga clic en la función que desee.  
  
3.  Arrastre la función en **acciones**. También puede hacer clic **acciones**y seleccione una acción integrada en el menú contextual.  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a>Para agregar un argumento a una condición o acción  
  
1.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha y, a continuación, haga clic en una carpeta de vocabulario.  
  
2.  Expanda una versión publicada del vocabulario y haga clic en el término que desee. El término debe ser de un tipo esperado por el predicado o la función.  
  
3.  Arrastre el término hasta un argumento de predicado en una condición o un argumento de función en una acción.  
  
    > [!NOTE]
    >  También puede agregar un argumento directamente desde un origen de datos o, si se trata de XML, puede especificar el tipo de campo en las propiedades cuando seleccione un campo; naturalmente, esto debe ser compatible con los propios datos, siempre que el elemento de datos sea de un tipo esperado por el predicado o la acción. Para agregar un argumento directamente desde un origen de datos, haga clic en la pestaña apropiada en la ventana Hechos, desplácese hasta el elemento que desee y arrástrelo hasta un argumento de predicado o un argumento de función.  
  
    > [!NOTE]
    >  Puede agregar un valor constante a un argumento haciendo clic directamente en el argumento y escribiendo el valor constante que desee.