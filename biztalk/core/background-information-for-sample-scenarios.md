---
title: "Información acerca de escenarios de ejemplo en segundo plano | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security examples [TMA], background information
- DFD
- TMA, examples
ms.assetid: f9518fe7-9892-44f5-8e05-fe48bdb5161a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dbb247e42116d5b308170d5ef365ed9f20d793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="background-information-for-sample-scenarios"></a><span data-ttu-id="74e70-102">Información general acerca de los escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="74e70-102">Background Information for Sample Scenarios</span></span>
<span data-ttu-id="74e70-103">En este tema se incluye información general acerca de los escenarios de esta sección.</span><span class="sxs-lookup"><span data-stu-id="74e70-103">This topic contains background information for the scenarios in this section.</span></span>  
  
## <a name="background-for-all-scenarios"></a><span data-ttu-id="74e70-104">Información general para todos los escenarios</span><span class="sxs-lookup"><span data-stu-id="74e70-104">Background for all scenarios</span></span>  
 <span data-ttu-id="74e70-105">Antes de la reunión del modelo de amenazas principal, recopilamos la siguiente información general.</span><span class="sxs-lookup"><span data-stu-id="74e70-105">Before the main threat model meeting, we collected the following background information.</span></span> <span data-ttu-id="74e70-106">Esta información es aplicable a todos los escenarios de uso que identificamos en la arquitectura de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="74e70-106">This information applies to all the usage scenarios we identified for the sample architecture:</span></span>  
  
-   <span data-ttu-id="74e70-107">Límites y ámbito de la arquitectura</span><span class="sxs-lookup"><span data-stu-id="74e70-107">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="74e70-108">Límites entre los componentes de confianza y de no confianza</span><span class="sxs-lookup"><span data-stu-id="74e70-108">Boundaries between trusted and untrusted components</span></span>  
  
-   <span data-ttu-id="74e70-109">Modelo de configuración y administración para cada componente</span><span class="sxs-lookup"><span data-stu-id="74e70-109">Configuration and administration model for each component</span></span>  
  
-   <span data-ttu-id="74e70-110">Suposiciones sobre otros componentes y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="74e70-110">Assumptions about other components and applications</span></span>  
  
### <a name="boundaries-and-scope-of-the-architecture"></a><span data-ttu-id="74e70-111">Límites y ámbito de la arquitectura</span><span class="sxs-lookup"><span data-stu-id="74e70-111">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="74e70-112">El servidor de seguridad 2 protege de la red perimetral y de otros dominios del entorno (por ejemplo, los dominios corporativos para otras aplicaciones) a los servidores y aplicaciones pertenecientes al dominio de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="74e70-112">Firewall 2 helps protect the servers and applications in the E-Business domain both from the perimeter network and from any other domains in your environment (for example, a corporate domain or domains for other applications).</span></span>  
  
-   <span data-ttu-id="74e70-113">El servidor de seguridad 2 enruta todo el tráfico entrante y saliente al dominio de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="74e70-113">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="74e70-114">Todas las cuentas y grupos de usuarios que tienen acceso al entorno de BizTalk Server deben ser grupos globales en el dominio de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="74e70-114">All user groups and accounts that access the BizTalk Server environment must be global groups in the E-Business domain.</span></span>  
  
-   <span data-ttu-id="74e70-115">El acceso está limitado a la cuenta de servicio de la instancia de host; a las aplicaciones que descargan mensajes en el servidor de recepción SQL, de archivos o de Message Queue Server, y a los administradores de BizTalk Server, inicio de sesión único (SSO) empresarial y Windows.</span><span class="sxs-lookup"><span data-stu-id="74e70-115">Access is limited to the service account for the host instance; any applications that drop messages in the receive server for File, SQL, or Message Queuing; and administrators for BizTalk Server, Enterprise Single Sign-On (SSO), and Windows.</span></span>  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a><span data-ttu-id="74e70-116">Límites entre los componentes de confianza y de no confianza</span><span class="sxs-lookup"><span data-stu-id="74e70-116">Boundaries between trusted and untrusted companies</span></span>  
  
-   <span data-ttu-id="74e70-117">El servidor de seguridad 2 enruta todo el tráfico entrante y saliente al dominio de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="74e70-117">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="74e70-118">Use hosts de BizTalk distintos como límite de seguridad entre aplicaciones dentro de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="74e70-118">Use different BizTalk Hosts as a security boundary between applications within BizTalk Server.</span></span>  
  
-   <span data-ttu-id="74e70-119">Utilice hosts de confianza sólo si confía en el código de la aplicación (por ejemplo, no ejecute componentes de terceros en un host de confianza).</span><span class="sxs-lookup"><span data-stu-id="74e70-119">Use trusted hosts only when you trust the code within the application (for example, do not run third-party components in a trusted host).</span></span>  
  
