---
title: "Análisis de modelo de amenazas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TMA, about TMA
- TMA
- TMA, procedure steps
ms.assetid: dfbf46aa-0a35-4925-8718-df8591efc279
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06f5de73434d2c3a7bf67e659c6566b530b38aeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="threat-model-analysis"></a><span data-ttu-id="4f5e4-102">Análisis de modelo de amenazas</span><span class="sxs-lookup"><span data-stu-id="4f5e4-102">Threat Model Analysis</span></span>
<span data-ttu-id="4f5e4-103">El análisis de modelo de amenazas (TMA) es un análisis que ayuda a determinar los riesgos de seguridad que pueden acaecer en un producto, aplicación, red o entorno, así como la forma en la que se aparecen los ataques.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-103">A threat model analysis (TMA) is an analysis that helps determine the security risks posed to a product, application, network, or environment, and how attacks can show up.</span></span> <span data-ttu-id="4f5e4-104">El objetivo consiste en determinar cuáles son las amenazas que requieren mitigación y los modos de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-104">The goal is to determine which threats require mitigation and how to mitigate them.</span></span>  
  
 <span data-ttu-id="4f5e4-105">Esta sección proporciona información de alto nivel acerca del proceso TMA.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-105">This section provides high-level information about the TMA process.</span></span> <span data-ttu-id="4f5e4-106">Para obtener más información, consulte el capítulo 4 de *Writing Secure Code, segunda edición*, de Michael Howard y David LeBlanc.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-106">For more information, see Chapter 4 of *Writing Secure Code, Second edition*, by Michael Howard and David LeBlanc.</span></span>  
  
 <span data-ttu-id="4f5e4-107">Algunas de las ventajas de un TMA son:</span><span class="sxs-lookup"><span data-stu-id="4f5e4-107">Some of the benefits of a TMA are:</span></span>  
  
-   <span data-ttu-id="4f5e4-108">Facilita la comprensión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-108">Provides a better understanding of your application</span></span>  
  
-   <span data-ttu-id="4f5e4-109">Ayuda a detectar errores</span><span class="sxs-lookup"><span data-stu-id="4f5e4-109">Helps you find bugs</span></span>  
  
-   <span data-ttu-id="4f5e4-110">Puede ayudar a los miembros del nuevo equipo a entender la aplicación con mayor profundidad.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-110">Can help new team members understand the application in detail</span></span>  
  
-   <span data-ttu-id="4f5e4-111">Contiene información importante para otros equipos que trabajan en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-111">Contains important information for other teams that build on your application</span></span>  
  
-   <span data-ttu-id="4f5e4-112">Resulta de utilidad para los evaluadores.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-112">Useful for testers</span></span>  
  
 <span data-ttu-id="4f5e4-113">Los pasos de nivel alto para llevar a cabo un TMA son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f5e4-113">The high-level steps to perform a TMA are:</span></span>  
  
-   <span data-ttu-id="4f5e4-114">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-114">Step 1.</span></span> <span data-ttu-id="4f5e4-115">Recopilar información básica</span><span class="sxs-lookup"><span data-stu-id="4f5e4-115">Collect Background Information</span></span>  
  
-   <span data-ttu-id="4f5e4-116">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-116">Step 2.</span></span> <span data-ttu-id="4f5e4-117">Crear y analizar el modelo de amenazas</span><span class="sxs-lookup"><span data-stu-id="4f5e4-117">Create and Analyze the Threat Model</span></span>  
  
-   <span data-ttu-id="4f5e4-118">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-118">Step 3.</span></span> <span data-ttu-id="4f5e4-119">Analizar las amenazas</span><span class="sxs-lookup"><span data-stu-id="4f5e4-119">Review Threats</span></span>  
  
-   <span data-ttu-id="4f5e4-120">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-120">Step 4.</span></span> <span data-ttu-id="4f5e4-121">Identificar las tecnologías y técnicas de mitigación</span><span class="sxs-lookup"><span data-stu-id="4f5e4-121">Identify Mitigation Techniques and Technologies</span></span>  
  
