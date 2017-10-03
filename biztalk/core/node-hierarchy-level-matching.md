---
title: "Coincidencia del nivel jerárquico de nodos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Field nodes
- BizTalk Mapper, processing
- Record node
- BizTalk Mapper, compiler directives
- destination schemas, matching nodes
- source schemas, matching nodes
- maps, links
- Target Links property
- BizTalk Mapper, links
- compiler directives, matching schema nodes
- compiler directives, flattening source hierarchies
- maps, processing
ms.assetid: 5ba1ac77-0e70-4c58-9b8c-1b379dbbb3bd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2d0c363abfefb9e3d0eb8abfb332c59539bb67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="node-hierarchy-level-matching"></a><span data-ttu-id="c9c9c-102">Coincidencia del nivel jerárquico de nodos</span><span class="sxs-lookup"><span data-stu-id="c9c9c-102">Node-Hierarchy Level Matching</span></span>
<span data-ttu-id="c9c9c-103">El Asignador de BizTalk le permite configurar una propiedad de vínculo para controlar cómo el compilador hace coincidir las jerarquías de nodos entre los esquemas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-103">BizTalk Mapper enables you to configure a link property to control how the compiler matches node hierarchies between the source and destination schemas.</span></span> <span data-ttu-id="c9c9c-104">Cuando crea un vínculo desde un campo del esquema de origen hacia un campo del esquema de destino, el Asignador de BizTalk agrega automáticamente vínculos de compilador.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-104">When you create a link from a field in the source schema to a field in the destination schema, BizTalk Mapper automatically adds compiler links.</span></span> <span data-ttu-id="c9c9c-105">Estos vínculos de compilador dependen de la coincidencia que seleccione.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-105">These compiler links depend on the matching you select.</span></span>  
  
 <span data-ttu-id="c9c9c-106">Cuando se selecciona un vínculo en la página de cuadrícula mostrada, una de las propiedades se muestra en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades es el **vínculos de destino** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-106">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Target Links** property.</span></span> <span data-ttu-id="c9c9c-107">Puede elegir entre alguno de los siguientes valores posibles para cada vínculo de la asignación:</span><span class="sxs-lookup"><span data-stu-id="c9c9c-107">You can choose among the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="c9c9c-108">**Vínculos sin formato.**</span><span class="sxs-lookup"><span data-stu-id="c9c9c-108">**Flatten links.**</span></span> <span data-ttu-id="c9c9c-109">Utilice este valor para quitar el formato de todas las jerarquías de origen del registro primario del nodo de esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-109">Use this value to flatten all source hierarchies to the parent record in the destination schema node.</span></span>  
  
-   <span data-ttu-id="c9c9c-110">**Coincidir vínculos de arriba hacia abajo.**</span><span class="sxs-lookup"><span data-stu-id="c9c9c-110">**Match links top down.**</span></span> <span data-ttu-id="c9c9c-111">Utilice este valor para hacer coincidir los niveles de nodos de la parte alta a la parte baja de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-111">Use this value to match node levels from the top of the schemas to the bottom of the schemas.</span></span>  
  
-   <span data-ttu-id="c9c9c-112">**Coincidir vínculos de abajo arriba.**</span><span class="sxs-lookup"><span data-stu-id="c9c9c-112">**Match links bottom up.**</span></span> <span data-ttu-id="c9c9c-113">Utilice este valor para hacer coincidir los niveles de nodos de la parte baja a la parte alta de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-113">Use this value to match node levels from the bottom of the schemas to the top of the schemas.</span></span>  
  
## <a name="flatten-links"></a><span data-ttu-id="c9c9c-114">Vínculos sin formato</span><span class="sxs-lookup"><span data-stu-id="c9c9c-114">Flatten Links</span></span>  
 <span data-ttu-id="c9c9c-115">En este modo, se quita el formato de todas las jerarquías de origen del registro primario del nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-115">In this mode, all the source hierarchies are flattened to the parent record of the destination node.</span></span> <span data-ttu-id="c9c9c-116">En el primer caso, el esquema de origen es más complejo que el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-116">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="c9c9c-117">En el segundo caso, el esquema de destino es más complejo.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-117">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
