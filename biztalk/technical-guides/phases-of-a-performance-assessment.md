---
title: "Fases de una evaluación de rendimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 120706f9-9fa1-4f41-bd89-3b9eada940ad
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32d3c32158bc5a334aa614f03aa1a86afd6fffd9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="phases-of-a-performance-assessment"></a><span data-ttu-id="11e32-102">Fases de una evaluación del rendimiento</span><span class="sxs-lookup"><span data-stu-id="11e32-102">Phases of a Performance Assessment</span></span>
<span data-ttu-id="11e32-103">Uno de los objetivos principales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consiste en ofrecer la máxima flexibilidad para alojar las situaciones de procesamiento tantos como sea posible.</span><span class="sxs-lookup"><span data-stu-id="11e32-103">One of the primary goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="11e32-104">Debido a esta gran flexibilidad, uno de los principales retos para los desarrolladores de una solución de BizTalk es determinar cómo realizar un mejor uso de las características disponibles en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su negocio necesidades.</span><span class="sxs-lookup"><span data-stu-id="11e32-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to meet their business needs.</span></span> <span data-ttu-id="11e32-105">Esta flexibilidad también supone un desafío al optimizar el rendimiento de una solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="11e32-105">This flexibility also poses a challenge when optimizing the performance of a BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="11e32-106">Esta sección describe la metodología que se debe usar para optimizar el rendimiento de una solución de BizTalk Server si se ocupa de una evaluación del rendimiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="11e32-106">This section describes the methodology that should be used to optimize the performance of a BizTalk Server solution by engaging in a BizTalk Server performance assessment.</span></span> <span data-ttu-id="11e32-107">Una evaluación del rendimiento de BizTalk Server se utiliza para maximizar el rendimiento de una solución de BizTalk Server determinado.</span><span class="sxs-lookup"><span data-stu-id="11e32-107">A BizTalk Server performance assessment is used to maximize the performance of a particular BizTalk Server solution.</span></span> <span data-ttu-id="11e32-108">Para obtener el máximo beneficio de una evaluación del rendimiento de BizTalk Server, se debe dividir la evaluación del rendimiento en las siguientes cinco pasos o fases distintas:</span><span class="sxs-lookup"><span data-stu-id="11e32-108">In order to gain the maximum benefit from a BizTalk Server performance assessment, the performance assessment should be divided into the following five distinct steps/phases:</span></span>  
  
1.  <span data-ttu-id="11e32-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="11e32-109">Scope</span></span>  
  
2.  <span data-ttu-id="11e32-110">Plan</span><span class="sxs-lookup"><span data-stu-id="11e32-110">Plan</span></span>  
  
3.  <span data-ttu-id="11e32-111">Preparar</span><span class="sxs-lookup"><span data-stu-id="11e32-111">Prepare</span></span>  
  
4.  <span data-ttu-id="11e32-112">Laboratorio de compilación</span><span class="sxs-lookup"><span data-stu-id="11e32-112">Build lab</span></span>  
  
5.  <span data-ttu-id="11e32-113">Execute</span><span class="sxs-lookup"><span data-stu-id="11e32-113">Execute</span></span>  
  
 <span data-ttu-id="11e32-114">Este tema describe cada una de estas fases con más detalle.</span><span class="sxs-lookup"><span data-stu-id="11e32-114">This topic describes each of these phases in greater detail.</span></span>  
  
 <span data-ttu-id="11e32-115">![Fases de un proceso de evaluación de rendimiento](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span><span class="sxs-lookup"><span data-stu-id="11e32-115">![Phases of a performance assessment process](../technical-guides/media/assessmentprocess.gif "AssessmentProcess")</span></span>  
<span data-ttu-id="11e32-116">Fases de una evaluación del rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="11e32-116">Phases of a BizTalk Server performance assessment</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11e32-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11e32-117">In This Section</span></span>  
  
-   <span data-ttu-id="11e32-118">[Fase 1: La evaluación de ámbito de](../technical-guides/phase-1-scoping-the-assessment.md) -describe los pasos que deben seguirse al establecer el ámbito de la evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="11e32-118">[Phase 1: Scoping the Assessment](../technical-guides/phase-1-scoping-the-assessment.md) - Describes the steps that should be followed when establishing the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="11e32-119">[Fase 2: Planear la evaluación](../technical-guides/phase-2-planning-the-assessment.md) : describe cómo crear una escala de tiempo de los hitos de solución.</span><span class="sxs-lookup"><span data-stu-id="11e32-119">[Phase 2: Planning the Assessment](../technical-guides/phase-2-planning-the-assessment.md) – Describes how to create a solution milestones timeline.</span></span> <span data-ttu-id="11e32-120">Esto se utiliza como un plan maestro para documentar claramente cuando deben cumplir los objetivos previstos para la prueba de la solución.</span><span class="sxs-lookup"><span data-stu-id="11e32-120">This is used as a master plan to clearly document when expected goals for the testing of the solution should be met.</span></span>  
  
-   <span data-ttu-id="11e32-121">[Fase 3: Preparar para la evaluación](../technical-guides/phase-3-preparing-for-the-assessment.md) : describe cómo proporcionar un diagrama de arquitectura detallado de la solución y aspectos específicos de la configuración de hardware utilizados por la solución.</span><span class="sxs-lookup"><span data-stu-id="11e32-121">[Phase 3: Preparing for the Assessment](../technical-guides/phase-3-preparing-for-the-assessment.md) – Describes how to provide a detailed architectural diagram of the solution and specific aspects of the hardware configuration used by the solution.</span></span>  
  
-   <span data-ttu-id="11e32-122">[Fase 4: Crear el entorno de evaluación](../technical-guides/phase-4-building-the-assessment-environment.md) : describe la instalación del hardware y las aplicaciones según el diseño detallado de la plataforma de solución que se estableció previamente.</span><span class="sxs-lookup"><span data-stu-id="11e32-122">[Phase 4: Building the Assessment Environment](../technical-guides/phase-4-building-the-assessment-environment.md) – Describes installation of hardware and applications according to the detailed design of the solution platform that was established previously.</span></span>  
  
-   <span data-ttu-id="11e32-123">[Fase 5: Ejecutar la evaluación](../technical-guides/phase-5-executing-the-assessment.md) : proporciona información sobre la generación de datos de rendimiento a través de pruebas de carga automatizada y cómo detectar y eliminar los cuellos de botella en la solución.</span><span class="sxs-lookup"><span data-stu-id="11e32-123">[Phase 5: Executing the Assessment](../technical-guides/phase-5-executing-the-assessment.md) – Provides information about generating performance data via automated load testing and how to detect and eliminate any bottlenecks in the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e32-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="11e32-124">See Also</span></span>  
 [<span data-ttu-id="11e32-125">Metodología de pruebas de rendimiento de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="11e32-125">BizTalk Server Performance Testing Methodology</span></span>](../technical-guides/biztalk-server-performance-testing-methodology.md)