-   <span data-ttu-id="4f5e4-122">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-122">Step 5.</span></span> <span data-ttu-id="4f5e4-123">Modelo de seguridad de documento y las consideraciones de implementación</span><span class="sxs-lookup"><span data-stu-id="4f5e4-123">Document Security Model and Deployment Considerations</span></span>  
  
-   <span data-ttu-id="4f5e4-124">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-124">Step 6.</span></span> <span data-ttu-id="4f5e4-125">Implementar y probar las mitigaciones</span><span class="sxs-lookup"><span data-stu-id="4f5e4-125">Implement and Test Mitigations</span></span>  
  
-   <span data-ttu-id="4f5e4-126">Paso 7.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-126">Step 7.</span></span> <span data-ttu-id="4f5e4-127">Mantener el modelo de amenazas sincronizado con el diseño</span><span class="sxs-lookup"><span data-stu-id="4f5e4-127">Keep the Threat Model in Sync with Design</span></span>  
  
## <a name="step-1-collect-background-information"></a><span data-ttu-id="4f5e4-128">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-128">Step 1.</span></span> <span data-ttu-id="4f5e4-129">Recopilar información básica</span><span class="sxs-lookup"><span data-stu-id="4f5e4-129">Collect Background Information</span></span>  
 <span data-ttu-id="4f5e4-130">Para preparar un TMA correcto, debe recopilar información básica.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-130">To prepare for a successful TMA, you have to collect some background information.</span></span> <span data-ttu-id="4f5e4-131">Resulta de utilidad analizar el entorno de destino (una aplicación, un programa o la infraestructura completa) de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f5e4-131">It is useful to analyze your target environment (an application, program, or the whole infrastructure) as follows:</span></span>  
  
-   <span data-ttu-id="4f5e4-132">Identificar escenarios de casos de uso.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-132">Identify use-case scenarios.</span></span> <span data-ttu-id="4f5e4-133">En cada escenario de caso de uso de su entorno de destino, identifique cómo espera que su empresa utilice el entorno de destino, así como las limitaciones y restricciones del entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-133">For each use-case scenario for your target environment, identify how you expect your company to use the target environment, and any limitations or restrictions on the target environment.</span></span> <span data-ttu-id="4f5e4-134">Esta información ayuda a definir el ámbito de discusión del modelo de amenazas, y proporciona los indicadores a los activos (cualquier elemento de valor de la empresa, como, por ejemplo, la información y los equipos) y los puntos de entrada.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-134">This information helps define the scope of the threat model discussion, and provides pointers to assets (anything of value to your company, such as data and computers) and entry points.</span></span>  
  
-   <span data-ttu-id="4f5e4-135">Crear un diagrama de flujo de datos (DFD) para cada escenario.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-135">Create a data flow diagram (DFD) for each scenario.</span></span> <span data-ttu-id="4f5e4-136">Asegúrese de que profundiza lo suficiente para entender las amenazas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-136">Make sure that you go deep enough to understand your threats.</span></span>  
  
-   <span data-ttu-id="4f5e4-137">Determinar los límites y el ámbito del entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-137">Determine the boundaries and scope of the target environment.</span></span>  
  
-   <span data-ttu-id="4f5e4-138">Comprender los límites entre los componentes que son de confianza y los que no lo son.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-138">Understand the boundaries between trusted and untrusted components.</span></span>  
  
-   <span data-ttu-id="4f5e4-139">Comprender el modelo de administración y configuración de cada componente.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-139">Understand the configuration and administration model for each component.</span></span>  
  
-   <span data-ttu-id="4f5e4-140">Crear una lista de dependencias externas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-140">Create a list of external dependencies.</span></span>  
  
-   <span data-ttu-id="4f5e4-141">Crear una lista de supuestos acerca de los componentes de los que depende cada componente.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-141">Create a list of assumptions about other components on which each component depends.</span></span> <span data-ttu-id="4f5e4-142">Esto ayuda a validar los elementos de seguimiento, los elementos de acción y los supuestos derivados de varios componentes con otros equipos.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-142">This helps validate cross-component assumptions, action items, and follow-up items with other teams.</span></span>  
  
