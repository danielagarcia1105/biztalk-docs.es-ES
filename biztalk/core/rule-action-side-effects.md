---
title: Efectos secundarios de acciones de regla | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, side effects
ms.assetid: 1ef65014-9c0a-40d3-b941-2a67c20b54d3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ed890ca8efca6fdd1403c4ec89f4c0c5d32eaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268844"
---
# <a name="rule-action-side-effects"></a><span data-ttu-id="c8a06-102">Efectos secundarios de acciones de reglas</span><span class="sxs-lookup"><span data-stu-id="c8a06-102">Rule Action Side Effects</span></span>
<span data-ttu-id="c8a06-103">Si la ejecución de una acción afecta al estado de un objeto o a un término empleado en las condiciones, se considera que dicha acción tiene un efecto secundario sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="c8a06-103">If the execution of an action affects the state of an object or a term used in conditions, that action is considered to have a side effect on the object.</span></span>  
  
 <span data-ttu-id="c8a06-104">Suponga que tenemos las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="c8a06-104">Assume we have the following rules.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="c8a06-105">Regla 1</span><span class="sxs-lookup"><span data-stu-id="c8a06-105">Rule 1</span></span>  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a><span data-ttu-id="c8a06-106">Regla 2</span><span class="sxs-lookup"><span data-stu-id="c8a06-106">Rule 2</span></span>  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 <span data-ttu-id="c8a06-107">En este caso, **OrderForm.UpdateStatus** se dice que tiene un efecto secundario **OrderForm.Status**.</span><span class="sxs-lookup"><span data-stu-id="c8a06-107">In this case, **OrderForm.UpdateStatus** is said to have a side effect on **OrderForm.Status**.</span></span> <span data-ttu-id="c8a06-108">Esto no significa que **OrderForm.UpdateStatus** tiene efectos secundarios; en su lugar, **OrderForm.Status** potencialmente se ve afectado por una o varias acciones.</span><span class="sxs-lookup"><span data-stu-id="c8a06-108">This does not mean that **OrderForm.UpdateStatus** has side effects; instead, **OrderForm.Status** is potentially affected by one or more actions.</span></span>  
  
 <span data-ttu-id="c8a06-109">De forma predeterminada, el **SideEffects** propiedad para los miembros de clase de .NET es **true**, que impide que el motor de reglas de almacenamiento en caché el miembro con efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c8a06-109">By default, the **SideEffects** property for .NET class members is **true**, which prevents the rule engine from caching the member with side effects.</span></span> <span data-ttu-id="c8a06-110">En nuestro ejemplo, el motor de reglas no almacena en caché **OrderForm.Status** en la memoria de trabajo, sino que obtiene el valor más actualizado de **OrderForm.Status** cada vez que se evalúa la regla 1.</span><span class="sxs-lookup"><span data-stu-id="c8a06-110">In our example, the rule engine does not cache **OrderForm.Status** in the working memory; instead it gets the most up-to-date value of **OrderForm.Status** every time Rule 1 is evaluated.</span></span> <span data-ttu-id="c8a06-111">Si el **SideEffects** propiedad está establecida en **false**, el motor de reglas almacena en caché el valor de la primera vez que se evalúa como **OrderForm.Status**, pero para evaluaciones posteriores (en escenarios de encadenamiento directo), utiliza el valor almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="c8a06-111">If the **SideEffects** property is set to **false**, the rule engine caches the value first time it evaluates **OrderForm.Status**, but for later evaluations (in forward-chaining scenarios), it uses the cached value.</span></span>  
  
 <span data-ttu-id="c8a06-112">Actualmente el Compositor de reglas de negocio no proporciona una manera para que los usuarios modifiquen **SideEffects**, sin embargo, sólo se puede establecer la **SideEffects** propiedad mediante programación con el marco de trabajo de reglas de negocios .</span><span class="sxs-lookup"><span data-stu-id="c8a06-112">Currently the Business Rule Composer does not provide a way for users to modify **SideEffects**, however, you can only set the **SideEffects** property programmatically through the Business Rules Framework.</span></span> <span data-ttu-id="c8a06-113">Se realiza esto en el enlace, mediante el [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx) clase para especificar métodos de objetos, propiedades y campos que se usan en condiciones de regla y las acciones.</span><span class="sxs-lookup"><span data-stu-id="c8a06-113">You set do this at binding, using the [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx) class to specify object methods, properties, and fields used in rule conditions and actions.</span></span> <span data-ttu-id="c8a06-114">**ClassMemberBinding** tiene una propiedad, [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects), que contiene un valor booleano que indica si obtiene acceso al miembro cambia su valor.</span><span class="sxs-lookup"><span data-stu-id="c8a06-114">**ClassMemberBinding** has a property, [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects), which contains a Boolean value indicating whether accessing the member changes its value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a06-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8a06-115">See Also</span></span>  
 [<span data-ttu-id="c8a06-116">Motor de reglas</span><span class="sxs-lookup"><span data-stu-id="c8a06-116">Rule Engine</span></span>](../core/rule-engine.md)