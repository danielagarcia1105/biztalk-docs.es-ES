---
title: Fases de una valoración del rendimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 120706f9-9fa1-4f41-bd89-3b9eada940ad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abcf4bc5778d78d550184a8365e4d3775c3a15ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023034"
---
# <a name="phases-of-a-performance-assessment"></a><span data-ttu-id="69520-102">Fases de una valoración del rendimiento</span><span class="sxs-lookup"><span data-stu-id="69520-102">Phases of a Performance Assessment</span></span>
<span data-ttu-id="69520-103">Uno de los objetivos principales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consiste en proporcionar la máxima flexibilidad para adaptar los escenarios de procesamiento tantos como sea posible.</span><span class="sxs-lookup"><span data-stu-id="69520-103">One of the primary goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="69520-104">Debido a este gran flexibilidad, uno de los principales desafíos que enfrentan los desarrolladores de una solución de BizTalk consiste en determinar cómo hacer mejor uso de las características disponibles en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su negocio necesidades.</span><span class="sxs-lookup"><span data-stu-id="69520-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to meet their business needs.</span></span> <span data-ttu-id="69520-105">Esta flexibilidad también plantea un desafío al optimizar el rendimiento de una solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="69520-105">This flexibility also poses a challenge when optimizing the performance of a BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="69520-106">En esta sección se describe la metodología que debe usarse para optimizar el rendimiento de una solución de BizTalk Server si se ocupa de una valoración del rendimiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="69520-106">This section describes the methodology that should be used to optimize the performance of a BizTalk Server solution by engaging in a BizTalk Server performance assessment.</span></span> <span data-ttu-id="69520-107">Una evaluación del rendimiento de BizTalk Server se usa para maximizar el rendimiento de una determinada solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="69520-107">A BizTalk Server performance assessment is used to maximize the performance of a particular BizTalk Server solution.</span></span> <span data-ttu-id="69520-108">Para obtener el máximo beneficio de una valoración del rendimiento de BizTalk Server, la evaluación del rendimiento debe dividirse en las siguientes cinco pasos o fases distintas:</span><span class="sxs-lookup"><span data-stu-id="69520-108">In order to gain the maximum benefit from a BizTalk Server performance assessment, the performance assessment should be divided into the following five distinct steps/phases:</span></span>  
  
1. <span data-ttu-id="69520-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="69520-109">Scope</span></span>  
  
2. <span data-ttu-id="69520-110">Plan</span><span class="sxs-lookup"><span data-stu-id="69520-110">Plan</span></span>  
  
3. <span data-ttu-id="69520-111">Preparar</span><span class="sxs-lookup"><span data-stu-id="69520-111">Prepare</span></span>  
  
4. <span data-ttu-id="69520-112">Laboratorio de compilación</span><span class="sxs-lookup"><span data-stu-id="69520-112">Build lab</span></span>  
  
5. <span data-ttu-id="69520-113">Execute</span><span class="sxs-lookup"><span data-stu-id="69520-113">Execute</span></span>  
  
   <span data-ttu-id="69520-114">Este tema describe cada una de estas fases con más detalle.</span><span class="sxs-lookup"><span data-stu-id="69520-114">This topic describes each of these phases in greater detail.</span></span>  
  
   <span data-ttu-id="69520-115">![Fases de un proceso de evaluación del rendimiento](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span><span class="sxs-lookup"><span data-stu-id="69520-115">![Phases of a performance assessment process](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span></span>  
   <span data-ttu-id="69520-116">Fases de una evaluación del rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="69520-116">Phases of a BizTalk Server performance assessment</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69520-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="69520-117">In This Section</span></span>  
  
-   <span data-ttu-id="69520-118">[Fase 1: Ámbito de la valoración](../technical-guides/phase-1-scoping-the-assessment.md) -se describen los pasos que se deben seguir al establecer el ámbito de la evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69520-118">[Phase 1: Scoping the Assessment](../technical-guides/phase-1-scoping-the-assessment.md) - Describes the steps that should be followed when establishing the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="69520-119">[Fase 2: Planificación de la valoración](../technical-guides/phase-2-planning-the-assessment.md) : se describe cómo crear una escala de tiempo de los hitos de solución.</span><span class="sxs-lookup"><span data-stu-id="69520-119">[Phase 2: Planning the Assessment](../technical-guides/phase-2-planning-the-assessment.md) – Describes how to create a solution milestones timeline.</span></span> <span data-ttu-id="69520-120">Esto se utiliza como un plan maestro que documente claramente cuando se deben cumplir los objetivos previstos para la prueba de la solución.</span><span class="sxs-lookup"><span data-stu-id="69520-120">This is used as a master plan to clearly document when expected goals for the testing of the solution should be met.</span></span>  
  
-   <span data-ttu-id="69520-121">[Fase 3: Preparación para la valoración](../technical-guides/phase-3-preparing-for-the-assessment.md) : se describe cómo proporcionar un diagrama de arquitectura detallado de la solución y los aspectos específicos de la configuración de hardware utilizados por la solución.</span><span class="sxs-lookup"><span data-stu-id="69520-121">[Phase 3: Preparing for the Assessment](../technical-guides/phase-3-preparing-for-the-assessment.md) – Describes how to provide a detailed architectural diagram of the solution and specific aspects of the hardware configuration used by the solution.</span></span>  
  
-   <span data-ttu-id="69520-122">[Fase 4: Creación del entorno de evaluación](../technical-guides/phase-4-building-the-assessment-environment.md) : describe la instalación de hardware y aplicaciones según el diseño detallado de la plataforma de solución que se estableció previamente.</span><span class="sxs-lookup"><span data-stu-id="69520-122">[Phase 4: Building the Assessment Environment](../technical-guides/phase-4-building-the-assessment-environment.md) – Describes installation of hardware and applications according to the detailed design of the solution platform that was established previously.</span></span>  
  
-   <span data-ttu-id="69520-123">[Fase 5: Ejecución de la valoración](../technical-guides/phase-5-executing-the-assessment.md) : proporciona información acerca de cómo generar datos de rendimiento a través de las pruebas de carga automatizada y cómo detectar y eliminar los cuellos de botella en la solución.</span><span class="sxs-lookup"><span data-stu-id="69520-123">[Phase 5: Executing the Assessment](../technical-guides/phase-5-executing-the-assessment.md) – Provides information about generating performance data via automated load testing and how to detect and eliminate any bottlenecks in the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69520-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="69520-124">See Also</span></span>  
 [<span data-ttu-id="69520-125">Metodología de pruebas de rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="69520-125">BizTalk Server Performance Testing Methodology</span></span>](../technical-guides/biztalk-server-performance-testing-methodology.md)