---
title: Cómo agregar parámetros a orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, parameters
ms.assetid: 35c731ed-6327-4de7-8d2e-4d14024bda77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8328a97631efb2b8454e0a2679b257d35402cf4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-parameters-to-orchestrations"></a><span data-ttu-id="7fe57-102">Cómo agregar parámetros a orquestaciones</span><span class="sxs-lookup"><span data-stu-id="7fe57-102">How to Add Parameters to Orchestrations</span></span>
<span data-ttu-id="7fe57-103">Puede especificar qué parámetros debería tomar la orquestación en la ventana Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="7fe57-103">You can specify what parameters your orchestration should take in the Orchestration View window.</span></span> <span data-ttu-id="7fe57-104">Una orquestación puede tomar los siguientes elementos como parámetros:</span><span class="sxs-lookup"><span data-stu-id="7fe57-104">An orchestration can take the following items as parameters:</span></span>  
  
-   <span data-ttu-id="7fe57-105">Mensajes</span><span class="sxs-lookup"><span data-stu-id="7fe57-105">Messages</span></span>  
  
-   <span data-ttu-id="7fe57-106">Variables (objetos incluidos)</span><span class="sxs-lookup"><span data-stu-id="7fe57-106">Variables (including objects)</span></span>  
  
-   <span data-ttu-id="7fe57-107">Conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="7fe57-107">Correlation sets</span></span>  
  
-   <span data-ttu-id="7fe57-108">Vínculos de rol</span><span class="sxs-lookup"><span data-stu-id="7fe57-108">Role links</span></span>  
  
-   <span data-ttu-id="7fe57-109">Puertos</span><span class="sxs-lookup"><span data-stu-id="7fe57-109">Ports</span></span>  
  
 <span data-ttu-id="7fe57-110">Los parámetros se pueden pasar entre orquestaciones como parámetros de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="7fe57-110">Parameters can be passed between orchestrations as in parameters or out parameters.</span></span> <span data-ttu-id="7fe57-111">Los parámetros de entrada se pueden pasar por valor o por referencia.</span><span class="sxs-lookup"><span data-stu-id="7fe57-111">In parameters can be passed by value or by reference.</span></span> <span data-ttu-id="7fe57-112">En cambio, los parámetros de salida solo se pueden pasar por referencia.</span><span class="sxs-lookup"><span data-stu-id="7fe57-112">Out parameters can only be passed by reference.</span></span> <span data-ttu-id="7fe57-113">Los parámetros pueden incluir variables, mensajes, conjuntos de correlaciones, vínculos de rol y puertos.</span><span class="sxs-lookup"><span data-stu-id="7fe57-113">Parameters can include variables, messages, correlation sets, role links, and ports.</span></span>  
  
### <a name="to-set-orchestration-parameters"></a><span data-ttu-id="7fe57-114">Para establecer parámetros de orquestación</span><span class="sxs-lookup"><span data-stu-id="7fe57-114">To set orchestration parameters</span></span>  
  
1.  <span data-ttu-id="7fe57-115">En la ventana Vista orquestación, use la **parámetros de orquestación** carpeta para agregar las variables, mensajes y puertos.</span><span class="sxs-lookup"><span data-stu-id="7fe57-115">In the Orchestration View window, use the **Orchestration Parameters** folder to add variables, messages, and ports.</span></span>  
  
2.  <span data-ttu-id="7fe57-116">Para cada elemento agregado a la **parámetros de orquestación** carpeta, utilice la ventana Propiedades para especificar el **dirección** propiedad:</span><span class="sxs-lookup"><span data-stu-id="7fe57-116">For each item added to the **Orchestration Parameters** folder, use the Properties window to specify the **Direction** property:</span></span>  
  
    -   <span data-ttu-id="7fe57-117">En, se pasa un parámetro por valor.</span><span class="sxs-lookup"><span data-stu-id="7fe57-117">In—A parameter passed in by value.</span></span>  
  
    -   <span data-ttu-id="7fe57-118">Ref, se pasa un parámetro por referencia.</span><span class="sxs-lookup"><span data-stu-id="7fe57-118">Ref—A parameter passed in by reference.</span></span>  
  
    -   <span data-ttu-id="7fe57-119">Salida: un parámetro se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="7fe57-119">Out—A parameter passed out by reference.</span></span>  
  
### <a name="to-add-a-parameter-to-an-orchestration"></a><span data-ttu-id="7fe57-120">Para agregar un parámetro a una orquestación</span><span class="sxs-lookup"><span data-stu-id="7fe57-120">To add a parameter to an orchestration</span></span>  
  
