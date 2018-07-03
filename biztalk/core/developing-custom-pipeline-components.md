---
title: Desarrollar componentes de canalización personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom]
- pipeline components [custom], about pipeline components
- pipeline components [custom], creating
- customizing, pipeline components
- pipeline interfaces
- IDisassemblerComponent
- pipeline interfaces, about pipeline interfaces
- creating, pipeline components [custom]
- IAssemblerComponent
- IComponent
- pipeline components [custom], customizing
- pipeline interfaces, interface types
- pipeline components [custom], interfaces
- pipeline components [custom], component types
ms.assetid: cce61e0d-f1e3-4ec2-b38c-7c6eaf83ac10
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74828d31b55a4b50bdb18a537fbf7bb293445545
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008973"
---
# <a name="developing-custom-pipeline-components"></a><span data-ttu-id="1e35d-102">Desarrollar componentes de canalización personalizado</span><span class="sxs-lookup"><span data-stu-id="1e35d-102">Developing Custom Pipeline Components</span></span>
<span data-ttu-id="1e35d-103">En esta sección, se describe cómo desarrollar un componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="1e35d-103">This section describes how to develop a pipeline component.</span></span> <span data-ttu-id="1e35d-104">Puede crear tres tipos de componentes de canalización: general, ensamblado y de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="1e35d-104">You can create three types of pipeline components: general, assembling, and disassembling.</span></span> <span data-ttu-id="1e35d-105">Todos ellos pueden, de forma adicional, implementar la funcionalidad de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1e35d-105">Each of the three types can additionally implement probing functionality.</span></span> <span data-ttu-id="1e35d-106">Cada tipo de componente de canalización tiene una interfaz asociada que se debe implementar para que el componente en el motor de mensajería de BizTalk; las interfaces de canalización que distinguen los tipos de componentes son **IComponent**, **IAssemblerComponent**, y **IDisassemblerComponent**.</span><span class="sxs-lookup"><span data-stu-id="1e35d-106">Each type of pipeline component has an associated interface that must be implemented for the component to be plugged into the BizTalk Messaging Engine; the pipeline interfaces that distinguish the types of components are **IComponent**, **IAssemblerComponent**, and **IDisassemblerComponent**.</span></span> <span data-ttu-id="1e35d-107">Para buscar componentes, debe implementar la **IProbeMessage** interfaz.</span><span class="sxs-lookup"><span data-stu-id="1e35d-107">For probing components, you must implement the **IProbeMessage** interface.</span></span>  
  
 <span data-ttu-id="1e35d-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contiene un componente de canalización de ejemplo al que puede hacer referencia al crear su propio componente.</span><span class="sxs-lookup"><span data-stu-id="1e35d-108">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a sample pipeline component that you can reference when creating your own component.</span></span> <span data-ttu-id="1e35d-109">El componente de ejemplo demuestra cómo anexar datos al final de un mensaje y agregarlos al comienzo de éste.</span><span class="sxs-lookup"><span data-stu-id="1e35d-109">The sample component demonstrates how to append data to the end of a message and add data at the beginning of the message.</span></span> <span data-ttu-id="1e35d-110">Para obtener más información sobre el componente de canalización de ejemplo, vea [CustomComponent (ejemplo de BizTalk Server)](../core/customcomponent-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="1e35d-110">For more information about the sample pipeline component, see [CustomComponent (BizTalk Server Sample)](../core/customcomponent-biztalk-server-sample.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1e35d-111">Si se hacen referencia a un componente de canalización personalizado desde una canalización en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede producirse un error de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1e35d-111">If you reference a custom pipeline component from a pipeline in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], a compile-time error may occur.</span></span> <span data-ttu-id="1e35d-112">Para corregir el error, cierre el Diseñador de canalizaciones y vuelva a abrirlo antes de efectuar la compilación.</span><span class="sxs-lookup"><span data-stu-id="1e35d-112">To correct the error, close Pipeline Designer and reopen it before compiling.</span></span> <span data-ttu-id="1e35d-113">Como alternativa, puede quitar el componente y, a continuación, agregarlo.</span><span class="sxs-lookup"><span data-stu-id="1e35d-113">Alternatively, you can remove the component, and then add it.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="1e35d-114">Al actualizar a BizTalk Server, asegúrese de que las variables de cadena de los componentes de canalización personalizados existentes no contienen ningún carácter de nueva línea como '\n'.</span><span class="sxs-lookup"><span data-stu-id="1e35d-114">When upgrading to BizTalk Server, ensure that any string variables in your existing custom pipeline components do not contain any newline characters such as ‘\n’.</span></span> <span data-ttu-id="1e35d-115">De lo contrario, se producirá el error “nueva línea en constante” al compilar este componente en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e35d-115">Otherwise, a “newline in constant” error will occur when compiling this component in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e35d-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1e35d-116">In This Section</span></span>  
  
-   [<span data-ttu-id="1e35d-117">Uso de interfaces de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="1e35d-117">Using Pipeline Interfaces</span></span>](../core/using-pipeline-interfaces.md)  
  
-   [<span data-ttu-id="1e35d-118">Desarrollo de un componente general de canalización</span><span class="sxs-lookup"><span data-stu-id="1e35d-118">Developing a General Pipeline Component</span></span>](../core/developing-a-general-pipeline-component.md)  
  
-   [<span data-ttu-id="1e35d-119">Desarrollo de un componente de canalización de ensamblado</span><span class="sxs-lookup"><span data-stu-id="1e35d-119">Developing an Assembling Pipeline Component</span></span>](../core/developing-an-assembling-pipeline-component.md)  
  
-   [<span data-ttu-id="1e35d-120">Desarrollo de un componente de canalización de desensamblado</span><span class="sxs-lookup"><span data-stu-id="1e35d-120">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)  
  
-   [<span data-ttu-id="1e35d-121">Desarrollo de un componente de canalización de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1e35d-121">Developing a Probing Pipeline Component</span></span>](../core/developing-a-probing-pipeline-component.md)  
  
-   [<span data-ttu-id="1e35d-122">Implementación del método Seek en un componente de canalización de streaming administrado</span><span class="sxs-lookup"><span data-stu-id="1e35d-122">Implementing a Seek Method in a Managed Streaming Pipeline Component</span></span>](../core/implementing-a-seek-method-in-a-managed-streaming-pipeline-component.md)  
  
-   [<span data-ttu-id="1e35d-123">Uso de los motores de análisis y serialización</span><span class="sxs-lookup"><span data-stu-id="1e35d-123">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)  
  
-   [<span data-ttu-id="1e35d-124">Notificación de errores de los componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="1e35d-124">Reporting Errors from Pipeline Components</span></span>](../core/reporting-errors-from-pipeline-components.md)  
  
-   [<span data-ttu-id="1e35d-125">Implementación de componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="1e35d-125">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)  
  
-   [<span data-ttu-id="1e35d-126">Depuración de canalizaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="1e35d-126">Debugging Custom Pipelines</span></span>](../core/debugging-custom-pipelines.md)