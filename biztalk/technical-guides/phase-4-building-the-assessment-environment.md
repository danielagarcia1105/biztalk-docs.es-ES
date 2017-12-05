---
title: "Fase 4: Crear el entorno de evaluación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88fa45a17e1475aee989f22d2f8d1ef0d015a9ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="phase-4-building-the-assessment-environment"></a><span data-ttu-id="6177d-102">Fase 4: Crear el entorno de evaluación</span><span class="sxs-lookup"><span data-stu-id="6177d-102">Phase 4: Building the Assessment Environment</span></span>
<span data-ttu-id="6177d-103">La fase de laboratorio de compilación de una evaluación de rendimiento se usa para instalar el hardware y software para el entorno de acuerdo a las decisiones de diseño adoptadas para fases anteriores.</span><span class="sxs-lookup"><span data-stu-id="6177d-103">The Build lab phase of a performance assessment is used to install the hardware and software for the environment in conformance to the design decisions made in previous phases.</span></span> <span data-ttu-id="6177d-104">Dado que la fase de laboratorio de compilación puede llevar mucho tiempo, no es inusual para esta fase superponer las fases anteriores.</span><span class="sxs-lookup"><span data-stu-id="6177d-104">Because the Build lab phase can be time consuming, it is not unusual for this phase to overlap earlier phases.</span></span> <span data-ttu-id="6177d-105">En muchos escenarios, el hardware y el sistema operativo pueden instalarse antes de que se ha tomado una decisión final en cuanto a la arquitectura de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6177d-105">In many scenarios, the hardware and operating system may be installed before a final decision has been made as to the application architecture.</span></span> <span data-ttu-id="6177d-106">Normalmente, la fase de laboratorio de compilación de una evaluación de rendimiento incluye las tareas descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="6177d-106">The Build lab phase of a performance assessment typically includes the tasks discussed in this topic.</span></span>  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a><span data-ttu-id="6177d-107">Obtener todas las infraestructura del laboratorio de compilación al menos una semana antes de la fecha de inicio de laboratorio</span><span class="sxs-lookup"><span data-stu-id="6177d-107">Obtain all build-lab infrastructure at least a week in advance of the lab start date</span></span>  
 <span data-ttu-id="6177d-108">Debe tener disponible de todos los requisitos de hardware y software al menos una semana antes de la fecha de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="6177d-108">Plan to have available all of the required hardware and software at least a week before the lab start date.</span></span> <span data-ttu-id="6177d-109">Así se asegurará de que no pierde tiempo de laboratorio valiosa para desea de la infraestructura necesaria.</span><span class="sxs-lookup"><span data-stu-id="6177d-109">This will ensure that valuable lab time is not wasted for want of the required infrastructure.</span></span>  
  
