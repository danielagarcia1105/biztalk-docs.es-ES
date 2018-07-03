---
title: Planeación de la solución de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f337efa7b72a40c37a4cc3f42a2bd5d846923dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970957"
---
# <a name="plan-for-your-biztalk-solution"></a><span data-ttu-id="c3178-102">Plan para la solución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c3178-102">Plan for your BizTalk Solution</span></span>
<span data-ttu-id="c3178-103">Uno de los objetivos principales del diseño de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consiste en proporcionar la máxima flexibilidad para adaptar los escenarios de procesamiento tantos como sea posible.</span><span class="sxs-lookup"><span data-stu-id="c3178-103">One of the primary design goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="c3178-104">Debido a este gran flexibilidad, uno de los principales desafíos que enfrentan los desarrolladores de una solución de BizTalk consiste en determinar cómo hacer mejor uso de las características disponibles en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para mejor sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="c3178-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to best meet their business needs.</span></span> <span data-ttu-id="c3178-105">Planear la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede dividirse en fases que se resumen a continuación.</span><span class="sxs-lookup"><span data-stu-id="c3178-105">Planning the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be broken down into distinct phases which are summarized below.</span></span>  
  
## <a name="scoping-the-solution"></a><span data-ttu-id="c3178-106">Definir el ámbito de la solución</span><span class="sxs-lookup"><span data-stu-id="c3178-106">Scoping the Solution</span></span>  
  
### <a name="performance-considerations"></a><span data-ttu-id="c3178-107">Consideraciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="c3178-107">Performance Considerations</span></span>  
 <span data-ttu-id="c3178-108">Al definir el ámbito de la solución de BizTalk, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3178-108">Consider the following when scoping your BizTalk solution:</span></span>  
  
- <span data-ttu-id="c3178-109">¿Qué adaptadores o aceleradores son necesarios?</span><span class="sxs-lookup"><span data-stu-id="c3178-109">Which adapters and/or accelerators are required?</span></span>  
  
- <span data-ttu-id="c3178-110">¿Cuáles son los requisitos para implementar las orquestaciones en la solución?</span><span class="sxs-lookup"><span data-stu-id="c3178-110">What are the requirements for implementing orchestrations in the solution?</span></span>  
  
- <span data-ttu-id="c3178-111">Requisitos de rendimiento de documento: ¿Cuáles son los requisitos de rendimiento máximo sostenible para la solución?</span><span class="sxs-lookup"><span data-stu-id="c3178-111">Document throughput requirements: What are the maximum sustainable throughput requirements for the solution?</span></span>  
  
- <span data-ttu-id="c3178-112">¿Requisitos de latencia: cómo responde la solución tiene que ser para escenarios de solicitud-respuesta y de petición-respuesta?</span><span class="sxs-lookup"><span data-stu-id="c3178-112">Latency requirements: How responsive does the solution need to be for solicit-response and request-response scenarios?</span></span>  
  
- <span data-ttu-id="c3178-113">¿Grado recupera la solución de períodos de máxima carga de documento?</span><span class="sxs-lookup"><span data-stu-id="c3178-113">How well does the solution recover from periods of peak document load?</span></span>  
  
- <span data-ttu-id="c3178-114">¿Cuáles son los requisitos de alta disponibilidad de la solución?</span><span class="sxs-lookup"><span data-stu-id="c3178-114">What are the high availability requirements of the solution?</span></span>  
  
- <span data-ttu-id="c3178-115">¿Cuáles son los requisitos de seguimiento de documentos de la solución?</span><span class="sxs-lookup"><span data-stu-id="c3178-115">What are the document tracking requirements of the solution?</span></span>  
  
- <span data-ttu-id="c3178-116">¿Cuáles son las características de rendimiento de las aplicaciones dependientes, como un servicio Web remoto u otro sistema?</span><span class="sxs-lookup"><span data-stu-id="c3178-116">What are the performance characteristics of any dependent applications such as a remote Web service or other system?</span></span> <span data-ttu-id="c3178-117">Si las aplicaciones dependientes no Manténgase al día de la carga necesarios, a continuación, el rendimiento general del sistema se degradará en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="c3178-117">If dependent applications do not keep up with the required load then the overall system performance will be degraded accordingly.</span></span>  
  
