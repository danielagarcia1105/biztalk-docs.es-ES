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
# <a name="how-to-create-policies-and-rules"></a><span data-ttu-id="725c3-102">Cómo crear directivas y reglas</span><span class="sxs-lookup"><span data-stu-id="725c3-102">How to Create Policies and Rules</span></span>
<span data-ttu-id="725c3-103">Puede crear reglas con condiciones que son agrupaciones lógicas de operadores lógicos (**AND**, **OR**, y **no**) aplicadas a predicados (funciones integrados o definidos por el usuario u operadores) que toman argumentos (referencias de hechos integrados o definidos por el usuario).</span><span class="sxs-lookup"><span data-stu-id="725c3-103">You can create rules with conditions that are logical groupings of logical operators (**AND**, **OR**, and **NOT**) applied to predicates (built-in or user-defined functions or operators) that take arguments (built-in or user-defined fact references).</span></span> <span data-ttu-id="725c3-104">También puede hacer clic **condiciones** o en operadores lógicos y seleccionar un operador lógico o predicado integrado en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="725c3-104">You can also right-click **Conditions** or logical operators and select a logical operator or built-in predicate from the context menu.</span></span>  
  
 <span data-ttu-id="725c3-105">Puede definir acciones (funciones integradas o definidas por el usuario) que se ejecutarán si la condición de regla se evalúa como **true**.</span><span class="sxs-lookup"><span data-stu-id="725c3-105">You can define actions (built-in or user-defined functions) to be executed if the rule condition evaluates to **true**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="725c3-106">Si incluye más de un predicado en una regla, todos los predicados deben aparecer como argumentos para un operador lógico.</span><span class="sxs-lookup"><span data-stu-id="725c3-106">If you include more than one predicate in a rule, all predicates must appear as arguments to a logical operator.</span></span> <span data-ttu-id="725c3-107">(El nivel superior puede ser un miembro .NET único, una columna de base de datos o un campo/atributo XML que sea de tipo booleano.)</span><span class="sxs-lookup"><span data-stu-id="725c3-107">(The top level can be a single .NET member, db column, or XML field/attribute that is of boolean type.)</span></span>  
  
### <a name="to-create-a-policy"></a><span data-ttu-id="725c3-108">Para crear una directiva</span><span class="sxs-lookup"><span data-stu-id="725c3-108">To create a policy</span></span>  
  
1.  <span data-ttu-id="725c3-109">En el panel Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="725c3-109">In the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
     <span data-ttu-id="725c3-110">Una nueva carpeta, **Policy1**, se crea en **directivas**.</span><span class="sxs-lookup"><span data-stu-id="725c3-110">A new folder, **Policy1**, is created under **Policies**.</span></span> <span data-ttu-id="725c3-111">De forma predeterminada, se crea la versión 1 de una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="725c3-111">By default, version 1 of a new policy is created for you.</span></span>  
  
2.  <span data-ttu-id="725c3-112">Haga clic en **Policy1**.</span><span class="sxs-lookup"><span data-stu-id="725c3-112">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="725c3-113">En el panel de la propiedad Nombre, escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="725c3-113">In the Name property pane, type a name.</span></span>  
  
### <a name="to-add-a-rule-to-a-policy-version"></a><span data-ttu-id="725c3-114">Para agregar una regla a una versión de directiva</span><span class="sxs-lookup"><span data-stu-id="725c3-114">To add a rule to a policy version</span></span>  
  
-   <span data-ttu-id="725c3-115">En el panel Explorador de directivas, expanda [**la directiva de**], haga clic en **versión 1.0 (sin guardar)**y, a continuación, seleccione **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="725c3-115">In the Policy Explorer pane, expand [**your policy**], right-click **Version 1.0 (not saved)**, and then select **Add New Rule**.</span></span>  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a><span data-ttu-id="725c3-116">Para agregar un operador lógico a una condición de regla</span><span class="sxs-lookup"><span data-stu-id="725c3-116">To add a logical operator to a rule condition</span></span>  
  
-   <span data-ttu-id="725c3-117">En la ventana de definición de la regla, haga clic en **condiciones**y, a continuación, haga clic en uno de **Agregar operador lógico AND**, **Agregar operador lógico OR**, o **Agregar operador lógico NOT**.</span><span class="sxs-lookup"><span data-stu-id="725c3-117">In the Rule Definition window, right-click **Conditions**, and then click one of **Add Logical AND**, **Add Logical OR**, or **Add Logical NOT**.</span></span>  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a><span data-ttu-id="725c3-118">Para agregar un predicado integrado a una condición de regla o a un operador lógico</span><span class="sxs-lookup"><span data-stu-id="725c3-118">To add a built-in predicate to a rule condition or logical operator</span></span>  
  
