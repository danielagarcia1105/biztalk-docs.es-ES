---
title: Cómo modificar reglas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fce3fb78ce67b6c82f2301dfcb4cb2175aee0dde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254236"
---
# <a name="how-to-modify-rules"></a><span data-ttu-id="4d1b0-102">Cómo modificar reglas</span><span class="sxs-lookup"><span data-stu-id="4d1b0-102">How to Modify Rules</span></span>
<span data-ttu-id="4d1b0-103">La capacidad de cambiar reglas es una parte importante del paradigma de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-103">The ability to change rules is an important part of the business rules paradigm.</span></span> <span data-ttu-id="4d1b0-104">Puede modificar las reglas de una directiva de dos maneras: mediante la creación de una nueva versión de la directiva, o bien modificando directamente una versión no publicada de la directiva.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-104">You can modify rules within a policy in two ways: either by creating a new version of the policy, or by directly modifying an unpublished version of the policy.</span></span>  
  
 <span data-ttu-id="4d1b0-105">Puede modificar reglas de forma individual, agregar nuevas reglas o eliminar otras existentes.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-105">You can modify rules individually, add new rules, or delete existing rules.</span></span> <span data-ttu-id="4d1b0-106">Puede eliminar predicados y operadores lógicos de una condición de regla, eliminar acciones, subir y bajar acciones en el panel de visualización, o mover predicados y operadores lógicos dentro de una condición.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-106">You can delete predicates and logical operators from a rule condition, delete actions, move actions up and down in the display, or move predicates and logical operators within a condition.</span></span> <span data-ttu-id="4d1b0-107">Recuerde, no obstante, que el orden en que los predicados y operadores lógicos se muestran no determina el orden de evaluación.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-107">Keep in mind, however, the order in which the predicates and logical operators are displayed does not determine the order of evaluation.</span></span>  
  
 <span data-ttu-id="4d1b0-108">Puede establecer una regla para que esté inactiva, de manera que no se ejecute cuando lo haga la directiva, o puede reactivar una regla que haya sido desactivada.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-108">You can set a rule to be inactive, so that the rule is not executed when the policy is executed, or you can reactivate a rule that has been deactivated.</span></span>  
  
 <span data-ttu-id="4d1b0-109">Puede establecer la prioridad en una regla, de manera que sus acciones se ejecuten antes o después de las acciones de cualquier regla de prioridad diferente.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-109">You can set the priority on a rule so that its actions will be executed before or after the actions of any rule of different priority.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4d1b0-110">Si necesita detener el equipo del servidor SQL Server, asegúrese de guardar todas la versiones o definiciones de vocabulario no guardadas y de cerrar el Compositor de reglas de negocio para que no se pierda ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-110">If you need to stop your SQL Server computer, be sure to save any unsaved vocabulary versions or vocabulary definitions, and close the Business Rule Composer so that no changes are lost.</span></span>  
  
 <span data-ttu-id="4d1b0-111">Este tema contiene procedimientos para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="4d1b0-111">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="4d1b0-112">Para cambiar un argumento en una condición o acción</span><span class="sxs-lookup"><span data-stu-id="4d1b0-112">To change an argument in a condition or action</span></span>  
  
-   <span data-ttu-id="4d1b0-113">Para mover un predicado dentro de una condición</span><span class="sxs-lookup"><span data-stu-id="4d1b0-113">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="4d1b0-114">Para mover un operador lógico dentro de una condición</span><span class="sxs-lookup"><span data-stu-id="4d1b0-114">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="4d1b0-115">Para cambiar el orden de las acciones dentro de una regla</span><span class="sxs-lookup"><span data-stu-id="4d1b0-115">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="4d1b0-116">Para eliminar un predicado, operador lógico o acción</span><span class="sxs-lookup"><span data-stu-id="4d1b0-116">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="4d1b0-117">Para activar o desactivar una regla</span><span class="sxs-lookup"><span data-stu-id="4d1b0-117">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="4d1b0-118">Para establecer una prioridad en una regla</span><span class="sxs-lookup"><span data-stu-id="4d1b0-118">To set a priority on a rule</span></span>  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a><span data-ttu-id="4d1b0-119">Para cambiar un argumento en una condición o acción</span><span class="sxs-lookup"><span data-stu-id="4d1b0-119">To change an argument in a condition or action</span></span>  
  
