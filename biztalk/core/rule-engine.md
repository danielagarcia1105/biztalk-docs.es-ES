---
title: Motor de reglas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RuleEngine object
- Business Rules Engine, ruleset executor
- Business Rules Engine, ruleset translator
- Business Rules Engine, ruleset tracking interceptor
- Business Rules Engine, Business Rules Engine
ms.assetid: c4043a1f-357f-47bc-84e1-5e4bd9f8b5b8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dc2d293697ccbb64851591037440d0371c1346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="rule-engine"></a><span data-ttu-id="76e5d-102">Motor de reglas</span><span class="sxs-lookup"><span data-stu-id="76e5d-102">Rule Engine</span></span>
<span data-ttu-id="76e5d-103">Esta sección describe varios componentes, funcionalidades y operaciones del motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="76e5d-103">This section describes several components, functionalities, and operations of the Business Rule engine.</span></span> <span data-ttu-id="76e5d-104">El motor de reglas proporciona el contexto de ejecución de un conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="76e5d-104">The rule engine provides the execution context for a rule set.</span></span> <span data-ttu-id="76e5d-105">El **RuleEngine** objeto utiliza los siguientes componentes de complementos para la implementación:</span><span class="sxs-lookup"><span data-stu-id="76e5d-105">The **RuleEngine** object uses the following plug–in components for implementation:</span></span>  
  
-   <span data-ttu-id="76e5d-106">**Ejecutor de conjunto de reglas (motor de inferencia)**.</span><span class="sxs-lookup"><span data-stu-id="76e5d-106">**Ruleset executor (inference engine)**.</span></span> <span data-ttu-id="76e5d-107">implementa el algoritmo responsable de la evaluación de condiciones y la ejecución de acciones.</span><span class="sxs-lookup"><span data-stu-id="76e5d-107">Implements the algorithm responsible for rule condition evaluation and action execution.</span></span> <span data-ttu-id="76e5d-108">El ejecutor predeterminado de conjuntos de reglas es un motor de inferencia de encadenamiento inverso basado en una red de discriminación que está diseñado para optimizar las operaciones en memoria.</span><span class="sxs-lookup"><span data-stu-id="76e5d-108">The default rule set executor is a discrimination network-based forward-chaining inference engine designed to optimize in-memory operation.</span></span>  
  
-   <span data-ttu-id="76e5d-109">**Traductor de conjunto de reglas**.</span><span class="sxs-lookup"><span data-stu-id="76e5d-109">**Ruleset translator**.</span></span> <span data-ttu-id="76e5d-110">Toma como entrada un **RuleSet** objeto y genera una representación ejecutable del conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="76e5d-110">Takes as input a **RuleSet** object and produces an executable representation of the rule set.</span></span> <span data-ttu-id="76e5d-111">El traductor en memoria predeterminado crea una red de discriminación compilada a partir de la definición del conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="76e5d-111">The default in-memory translator creates a compiled discrimination network from the rule set definition.</span></span>  
  
-   <span data-ttu-id="76e5d-112">**Interceptor de seguimiento de conjunto de reglas**.</span><span class="sxs-lookup"><span data-stu-id="76e5d-112">**Rule set tracking interceptor**.</span></span> <span data-ttu-id="76e5d-113">Recibe la salida del ejecutor de conjunto de reglas (motor de inferencia) y la reenvía a las herramientas de seguimiento y supervisión de conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="76e5d-113">Receives output from the rule set executor (inference engine) and forwards it to rule set tracking and monitoring tools.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76e5d-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="76e5d-114">In This Section</span></span>  
  
-   [<span data-ttu-id="76e5d-115">Evaluación de condiciones y ejecución de acciones</span><span class="sxs-lookup"><span data-stu-id="76e5d-115">Condition Evaluation and Action Execution</span></span>](../core/condition-evaluation-and-action-execution.md)  
  
-   [<span data-ttu-id="76e5d-116">Agenda y prioridad</span><span class="sxs-lookup"><span data-stu-id="76e5d-116">Agenda and Priority</span></span>](../core/agenda-and-priority.md)  
  
-   [<span data-ttu-id="76e5d-117">Funciones de Control del motor</span><span class="sxs-lookup"><span data-stu-id="76e5d-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)  
  
-   [<span data-ttu-id="76e5d-118">Acceso a datos en el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="76e5d-118">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="76e5d-119">Efectos secundarios de acción de regla</span><span class="sxs-lookup"><span data-stu-id="76e5d-119">Rule Action Side Effects</span></span>](../core/rule-action-side-effects.md)  
  
-   [<span data-ttu-id="76e5d-120">Compatibilidad con herencia de clases en el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="76e5d-120">Support for Class Inheritance in the Business Rule Engine</span></span>](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="76e5d-121">Configuración del motor de reglas y parámetros de ajuste</span><span class="sxs-lookup"><span data-stu-id="76e5d-121">Rule Engine Configuration and Tuning Parameters</span></span>](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [<span data-ttu-id="76e5d-122">Consideraciones sobre el rendimiento cuando se usa el motor de reglas</span><span class="sxs-lookup"><span data-stu-id="76e5d-122">Performance Considerations When Using the Rule Engine</span></span>](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a><span data-ttu-id="76e5d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e5d-123">See Also</span></span>  
 [<span data-ttu-id="76e5d-124">Motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="76e5d-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)