- <span data-ttu-id="c3178-118">¿La aplicación de BizTalk consuma las bases de datos no relacionados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]?</span><span class="sxs-lookup"><span data-stu-id="c3178-118">Would the BizTalk application be consuming databases not related to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]?</span></span> <span data-ttu-id="c3178-119">¿Por ejemplo, si la aplicación de BizTalk está consumiendo tablas en una base de datos de SQL Server mediante el adaptador de SQL, las tablas de forma eficaz configuradas?</span><span class="sxs-lookup"><span data-stu-id="c3178-119">For example, if the BizTalk application is consuming tables in a SQL Server database using the SQL adapter, are the tables efficiently configured?</span></span>  
  
### <a name="hardware-considerations"></a><span data-ttu-id="c3178-120">Consideraciones acerca del hardware</span><span class="sxs-lookup"><span data-stu-id="c3178-120">Hardware Considerations</span></span>  
 <span data-ttu-id="c3178-121">Al definir el ámbito de la solución, cree un diagrama de hardware de alto nivel que incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3178-121">When scoping the solution, create a high-level hardware diagram that includes the following:</span></span>  
  
-   <span data-ttu-id="c3178-122">Arquitectura de equipo (por ejemplo, x86, x64 e IA64)</span><span class="sxs-lookup"><span data-stu-id="c3178-122">Computer architecture (such as x86, x64, and IA64)</span></span>  
  
-   <span data-ttu-id="c3178-123">Requisitos de CPU (por ejemplo, tipo, velocidad, número, núcleos y uso de Hyper-Threading)</span><span class="sxs-lookup"><span data-stu-id="c3178-123">CPU requirements (such as type, speed, number, cores, and use of hyperthreading)</span></span>  
  
-   <span data-ttu-id="c3178-124">Requisitos de RAM para cada equipo</span><span class="sxs-lookup"><span data-stu-id="c3178-124">RAM requirements for each computer</span></span>  
  
-   <span data-ttu-id="c3178-125">Almacenamiento en disco local (tipo, tamaño, velocidad)</span><span class="sxs-lookup"><span data-stu-id="c3178-125">Local disk storage (type, size, speed)</span></span>  
  
-   <span data-ttu-id="c3178-126">SAN (requisitos de almacenamiento: número de LUN; Tipo de tarjeta de SAN)</span><span class="sxs-lookup"><span data-stu-id="c3178-126">SAN (storage requirements: number of LUNS; SAN card type)</span></span>  
  
-   <span data-ttu-id="c3178-127">Tarjetas de red (número de cada equipo, 100 megabits (Mbps) en lugar de 1 Gigabit (1 Gbps).)</span><span class="sxs-lookup"><span data-stu-id="c3178-127">Network cards (number in each computer, 100 megabits (Mbps) versus 1 Gigabit (1 Gbps).)</span></span>  
  
-   <span data-ttu-id="c3178-128">¿Cómo se implementarán los firewalls en la solución?</span><span class="sxs-lookup"><span data-stu-id="c3178-128">How will firewalls be deployed in the solution?</span></span>  
  
-   <span data-ttu-id="c3178-129">¿Se usará el equilibrio de carga de red de hardware?</span><span class="sxs-lookup"><span data-stu-id="c3178-129">Will Network Load Balancing hardware be used?</span></span>  
  
-   <span data-ttu-id="c3178-130">¿Son equipos específicos se agrupará?</span><span class="sxs-lookup"><span data-stu-id="c3178-130">Are specific computers to be clustered?</span></span>  
  
-   <span data-ttu-id="c3178-131">¿Va a utilizar un entorno virtual que afectan a Microsoft Hyper-V Server u otros productos de virtualización?</span><span class="sxs-lookup"><span data-stu-id="c3178-131">Would you be using a virtual environment involving Microsoft Hyper-V Server or any other virtualization products?</span></span>  
  
## <a name="planning-the-solution"></a><span data-ttu-id="c3178-132">Planeación de la solución</span><span class="sxs-lookup"><span data-stu-id="c3178-132">Planning the Solution</span></span>  
  