## <a name="step-2-create-and-analyze-the-threat-model"></a><span data-ttu-id="4f5e4-143">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-143">Step 2.</span></span> <span data-ttu-id="4f5e4-144">Crear y analizar el modelo de amenazas</span><span class="sxs-lookup"><span data-stu-id="4f5e4-144">Create and Analyze the Threat Model</span></span>  
 <span data-ttu-id="4f5e4-145">Después de recopilar la información básica, debe concertar una o varias reuniones sobre el modelo de amenazas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-145">After you collect the background information, you should have a threat model meeting or meetings.</span></span> <span data-ttu-id="4f5e4-146">Asegúrese de que a dicha reunión asiste, al menos, un miembro de cada disciplina de desarrollo, como, por ejemplo, los administradores de programa, programadores y evaluadores.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-146">Make sure that at least one member of each development discipline (for example, program managers, developers, and testers) is at the meeting.</span></span> <span data-ttu-id="4f5e4-147">Procure también recordar a los asistentes que el objetivo de la reunión se encuentra en detectar amenazas, no en solucionarlas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-147">Make sure that you remind the attendees that the goal of the meeting is to find threats, not to fix them.</span></span> <span data-ttu-id="4f5e4-148">Durante la reunión sobre el modelo de amenazas, lleve a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4f5e4-148">During the threat model meeting, do the following:</span></span>  
  
-   <span data-ttu-id="4f5e4-149">Examine el DFD en cada caso de uso.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-149">Examine the DFD for each use case.</span></span> <span data-ttu-id="4f5e4-150">En cada uno de estos casos, identifique los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f5e4-150">For each use case identify:</span></span>  
  
    -   <span data-ttu-id="4f5e4-151">Puntos de entrada</span><span class="sxs-lookup"><span data-stu-id="4f5e4-151">Entry points</span></span>  
  
    -   <span data-ttu-id="4f5e4-152">Límites de confianza</span><span class="sxs-lookup"><span data-stu-id="4f5e4-152">Trust boundaries</span></span>  
  
    -   <span data-ttu-id="4f5e4-153">Flujo de datos desde el punto de entrada hasta su última ubicación (y al contrario)</span><span class="sxs-lookup"><span data-stu-id="4f5e4-153">Flow of data from entry point to final resting location (and back)</span></span>  
  
-   <span data-ttu-id="4f5e4-154">Anote los activos implicados.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-154">Note the assets involved.</span></span>  
  
-   <span data-ttu-id="4f5e4-155">Aborde cada DFD y busque las amenazas en las siguientes categorías para todas las entradas de DFD: **S**poofing identificar, **T**lteración con datos, **R**epudiation, **I**revelación de información, **d.**denegación de servicio, y **E**levación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-155">Discuss each DFD, and look for threats in the following categories for all entries in the DFD: **S**poofing identify, **T**ampering with data, **R**epudiation, **I**nformation disclosure, **D**enial of service, and **E**levation of privileges.</span></span>  
  
-   <span data-ttu-id="4f5e4-156">Cree una lista de amenazas identificadas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-156">Create a list of the identified threats.</span></span> <span data-ttu-id="4f5e4-157">Se recomienda que esta lista incluya lo siguiente: título, descripción breve (incluyendo los árboles de amenazas), activo (activo), impactos, riesgo, técnicas de mitigación, estado de mitigación y número de error.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-157">We recommend that this list include the following: title, brief description (including threat trees), asset (asset), impact(s), risk, mitigation techniques, mitigation status, and a bug number.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f5e4-158">Puede agregar las categorías de riesgo, técnicas de mitigación y estado de mitigación al revisar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-158">You can add risk, mitigation techniques, and mitigation status as you review the threats.</span></span> <span data-ttu-id="4f5e4-159">No invierta demasiado tiempo en estas áreas durante la reunión sobre el modelo de amenazas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-159">Do not spend too much time in these areas during the threat model meeting.</span></span>  
  