### <a name="configuration-and-administration-model-for-each-component"></a><span data-ttu-id="74e70-120">Modelo de configuración y administración para cada componente</span><span class="sxs-lookup"><span data-stu-id="74e70-120">Configuration and administration model for each component</span></span>  
 <span data-ttu-id="74e70-121">**Modelo de configuración:**</span><span class="sxs-lookup"><span data-stu-id="74e70-121">**Configuration model:**</span></span>  
  
-   <span data-ttu-id="74e70-122">Los componentes en tiempo de ejecución de BizTalk Server sólo se instalan en los servidores BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="74e70-122">BizTalk Server runtime components are installed only on the BizTalk Servers.</span></span>  
  
-   <span data-ttu-id="74e70-123">El servidor secreto principal no tiene componentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="74e70-123">Master secret server has no additional components.</span></span>  
  
-   <span data-ttu-id="74e70-124">El servidor SQL contiene todas bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="74e70-124">SQL Server contains all BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="74e70-125">Los servidores de las redes perimetrales no tienen ningún componente de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="74e70-125">Servers in the perimeter networks do not have any BizTalk Server components.</span></span>  
  
-   <span data-ttu-id="74e70-126">El cliente de administración se utiliza para administrar todos los servidores del dominio de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="74e70-126">Administration client is used to administer all servers in the E-Business domain.</span></span>  
  
 <span data-ttu-id="74e70-127">**Modelo de administración:**</span><span class="sxs-lookup"><span data-stu-id="74e70-127">**Administration model:**</span></span>  
  
-   <span data-ttu-id="74e70-128">Desde un equipo de escritorio o portátil, el administrador se conecta al equipo en el que se encuentran las herramientas administrativas (mediante una conexión de Terminal Server o de Escritorio remoto).</span><span class="sxs-lookup"><span data-stu-id="74e70-128">From a desktop (or laptop), an administrator connects to the computer that has the administration tools (using either Terminal Services or Remote Desktop connection).</span></span> <span data-ttu-id="74e70-129">Una vez establecida la conexión al equipo que contiene las herramientas de administración de BizTalk, el administrador puede emplearlas para administrar todos los servidores y aplicaciones del dominio.</span><span class="sxs-lookup"><span data-stu-id="74e70-129">After the administrator connects to the computer that has the administration tools, the administrator can use the BizTalk Administration tools to manage all servers and applications within the domain.</span></span>  
  
### <a name="assumptions-about-other-components-and-applications"></a><span data-ttu-id="74e70-130">Suposiciones sobre otros componentes y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="74e70-130">Assumptions about other components and applications</span></span>  
 <span data-ttu-id="74e70-131">El resto de las aplicaciones y componentes que interactúan con el entorno de BizTalk Server se encuentran en dominios distintos del dominio de negocio electrónico (por ejemplo, en una red perimetral).</span><span class="sxs-lookup"><span data-stu-id="74e70-131">All other applications and components that interact with the BizTalk Server environment are in a domain other than the E-Business domain (for example, in a perimeter network).</span></span> <span data-ttu-id="74e70-132">El tráfico entre esas aplicaciones y componentes y el entorno de BizTalk Server atraviesa el servidor de seguridad 2.</span><span class="sxs-lookup"><span data-stu-id="74e70-132">The traffic from those applications and components to and from the BizTalk Server environment goes through Firewall 2.</span></span>  
  
 <span data-ttu-id="74e70-133">Las aplicaciones de terceros para BizTalk Server proceden de un proveedor de confianza.</span><span class="sxs-lookup"><span data-stu-id="74e70-133">Any third-party applications for BizTalk Server come from a trusted vendor.</span></span>  
  