### <a name="solution-milestones-timeline"></a><span data-ttu-id="c3178-133">Escala de tiempo de los hitos de solución</span><span class="sxs-lookup"><span data-stu-id="c3178-133">Solution Milestones Timeline</span></span>  
 <span data-ttu-id="c3178-134">Crear una programación con hitos para completar los aspectos específicos de la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c3178-134">Create a schedule with milestones for completing specific aspects of your BizTalk solution.</span></span> <span data-ttu-id="c3178-135">Establecer los hitos específicos, aumentará la probabilidad de que será la solución completa de manera oportuna.</span><span class="sxs-lookup"><span data-stu-id="c3178-135">Setting specific milestones will increase the likelihood that the solution will be completed in a timely manner.</span></span>  
  
### <a name="non-microsoft-software-considerations"></a><span data-ttu-id="c3178-136">Consideraciones de Software que no sea de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c3178-136">Non-Microsoft Software Considerations</span></span>  
 <span data-ttu-id="c3178-137">Cuando el software ajeno a Microsoft se usará con la solución, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3178-137">Consider the following when non-Microsoft software will be used with the solution:</span></span>  
  
-   <span data-ttu-id="c3178-138">Determinar cómo el software o hardware necesarios se obtienen.</span><span class="sxs-lookup"><span data-stu-id="c3178-138">Determine how the software or hardware required be obtained.</span></span>  
  
-   <span data-ttu-id="c3178-139">Planear la capacidad y ajuste de tamaño para asegurarse de que el software que no son de Microsoft no es un cuello de botella en la solución.</span><span class="sxs-lookup"><span data-stu-id="c3178-139">Plan for capacity and sizing to ensure that non-Microsoft software does not become a bottleneck in your solution.</span></span>  
  
-   <span data-ttu-id="c3178-140">Determinar un plan de acción para la instalación requiere software ajeno a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3178-140">Determine a plan of action for installing required non-Microsoft software.</span></span>  
  
-   <span data-ttu-id="c3178-141">Crear un plan de acción para configurar y optimizar el software necesario de que no sean de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3178-141">Create a plan of action for configuring and optimizing required non-Microsoft software.</span></span>  
  
## <a name="preparing-for-the-solution"></a><span data-ttu-id="c3178-142">Preparación para la solución</span><span class="sxs-lookup"><span data-stu-id="c3178-142">Preparing for the Solution</span></span>  
 <span data-ttu-id="c3178-143">Incluir los siguientes elementos en la fase de preparación:</span><span class="sxs-lookup"><span data-stu-id="c3178-143">Include the following elements in your preparation phase:</span></span>  
  
### <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="c3178-144">Diseño detallado de la plataforma de soluciones</span><span class="sxs-lookup"><span data-stu-id="c3178-144">Detailed Design of the Solution Platform</span></span>  
 <span data-ttu-id="c3178-145">Un diseño de solución detallada facilita las comunicaciones y evita las suposiciones, lo que mejorarán la agilidad y la eficacia de todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="c3178-145">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="c3178-146">Debe documentar completamente los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c3178-146">You should fully document the following elements:</span></span>  
  
- <span data-ttu-id="c3178-147">Las bases de datos de BizTalk Server y cómo se distribuirá en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="c3178-147">BizTalk Server databases and how they will be distributed across computers.</span></span>  
  
- <span data-ttu-id="c3178-148">Diseño de Host de BizTalk y las descripciones de cada host y sus instancias.</span><span class="sxs-lookup"><span data-stu-id="c3178-148">BizTalk Host design and descriptions of each host and their instances.</span></span>  
  
- <span data-ttu-id="c3178-149">Descripción de cada orquestación.</span><span class="sxs-lookup"><span data-stu-id="c3178-149">Description of each orchestration.</span></span>  
  
- <span data-ttu-id="c3178-150">Descripción de cada canalización.</span><span class="sxs-lookup"><span data-stu-id="c3178-150">Description of each pipeline.</span></span>  
  
- <span data-ttu-id="c3178-151">Descripción de los componentes personalizados como ensamblados .NET y componentes COM +.</span><span class="sxs-lookup"><span data-stu-id="c3178-151">Description of custom components such as .NET assemblies and COM+ components.</span></span>  
  
  <span data-ttu-id="c3178-152">**Diagramas de flujo de mensajes**</span><span class="sxs-lookup"><span data-stu-id="c3178-152">**Message Flow Diagrams**</span></span>  
  
  <span data-ttu-id="c3178-153">Crear diagramas de flujo de mensaje detallado para ayudar a evitar cualquier confusión o false suposiciones con respecto a qué tiene que estar ocurriendo con los mensajes durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c3178-153">Create detailed message flow diagrams to help avoid any confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span> <span data-ttu-id="c3178-154">Al crear los diagramas de flujo de mensaje, se deben considerar los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="c3178-154">The following details should be considered when creating the message flow diagrams:</span></span>  
  