## <a name="step-3-review-threats"></a><span data-ttu-id="4f5e4-160">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-160">Step 3.</span></span> <span data-ttu-id="4f5e4-161">Analizar las amenazas</span><span class="sxs-lookup"><span data-stu-id="4f5e4-161">Review Threats</span></span>  
 <span data-ttu-id="4f5e4-162">Una vez identificadas las amenazas del entorno, debe valorar el riesgo de cada una de ellas y determinar cómo va a actuar ante ellas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-162">After you have identified the threats to your environment, you must rank the risk of each threat and determine how you want to respond to each threat.</span></span> <span data-ttu-id="4f5e4-163">Para ello puede convocar nuevas reuniones o utilizar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-163">You can do this with additional team meetings or through e-mail.</span></span> <span data-ttu-id="4f5e4-164">Puede usar las siguientes categorías de efecto para calcular la exposición al riesgo: **d.**años potenciales, **R**apacidad de reproducción, **E**provechamiento, **una**usuarios afectados y **d.**capacidad de descubrimiento.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-164">You can use the following effect categories to calculate risk exposure: **D**amage potential, **R**eproducibility, **E**xploitability, **A**ffected users, and **D**iscoverability.</span></span>  
  
 <span data-ttu-id="4f5e4-165">Cuando disponga de una lista de las amenazas que ponen en peligro su entorno de destino en función del riesgo, debe determinar cómo actuará ante cada una.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-165">After you have a list of the threats to your target environment prioritized by risk, you must determine how you will respond to each threat.</span></span> <span data-ttu-id="4f5e4-166">Su respuesta puede ser no hacer nada (aunque ésta no suele ser una buena opción), advertir a los usuarios del posible problema o eliminar el problema o solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-166">Your response can be to do nothing (rarely a good choice), warn users about the potential problem, remove the problem, or fix the problem.</span></span>  
  
## <a name="step-4-identify-mitigation-techniques-and-technologies"></a><span data-ttu-id="4f5e4-167">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-167">Step 4.</span></span> <span data-ttu-id="4f5e4-168">Identificar las tecnologías y técnicas de mitigación</span><span class="sxs-lookup"><span data-stu-id="4f5e4-168">Identify Mitigation Techniques and Technologies</span></span>  
 <span data-ttu-id="4f5e4-169">Después de identificar las amenazas que se van a solucionar, debe determinar las técnicas de mitigación disponibles para cada amenaza, así como la tecnología más adecuada para reducir su efecto.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-169">After you identify which threats you will fix, you must determine the available mitigation techniques for each threat, and the most appropriate technology to reduce the effect of each threat.</span></span>  
  
 <span data-ttu-id="4f5e4-170">Por ejemplo, en función de los detalles del entorno de destino, es posible reducir el efecto de las amenazas de alteración de datos con técnicas de autorización.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-170">For example, depending on the details of your target environment, you can reduce the effect of data-tamper threats by using authorization techniques.</span></span> <span data-ttu-id="4f5e4-171">A continuación, debe determinar la tecnología de autorización más adecuada, como, por ejemplo, las listas de control de acceso discrecional (DACL), los permisos o las restricciones IP.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-171">You then have to determine the appropriate authorization technology to use (for example, discretionary access control lists (DACLs), permissions, or IP restrictions).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4f5e4-172">Al evaluar las tecnologías y técnicas de mitigación que se van a utilizar, debe tener en cuenta los fundamentos de la empresa y aquellas directivas propias que pueden afectar la elección de técnicas de mitigación determinadas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-172">When you evaluate mitigation techniques and technologies to use, you must consider what makes business sense for your company, and any policies your company has that might affect the mitigation technique to choose.</span></span>  
  
 <span data-ttu-id="4f5e4-173">Una vez que ha completado el TMA, realice las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4f5e4-173">After you complete the TMA, do the following:</span></span>  
  
-   <span data-ttu-id="4f5e4-174">Documentar el modelo de seguridad y las consideraciones de implementación</span><span class="sxs-lookup"><span data-stu-id="4f5e4-174">Document the security model and deployment considerations</span></span>  
  