1.  <span data-ttu-id="4d1b0-120">En la ventana Hechos y definiciones, haga clic en la pestaña apropiada y desplácese hasta el término que desea utilizar como argumento.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-120">In the Facts and Definitions window, click the appropriate tab, and navigate to the term you want to use as an argument.</span></span> <span data-ttu-id="4d1b0-121">El término debe ser de un tipo esperado por el predicado o la función.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-121">The term must be of a type expected by the predicate or function.</span></span>  
  
2.  <span data-ttu-id="4d1b0-122">Haga clic en el término y arrástrelo hasta un argumento de predicado en una condición o un argumento de función en una acción.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-122">Click the term and drag it onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
### <a name="to-move-a-predicate-within-a-condition"></a><span data-ttu-id="4d1b0-123">Para mover un predicado dentro de una condición</span><span class="sxs-lookup"><span data-stu-id="4d1b0-123">To move a predicate within a condition</span></span>  
  
-   <span data-ttu-id="4d1b0-124">Haga clic en el predicado y arrástrelo hasta otro operador lógico.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-124">Click the predicate, and drag it to another logical operator.</span></span>  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a><span data-ttu-id="4d1b0-125">Para mover un operador lógico dentro de una condición</span><span class="sxs-lookup"><span data-stu-id="4d1b0-125">To move a logical operator within a condition</span></span>  
  
-   <span data-ttu-id="4d1b0-126">Haga clic en el operador lógico y arrástrela hasta otro operador lógico o **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-126">Click the logical operator, and drag it onto another logical operator or onto **Conditions**.</span></span>  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a><span data-ttu-id="4d1b0-127">Para cambiar el orden de las acciones dentro de una regla</span><span class="sxs-lookup"><span data-stu-id="4d1b0-127">To change the order of actions within a rule</span></span>  
  
-   <span data-ttu-id="4d1b0-128">Haga clic en la acción y, a continuación, haga clic en **Subir acción** o **Bajar acción**.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-128">Click the action and then click **Move action up** or **Move action down**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d1b0-129">Las acciones de una regla se ejecutarán en el orden especificado a excepción de las funciones de control del motor, que se ejecutan después del resto de acciones.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-129">The actions of a rule will be executed in the order specified with the exception of engine control functions which are executed after the other actions.</span></span>  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a><span data-ttu-id="4d1b0-130">Para eliminar un predicado, operador lógico o acción</span><span class="sxs-lookup"><span data-stu-id="4d1b0-130">To delete a predicate, logical operator, or action</span></span>  
  
-   <span data-ttu-id="4d1b0-131">Haga clic en el predicado, operador lógico o acción y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-131">Click the predicate, logical operator, or action, and then click **Delete**.</span></span>  
  
### <a name="to-activate-or-deactivate-a-rule"></a><span data-ttu-id="4d1b0-132">Para activar o desactivar una regla</span><span class="sxs-lookup"><span data-stu-id="4d1b0-132">To activate or deactivate a rule</span></span>  
  
-   <span data-ttu-id="4d1b0-133">Haga clic en la regla y, a continuación, en la ventana Propiedades, establezca **Active** como **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-133">Click the rule, and then in the Properties window, set **Active** to either **True** or **False**.</span></span>  
  
### <a name="to-set-a-priority-on-a-rule"></a><span data-ttu-id="4d1b0-134">Para establecer una prioridad en una regla</span><span class="sxs-lookup"><span data-stu-id="4d1b0-134">To set a priority on a rule</span></span>  
  
-   <span data-ttu-id="4d1b0-135">Haga clic en la regla y, a continuación, en la ventana Propiedades, establezca **prioridad** a un valor entero.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-135">Click the rule, and then in the Properties window, set **Priority** to an integer value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d1b0-136">Las prioridades son relativas y todas las acciones de una regla de una prioridad dada se ejecutarán en orden antes que las acciones de una regla con un valor de prioridad más bajo.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-136">Priorities are relative, and all of the actions of a rule of a given priority will be executed in order before any of the actions of a rule with a lower value for priority.</span></span> <span data-ttu-id="4d1b0-137">El valor predeterminado de una prioridad es cero, pero puede ser un valor positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4d1b0-137">The priority value defaults to zero, but it can be positive or negative.</span></span>