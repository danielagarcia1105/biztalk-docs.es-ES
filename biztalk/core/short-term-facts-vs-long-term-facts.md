---
title: Frente a hechos a corto plazo Hechos a largo plazo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- facts, short-term
- facts, long-term
- short-term facts
- business rules, facts
- long-term facts
ms.assetid: de020b20-1012-498a-969e-4adc4549918c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed46b71c205ef7db5dc8d918ba0cdae68ebd41d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990013"
---
# <a name="short-term-facts-vs-long-term-facts"></a><span data-ttu-id="70d43-102">Frente a hechos a corto plazo Hechos a largo plazo</span><span class="sxs-lookup"><span data-stu-id="70d43-102">Short-Term Facts vs. Long-Term Facts</span></span>
<span data-ttu-id="70d43-103">Dos tipos de hechos se imponen en la memoria de trabajo del motor de reglas: los hechos a corto plazo y los hechos a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="70d43-103">Two types of facts are asserted into the working memory of the rule engine—short-term facts and long-term facts.</span></span>  
  
## <a name="short-term-facts"></a><span data-ttu-id="70d43-104">Hechos a corto plazo</span><span class="sxs-lookup"><span data-stu-id="70d43-104">Short-Term Facts</span></span>  
 <span data-ttu-id="70d43-105">Un hecho a corto plazo se corresponde específicamente con un ciclo de ejecución sencillo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="70d43-105">A short-term fact is specific to a single execution cycle of the rule engine.</span></span> <span data-ttu-id="70d43-106">Estos hechos se retiran automáticamente de la memoria de trabajo del motor de reglas tras ejecutarse la directiva.</span><span class="sxs-lookup"><span data-stu-id="70d43-106">Short-term facts are retracted automatically from the working memory of the rule engine after the policy executes.</span></span> <span data-ttu-id="70d43-107">Si los hechos cambian entre dos ciclos de ejecución del motor de reglas para una directiva, debe enviarlos al motor de reglas como hechos a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="70d43-107">If your data changes between execution cycles of the rule engine for a policy, you submit the data as a short-term fact to the rule engine.</span></span>  
  
 <span data-ttu-id="70d43-108">Ejemplos de hechos a corto plazo:</span><span class="sxs-lookup"><span data-stu-id="70d43-108">Examples of short-term facts are:</span></span>  
  
-   <span data-ttu-id="70d43-109">Los hechos que envía como parámetros a la **Policy.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="70d43-109">The facts you submit as parameters to the **Policy.Execute** method.</span></span>  
  
-   <span data-ttu-id="70d43-110">Los hechos que envía como parámetros a la **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="70d43-110">The facts you submit as parameters to the **Call Rules** shape.</span></span>  
  
-   <span data-ttu-id="70d43-111">Los hechos que envía desde una acción de una regla mediante la **Assert** función.</span><span class="sxs-lookup"><span data-stu-id="70d43-111">The facts you submit from an action of a rule using the **Assert** function.</span></span>  
  
## <a name="long-term-facts"></a><span data-ttu-id="70d43-112">Hechos a largo plazo</span><span class="sxs-lookup"><span data-stu-id="70d43-112">Long-Term Facts</span></span>  
 <span data-ttu-id="70d43-113">Un hecho a largo plazo se carga en la memoria de trabajo del motor de reglas para su uso por un número arbitrario de ciclos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70d43-113">A long-term fact is loaded into the working memory of the rule engine for use over an arbitrary number of execution cycles.</span></span> <span data-ttu-id="70d43-114">Normalmente, estos hechos son bastante constantes y no cambian de una ejecución a otra de una directiva.</span><span class="sxs-lookup"><span data-stu-id="70d43-114">Typically, long-term facts are slowly changing facts that do not typically change between executions of a policy.</span></span> <span data-ttu-id="70d43-115">Por ejemplo, quizá desee crear una conexión de base de datos una sola vez y, a continuación, ejecutar la directiva varias veces a través de esa misma conexión.</span><span class="sxs-lookup"><span data-stu-id="70d43-115">For example, you may want to create a database connection only once, and execute the policy several times by using the same database connection.</span></span> <span data-ttu-id="70d43-116">La única diferencia real entre los hechos a corto plazo y los hechos a largo plazo se encuentra en la implementación.</span><span class="sxs-lookup"><span data-stu-id="70d43-116">The only real distinction between short-term facts and long-term facts is in implementation.</span></span>  
  
 <span data-ttu-id="70d43-117">Para enviar un hecho como de largo plazo, debe seguir los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="70d43-117">To submit a fact as a long-term fact, you need to perform the following steps:</span></span>  
  
1. <span data-ttu-id="70d43-118">Crear un componente de almacenes de datos de hechos que implementa el **IFactRetriever** interfaz.</span><span class="sxs-lookup"><span data-stu-id="70d43-118">Create a fact retriever component that implements the **IFactRetriever** interface.</span></span> <span data-ttu-id="70d43-119">Cree e imponga el hecho en la memoria de trabajo de la regla engine cuando el **UpdateFacts** método se invoca para la primera vez y actualice el hecho cuando sea necesario en las siguientes invocaciones de la **UpdateFacts**método.</span><span class="sxs-lookup"><span data-stu-id="70d43-119">Create and assert the fact into the working memory of the rule engine when the **UpdateFacts** method is invoked for the first time, and update the fact when necessary on subsequent invocations of the **UpdateFacts** method.</span></span>  
  
2. <span data-ttu-id="70d43-120">Configure la directiva para usar el componente recuperador datos a través del Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="70d43-120">Configure the policy to use the fact retriever component by using the Business Rule Composer.</span></span>  
  
   <span data-ttu-id="70d43-121">Para obtener más información sobre cómo crear un administrador de almacenes y usarlo en una directiva, consulte [cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md).</span><span class="sxs-lookup"><span data-stu-id="70d43-121">For more information about creating a fact retriever and using it in a policy, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d43-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="70d43-122">See Also</span></span>  
 [<span data-ttu-id="70d43-123">Hechos</span><span class="sxs-lookup"><span data-stu-id="70d43-123">Facts</span></span>](../core/facts.md)