1.  <span data-ttu-id="7fe57-121">En la ventana Vista orquestación, haga clic en el **parámetros de orquestación** carpeta y, a continuación, haga clic en el tipo de parámetro que desee.</span><span class="sxs-lookup"><span data-stu-id="7fe57-121">In the Orchestration View window, right-click the **Orchestration Parameters** folder and then click the kind of parameter you want.</span></span>  
  
2.  <span data-ttu-id="7fe57-122">En el caso de puertos y vínculos de rol configurados, use el Asistente para configurar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="7fe57-122">For configured ports and role links, use the wizard to configure the parameter.</span></span>  
  
     <span data-ttu-id="7fe57-123">: "O":</span><span class="sxs-lookup"><span data-stu-id="7fe57-123">—Or—</span></span>  
  
     <span data-ttu-id="7fe57-124">Para otros tipos de parámetros, use la página de propiedades para configurar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="7fe57-124">For other parameter types, use the properties page to configure the parameter.</span></span>  
  
 <span data-ttu-id="7fe57-125">**Tipos de parámetros**</span><span class="sxs-lookup"><span data-stu-id="7fe57-125">**Parameter types**</span></span>  
  
 <span data-ttu-id="7fe57-126">Los parámetros se pueden pasar por valor, como parámetros de referencia y como parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="7fe57-126">Parameters can be passed by value, as reference parameters, and as out parameters.</span></span> <span data-ttu-id="7fe57-127">Cuando se pasa un parámetro por valor a una orquestación, se realiza una copia de los datos y la orquestación la usa.</span><span class="sxs-lookup"><span data-stu-id="7fe57-127">When a parameter is passed by value to an orchestration, a copy of the data is made and used by the orchestration.</span></span>  
  
 <span data-ttu-id="7fe57-128">Cuando se usa un parámetro de referencia, no se realiza ninguna copia.</span><span class="sxs-lookup"><span data-stu-id="7fe57-128">When you use a reference parameter, no copy is made.</span></span> <span data-ttu-id="7fe57-129">El programa que llama y la orquestación comparten la ubicación de la memoria que contiene los datos y la orquestación puede modificar este contenido.</span><span class="sxs-lookup"><span data-stu-id="7fe57-129">The memory location that contains the data is shared between the calling program and the orchestration, and the contents of this memory location can be modified by the orchestration.</span></span> <span data-ttu-id="7fe57-130">Esta modificación implica que el valor del parámetro se cambia no solo en la orquestación sino también en el programa que llama.</span><span class="sxs-lookup"><span data-stu-id="7fe57-130">Such a modification means that the value of the parameter is changed not only in the orchestration, but also in the calling program.</span></span>  
  
 <span data-ttu-id="7fe57-131">Un parámetro de salida es similar a un parámetro de referencia pero la orquestación no puede asumir que contiene datos válidos cuando lo pasa; en su lugar, el programa que llama espera que la orquestación asigne un valor a este parámetro.</span><span class="sxs-lookup"><span data-stu-id="7fe57-131">An out parameter is similar to a reference parameter, but the orchestration cannot assume that it contains valid data when passed in; rather, the calling program expects the orchestration to assign a value to this parameter.</span></span>  
  
 <span data-ttu-id="7fe57-132">**Reglas de los parámetros de orquestación**</span><span class="sxs-lookup"><span data-stu-id="7fe57-132">**Rules for orchestration parameters**</span></span>  
  
-   <span data-ttu-id="7fe57-133">solo puede pasar mensajes y variables (objetos incluidos) como parámetros de salida o de referencia.</span><span class="sxs-lookup"><span data-stu-id="7fe57-133">You can pass only messages and variables (including objects) as out or reference parameters.</span></span>  
  
-   <span data-ttu-id="7fe57-134">No se puede eliminar ni hacer referencia a parámetros a una orquestación en un **Iniciar orquestación** forma.</span><span class="sxs-lookup"><span data-stu-id="7fe57-134">You cannot pass out or reference parameters to an orchestration in a **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="7fe57-135">Los parámetros de entrada, incluidos los vínculos de rol y los puertos dinámicos, deben estar asignados de forma definitiva antes de que se puedan pasar a una orquestación.</span><span class="sxs-lookup"><span data-stu-id="7fe57-135">In parameters, including any role links and dynamic ports, must be definitely assigned before being passed to an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe57-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fe57-136">See Also</span></span>  
 <span data-ttu-id="7fe57-137">[Formas de orquestación](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="7fe57-137">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="7fe57-138">[Cómo agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="7fe57-138">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="7fe57-139">Cómo usar el cuadro de diálogo de tipo de artefacto Select</span><span class="sxs-lookup"><span data-stu-id="7fe57-139">How to Use the Select Artifact Type Dialog Box</span></span>](../core/how-to-use-the-select-artifact-type-dialog-box.md)