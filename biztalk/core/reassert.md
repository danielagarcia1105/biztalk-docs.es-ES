---
title: Volver a imponer | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine]
ms.assetid: 9cd640a2-bfeb-4c7a-b737-1c92cc122a9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22fcc8be7760d85a12cb05c53137177703c0fa73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reassert"></a><span data-ttu-id="9a1e7-102">Reassert</span><span class="sxs-lookup"><span data-stu-id="9a1e7-102">Reassert</span></span>
<span data-ttu-id="9a1e7-103">Para *imponer* significa llamar a la **Assert** función en un objeto que ya está en el motor de la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-103">To *reassert* means to call the **Assert** function on an object that is already in the engine's working memory.</span></span> <span data-ttu-id="9a1e7-104">Un comando reassert es equivalente a emitir un comando retract y, a continuación, un comando assert para el objeto.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-104">A reassert command is equivalent to issuing a retract command for the object, followed by an assert command.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="9a1e7-105">Objetos .NET</span><span class="sxs-lookup"><span data-stu-id="9a1e7-105">.NET Objects</span></span>  
 <span data-ttu-id="9a1e7-106">En primer lugar, se retrae el objeto y se quita cualquier acción de la agenda para las reglas que usan el objeto (en un predicado o una acción).</span><span class="sxs-lookup"><span data-stu-id="9a1e7-106">The object is first retracted and any actions on the agenda for rules that use the object (in a predicate or action) are removed.</span></span> <span data-ttu-id="9a1e7-107">A continuación, el objeto se vuelve a imponer en la memoria de trabajo y se evalúa como cualquier objeto que se haya impuesto recientemente.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-107">The object is then asserted back into working memory and evaluated as any object that is newly asserted.</span></span> <span data-ttu-id="9a1e7-108">Esto significa que se vuelve a evaluar cualquier regla que utilice el objeto en un predicado y que las acciones se agregan a la agenda según corresponda.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-108">This means that any rules that use the object in a predicate are re-evaluated and their actions are added to the agenda as appropriate.</span></span> <span data-ttu-id="9a1e7-109">Cualquier regla evaluada anteriormente a **true** y use sólo el objeto en sus acciones tendrán sus acciones agregarse de nuevo a la agenda.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-109">Any rules that previously evaluated to **true** and only use the object in their actions will have their actions re-added to the agenda.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="9a1e7-110">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="9a1e7-110">TypedXmlDocument</span></span>  
 <span data-ttu-id="9a1e7-111">Cuando una nivel superior **TypedXmlDocument** (**TXD**) se vuelve a imponer, el elemento secundario **TXD**s que se crean cuando el nivel superior **TXD** es inicialmente impone tenga distintos comportamientos según el estado del elemento secundario **TXD**s.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-111">When a top level **TypedXmlDocument** (**TXD**) is reasserted, the child **TXD**s that are created when the top level **TXD** is initially asserted have different behaviors depending on the state of the child **TXD**s.</span></span> <span data-ttu-id="9a1e7-112">En el caso de un elemento secundario nuevo nodo o un nodo secundario que está desfasado, lo que significa que se ha cambiado al menos uno de sus campos en la directiva mediante el uso de una acción de regla, una aserción, o volver a imponer acción se realiza en el nodo secundario.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-112">In the case of a new child node or a child node that is dirty, meaning that at least one of its fields has been changed in the policy by using a rule action, an assert, or reassert action is performed on the child node.</span></span> <span data-ttu-id="9a1e7-113">Cualquier nodo secundario existente no modificado se conservará en la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-113">Any existing child node that is not dirty remains in the working memory.</span></span> <span data-ttu-id="9a1e7-114">El siguiente ejemplo es un escenario simplificado que describe los comportamientos de los nodos secundarios cuando se vuelve a imponer el nodo primario.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-114">The following example is a simplified scenario that describes the behaviors of the child nodes when their parent node is reasserted.</span></span>  
  
 <span data-ttu-id="9a1e7-115">Supongamos que hay tres **TXD**s actualmente en la memoria de trabajo: **P**, **C**1, **C**2, y **C**3.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-115">Assume there are three **TXD**s currently in the working memory: **P**, **C**1, **C**2, and **C**3.</span></span> <span data-ttu-id="9a1e7-116">**P** es el nivel superior **TXD**, el nodo primario; cada niño para el nodo contiene un campo **x**.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-116">**P** is the top level **TXD**, the parent node; each child node contains a field **x**.</span></span>  
  
 <span data-ttu-id="9a1e7-117">**P**</span><span class="sxs-lookup"><span data-stu-id="9a1e7-117">**P**</span></span>  
  
 <span data-ttu-id="9a1e7-118">**C**1 (**C**1. **x** = 1)</span><span class="sxs-lookup"><span data-stu-id="9a1e7-118">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="9a1e7-119">**C**2 (**C**2. **x** = 1)</span><span class="sxs-lookup"><span data-stu-id="9a1e7-119">**C**2 (**C**2.**x** = 1)</span></span>  
  
 <span data-ttu-id="9a1e7-120">**C**3 (**C**3. **x** = 1)</span><span class="sxs-lookup"><span data-stu-id="9a1e7-120">**C**3 (**C**3.**x** = 1)</span></span>  
  
 <span data-ttu-id="9a1e7-121">Además, supongamos que se han realizado las siguientes operaciones como resultado de la acción de una regla:</span><span class="sxs-lookup"><span data-stu-id="9a1e7-121">Next, assume the following operations have been performed as a result of rule action:</span></span>  
  
