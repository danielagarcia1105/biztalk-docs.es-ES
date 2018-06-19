---
title: Recomendaciones para la planificación de proyectos por fases | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, performance
- performance, planning
ms.assetid: 422f05e3-5ad4-4f47-9be3-c229a20a6ef3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8886f3e52d347651630a4cafb716049fdf19fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264956"
---
# <a name="project-planning-recommendations-by-phase"></a><span data-ttu-id="213f6-102">Recomendaciones de planeación de proyectos por fases</span><span class="sxs-lookup"><span data-stu-id="213f6-102">Project Planning Recommendations by Phase</span></span>
<span data-ttu-id="213f6-103">Actualmente existen varios modelos de ciclo de vida del desarrollo de software, cada uno con sus propios enfoques, ventajas y limitaciones.</span><span class="sxs-lookup"><span data-stu-id="213f6-103">There are a number of software development lifecycle models in existence today, each with their own approaches, benefits, and limitations.</span></span> <span data-ttu-id="213f6-104">El objetivo de esta sección es proporcionar un conjunto de recomendaciones que le ayudarán a planear de forma adecuada un proyecto de desarrollo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] correcto.</span><span class="sxs-lookup"><span data-stu-id="213f6-104">The goal of this section is to provide a set of recommendations that will help you plan appropriately for a successful [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development project.</span></span>  
  
 <span data-ttu-id="213f6-105">En esta sección se utiliza el modelo de ciclo de vida empleado generalmente en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="213f6-105">In this section, we use the lifecycle model employed broadly at Microsoft.</span></span> <span data-ttu-id="213f6-106">Este modelo es una combinación de los modelos de ciclo de vida iterativo y en cascada.</span><span class="sxs-lookup"><span data-stu-id="213f6-106">This model is a combination of iterative and waterfall lifecycle models.</span></span>  
  
 <span data-ttu-id="213f6-107">En este modelo hay cinco fases cuyos límites definen un conjunto secuencias de hitos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="213f6-107">In this model, there are five phases whose boundaries define a sequential set of milestones for the project.</span></span> <span data-ttu-id="213f6-108">Las fases, por orden de ejecución, son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="213f6-108">The phases, in order of execution, are as follows:</span></span>  
  
-   <span data-ttu-id="213f6-109">**Requisitos de**.</span><span class="sxs-lookup"><span data-stu-id="213f6-109">**Requirements**.</span></span> <span data-ttu-id="213f6-110">Requisitos de los usuarios se recogen en especificaciones funcionales que definen lo que se van a compilar.</span><span class="sxs-lookup"><span data-stu-id="213f6-110">User requirements are captured in functional specifications that define what is to be built.</span></span>  
  
-   <span data-ttu-id="213f6-111">**Diseño**.</span><span class="sxs-lookup"><span data-stu-id="213f6-111">**Design**.</span></span> <span data-ttu-id="213f6-112">Según los requisitos funcionales, especificaciones de diseño físico se crean y se realiza el prototipo para comprobar las ideas de diseño e investigar las capacidades de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="213f6-112">Based on the functional requirements, physical design specifications are created and prototyping is conducted to verify design ideas and investigate platform capabilities.</span></span>  
  
-   <span data-ttu-id="213f6-113">**Implementación**.</span><span class="sxs-lookup"><span data-stu-id="213f6-113">**Implementation**.</span></span> <span data-ttu-id="213f6-114">Uso de las especificaciones funcionales y diseño, el código del software se realiza.</span><span class="sxs-lookup"><span data-stu-id="213f6-114">Using the design and functional specifications, the software coding is done.</span></span>  
  
-   <span data-ttu-id="213f6-115">**Comprobación**.</span><span class="sxs-lookup"><span data-stu-id="213f6-115">**Verification**.</span></span> <span data-ttu-id="213f6-116">Este es el proceso de prueba del software para comprobar que funciona según las especificaciones.</span><span class="sxs-lookup"><span data-stu-id="213f6-116">This is the process of testing the software to verify that it performs according to the specifications.</span></span>  
  
-   <span data-ttu-id="213f6-117">**Versión**.</span><span class="sxs-lookup"><span data-stu-id="213f6-117">**Release**.</span></span> <span data-ttu-id="213f6-118">Después de que el software se ha comprobado totalmente, se empaqueta y se prepara para lanzamiento a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="213f6-118">After the software has been fully verified, it is packed and prepared for release to users.</span></span>  
  
 <span data-ttu-id="213f6-119">La siguiente ilustración muestra el ciclo de planeamiento de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="213f6-119">The following figure shows this project planning cycle.</span></span>  
  
 <span data-ttu-id="213f6-120">![Recomendaciones para la planificación de proyectos por fases](../core/media/planningbyphase.gif "PlanningByPhase")</span><span class="sxs-lookup"><span data-stu-id="213f6-120">![Project Planning Recommendations by Phase](../core/media/planningbyphase.gif "PlanningByPhase")</span></span>  
  
 <span data-ttu-id="213f6-121">La mayoría de estas fases, si no todas, se superponen en el tiempo y normalmente hay subfases iterativas.</span><span class="sxs-lookup"><span data-stu-id="213f6-121">Most, if not all, of these phases overlap in time and there are typically iterative sub-phases.</span></span> <span data-ttu-id="213f6-122">Por ejemplo, es habitual completar la implementación de un subjuego de las características del producto y, con fines de comprobación, comenzar con ese subjuego mientras se realiza la implementación del siguiente subjuego de características.</span><span class="sxs-lookup"><span data-stu-id="213f6-122">For example, it is common to complete implementation of a sub-set of the product features and for verification to begin on that subset while implementation of the next sub set of features is under way.</span></span> <span data-ttu-id="213f6-123">Por consiguiente, mientras que las recomendaciones de esta sección están relacionadas con determinadas fases, no se pretende dar a entender que no puedan suceder en paralelo, sino indicar en cierta medida el orden relativo en el que se deben tener en cuenta las recomendaciones y su importancia en la planeamiento.</span><span class="sxs-lookup"><span data-stu-id="213f6-123">Therefore, while the recommendations in this section are associated with certain phases, the intention is not to imply that they cannot happen in parallel, but rather to give some idea of the relative order that the recommendations should be considered and factored into planning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="213f6-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="213f6-124">In This Section</span></span>  
  
-   [<span data-ttu-id="213f6-125">Recomendaciones de la fase de requisitos</span><span class="sxs-lookup"><span data-stu-id="213f6-125">Requirements Phase Recommendations</span></span>](../core/requirements-phase-recommendations.md)  
  
-   [<span data-ttu-id="213f6-126">Recomendaciones de la fase de diseño</span><span class="sxs-lookup"><span data-stu-id="213f6-126">Design Phase Recommendations</span></span>](../core/design-phase-recommendations.md)  
  
-   [<span data-ttu-id="213f6-127">Recomendaciones de la fase de implementación</span><span class="sxs-lookup"><span data-stu-id="213f6-127">Implementation Phase Recommendations</span></span>](../core/implementation-phase-recommendations.md)  
  
-   [<span data-ttu-id="213f6-128">Recomendaciones de la fase de comprobación</span><span class="sxs-lookup"><span data-stu-id="213f6-128">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)  
  
-   [<span data-ttu-id="213f6-129">Recomendaciones para la fase versión</span><span class="sxs-lookup"><span data-stu-id="213f6-129">Release Phase Recommendations</span></span>](../core/release-phase-recommendations.md)