1.  <span data-ttu-id="725c3-119">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha y, a continuación, haga clic en el **predicados** carpeta.</span><span class="sxs-lookup"><span data-stu-id="725c3-119">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Predicates** folder.</span></span>  
  
2.  <span data-ttu-id="725c3-120">Expanda una versión publicada de un vocabulario de predicados y haga clic en el predicado que desee.</span><span class="sxs-lookup"><span data-stu-id="725c3-120">Expand a published version of a predicate vocabulary, and click the predicate you want.</span></span>  
  
3.  <span data-ttu-id="725c3-121">Arrastre el predicado en el operador lógico, o bien **condiciones** si la regla contiene sólo un predicado.</span><span class="sxs-lookup"><span data-stu-id="725c3-121">Drag the predicate onto the logical operator, or onto **Conditions** if your rule will contain only one predicate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="725c3-122">También puede agregar un predicado directamente desde un origen de datos, siempre que el elemento de datos actúa como un predicado (se evalúa como **true** o **false**).</span><span class="sxs-lookup"><span data-stu-id="725c3-122">You can also add a predicate directly from a data source, provided that the data element acts as a predicate (evaluates to **true** or **false**).</span></span>  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a><span data-ttu-id="725c3-123">Para agregar una acción integrada a una regla</span><span class="sxs-lookup"><span data-stu-id="725c3-123">To add a built-in action to a rule</span></span>  
  
1.  <span data-ttu-id="725c3-124">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha y, a continuación, haga clic en el **funciones** carpeta.</span><span class="sxs-lookup"><span data-stu-id="725c3-124">In the Facts Explorer window, click the **Vocabularies** tab, and then click the **Functions** folder.</span></span>  
  
2.  <span data-ttu-id="725c3-125">Expanda una versión publicada de un vocabulario de funciones y haga clic en la función que desee.</span><span class="sxs-lookup"><span data-stu-id="725c3-125">Expand a published version of the function vocabulary, and click the function you want.</span></span>  
  
3.  <span data-ttu-id="725c3-126">Arrastre la función en **acciones**.</span><span class="sxs-lookup"><span data-stu-id="725c3-126">Drag the function onto **Actions**.</span></span> <span data-ttu-id="725c3-127">También puede hacer clic **acciones**y seleccione una acción integrada en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="725c3-127">You can also right-click **Actions**, and select a built-in action from the context menu.</span></span>  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a><span data-ttu-id="725c3-128">Para agregar un argumento a una condición o acción</span><span class="sxs-lookup"><span data-stu-id="725c3-128">To add an argument to a condition or action</span></span>  
  
1.  <span data-ttu-id="725c3-129">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha y, a continuación, haga clic en una carpeta de vocabulario.</span><span class="sxs-lookup"><span data-stu-id="725c3-129">In the Facts Explorer window, click the **Vocabularies** tab, and then click a vocabulary folder.</span></span>  
  
2.  <span data-ttu-id="725c3-130">Expanda una versión publicada del vocabulario y haga clic en el término que desee.</span><span class="sxs-lookup"><span data-stu-id="725c3-130">Expand a published version of the vocabulary, and click the term you want.</span></span> <span data-ttu-id="725c3-131">El término debe ser de un tipo esperado por el predicado o la función.</span><span class="sxs-lookup"><span data-stu-id="725c3-131">The term must be of a type expected by the predicate or function.</span></span>  
  
3.  <span data-ttu-id="725c3-132">Arrastre el término hasta un argumento de predicado en una condición o un argumento de función en una acción.</span><span class="sxs-lookup"><span data-stu-id="725c3-132">Drag the term onto a predicate argument in a condition or a function argument in an action.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="725c3-133">También puede agregar un argumento directamente desde un origen de datos o, si se trata de XML, puede especificar el tipo de campo en las propiedades cuando seleccione un campo; naturalmente, esto debe ser compatible con los propios datos, siempre que el elemento de datos sea de un tipo esperado por el predicado o la acción.</span><span class="sxs-lookup"><span data-stu-id="725c3-133">You can also add an argument directly from a data source or in the case of XML you can specify the field type in the properties when selecting a field; this must of course be compatible with the data itself , provided that the data element is of a type expected by the predicate or action.</span></span> <span data-ttu-id="725c3-134">Para agregar un argumento directamente desde un origen de datos, haga clic en la pestaña apropiada en la ventana Hechos, desplácese hasta el elemento que desee y arrástrelo hasta un argumento de predicado o un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="725c3-134">To add an argument directly from a data source, click the appropriate tab in the Facts Explorer window, navigate to the item you want, and drag it onto a predicate argument or function argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="725c3-135">Puede agregar un valor constante a un argumento haciendo clic directamente en el argumento y escribiendo el valor constante que desee.</span><span class="sxs-lookup"><span data-stu-id="725c3-135">You can add a constant value to an argument directly by clicking the argument and entering the constant value you want.</span></span>