-   <span data-ttu-id="4f5e4-175">Implementar y probar las mitigaciones</span><span class="sxs-lookup"><span data-stu-id="4f5e4-175">Implement and test mitigations</span></span>  
  
-   <span data-ttu-id="4f5e4-176">Mantener el modelo de amenazas sincronizado con el diseño</span><span class="sxs-lookup"><span data-stu-id="4f5e4-176">Keep the threat model synchronized with design</span></span>  
  
## <a name="step-5-document-security-model-and-deployment-considerations"></a><span data-ttu-id="4f5e4-177">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-177">Step 5.</span></span> <span data-ttu-id="4f5e4-178">Modelo de seguridad de documento y las consideraciones de implementación</span><span class="sxs-lookup"><span data-stu-id="4f5e4-178">Document Security Model and Deployment Considerations</span></span>  
 <span data-ttu-id="4f5e4-179">Resulta de gran valor documentar todo aquello que se descubre durante el TMA y la forma en que se decide reducir el efecto de las amenazas de su entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-179">It is valuable to document what you discover during the TMA and how you decide to reduce the effect of the threats to your target environment.</span></span> <span data-ttu-id="4f5e4-180">Esta documentación puede ser de gran ayuda en los controles de calidad (QA), pruebas y soportes, así como para el personal de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-180">This documentation can be useful to quality assurance (QA), test, support, and operations personnel.</span></span> <span data-ttu-id="4f5e4-181">Incluya información sobre las aplicaciones que interactúan o funcionan con el entorno de destino, así como los requisitos y recomendaciones de topologías y servidores de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-181">Include information about other applications that interact or interface with your target environment, and the firewall and topology recommendations and requirements.</span></span>  
  
## <a name="step-6-implement-and-test-mitigations"></a><span data-ttu-id="4f5e4-182">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-182">Step 6.</span></span> <span data-ttu-id="4f5e4-183">Implementar y probar las mitigaciones</span><span class="sxs-lookup"><span data-stu-id="4f5e4-183">Implement and Test Mitigations</span></span>  
 <span data-ttu-id="4f5e4-184">Cuando el equipo está preparado para solucionar las amenazas que se han identificado durante el TMA, asegúrese de que utiliza listas de comprobación de implementación y desarrollo. Gracias a ellas podrá seguir las normativas de implementación y código seguro que le ayudarán a minimizar la entrada de nuevas amenazas.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-184">When your team is ready to fix threats identified during the TMA, make sure you use development and deployment checklists to follow secure code and deployment standards that will help minimize the introduction of new threats.</span></span>  
  
 <span data-ttu-id="4f5e4-185">Tras implementar una mitigación, pruébela para asegurarse de que proporciona el nivel de protección adecuado para la amenaza.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-185">After you implement a mitigation, make sure you test it to make sure it provides the level of protection that you want for the threat.</span></span>  
  
## <a name="step-7-keep-the-threat-model-in-sync-with-design"></a><span data-ttu-id="4f5e4-186">Paso 7.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-186">Step 7.</span></span> <span data-ttu-id="4f5e4-187">Mantener el modelo de amenazas sincronizado con el diseño</span><span class="sxs-lookup"><span data-stu-id="4f5e4-187">Keep the Threat Model in Sync with Design</span></span>  
 <span data-ttu-id="4f5e4-188">A medida que agrega aplicaciones nuevas, servidores y otros elementos a su entorno, asegúrese de que revisa los hallazgos del análisis de modelo de amenazas y de que realiza otros análisis para obtener nuevas funciones.</span><span class="sxs-lookup"><span data-stu-id="4f5e4-188">As you add new applications, servers, and other elements to your environment, make sure that you revisit the findings of the threat model analysis and do TMAs for any new functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f5e4-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f5e4-189">See Also</span></span>  
<span data-ttu-id="4f5e4-190">[Casos prácticos de seguridad para pequeñas y medianas empresas](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="4f5e4-190">[Security Case Studies for Small to Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="4f5e4-191">Escenarios de ejemplo para el análisis de modelo de amenaza</span><span class="sxs-lookup"><span data-stu-id="4f5e4-191">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)