---
title: Consideraciones al crear proyectos de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0302d2329f848352f55d15f0c6e21bbdf72b0ca
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005957"
---
# <a name="considerations-when-creating-biztalk-projects"></a><span data-ttu-id="c915a-102">Consideraciones acerca de la creación de proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c915a-102">Considerations When Creating BizTalk Projects</span></span>
<span data-ttu-id="c915a-103">Esta sección proporciona información que debe tener en cuenta al crear BizTalk proyectos utilizando [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c915a-103">This section provides information that you should take into consideration when creating BizTalk projects using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a><span data-ttu-id="c915a-104">Evitar los errores de compilación que causan los proyectos demasiado grandes</span><span class="sxs-lookup"><span data-stu-id="c915a-104">Avoid compilation errors caused by projects that are too large</span></span>  
 <span data-ttu-id="c915a-105">El compilador de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no compila correctamente un proyecto si el resultado es un ensamblado de más de 75 megabytes.</span><span class="sxs-lookup"><span data-stu-id="c915a-105">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler will not successfully compile a project if it would result in an assembly larger than 75 megabytes.</span></span> <span data-ttu-id="c915a-106">Cuando el compilador alcanza una restricción de tamaño emite un error grave CS0013 "Error inesperado al escribir metadatos en el archivo \<filename\>" y se interrumpirá.</span><span class="sxs-lookup"><span data-stu-id="c915a-106">When the compiler reaches a size constraint it will emit fatal error CS0013 "Unexpected error writing metadata to file \<filename\>" and halt.</span></span>  
  
 <span data-ttu-id="c915a-107">Para evitar este problema, se recomienda que los proyectos no excedan los 10 megabytes a menos que sea absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="c915a-107">To avoid this problem, we recommend that projects not exceed 10 megabytes unless absolutely necessary.</span></span> <span data-ttu-id="c915a-108">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="c915a-108">Why?</span></span>  
  
-   <span data-ttu-id="c915a-109">Los proyectos más pequeños suelen ser más fáciles de implementar porque hay menos pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="c915a-109">Smaller projects are potentially simpler to deploy because there are fewer deployment steps.</span></span> <span data-ttu-id="c915a-110">Y con los proyectos más pequeños, es más probable que los pasos estén más relacionados (por ejemplo, administración de descuentos de socios comerciales o administración de sugerencias).</span><span class="sxs-lookup"><span data-stu-id="c915a-110">And with smaller projects the steps are more likely to be closely related -- managing trading partner discounts or handling RFPs.</span></span>  
  
-   <span data-ttu-id="c915a-111">Es más fácil aislar errores, problemas de implementación y solucionar otras cuestiones cuando se trabaja con proyectos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="c915a-111">It is easier to isolate bugs, deployment issues, and other problems when using smaller projects.</span></span> <span data-ttu-id="c915a-112">Encontrar un error en un proyecto con 140 esquemas y muchas asignaciones y secuencias de comandos personalizados será mucho más difícil que encontrar un error en un proyecto con solo 10 esquemas y algunas asignaciones y secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="c915a-112">Finding a bug in a project with 140 schemas and many custom maps and scripts will be more difficult than finding one in a project with only 10 schemas and a few custom maps and scripts.</span></span>  
  
-   <span data-ttu-id="c915a-113">Separar un proyecto grande en varios más pequeños puede reducir su complejidad.</span><span class="sxs-lookup"><span data-stu-id="c915a-113">Separating a large project into smaller projects can reduce complexity.</span></span> <span data-ttu-id="c915a-114">Los proyectos pequeños son más fáciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="c915a-114">The smaller projects are more manageable.</span></span>  
  
-   <span data-ttu-id="c915a-115">Los proyectos pequeños se compilan más rápido.</span><span class="sxs-lookup"><span data-stu-id="c915a-115">Smaller projects compile faster.</span></span>  
  
-   <span data-ttu-id="c915a-116">Dividir un proyecto grande con muchos esquemas no relacionados en proyectos más pequeños con esquemas muy relacionados entre sí puede mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c915a-116">Splitting a large project with many unrelated schemas into smaller projects with strongly related schemas may result in better performance.</span></span> <span data-ttu-id="c915a-117">Esto se debe a que solo algunos de los ensamblados se cargarán a la misma vez.</span><span class="sxs-lookup"><span data-stu-id="c915a-117">This is because only some of the assemblies will be loaded at a time.</span></span>  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a><span data-ttu-id="c915a-118">Evitar utilizar el nombre del proyecto como el nombre de tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="c915a-118">Avoid using the Project Name as the Map Type Name</span></span>  
 <span data-ttu-id="c915a-119">Cuando agregue una nueva asignación a un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no use el nombre del proyecto como el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="c915a-119">When adding a new map to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not use the project name as the type name.</span></span> <span data-ttu-id="c915a-120">Si lo hace, el compilador generará uno o más errores similares a "el nombre de tipo \<nombre\>' no existe en el tipo".</span><span class="sxs-lookup"><span data-stu-id="c915a-120">If you do, the compiler will generate one or more errors similar to "The type name \<name\>' does not exist in the type".</span></span>  
  
 <span data-ttu-id="c915a-121">Para cambiar el nombre de tipo para una asignación desde dentro de un proyecto de BizTalk, haga clic en la asignación en el panel Explorador de soluciones, compruebe la propiedad de nombre de tipo en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="c915a-121">To change the type name for a map from within a BizTalk project, click the map in the Solution Explorer pane, then verify the type name property in the Properties pane.</span></span> <span data-ttu-id="c915a-122">Si es el mismo, necesita modificarlo sin olvidarse de cambiar cualquier configuración que dependa de él.</span><span class="sxs-lookup"><span data-stu-id="c915a-122">If it is the same, you need to modify it making sure to change any configurations that rely on it.</span></span>  
  
## <a name="visual-studio-team-system-support"></a><span data-ttu-id="c915a-123">Compatibilidad con Visual Studio Team System</span><span class="sxs-lookup"><span data-stu-id="c915a-123">Visual Studio Team System Support</span></span>  
 <span data-ttu-id="c915a-124">Los proyectos de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no admiten todas las características de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System directamente.</span><span class="sxs-lookup"><span data-stu-id="c915a-124">BizTalk projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not directly support all features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System.</span></span> <span data-ttu-id="c915a-125">Las características de control de código fuente de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System son compatibles con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c915a-125">The source control features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System are supported for BizTalk Server.</span></span> <span data-ttu-id="c915a-126">Visual SourceSafe es también totalmente compatible con el seguimiento y las versiones de artefactos de proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c915a-126">Visual SourceSafe is also fully supported for the tracking and versioning of BizTalk project artifacts.</span></span>