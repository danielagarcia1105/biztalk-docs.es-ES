---
title: Detener | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ca8091d4ff4405704314d72939758c7600a71a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246100"
---
# <a name="halt"></a><span data-ttu-id="83967-102">Detener</span><span class="sxs-lookup"><span data-stu-id="83967-102">Halt</span></span>
<span data-ttu-id="83967-103">Puede usar el **detener** función para detener la ejecución del motor de reglas actual.</span><span class="sxs-lookup"><span data-stu-id="83967-103">You can use the **Halt** function to halt the current rule engine execution.</span></span> <span data-ttu-id="83967-104">El **detener** función toma un parámetro de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="83967-104">The **Halt** function takes one parameter of type `Boolean`.</span></span> <span data-ttu-id="83967-105">Si se especifica el valor del parámetro como `true`, el motor de reglas también borrará la agenda que contiene las reglas candidatas pendientes.</span><span class="sxs-lookup"><span data-stu-id="83967-105">If you specify the value for the parameter as `true`, the rule engine also clears the agenda that contains the pending candidate rules.</span></span>  
  
 <span data-ttu-id="83967-106">El **Policy.Execute** método es básicamente un contenedor alrededor de la **RuleEngine.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="83967-106">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="83967-107">Tiene código parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="83967-107">It has code similar to the following code:</span></span>  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="83967-108">Si usa el **Policy.Execute** método para ejecutar una directiva, el motor de reglas devuelve el control a la **Policy.Execute** método cuando el **detener** se ejecuta la función.</span><span class="sxs-lookup"><span data-stu-id="83967-108">If you use the **Policy.Execute** method to execute a policy, the rule engine returns control to the **Policy.Execute** method when the **Halt** function is executed.</span></span> <span data-ttu-id="83967-109">El **Policy.Execute** método retira los hechos y devuelve el control al llamador.</span><span class="sxs-lookup"><span data-stu-id="83967-109">The **Policy.Execute** method retracts the facts and returns control to the caller.</span></span> <span data-ttu-id="83967-110">Por tanto, la ejecución de directiva detenida no se puede reanudar en este caso.</span><span class="sxs-lookup"><span data-stu-id="83967-110">Therefore, the halted policy execution cannot be resumed in this case.</span></span> <span data-ttu-id="83967-111">Lo mismo sucede cuando se usa el **reglas de llamada** forma para invocar la directiva.</span><span class="sxs-lookup"><span data-stu-id="83967-111">The same thing happens when you use the **Call Rules** shape to invoke the policy.</span></span>  
  
 <span data-ttu-id="83967-112">Sin embargo, si usa el **RuleEngine.Execute** método directamente para ejecutar la directiva, puede reanudar la ejecución de directiva detenida con la siguiente activación de reglas pendiente mediante la llamada a **RuleEngine.Execute** nuevo (siempre y cuando no retirara los objetos necesarios entre las dos llamadas).</span><span class="sxs-lookup"><span data-stu-id="83967-112">However, if you use the **RuleEngine.Execute** method directly to execute the policy, you can resume the halted policy execution with the next pending rule firing by simply calling **RuleEngine.Execute** again (provided you did not retract any objects needed between the two calls).</span></span> <span data-ttu-id="83967-113">El código de ejemplo para reanudar la ejecución de la directiva detenida es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="83967-113">The sample code for resuming the halted policy execution is as follows:</span></span>  
  
```  
//assert facts into working memory of the rule engine instance  
RuleEngine.Assert(facts);   
//execute the policy  
RuleEngine.Execute();   
//policy invokes the Halt method when executing actions.   
//control is returned to here when the Halt method is invoked  
  
//when engine is halted do the following  
//Add your code here  
  
//To resume the halted rule engine execution  
RuleEngine.Execute();  
//retract or remove facts frm the working memory of the rule engine  
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="83967-114">Tenga en cuenta que la **Policy.Execute** método almacena en caché las instancias del motor de reglas para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="83967-114">Note that the **Policy.Execute** method caches the rule engine instances for better performance.</span></span> <span data-ttu-id="83967-115">Cuando se usa el **RuleEngine.Execute** directo del método, el motor de reglas de instancias no se almacenan en caché.</span><span class="sxs-lookup"><span data-stu-id="83967-115">When you use the **RuleEngine.Execute** method directly, the rule engine instances are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83967-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="83967-116">See Also</span></span>  
 [<span data-ttu-id="83967-117">Funciones de Control del motor</span><span class="sxs-lookup"><span data-stu-id="83967-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)