### <a name="data-flow-diagrams"></a><span data-ttu-id="74e70-134">Diagramas de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="74e70-134">Data flow diagrams</span></span>  
 <span data-ttu-id="74e70-135">El elemento final de la información global de cada escenario de uso es un diagrama de flujo de datos (DFD).</span><span class="sxs-lookup"><span data-stu-id="74e70-135">The final element of background information for each usage scenario is a data flow diagram (DFD).</span></span> <span data-ttu-id="74e70-136">El DFD ilustra el flujo de los datos a través de la arquitectura.</span><span class="sxs-lookup"><span data-stu-id="74e70-136">A DFD illustrates how data flows through the architecture.</span></span> <span data-ttu-id="74e70-137">Hay un DFD diferente para cada escenario.</span><span class="sxs-lookup"><span data-stu-id="74e70-137">Each scenario has a different DFD.</span></span> <span data-ttu-id="74e70-138">En este documento, los diagramas de flujo de datos contienen los elementos que aparecen en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="74e70-138">In this document, the data flow diagrams contain the elements shown in the following figure.</span></span>  
  
 <span data-ttu-id="74e70-139">**Figura 1: elementos de DFD**</span><span class="sxs-lookup"><span data-stu-id="74e70-139">**Figure 1 Elements of the DFD**</span></span>  
  
 <span data-ttu-id="74e70-140">![Elementos de DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span><span class="sxs-lookup"><span data-stu-id="74e70-140">![Elements of the DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span></span>  
  
## <a name="background-for-adapter-scenarios"></a><span data-ttu-id="74e70-141">Información general para escenarios de adaptadores</span><span class="sxs-lookup"><span data-stu-id="74e70-141">Background for adapter scenarios</span></span>  
 <span data-ttu-id="74e70-142">En nuestra arquitectura de ejemplo, hemos identificado los siguientes escenarios de uso basados en algunos de los adaptadores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="74e70-142">In our sample architecture, we identified the following usage scenarios based on some of the adapters you can use out-of-the-box:</span></span>  
  
-   <span data-ttu-id="74e70-143">Escenario de los adaptadores de HTTP y SOAP (servicios Web)</span><span class="sxs-lookup"><span data-stu-id="74e70-143">HTTP and SOAP (Web services) adapters scenario</span></span>  
  
-   <span data-ttu-id="74e70-144">Escenario del adaptador de BizTalk para Message Queue</span><span class="sxs-lookup"><span data-stu-id="74e70-144">BizTalk Message Queuing adapter scenario</span></span>  
  
-   <span data-ttu-id="74e70-145">Escenario del adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="74e70-145">File adapter scenario</span></span>  
  
-   <span data-ttu-id="74e70-146">Escenario del adaptador FTP</span><span class="sxs-lookup"><span data-stu-id="74e70-146">FTP adapter scenario</span></span>  
  
 <span data-ttu-id="74e70-147">En cada escenario, seguimos estos siguientes para completar el análisis del modelo de amenazas:</span><span class="sxs-lookup"><span data-stu-id="74e70-147">For each scenario, we followed these steps to complete the threat model analysis:</span></span>  
  
-   <span data-ttu-id="74e70-148">Recopilar información general</span><span class="sxs-lookup"><span data-stu-id="74e70-148">Collect background information</span></span>  
  
-   <span data-ttu-id="74e70-149">Crear y analizar el modelo de amenazas</span><span class="sxs-lookup"><span data-stu-id="74e70-149">Create and analyze the threat model</span></span>  
  
-   <span data-ttu-id="74e70-150">Analizar las amenazas</span><span class="sxs-lookup"><span data-stu-id="74e70-150">Review threats</span></span>  
  
-   <span data-ttu-id="74e70-151">Identificar las tecnologías y técnicas de mitigación</span><span class="sxs-lookup"><span data-stu-id="74e70-151">Identify mitigation techniques and technologies</span></span>  
  
 <span data-ttu-id="74e70-152">Para cada escenario, hemos intentado desarrollar evaluaciones genéricas del nivel de amenaza que pueden representar los distintos ataques.</span><span class="sxs-lookup"><span data-stu-id="74e70-152">For each scenario, we have tried to develop generic ratings of the level of threat that the various attacks might represent.</span></span> <span data-ttu-id="74e70-153">No obstante, es posible que el entorno o la experiencia sugieran que una determinada amenaza merece una evaluación distinta.</span><span class="sxs-lookup"><span data-stu-id="74e70-153">However, your environment or experience might suggest that a particular threat deserves a different rating than we have given it.</span></span> <span data-ttu-id="74e70-154">Como en todos los escenarios de seguridad, sus propios datos constituyen la base más sólida para determinar los niveles de amenaza. Es recomendable que realice su propio análisis tomando nuestros análisis y resultados como referencia.</span><span class="sxs-lookup"><span data-stu-id="74e70-154">As with all security scenarios, your own data is the most robust to determine threat levels, and we recommend that you conduct your own analysis, using our analysis and results as a guide.</span></span>  
  
 <span data-ttu-id="74e70-155">La información básica, excepto el diagrama de flujo de datos (DFD): es el mismo para los cuatro escenarios de uso.</span><span class="sxs-lookup"><span data-stu-id="74e70-155">The background information—except for the data flow diagram (DFD)—is the same for all our usage scenarios.</span></span> <span data-ttu-id="74e70-156">En las secciones siguientes se muestra el DFD de cada escenario.</span><span class="sxs-lookup"><span data-stu-id="74e70-156">In the next sections we show the DFD for each scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e70-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="74e70-157">See Also</span></span>  
 <span data-ttu-id="74e70-158">[Análisis de modelo de amenazas](../core/threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="74e70-158">[Threat Model Analysis](../core/threat-model-analysis.md) </span></span>  
 <span data-ttu-id="74e70-159">[Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="74e70-159">[Sample Scenarios for Threat Model Analysis](../core/sample-scenarios-for-threat-model-analysis.md) </span></span>  
 <span data-ttu-id="74e70-160">[Planear la seguridad](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="74e70-160">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="74e70-161">Arquitecturas de ejemplo para pequeñas y medianas empresas</span><span class="sxs-lookup"><span data-stu-id="74e70-161">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)