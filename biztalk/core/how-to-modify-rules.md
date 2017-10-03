---
title: "Cómo modificar reglas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, activating
- deactivating business rules
- business rules, priorities
- activating business rules
- business rules, deactivating
- modifying, business rules
- business rules, modifying
ms.assetid: 661b2637-b5d6-4bde-9c42-24cd9e9d241c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fce3fb78ce67b6c82f2301dfcb4cb2175aee0dde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-rules"></a>Cómo modificar reglas
La capacidad de cambiar reglas es una parte importante del paradigma de reglas de negocios. Puede modificar las reglas de una directiva de dos maneras: mediante la creación de una nueva versión de la directiva, o bien modificando directamente una versión no publicada de la directiva.  
  
 Puede modificar reglas de forma individual, agregar nuevas reglas o eliminar otras existentes. Puede eliminar predicados y operadores lógicos de una condición de regla, eliminar acciones, subir y bajar acciones en el panel de visualización, o mover predicados y operadores lógicos dentro de una condición. Recuerde, no obstante, que el orden en que los predicados y operadores lógicos se muestran no determina el orden de evaluación.  
  
 Puede establecer una regla para que esté inactiva, de manera que no se ejecute cuando lo haga la directiva, o puede reactivar una regla que haya sido desactivada.  
  
 Puede establecer la prioridad en una regla, de manera que sus acciones se ejecuten antes o después de las acciones de cualquier regla de prioridad diferente.  
  
> [!CAUTION]
>  Si necesita detener el equipo del servidor SQL Server, asegúrese de guardar todas la versiones o definiciones de vocabulario no guardadas y de cerrar el Compositor de reglas de negocio para que no se pierda ningún cambio.  
  
 Este tema contiene procedimientos para las siguientes tareas:  
  
-   Para cambiar un argumento en una condición o acción  
  
-   Para mover un predicado dentro de una condición  
  
-   Para mover un operador lógico dentro de una condición  
  
-   Para cambiar el orden de las acciones dentro de una regla  
  
-   Para eliminar un predicado, operador lógico o acción  
  
-   Para activar o desactivar una regla  
  
-   Para establecer una prioridad en una regla  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a>Para cambiar un argumento en una condición o acción  
  
1.  En la ventana Hechos y definiciones, haga clic en la pestaña apropiada y desplácese hasta el término que desea utilizar como argumento. El término debe ser de un tipo esperado por el predicado o la función.  
  
2.  Haga clic en el término y arrástrelo hasta un argumento de predicado en una condición o un argumento de función en una acción.  
  
### <a name="to-move-a-predicate-within-a-condition"></a>Para mover un predicado dentro de una condición  
  
-   Haga clic en el predicado y arrástrelo hasta otro operador lógico.  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a>Para mover un operador lógico dentro de una condición  
  
-   Haga clic en el operador lógico y arrástrela hasta otro operador lógico o **condiciones**.  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a>Para cambiar el orden de las acciones dentro de una regla  
  
-   Haga clic en la acción y, a continuación, haga clic en **Subir acción** o **Bajar acción**.  
  
    > [!NOTE]
    >  Las acciones de una regla se ejecutarán en el orden especificado a excepción de las funciones de control del motor, que se ejecutan después del resto de acciones.  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a>Para eliminar un predicado, operador lógico o acción  
  
-   Haga clic en el predicado, operador lógico o acción y, a continuación, haga clic en **eliminar**.  
  
### <a name="to-activate-or-deactivate-a-rule"></a>Para activar o desactivar una regla  
  
-   Haga clic en la regla y, a continuación, en la ventana Propiedades, establezca **Active** como **True** o **False**.  
  
### <a name="to-set-a-priority-on-a-rule"></a>Para establecer una prioridad en una regla  
  
-   Haga clic en la regla y, a continuación, en la ventana Propiedades, establezca **prioridad** a un valor entero.  
  
    > [!NOTE]
    >  Las prioridades son relativas y todas las acciones de una regla de una prioridad dada se ejecutarán en orden antes que las acciones de una regla con un valor de prioridad más bajo. El valor predeterminado de una prioridad es cero, pero puede ser un valor positivo o negativo.