<span data-ttu-id="c9c9c-118">Vínculos sin formato</span><span class="sxs-lookup"><span data-stu-id="c9c9c-118">Flatten Links</span></span>  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
<span data-ttu-id="c9c9c-119">Vínculos sin formato, segundo caso</span><span class="sxs-lookup"><span data-stu-id="c9c9c-119">Flatten Links, Second Case</span></span>  
  
## <a name="match-links-top-down"></a><span data-ttu-id="c9c9c-120">Coincidir vínculos de arriba abajo</span><span class="sxs-lookup"><span data-stu-id="c9c9c-120">Match Links Top-Down</span></span>  
 <span data-ttu-id="c9c9c-121">Este modo hace coincidir nivel a nivel en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-121">This mode matches level to level from the top down.</span></span> <span data-ttu-id="c9c9c-122">En el primer caso, el esquema de origen es más complejo que el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-122">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="c9c9c-123">En el segundo caso, el esquema de destino es más complejo.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-123">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
<span data-ttu-id="c9c9c-124">Coincidencia de arriba abajo</span><span class="sxs-lookup"><span data-stu-id="c9c9c-124">Top-Down Matching</span></span>  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
<span data-ttu-id="c9c9c-125">Coincidencia de arriba abajo, segundo caso</span><span class="sxs-lookup"><span data-stu-id="c9c9c-125">Top-Down Matching, Second Case</span></span>  
  
## <a name="match-links-bottom-up"></a><span data-ttu-id="c9c9c-126">Coincidir vínculos de abajo arriba</span><span class="sxs-lookup"><span data-stu-id="c9c9c-126">Match Links Bottom-Up</span></span>  
 <span data-ttu-id="c9c9c-127">Este modo hace coincidir nivel a nivel en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-127">This mode matches level to level from the bottom up.</span></span> <span data-ttu-id="c9c9c-128">En el primer caso, el esquema de origen es más complejo que el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-128">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="c9c9c-129">En el segundo caso, el esquema de destino es más complejo.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-129">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
<span data-ttu-id="c9c9c-130">Coincidencia de abajo arriba</span><span class="sxs-lookup"><span data-stu-id="c9c9c-130">Bottom-Up Matching</span></span>  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
<span data-ttu-id="c9c9c-131">Coincidencia de abajo arriba, segundo caso</span><span class="sxs-lookup"><span data-stu-id="c9c9c-131">Bottom-Up Matching, Second Case</span></span>  
  
## <a name="how-biztalk-mapper-processes-link-types"></a><span data-ttu-id="c9c9c-132">Cómo procesa los tipos de vínculos el Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c9c9c-132">How BizTalk Mapper Processes Link Types</span></span>  
 <span data-ttu-id="c9c9c-133">Dado que puede establecer el **vínculos de destino** propiedad a valores distintos para vínculos diferentes, el asignador de BizTalk necesita una manera de resolver las diversas configuraciones cuando puedan entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-133">Because you can set the **Target Links** property to different values for different links, BizTalk Mapper needs a way to resolve the different settings when they may conflict.</span></span>  
  
 <span data-ttu-id="c9c9c-134">Por ejemplo, si usa una directiva de compilador sin formato, una directiva de compilador de arriba a abajo y una directiva de compilador de abajo arriba para vínculos de **campo** nodos **campo** nodos en el esquema de destino y estos nodos comparten la misma actividad primaria **registro** nodo, el asignador de BizTalk omite las directivas de compilador de arriba a abajo y de abajo arriba en conflicto y trata todos los vínculos como si estuvieran establecidos para la directiva de compilador sin formato.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-134">For example, if you use a flatten compiler directive, a top-down compiler directive, and a bottom-up compiler directive for links from **Field** nodes to **Field** nodes in the destination schema, and these nodes share the same parent **Record** node, BizTalk Mapper ignores the conflicting top-down and bottom-up compiler directives and treats all the links as if they were set to the flatten compiler directive.</span></span>  
  
 <span data-ttu-id="c9c9c-135">En la tabla siguiente se muestra cómo el asignador de BizTalk trata los vínculos a **campo** nodos en el mismo **registro** nodo del esquema de destino, en función de la configuración de la **vínculos de destino** propiedad para los vínculos dentro de la misma **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-135">The following table shows how BizTalk Mapper treats links to **Field** nodes in the same **Record** node in the destination schema, based on the settings for the **Target Links** property for the links within the same **Record** node.</span></span>  
  