- <span data-ttu-id="c3178-155">Describe el ciclo de vida de cada tipo de mensaje desde el momento en que llega a una ubicación de recepción hasta que todos los mensajes resultantes se envían y se ha completado todo el procesamiento relacionado.</span><span class="sxs-lookup"><span data-stu-id="c3178-155">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
- <span data-ttu-id="c3178-156">Describe cómo cambia el procesamiento de las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="c3178-156">Describe how processing changes for error conditions.</span></span>  
  
- <span data-ttu-id="c3178-157">Incluir detalles sobre la correlación, las notificaciones de entrega y confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="c3178-157">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
- <span data-ttu-id="c3178-158">Incluir información de requisitos de rendimiento con respecto a la latencia y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c3178-158">Include performance requirement information regarding latency and throughput.</span></span>  
  
  <span data-ttu-id="c3178-159">**Detalles de Software que no sea de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="c3178-159">**Non-Microsoft Software Details**</span></span>  
  
  <span data-ttu-id="c3178-160">Se debe documentar completamente todo el software que no son de Microsoft que se usa como parte del diseño de la solución detallada.</span><span class="sxs-lookup"><span data-stu-id="c3178-160">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
  <span data-ttu-id="c3178-161">**Pila detallado del Hardware**</span><span class="sxs-lookup"><span data-stu-id="c3178-161">**Detailed Hardware Stack**</span></span>  
  
  <span data-ttu-id="c3178-162">Compilar en el diagrama de hardware de alto nivel creada anteriormente, la siguiente información de hardware debe estar completamente documentada:</span><span class="sxs-lookup"><span data-stu-id="c3178-162">Building on the previously created high level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
- <span data-ttu-id="c3178-163">Procesadores</span><span class="sxs-lookup"><span data-stu-id="c3178-163">Processors</span></span>  
  
  -   <span data-ttu-id="c3178-164">Tipo</span><span class="sxs-lookup"><span data-stu-id="c3178-164">Type</span></span>  
  
  -   <span data-ttu-id="c3178-165">Velocidad</span><span class="sxs-lookup"><span data-stu-id="c3178-165">Speed</span></span>  
  
  -   <span data-ttu-id="c3178-166">Número de núcleos</span><span class="sxs-lookup"><span data-stu-id="c3178-166">Number of cores</span></span>  
  
  -   <span data-ttu-id="c3178-167">Hyperthreading</span><span class="sxs-lookup"><span data-stu-id="c3178-167">Hyperthreading</span></span>  
  
- <span data-ttu-id="c3178-168">Memoria</span><span class="sxs-lookup"><span data-stu-id="c3178-168">Memory</span></span>  
  
  -   <span data-ttu-id="c3178-169">Amount</span><span class="sxs-lookup"><span data-stu-id="c3178-169">Amount</span></span>  
  
  -   <span data-ttu-id="c3178-170">Velocidad</span><span class="sxs-lookup"><span data-stu-id="c3178-170">Speed</span></span>  
  
  -   <span data-ttu-id="c3178-171">Paridad</span><span class="sxs-lookup"><span data-stu-id="c3178-171">Parity</span></span>  
  
- <span data-ttu-id="c3178-172">red</span><span class="sxs-lookup"><span data-stu-id="c3178-172">Network</span></span>  
  
  -   <span data-ttu-id="c3178-173">Número de tarjetas de interfaz de red (NIC)</span><span class="sxs-lookup"><span data-stu-id="c3178-173">Number of network interface cards (NICs)</span></span>  
  
  -   <span data-ttu-id="c3178-174">Velocidad de red</span><span class="sxs-lookup"><span data-stu-id="c3178-174">Speed of network</span></span>  
  
