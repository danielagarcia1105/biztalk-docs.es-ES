---
title: Cómo generar orquestaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9000c986e95270328d9c31ef4f5e3bda7f1576e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987333"
---
# <a name="how-to-build-orchestrations"></a><span data-ttu-id="3719d-102">Cómo generar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="3719d-102">How to Build Orchestrations</span></span>
<span data-ttu-id="3719d-103">Tras finalizar el diseño de una orquestación, se crea el proyecto de BizTalk en un ensamblado que encapsula una orquestación ejecutable.</span><span class="sxs-lookup"><span data-stu-id="3719d-103">After you have completed an orchestration drawing, you build your BizTalk project into an assembly that encapsulates an executable orchestration.</span></span>  
  
 <span data-ttu-id="3719d-104">Durante el proceso de generación, el Diseñador de orquestaciones de BizTalk examina todas las formas para determinar si están completas y son correctas, y presenta un error en la lista de tareas si no lo son.</span><span class="sxs-lookup"><span data-stu-id="3719d-104">During the build process, BizTalk Orchestration Designer examines each shape to determine whether it is complete and correct, and reports an error in the task list if it is not.</span></span>  
  
 <span data-ttu-id="3719d-105">Existen varias opciones para generar aplicaciones en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="3719d-105">You have several options for building in Visual Studio:</span></span>  
  
- <span data-ttu-id="3719d-106">Puede generar la solución completa en la que resida su orquestación.</span><span class="sxs-lookup"><span data-stu-id="3719d-106">You can build the entire solution in which your orchestration resides.</span></span>  
  
- <span data-ttu-id="3719d-107">Puede generar un único proyecto dentro de la solución.</span><span class="sxs-lookup"><span data-stu-id="3719d-107">You can build a single project within the solution.</span></span>  
  
- <span data-ttu-id="3719d-108">Puede omitir la orquestación al generar el proyecto o solución.</span><span class="sxs-lookup"><span data-stu-id="3719d-108">You can skip the orchestration when building the project or solution.</span></span>  
  
  <span data-ttu-id="3719d-109">Si desea generar otros componentes, incluidas otras orquestaciones, pero no desea generar una orquestación específica, puede indicar en las propiedades del archivo .odx de la orquestación que no desea generarla y ésta se omitirá.</span><span class="sxs-lookup"><span data-stu-id="3719d-109">If you want to build other components, including other orchestrations, but do not want to build a particular orchestration, you can indicate in the file properties for the orchestration's .odx file that you do not want to build it, and it will be skipped.</span></span>  
  
### <a name="to-build-an-orchestration"></a><span data-ttu-id="3719d-110">Para generar una orquestación</span><span class="sxs-lookup"><span data-stu-id="3719d-110">To build an orchestration</span></span>  
  
-   <span data-ttu-id="3719d-111">Tras crear una orquestación, debe generar el proyecto de BizTalk que la contiene para poder probarla o usarla.</span><span class="sxs-lookup"><span data-stu-id="3719d-111">After creating your orchestration, you need to build the BizTalk project that contains it before you can test or use the orchestration.</span></span> <span data-ttu-id="3719d-112">Puede generar la solución completa o un único proyecto dentro de la solución.</span><span class="sxs-lookup"><span data-stu-id="3719d-112">You can build the entire solution, or a single project within the solution.</span></span>  
  
### <a name="to-build-a-solution"></a><span data-ttu-id="3719d-113">Para generar una solución</span><span class="sxs-lookup"><span data-stu-id="3719d-113">To build a solution</span></span>  
  
-   <span data-ttu-id="3719d-114">En el Explorador de soluciones, haga clic en la solución y seleccione **compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="3719d-114">In Solution Explorer, right-click the solution and select **Build Solution**.</span></span>  
  
### <a name="to-build-a-project"></a><span data-ttu-id="3719d-115">Para generar un proyecto</span><span class="sxs-lookup"><span data-stu-id="3719d-115">To build a project</span></span>  
  
-   <span data-ttu-id="3719d-116">Haga clic en un proyecto y seleccione **compilar**.</span><span class="sxs-lookup"><span data-stu-id="3719d-116">Right-click a project and select **Build**.</span></span>  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a><span data-ttu-id="3719d-117">Para generar un proyecto o solución sin compilar una orquestación específica</span><span class="sxs-lookup"><span data-stu-id="3719d-117">To build a project or solution without compiling a particular orchestration</span></span>  
  
-   <span data-ttu-id="3719d-118">Haga clic en el archivo .odx correspondiente a la orquestación y, en la ventana Propiedades, haga clic en el **acción de compilación** propiedad y seleccione **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="3719d-118">Click the .odx file corresponding to the orchestration, and in the Properties window, click the **Build Action** property and select **None**.</span></span>