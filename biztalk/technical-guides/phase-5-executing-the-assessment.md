---
title: 'Fase 5: Ejecutar la evaluación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fba6d49d8d69276af4282ad0a941ee1fc4d8068
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302692"
---
# <a name="phase-5-executing-the-assessment"></a><span data-ttu-id="6a528-102">Fase 5: Ejecutar la evaluación</span><span class="sxs-lookup"><span data-stu-id="6a528-102">Phase 5: Executing the Assessment</span></span>
<span data-ttu-id="6a528-103">La fase de ejecución es donde los datos de rendimiento se generan a través de pruebas de carga automatizada y donde los cuellos de botella de rendimiento son detectados y solucionarse.</span><span class="sxs-lookup"><span data-stu-id="6a528-103">The Execute phase is where the performance data is generated through automated load testing and where performance bottlenecks are discovered and addressed.</span></span> <span data-ttu-id="6a528-104">Esta fase tiene un proceso iterativo mediante el cual cuellos de botella de rendimiento se reduce o elimina probando, evaluar el rendimiento, optimizar y probar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6a528-104">This phase has an iterative process whereby performance bottlenecks are reduced or eliminated by testing, evaluating performance, optimizing, and testing again.</span></span>  
  
 <span data-ttu-id="6a528-105">En este tema se describe los pasos que se siguen normalmente durante la fase de ejecución de una evaluación del rendimiento de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="6a528-105">This topic describes the steps that are typically followed during the Execute phase of a BizTalk Server performance assessment:</span></span>  
  
## <a name="step-1-run-automated-tests"></a><span data-ttu-id="6a528-106">Paso 1: Ejecutar pruebas automatizadas</span><span class="sxs-lookup"><span data-stu-id="6a528-106">Step 1: Run automated tests</span></span>  
 <span data-ttu-id="6a528-107">Comenzar la fase de ejecución mediante la ejecución de pruebas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="6a528-107">Begin the Execute phase by running automated tests.</span></span> <span data-ttu-id="6a528-108">Una evaluación del rendimiento de BizTalk Server normalmente se centra en el rendimiento o pruebas de latencia, pero puede incluir la comprobación de la compilación y pruebas funcionales.</span><span class="sxs-lookup"><span data-stu-id="6a528-108">A BizTalk Server performance assessment typically focuses on throughput and/or latency testing but may include build verification and functional tests.</span></span> <span data-ttu-id="6a528-109">Para obtener información completa acerca de cómo ejecutar pruebas automatizadas, vea [implementar las pruebas automatizadas](../technical-guides/implementing-automated-testing.md).</span><span class="sxs-lookup"><span data-stu-id="6a528-109">For comprehensive information about running automated testing, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md).</span></span>  
  
## <a name="step-2-document-and-evaluate-test-results"></a><span data-ttu-id="6a528-110">Paso 2: Documentos y evaluar los resultados de pruebas</span><span class="sxs-lookup"><span data-stu-id="6a528-110">Step 2: Document and evaluate test results</span></span>  
 <span data-ttu-id="6a528-111">Al final de cada prueba exhaustivamente documentar los resultados de pruebas y evaluar si se cumplen los objetivos de rendimiento indicados.</span><span class="sxs-lookup"><span data-stu-id="6a528-111">At the conclusion of each test, thoroughly document the test results and evaluate whether the stated performance goals have been met.</span></span>  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a><span data-ttu-id="6a528-112">Paso 3: Modificar la configuración de BizTalk Server, sistemas de terceros o artefactos de la solución para la optimización del rendimiento en función de los resultados de pruebas</span><span class="sxs-lookup"><span data-stu-id="6a528-112">Step 3: Modify the configuration of BizTalk Server, third-party systems, or solution artifacts to tune for performance based on the test results</span></span>  
 <span data-ttu-id="6a528-113">Utilizar los resultados de pruebas para tomar decisiones acerca de cómo optimizar el entorno para alcanzar los objetivos de rendimiento o latencia indicados.</span><span class="sxs-lookup"><span data-stu-id="6a528-113">Use the test results to make decisions about how to optimize the environment to reach stated throughput or latency goals.</span></span>  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a><span data-ttu-id="6a528-114">Paso 4: Registrar todos los cambios realizados en el entorno</span><span class="sxs-lookup"><span data-stu-id="6a528-114">Step 4: Record all changes made to the environment</span></span>  
 <span data-ttu-id="6a528-115">Asegúrese de que han sido documentados en los cambios realizados en el entorno.</span><span class="sxs-lookup"><span data-stu-id="6a528-115">Ensure that any changes made to the environment are thoroughly documented.</span></span> <span data-ttu-id="6a528-116">Un registro de los cambios, podrá aplicar fácilmente los cambios en el entorno de producción y se alojará el Deshaciendo cambios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="6a528-116">A record of the changes will allow you to easily apply the changes in the production environment and will accommodate the undoing of changes if need be.</span></span>  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a><span data-ttu-id="6a528-117">Paso 5: Repita este ciclo hasta que se logre establecer objetivos</span><span class="sxs-lookup"><span data-stu-id="6a528-117">Step 5: Repeat this cycle until goals are achieved</span></span>  
 <span data-ttu-id="6a528-118">Continuar el ciclo de pruebas, evaluar y documentar los resultados, optimización del entorno y documentar los cambios en el entorno hasta que se alcancen los objetivos de rendimiento deseados.</span><span class="sxs-lookup"><span data-stu-id="6a528-118">Continue the cycle of testing, evaluating and documenting results, optimizing the environment, and documenting changes to the environment until the desired performance goals are reached.</span></span>  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a><span data-ttu-id="6a528-119">Paso 6: Resumir los resultados de pruebas al final de cada día</span><span class="sxs-lookup"><span data-stu-id="6a528-119">Step 6: Summarize test results at the end of each day</span></span>  
 <span data-ttu-id="6a528-120">Completar un "Resumen ejecutivo" de los resultados de pruebas y el progreso realizado al final de cada día.</span><span class="sxs-lookup"><span data-stu-id="6a528-120">Complete an “executive summary” of the test results and progress made at the end of each day.</span></span> <span data-ttu-id="6a528-121">Compilar un correo electrónico que contiene el resumen y enviar a todas las partes interesadas en la evaluación del rendimiento para mantener a todos informados del progreso que se está realizando.</span><span class="sxs-lookup"><span data-stu-id="6a528-121">Compile an e-mail that contains the summary, and send to all stakeholders in the performance assessment to keep everyone informed of progress that is being made.</span></span>  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a><span data-ttu-id="6a528-122">Paso 7: Actualizar el plan del proyecto que se cumplen los objetivos de la escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="6a528-122">Step 7: Update the project plan as timeline goals are met</span></span>  
 <span data-ttu-id="6a528-123">La escala de tiempo desarrollado en la fase de planificación es una buena referencia para ver el progreso general de la evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6a528-123">The timeline developed in the Plan phase is a good reference for the overall progress of the performance assessment.</span></span> <span data-ttu-id="6a528-124">Actualizar esta escala de tiempo según sea necesario para comunicar el progreso a todas las partes interesadas.</span><span class="sxs-lookup"><span data-stu-id="6a528-124">Update this timeline as necessary to communicate the progress to all stakeholders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a528-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a528-125">See Also</span></span>  
 [<span data-ttu-id="6a528-126">Fases de una evaluación del rendimiento</span><span class="sxs-lookup"><span data-stu-id="6a528-126">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)