|<span data-ttu-id="c9c9c-136">Sin formato</span><span class="sxs-lookup"><span data-stu-id="c9c9c-136">Flatten</span></span>|<span data-ttu-id="c9c9c-137">De arriba abajo</span><span class="sxs-lookup"><span data-stu-id="c9c9c-137">Top-down</span></span>|<span data-ttu-id="c9c9c-138">De abajo arriba</span><span class="sxs-lookup"><span data-stu-id="c9c9c-138">Bottom-up</span></span>|<span data-ttu-id="c9c9c-139">Resultado</span><span class="sxs-lookup"><span data-stu-id="c9c9c-139">Result</span></span>|  
|-------------|---------------|----------------|------------|  
|<span data-ttu-id="c9c9c-140">0 o más</span><span class="sxs-lookup"><span data-stu-id="c9c9c-140">0 or more</span></span>|<span data-ttu-id="c9c9c-141">1 o más</span><span class="sxs-lookup"><span data-stu-id="c9c9c-141">1 or more</span></span>|<span data-ttu-id="c9c9c-142">1 o más</span><span class="sxs-lookup"><span data-stu-id="c9c9c-142">1 or more</span></span>|<span data-ttu-id="c9c9c-143">El Asignador de BizTalk trata todos los vínculos como si estuvieran establecidos para la directiva de compilador sin formato.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-143">BizTalk Mapper treats all the links as if they were set to the flatten compiler directive.</span></span>|  
|<span data-ttu-id="c9c9c-144">1 o más</span><span class="sxs-lookup"><span data-stu-id="c9c9c-144">1 or more</span></span>|<span data-ttu-id="c9c9c-145">1 o más</span><span class="sxs-lookup"><span data-stu-id="c9c9c-145">1 or more</span></span>|<span data-ttu-id="c9c9c-146">0</span><span class="sxs-lookup"><span data-stu-id="c9c9c-146">0</span></span>|<span data-ttu-id="c9c9c-147">El Asignador de BizTalk trata todos los vínculos como si estuvieran establecidos para una directiva de compilador de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-147">BizTalk Mapper treats all the links as if they were set to the top-down compiler directive.</span></span>|  
|<span data-ttu-id="c9c9c-148">1 o más</span><span class="sxs-lookup"><span data-stu-id="c9c9c-148">1 or more</span></span>|<span data-ttu-id="c9c9c-149">0</span><span class="sxs-lookup"><span data-stu-id="c9c9c-149">0</span></span>|<span data-ttu-id="c9c9c-150">1 o más</span><span class="sxs-lookup"><span data-stu-id="c9c9c-150">1 or more</span></span>|<span data-ttu-id="c9c9c-151">El Asignador de BizTalk trata todos los vínculos como si estuvieran establecidos para una directiva de compilador de abajo arriba.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-151">BizTalk Mapper treats all the links as if they were set to the bottom-up compiler directive.</span></span>|  
  
 <span data-ttu-id="c9c9c-152">Las directivas de compilador de arriba abajo y de abajo arriba tienen prioridad sobre la directiva de compilador sin formato, pero se cancelan entre sí cuando ambas están presentes.</span><span class="sxs-lookup"><span data-stu-id="c9c9c-152">The top-down and bottom-up compiler directives take precedence over the flatten compiler directive, but cancel each other out when both are present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c9c-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9c9c-153">See Also</span></span>  
 <span data-ttu-id="c9c9c-154">[Functoid de copia masiva](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c9c9c-154">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="c9c9c-155">[Cómo establecer el valor de compilador de vínculos de origen](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="c9c9c-155">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="c9c9c-156">Compilar asignaciones</span><span class="sxs-lookup"><span data-stu-id="c9c9c-156">Compiling Maps</span></span>](../core/compiling-maps.md)