## <a name="configure-third-party-software-systems"></a><span data-ttu-id="6177d-110">Configurar los sistemas de software de terceros</span><span class="sxs-lookup"><span data-stu-id="6177d-110">Configure third-party software systems</span></span>  
 <span data-ttu-id="6177d-111">Puede haber sistemas de terceros que necesitan ser creado y configurado para que pueda comenzar la práctica.</span><span class="sxs-lookup"><span data-stu-id="6177d-111">There may be third-party systems that need to be built out and configured before the lab can begin.</span></span> <span data-ttu-id="6177d-112">Si son necesarios para estos sistemas de expertos en la materia (PYME), asegúrese de que estén programadas durante las fases de ejecución fuera de la compilación y laboratorio.</span><span class="sxs-lookup"><span data-stu-id="6177d-112">If subject matter experts (SMEs) are required for these systems, be sure they are scheduled during the build-out and lab execution stages.</span></span> <span data-ttu-id="6177d-113">Asegúrese de que documentar minuciosamente sus procedimientos de creación.</span><span class="sxs-lookup"><span data-stu-id="6177d-113">Ensure that they thoroughly document their build-out procedures.</span></span>  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a><span data-ttu-id="6177d-114">Instalar y configurar el entorno de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6177d-114">Install and configure the BizTalk Server environment</span></span>  
 <span data-ttu-id="6177d-115">Instrucciones detalladas para instalar BizTalk Server y el software de dependencia necesarios están en la [Installation and Upgrade Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="6177d-115">Detailed instructions for installing BizTalk Server and the required dependency software are in the [Installation and Upgrade Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span> <span data-ttu-id="6177d-116">Después de instalar y configurar el entorno de BizTalk Server correctamente, complete las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6177d-116">After successfully installing and configuring the BizTalk Server environment, complete the following tasks:</span></span>  
  
-   <span data-ttu-id="6177d-117">Siga las recomendaciones enumeradas en la [listas de comprobación de preparación operativa](operational-readiness-checklists.md)</span><span class="sxs-lookup"><span data-stu-id="6177d-117">Follow the recommendations listed in the [Operational Readiness Checklists](operational-readiness-checklists.md)</span></span>
  
-   <span data-ttu-id="6177d-118">Siga las recomendaciones de [optimizar el rendimiento](../technical-guides/optimizing-performance.md).</span><span class="sxs-lookup"><span data-stu-id="6177d-118">Follow the recommendations in [Optimizing Performance](../technical-guides/optimizing-performance.md).</span></span>  
  
-   <span data-ttu-id="6177d-119">Asegúrese de que todas las horas del equipo se han sincronizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6177d-119">Ensure all computer times are properly synchronized.</span></span>  
  
-   <span data-ttu-id="6177d-120">Comprobar la funcionalidad MSDTC entre todos los equipos en el entorno.</span><span class="sxs-lookup"><span data-stu-id="6177d-120">Verify MSDTC functionality between all computers in the environment.</span></span>  
  
-   <span data-ttu-id="6177d-121">Asegúrese de que cualquier seguimiento/registro personalizado está deshabilitada a menos que sea absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="6177d-121">Ensure any custom tracing/logging is disabled unless absolutely needed.</span></span>  
  
-   <span data-ttu-id="6177d-122">Instalar la edición de Visual Studio Ultimate para pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="6177d-122">Install the Visual Studio Ultimate edition for load testing.</span></span>  <span data-ttu-id="6177d-123">Para obtener más información sobre cómo realizar las pruebas automatizadas mediante Visual Studio, vea [con Visual Studio para facilitar las pruebas automatizadas](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).</span><span class="sxs-lookup"><span data-stu-id="6177d-123">For more information about how to perform automated testing using Visual Studio, see [Using Visual Studio to Facilitate Automated Testing](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).</span></span>  
  
-   <span data-ttu-id="6177d-124">Configurar los contadores del Monitor de rendimiento y registros, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6177d-124">Setup Performance Monitor counters and logs, as needed.</span></span>  
  
-   <span data-ttu-id="6177d-125">Configurar un equipo de depuración para depurar la solución si hay cambios en el código dentro del ámbito de la evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6177d-125">Setup a debugging computer to debug the solution if code changes are within the scope of the performance assessment.</span></span>  
  
-   <span data-ttu-id="6177d-126">Desfragmente todos los discos duros.</span><span class="sxs-lookup"><span data-stu-id="6177d-126">Defragment all hard drives.</span></span>  
  
-   <span data-ttu-id="6177d-127">Deshabilite el examen del antivirus en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="6177d-127">Disable antivirus real time scanning.</span></span>  
  
-   <span data-ttu-id="6177d-128">Hacer copia de seguridad del Enterprise Single Sign-On secreto principal.</span><span class="sxs-lookup"><span data-stu-id="6177d-128">Back up the Enterprise Single Sign-On Master Secret.</span></span>  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a><span data-ttu-id="6177d-129">Instalar la aplicación de BizTalk Server se va a probar</span><span class="sxs-lookup"><span data-stu-id="6177d-129">Install the BizTalk Server application to be tested</span></span>  
 <span data-ttu-id="6177d-130">Instalación de la aplicación se va a probar incluirá, normalmente, los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6177d-130">Installation of the application to be tested will typically include the following steps:</span></span>  
  
1.  <span data-ttu-id="6177d-131">Use la consola de administración de BizTalk Server para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6177d-131">Use the BizTalk Server Administration console to do the following:</span></span>  
  
    -   <span data-ttu-id="6177d-132">Crear Hosts</span><span class="sxs-lookup"><span data-stu-id="6177d-132">Create Hosts</span></span>  
  
    -   <span data-ttu-id="6177d-133">Crear controladores de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="6177d-133">Create Send/Receive Handlers.</span></span>  
  
    -   <span data-ttu-id="6177d-134">Crear instancias de Host.</span><span class="sxs-lookup"><span data-stu-id="6177d-134">Create Host instances.</span></span>  
  
    -   <span data-ttu-id="6177d-135">Crear aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6177d-135">Create BizTalk Server Applications.</span></span>  
  
2.  <span data-ttu-id="6177d-136">Instalación de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6177d-136">Application installation:</span></span>  
  
    1.  <span data-ttu-id="6177d-137">Implementar archivos binarios de BizTalk Server en el grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6177d-137">Deploy BizTalk Server binaries to the BizTalk Server group.</span></span>  
  
    2.  <span data-ttu-id="6177d-138">Importar enlaces en el grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6177d-138">Import bindings to the BizTalk Server group.</span></span>  
  
    3.  <span data-ttu-id="6177d-139">Archivos binarios de GAC BizTalk Server y no de BizTalk Server en todos los cuadros.</span><span class="sxs-lookup"><span data-stu-id="6177d-139">GAC BizTalk Server and non-BizTalk Server binaries on all boxes.</span></span>  
  
    4.  <span data-ttu-id="6177d-140">Asegúrese de que existen componentes de dependencia en todos los cuadros.</span><span class="sxs-lookup"><span data-stu-id="6177d-140">Ensure dependency components exist on all boxes.</span></span>  
  
3.  <span data-ttu-id="6177d-141">Instalar aplicaciones de dependencia.</span><span class="sxs-lookup"><span data-stu-id="6177d-141">Install dependency applications.</span></span>  
  
4.  <span data-ttu-id="6177d-142">Configurar transportes y los extremos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6177d-142">Configure transports and physical endpoints in the BizTalk Server Administration console.</span></span>  
  
5.  <span data-ttu-id="6177d-143">Iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="6177d-143">Start services.</span></span>  
  
6.  <span data-ttu-id="6177d-144">Realizar pruebas básicas de humos: pruebas de humo son pruebas funcionales-to-end que probar la funcionalidad básica de la solución.</span><span class="sxs-lookup"><span data-stu-id="6177d-144">Perform basic smoke tests – Smoke tests are end-to-end functional tests that test the basic functionality of your solution.</span></span>  
  
## <a name="implement-automated-build-and-load-testing"></a><span data-ttu-id="6177d-145">Implementar automatizado de compilación y prueba de carga</span><span class="sxs-lookup"><span data-stu-id="6177d-145">Implement automated build and load testing</span></span>  
 <span data-ttu-id="6177d-146">Implementación de una compilación automatizada y el proceso de prueba de carga sin duda es la piedra angular de una evaluación del rendimiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6177d-146">Implementation of an automated build and load testing process is arguably the cornerstone of a BizTalk Server performance assessment.</span></span> <span data-ttu-id="6177d-147">Se debe implementar un proceso automatizado de compilación si hay cambios en el código dentro del ámbito de la evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6177d-147">An automated build process should be implemented if code changes are within the scope of the performance assessment.</span></span> <span data-ttu-id="6177d-148">Pruebas de carga automatizada se deben implementar para todos los escenarios de prueba de carga.</span><span class="sxs-lookup"><span data-stu-id="6177d-148">Automated load testing should be implemented for all load testing scenarios.</span></span> <span data-ttu-id="6177d-149">La inversión de tiempo inicial necesaria para implementar automatizado de compilación y prueba de carga es recuperar rápidamente, permite la automatización de la repetición rápida y precisa de las tareas rutinarias de compilación y pruebas que están sujetas a errores humanos.</span><span class="sxs-lookup"><span data-stu-id="6177d-149">The initial time investment required to implement automated build and load testing is quickly recouped, automation accommodates rapid and precise repetition of mundane build/testing tasks that are subject to human error.</span></span> <span data-ttu-id="6177d-150">Para obtener más información acerca de cómo implementar una compilación automatizada y probar el proceso, consulte [implementar las pruebas automatizadas](../technical-guides/implementing-automated-testing.md) en esta guía.</span><span class="sxs-lookup"><span data-stu-id="6177d-150">For more information about implementing an automated build and testing process, see [Implementing Automated Testing](../technical-guides/implementing-automated-testing.md) in this guide.</span></span>  
  
## <a name="configure-performance-monitoring"></a><span data-ttu-id="6177d-151">Configurar la supervisión de rendimiento</span><span class="sxs-lookup"><span data-stu-id="6177d-151">Configure performance monitoring</span></span>  
 <span data-ttu-id="6177d-152">Supervisión de rendimiento precisos es fundamental para el éxito de la evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6177d-152">Accurate performance monitoring is critical to the success of the performance assessment.</span></span> <span data-ttu-id="6177d-153">Determinar qué medidas de rendimiento deben evaluarse en función de los objetivos de rendimiento y la latencia que se definieron en la fase de ámbito.</span><span class="sxs-lookup"><span data-stu-id="6177d-153">Determine which performance metrics should be evaluated based on the throughput and latency goals that were defined in the Scope phase.</span></span> <span data-ttu-id="6177d-154">Supervisión de rendimiento debe realizarse en cada equipo en el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6177d-154">Performance monitoring should be performed on each computer in the BizTalk Server environment.</span></span> <span data-ttu-id="6177d-155">Vea [contadores de rendimiento](../core/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="6177d-155">See [Performance Counters](../core/performance-counters.md).</span></span> <span data-ttu-id="6177d-156">Utilice la herramienta de análisis de registros de rendimiento (PAL) para generar informes HTML que gráficamente los contadores de rendimiento importantes del gráfico y generan alertas cuando se superan los umbrales de estos contadores.</span><span class="sxs-lookup"><span data-stu-id="6177d-156">Use the Performance Analysis of Logs tool (PAL) to generate HTML reports that graphically chart important performance counters and generate alerts when thresholds for these counters are exceeded.</span></span> <span data-ttu-id="6177d-157">S [herramienta de análisis de rendimiento de registros (PAL)](https://github.com/clinthuffman/PAL).</span><span class="sxs-lookup"><span data-stu-id="6177d-157">S [Performance Analysis of Logs (PAL) tool](https://github.com/clinthuffman/PAL).</span></span>  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a><span data-ttu-id="6177d-158">Establecer y documentar el rendimiento de línea de base de la solución</span><span class="sxs-lookup"><span data-stu-id="6177d-158">Establish and document the solution’s baseline performance</span></span>  
 <span data-ttu-id="6177d-159">Rendimiento de línea de base se debe calcular para que se puede medir el efecto de las optimizaciones de rendimiento que se aplican durante la evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6177d-159">Baseline performance should be calculated so that the effect of performance optimizations applied during the performance assessment can be measured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6177d-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="6177d-160">See Also</span></span>  
 [<span data-ttu-id="6177d-161">Fases de una valoración del rendimiento</span><span class="sxs-lookup"><span data-stu-id="6177d-161">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)