- <span data-ttu-id="c3178-175">SAN</span><span class="sxs-lookup"><span data-stu-id="c3178-175">SAN</span></span>  
  
  -   <span data-ttu-id="c3178-176">Número de tarjetas de SAN en cada equipo</span><span class="sxs-lookup"><span data-stu-id="c3178-176">Number of SAN cards in each computer</span></span>  
  
  -   <span data-ttu-id="c3178-177">Número de números de unidad lógica (LUN) para cada equipo y el propósito de cada LUN.</span><span class="sxs-lookup"><span data-stu-id="c3178-177">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
  -   <span data-ttu-id="c3178-178">Velocidad del área de almacenamiento (SAN) tarjetas de red</span><span class="sxs-lookup"><span data-stu-id="c3178-178">Speed of storage area network (SAN) Cards</span></span>  
  
  -   <span data-ttu-id="c3178-179">Detalles de configuración de tarjeta de SAN</span><span class="sxs-lookup"><span data-stu-id="c3178-179">SAN card configuration details</span></span>  
  
  -   <span data-ttu-id="c3178-180">Asignación de disco SAN, formato y creación de particiones</span><span class="sxs-lookup"><span data-stu-id="c3178-180">SAN disk allocation, formatting, and partitioning</span></span>  
  
- <span data-ttu-id="c3178-181">Disco</span><span class="sxs-lookup"><span data-stu-id="c3178-181">Disk</span></span>  
  
  -   <span data-ttu-id="c3178-182">Detalles del disco local para cada equipo</span><span class="sxs-lookup"><span data-stu-id="c3178-182">Local disk details for each computer</span></span>  
  
  -   <span data-ttu-id="c3178-183">Formato utilizado para discos locales</span><span class="sxs-lookup"><span data-stu-id="c3178-183">Formatting used for local disks</span></span>  
  
  -   <span data-ttu-id="c3178-184">Detalles de creación de particiones de discos locales</span><span class="sxs-lookup"><span data-stu-id="c3178-184">Partitioning details for local disks</span></span>  
  
- <span data-ttu-id="c3178-185">Cache</span><span class="sxs-lookup"><span data-stu-id="c3178-185">Cache</span></span>  
  
  -   <span data-ttu-id="c3178-186">Cantidad de caché L2</span><span class="sxs-lookup"><span data-stu-id="c3178-186">L2 Cache amount</span></span>  
  
  -   <span data-ttu-id="c3178-187">Cantidad de caché L3</span><span class="sxs-lookup"><span data-stu-id="c3178-187">L3 Cache amount</span></span>  
  
  <span data-ttu-id="c3178-188">**Pila detallado del Software**</span><span class="sxs-lookup"><span data-stu-id="c3178-188">**Detailed Software Stack**</span></span>  
  
  <span data-ttu-id="c3178-189">La siguiente información de software se debe documentar:</span><span class="sxs-lookup"><span data-stu-id="c3178-189">The following software information should be documented:</span></span>  
  
- <span data-ttu-id="c3178-190">Arquitectura, las ediciones y versiones de sistema operativo específico</span><span class="sxs-lookup"><span data-stu-id="c3178-190">Specific operating system versions, editions, and architecture</span></span>  
  
- <span data-ttu-id="c3178-191">Características del sistema operativo específico</span><span class="sxs-lookup"><span data-stu-id="c3178-191">Specific operating system features</span></span>  
  
- <span data-ttu-id="c3178-192">Software específico instalado en cada equipo</span><span class="sxs-lookup"><span data-stu-id="c3178-192">Specific software installed on each computer</span></span>  
  
- <span data-ttu-id="c3178-193">Controladores específicos</span><span class="sxs-lookup"><span data-stu-id="c3178-193">Specific drivers</span></span>  
  
- <span data-ttu-id="c3178-194">Service Packs y otras actualizaciones</span><span class="sxs-lookup"><span data-stu-id="c3178-194">Service Packs and other updates</span></span>  
  
- <span data-ttu-id="c3178-195">Valores de configuración para todas las características de software y sistema operativo usa si difieren de los valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="c3178-195">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="building-out-the-environment-for-the-solution"></a><span data-ttu-id="c3178-196">Creación de un entorno para la solución</span><span class="sxs-lookup"><span data-stu-id="c3178-196">Building Out the Environment for the Solution</span></span>  
 <span data-ttu-id="c3178-197">Instrucciones detalladas para instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y son los requisitos de software en el [guías de instalación de BizTalk Server](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="c3178-197">Detailed instructions for installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the software requirements are in the [BizTalk Server Installation Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c3178-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3178-198">See Also</span></span>  
 [<span data-ttu-id="c3178-199">Planificación del nivel de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c3178-199">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)