-   <span data-ttu-id="9a1e7-122">El campo (**x**) valor **C**2 se actualiza.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-122">The field (**x**) value for **C**2 is updated.</span></span>  
  
-   <span data-ttu-id="9a1e7-123">**C**3 se elimina mediante código de usuario.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-123">**C**3 is deleted by using user code.</span></span>  
  
-   <span data-ttu-id="9a1e7-124">Un nodo secundario adicional, **d.**, se agrega a **P** mediante código de usuario.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-124">An additional child node, **D**, is added to **P** by using user code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a1e7-125">El motor de reglas de negocios no marcará como modificados los nodos de los que no tenga conocimiento.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-125">A node will not be marked dirty by the Business Rule Engine from operations, of which the engine is not aware.</span></span> <span data-ttu-id="9a1e7-126">Por ejemplo, agregar, eliminar o modificar un nodo mediante programación en una aplicación externa.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-126">For example, adding, deleting, or modifying a node programmatically in an external application.</span></span>  
  
 <span data-ttu-id="9a1e7-127">La nueva representación de los objetos en la memoria de trabajo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a1e7-127">The new representation of the objects in working memory is as follows.</span></span>  
  
 <span data-ttu-id="9a1e7-128">**P**</span><span class="sxs-lookup"><span data-stu-id="9a1e7-128">**P**</span></span>  
  
 <span data-ttu-id="9a1e7-129">**C**1 (**C**1. **x** = 1)</span><span class="sxs-lookup"><span data-stu-id="9a1e7-129">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="9a1e7-130">**C**2 (**C**2. **x** = *0*)</span><span class="sxs-lookup"><span data-stu-id="9a1e7-130">**C**2 (**C**2.**x** = *0*)</span></span>  
  
 <span data-ttu-id="9a1e7-131">**D**</span><span class="sxs-lookup"><span data-stu-id="9a1e7-131">**D**</span></span>  
  
 <span data-ttu-id="9a1e7-132">Ahora, vuelva a imponer **P**. Los puntos siguientes resumen los comportamientos de los nodos secundarios:</span><span class="sxs-lookup"><span data-stu-id="9a1e7-132">Now, reassert **P**. The following points summarize the behaviors of the child nodes:</span></span>  
  
-   <span data-ttu-id="9a1e7-133">Nodo **C**2 se vuelve a imponer, porque se ha modificado después de su campo que se está actualizando.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-133">Node **C**2 is reasserted, because it has become dirty after its field being updated.</span></span>  
  
-   <span data-ttu-id="9a1e7-134">Nodo **C**3 se retrae de la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-134">Node **C**3 is retracted from the working memory.</span></span>  
  
-   <span data-ttu-id="9a1e7-135">Nodo **d.** se impone en la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-135">Node **D** is asserted into the working memory.</span></span>  
  
-   <span data-ttu-id="9a1e7-136">Nodo **C**1 permanece sin cambios en la memoria de trabajo, porque no se actualizó antes de **P** se volviese a imponer.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-136">Node **C**1 remains unchanged in the working memory, because it was not updated before **P** was reasserted.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="9a1e7-137">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="9a1e7-137">TypedDataTable</span></span>  
 <span data-ttu-id="9a1e7-138">Si **imponer** se emite en una **TypedDataRow**, esa fila se retira y, a continuación, se impone en la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-138">If **Reassert** is issued on a **TypedDataRow**, that row is retracted and then asserted into working memory.</span></span> <span data-ttu-id="9a1e7-139">Si **imponer** se emite en el **TypedDataTable**, todos los asociados **TypedDataRow**se retraen y, a continuación, se imponen.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-139">If **Reassert** is issued on the **TypedDataTable**, all associated **TypedDataRow**s are retracted and then asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="9a1e7-140">DataConnection</span><span class="sxs-lookup"><span data-stu-id="9a1e7-140">DataConnection</span></span>  
 <span data-ttu-id="9a1e7-141">Todos los **TypedDataRow**s recuperados a través de la **DataConnection** se retiran.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-141">All **TypedDataRow**s retrieved through the **DataConnection** are retracted.</span></span> <span data-ttu-id="9a1e7-142">Todos los predicados que utilizan el **DataConnection** se vuelven a evaluar, provocando la **DataConnection** para realizar una nueva consulta para crear la correspondiente **TypedDataRow**s.</span><span class="sxs-lookup"><span data-stu-id="9a1e7-142">All predicates that use the **DataConnection** are then re-evaluated, causing the **DataConnection** to be requeried to create the relevant **TypedDataRow**s.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1e7-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a1e7-143">See Also</span></span>  
 [<span data-ttu-id="9a1e7-144">Funciones de Control del motor</span><span class="sxs-lookup"><span data-stu-id="9a1e7-144">Engine Control Functions</span></span>](../core/engine-control-functions.md)