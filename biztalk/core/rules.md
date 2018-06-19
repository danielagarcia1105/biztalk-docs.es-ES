---
title: Reglas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35f398cf98181d17833be79fbe9d282e8515e052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268780"
---
# <a name="rules"></a><span data-ttu-id="c0a7f-102">Reglas</span><span class="sxs-lookup"><span data-stu-id="c0a7f-102">Rules</span></span>
<span data-ttu-id="c0a7f-103">Las reglas de negocios son instrucciones declarativas que rigen el comportamiento de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-103">Business rules are declarative statements that govern the conduct of business processes.</span></span> <span data-ttu-id="c0a7f-104">Una regla consta de una condición y de acciones.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-104">A rule consists of a condition and actions.</span></span> <span data-ttu-id="c0a7f-105">La condición se evalúa, y si se evalúa como **true**, el motor de reglas inicia una o varias acciones.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-105">The condition is evaluated, and if it evaluates to **true**, the rule engine initiates one or more actions.</span></span>  
  
 <span data-ttu-id="c0a7f-106">En el marco de trabajo de reglas de negocios, las reglas se definen con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0a7f-106">Rules in the Business Rules Framework are defined by using the following format:</span></span>  
  
 <span data-ttu-id="c0a7f-107">IF`condition` , A CONTINUACIÓN,`action`</span><span class="sxs-lookup"><span data-stu-id="c0a7f-107">IF`condition` THEN`action`</span></span>  
  
 <span data-ttu-id="c0a7f-108">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0a7f-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="c0a7f-109">SI el importe es inferior o igual a los fondos disponibles</span><span class="sxs-lookup"><span data-stu-id="c0a7f-109">IF amount is less than or equal to available funds</span></span>  
  
 <span data-ttu-id="c0a7f-110">ENTONCES se debe realizar la transacción e imprimir el recibo</span><span class="sxs-lookup"><span data-stu-id="c0a7f-110">THEN conduct transaction and print receipt</span></span>  
  
 <span data-ttu-id="c0a7f-111">Esta regla determina si se realizará una transacción mediante la aplicación de lógica de negocios, en forma de una comparación de dos valores monetarios, a datos o hechos, en forma de un importe de transacción y los fondos disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-111">This rule determines whether a transaction will be conducted by applying business logic, in the form of a comparison of two monetary values, to data or facts, in the form of a transaction amount and available funds.</span></span>  
  
 <span data-ttu-id="c0a7f-112">Puede usar el Compositor de reglas de negocio para crear, modificar, establecer la versión e implementar reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-112">You can use the Business Rule Composer to create, modify, version, and deploy business rules.</span></span> <span data-ttu-id="c0a7f-113">Como alternativa, puede realizar las tareas anteriores mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-113">Alternatively, you can perform the preceding tasks programmatically.</span></span>  
  
## <a name="conditions"></a><span data-ttu-id="c0a7f-114">Condiciones</span><span class="sxs-lookup"><span data-stu-id="c0a7f-114">Conditions</span></span>  
 <span data-ttu-id="c0a7f-115">Una condición es una expresión true o falsa (booleana) que consta de uno o más predicados aplicados a datos.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-115">A condition is a true/false (Boolean) expression that consists of one or more predicates that are applied to facts.</span></span>  
  
 <span data-ttu-id="c0a7f-116">En nuestro ejemplo, el predicado **menor o igual a** se aplica a los hechos **cantidad** y **fondos disponibles**.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-116">In our example, the predicate **less than or equal to** is applied to the facts **amount** and **available funds**.</span></span> <span data-ttu-id="c0a7f-117">Esta condición siempre se evaluará como **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-117">This condition will always evaluate to either **true** or **false**.</span></span>  
  
 <span data-ttu-id="c0a7f-118">Los predicados se pueden combinar con los operadores lógicos **AND**, **o**, y **no** para formar una expresión lógica que posiblemente es bastante grande, pero que se siempre se evalúan como cualquier **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-118">Predicates can be combined with the logical operators **AND**, **OR**, and **NOT** to form a logical expression that is potentially quite large, but will always evaluate to either **true** or **false**.</span></span>  
  
## <a name="actions"></a><span data-ttu-id="c0a7f-119">Acciones</span><span class="sxs-lookup"><span data-stu-id="c0a7f-119">Actions</span></span>  
 <span data-ttu-id="c0a7f-120">Las acciones son las consecuencias funcionales de la evaluación de las condiciones.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-120">Actions are the functional consequences of condition evaluation.</span></span> <span data-ttu-id="c0a7f-121">Si se cumple la condición de una regla, se inicia la acción o las acciones correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-121">If a rule condition is met, a corresponding action or actions are initiated.</span></span>  
  
 <span data-ttu-id="c0a7f-122">En este ejemplo, "realizar transacción" e "imprimir recibo" son las acciones que se ejecutan cuando se cumple la condición (en este caso, "SI el importe es inferior o igual a los fondos disponibles").</span><span class="sxs-lookup"><span data-stu-id="c0a7f-122">In our example, "conduct transaction" and "print receipt" are actions that are carried out when, and only when, the condition (in this case, "IF amount is less than or equal to available funds") is true.</span></span>  
  
 <span data-ttu-id="c0a7f-123">Las acciones se representan en el marco de trabajo de reglas de negocios al invocar métodos o establecer propiedades de objetos, o bien al realizar operaciones set en documentos XML o tablas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-123">Actions are represented in the Business Rules Framework by invoking methods or setting properties on objects, or by performing set operations on XML documents or database tables.</span></span>  
  
## <a name="facts"></a><span data-ttu-id="c0a7f-124">Hechos</span><span class="sxs-lookup"><span data-stu-id="c0a7f-124">Facts</span></span>  
 <span data-ttu-id="c0a7f-125">Los datos son la información para la que se ejecutan las reglas.</span><span class="sxs-lookup"><span data-stu-id="c0a7f-125">Facts are the data upon which rules operate.</span></span> <span data-ttu-id="c0a7f-126">En este ejemplo, los datos son "cantidad" y "fondos disponibles".</span><span class="sxs-lookup"><span data-stu-id="c0a7f-126">In our example, "amount" and "available funds" are facts.</span></span> <span data-ttu-id="c0a7f-127">Para obtener más información, consulte [hechos](../core/facts.md).</span><span class="sxs-lookup"><span data-stu-id="c0a7f-127">For more information, see [Facts](../core/facts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a7f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0a7f-128">See Also</span></span>  
 [<span data-ttu-id="c0a7f-129">Cómo crear directivas y reglas</span><span class="sxs-lookup"><span data-stu-id="c0a7f-129">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)