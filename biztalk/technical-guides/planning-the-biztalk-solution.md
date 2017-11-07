---
title: "Planeación de la solución de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 337883ce2ca3b7f28def19898930d872928a8ce4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="plan-for-your-biztalk-solution"></a><span data-ttu-id="e41d5-102">Plan para la solución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e41d5-102">Plan for your BizTalk Solution</span></span>
<span data-ttu-id="e41d5-103">Uno de los objetivos principales de diseño de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consiste en ofrecer la máxima flexibilidad para alojar las situaciones de procesamiento tantos como sea posible.</span><span class="sxs-lookup"><span data-stu-id="e41d5-103">One of the primary design goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="e41d5-104">Debido a esta gran flexibilidad, uno de los principales retos para los desarrolladores de una solución de BizTalk es determinar cómo realizar un mejor uso de las características disponibles en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para mejor sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="e41d5-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to best meet their business needs.</span></span> <span data-ttu-id="e41d5-105">Planear la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede dividirse en distintas fases que se resumen a continuación.</span><span class="sxs-lookup"><span data-stu-id="e41d5-105">Planning the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be broken down into distinct phases which are summarized below.</span></span>  
  
## <a name="scoping-the-solution"></a><span data-ttu-id="e41d5-106">Definir el ámbito de la solución</span><span class="sxs-lookup"><span data-stu-id="e41d5-106">Scoping the Solution</span></span>  
  
### <a name="performance-considerations"></a><span data-ttu-id="e41d5-107">Consideraciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="e41d5-107">Performance Considerations</span></span>  
 <span data-ttu-id="e41d5-108">Al definir el ámbito de la solución de BizTalk, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e41d5-108">Consider the following when scoping your BizTalk solution:</span></span>  
  
-   <span data-ttu-id="e41d5-109">¿Los adaptadores o aceleradores son necesarios?</span><span class="sxs-lookup"><span data-stu-id="e41d5-109">Which adapters and/or accelerators are required?</span></span>  
  
-   <span data-ttu-id="e41d5-110">¿Cuáles son los requisitos para implementar las orquestaciones en la solución?</span><span class="sxs-lookup"><span data-stu-id="e41d5-110">What are the requirements for implementing orchestrations in the solution?</span></span>  
  
-   <span data-ttu-id="e41d5-111">Requisitos de rendimiento de documento: ¿Cuáles son los requisitos de rendimiento máximo sostenible de la solución?</span><span class="sxs-lookup"><span data-stu-id="e41d5-111">Document throughput requirements: What are the maximum sustainable throughput requirements for the solution?</span></span>  
  
-   <span data-ttu-id="e41d5-112">¿Requisitos de latencia: la capacidad de respuesta es la solución necesario para escenarios de petición-respuesta y solicitudes y respuestas?</span><span class="sxs-lookup"><span data-stu-id="e41d5-112">Latency requirements: How responsive does the solution need to be for solicit-response and request-response scenarios?</span></span>  
  
-   <span data-ttu-id="e41d5-113">¿La medida recuperar la solución de períodos de picos de carga de documento?</span><span class="sxs-lookup"><span data-stu-id="e41d5-113">How well does the solution recover from periods of peak document load?</span></span>  
  
-   <span data-ttu-id="e41d5-114">¿Cuáles son los requisitos de alta disponibilidad de la solución?</span><span class="sxs-lookup"><span data-stu-id="e41d5-114">What are the high availability requirements of the solution?</span></span>  
  
-   <span data-ttu-id="e41d5-115">¿Cuáles son los requisitos de seguimiento de documentos de la solución?</span><span class="sxs-lookup"><span data-stu-id="e41d5-115">What are the document tracking requirements of the solution?</span></span>  
  
-   <span data-ttu-id="e41d5-116">¿Cuáles son las características de rendimiento de las aplicaciones dependientes, como un servicio Web remoto u otro sistema?</span><span class="sxs-lookup"><span data-stu-id="e41d5-116">What are the performance characteristics of any dependent applications such as a remote Web service or other system?</span></span> <span data-ttu-id="e41d5-117">Si las aplicaciones dependientes no hacer frente a la carga necesaria, a continuación, el rendimiento general del sistema disminuye en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="e41d5-117">If dependent applications do not keep up with the required load then the overall system performance will be degraded accordingly.</span></span>  
  
-   <span data-ttu-id="e41d5-118">¿La aplicación de BizTalk se consumen las bases de datos no relacionados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]?</span><span class="sxs-lookup"><span data-stu-id="e41d5-118">Would the BizTalk application be consuming databases not related to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]?</span></span> <span data-ttu-id="e41d5-119">¿Por ejemplo, si la aplicación de BizTalk consume tablas en una base de datos de SQL Server mediante el adaptador de SQL, las tablas de forma eficaz configuradas?</span><span class="sxs-lookup"><span data-stu-id="e41d5-119">For example, if the BizTalk application is consuming tables in a SQL Server database using the SQL adapter, are the tables efficiently configured?</span></span>  
  
### <a name="hardware-considerations"></a><span data-ttu-id="e41d5-120">Consideraciones acerca del hardware</span><span class="sxs-lookup"><span data-stu-id="e41d5-120">Hardware Considerations</span></span>  
 <span data-ttu-id="e41d5-121">Al definir el ámbito de la solución, cree un diagrama de hardware de alto nivel que incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e41d5-121">When scoping the solution, create a high-level hardware diagram that includes the following:</span></span>  
  
-   <span data-ttu-id="e41d5-122">Arquitectura del equipo (por ejemplo, x86, x64 e IA64)</span><span class="sxs-lookup"><span data-stu-id="e41d5-122">Computer architecture (such as x86, x64, and IA64)</span></span>  
  
-   <span data-ttu-id="e41d5-123">Requisitos de CPU (por ejemplo, tipo, velocidad, número, núcleos y uso de Hyper-Threading)</span><span class="sxs-lookup"><span data-stu-id="e41d5-123">CPU requirements (such as type, speed, number, cores, and use of hyperthreading)</span></span>  
  
-   <span data-ttu-id="e41d5-124">Requisitos de RAM para cada equipo</span><span class="sxs-lookup"><span data-stu-id="e41d5-124">RAM requirements for each computer</span></span>  
  
-   <span data-ttu-id="e41d5-125">Almacenamiento en disco local (tipo, tamaño, velocidad)</span><span class="sxs-lookup"><span data-stu-id="e41d5-125">Local disk storage (type, size, speed)</span></span>  
  
-   <span data-ttu-id="e41d5-126">SAN (requisitos de almacenamiento: número de LUN; Tipo de tarjeta de SAN)</span><span class="sxs-lookup"><span data-stu-id="e41d5-126">SAN (storage requirements: number of LUNS; SAN card type)</span></span>  
  
-   <span data-ttu-id="e41d5-127">Tarjetas de red (número de cada equipo, 100 megabits (Mbps) en lugar de 1 Gigabit (1 Gbps).)</span><span class="sxs-lookup"><span data-stu-id="e41d5-127">Network cards (number in each computer, 100 megabits (Mbps) versus 1 Gigabit (1 Gbps).)</span></span>  
  
-   <span data-ttu-id="e41d5-128">¿Cómo se implementará firewalls en la solución?</span><span class="sxs-lookup"><span data-stu-id="e41d5-128">How will firewalls be deployed in the solution?</span></span>  
  
-   <span data-ttu-id="e41d5-129">¿Se puede usar hardware de equilibrio de carga de red?</span><span class="sxs-lookup"><span data-stu-id="e41d5-129">Will Network Load Balancing hardware be used?</span></span>  
  
-   <span data-ttu-id="e41d5-130">¿Son los equipos específicos para su agrupación en clústeres?</span><span class="sxs-lookup"><span data-stu-id="e41d5-130">Are specific computers to be clustered?</span></span>  
  
-   <span data-ttu-id="e41d5-131">¿Va a utilizar un entorno virtual que implican Microsoft Hyper-V Server o cualquier otro producto de virtualización?</span><span class="sxs-lookup"><span data-stu-id="e41d5-131">Would you be using a virtual environment involving Microsoft Hyper-V Server or any other virtualization products?</span></span>  
  
## <a name="planning-the-solution"></a><span data-ttu-id="e41d5-132">Planificación de la solución</span><span class="sxs-lookup"><span data-stu-id="e41d5-132">Planning the Solution</span></span>  
  
### <a name="solution-milestones-timeline"></a><span data-ttu-id="e41d5-133">Escala de tiempo de los hitos de solución</span><span class="sxs-lookup"><span data-stu-id="e41d5-133">Solution Milestones Timeline</span></span>  
 <span data-ttu-id="e41d5-134">Crear una programación con hitos para completar los aspectos específicos de la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e41d5-134">Create a schedule with milestones for completing specific aspects of your BizTalk solution.</span></span> <span data-ttu-id="e41d5-135">Establecer los hitos específicos, aumentará la probabilidad de que la solución se completó de manera oportuna.</span><span class="sxs-lookup"><span data-stu-id="e41d5-135">Setting specific milestones will increase the likelihood that the solution will be completed in a timely manner.</span></span>  
  
### <a name="non-microsoft-software-considerations"></a><span data-ttu-id="e41d5-136">Consideraciones de Software que no sea de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e41d5-136">Non-Microsoft Software Considerations</span></span>  
 <span data-ttu-id="e41d5-137">Tenga en cuenta lo siguiente al software de Microsoft no se utilizarán con la solución:</span><span class="sxs-lookup"><span data-stu-id="e41d5-137">Consider the following when non-Microsoft software will be used with the solution:</span></span>  
  
-   <span data-ttu-id="e41d5-138">Determinar cómo el software o hardware necesario obtenido.</span><span class="sxs-lookup"><span data-stu-id="e41d5-138">Determine how the software or hardware required be obtained.</span></span>  
  
-   <span data-ttu-id="e41d5-139">Planear la capacidad y ajuste de tamaño para asegurarse de que el software no sean de Microsoft no es un cuello de botella en la solución.</span><span class="sxs-lookup"><span data-stu-id="e41d5-139">Plan for capacity and sizing to ensure that non-Microsoft software does not become a bottleneck in your solution.</span></span>  
  
-   <span data-ttu-id="e41d5-140">Determinar un plan de acción para la instalación de software de terceros necesarias.</span><span class="sxs-lookup"><span data-stu-id="e41d5-140">Determine a plan of action for installing required non-Microsoft software.</span></span>  
  
-   <span data-ttu-id="e41d5-141">Crear un plan de acción para configurar y optimizar el software de terceros necesarias.</span><span class="sxs-lookup"><span data-stu-id="e41d5-141">Create a plan of action for configuring and optimizing required non-Microsoft software.</span></span>  
  
## <a name="preparing-for-the-solution"></a><span data-ttu-id="e41d5-142">Preparación de la solución</span><span class="sxs-lookup"><span data-stu-id="e41d5-142">Preparing for the Solution</span></span>  
 <span data-ttu-id="e41d5-143">Incluir los elementos siguientes en la fase de preparación:</span><span class="sxs-lookup"><span data-stu-id="e41d5-143">Include the following elements in your preparation phase:</span></span>  
  
### <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="e41d5-144">Diseño detallado de la plataforma de soluciones</span><span class="sxs-lookup"><span data-stu-id="e41d5-144">Detailed Design of the Solution Platform</span></span>  
 <span data-ttu-id="e41d5-145">Un diseño de la solución detallada facilita las comunicaciones y evita suposiciones, lo que mejorarán la agilidad y la eficacia de todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="e41d5-145">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="e41d5-146">Debe documentar completamente los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="e41d5-146">You should fully document the following elements:</span></span>  
  
-   <span data-ttu-id="e41d5-147">Las bases de datos de BizTalk Server y cómo se distribuirán en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="e41d5-147">BizTalk Server databases and how they will be distributed across computers.</span></span>  
  
-   <span data-ttu-id="e41d5-148">Diseño de Host de BizTalk y las descripciones de cada host y sus instancias.</span><span class="sxs-lookup"><span data-stu-id="e41d5-148">BizTalk Host design and descriptions of each host and their instances.</span></span>  
  
-   <span data-ttu-id="e41d5-149">Descripción de cada orquestación.</span><span class="sxs-lookup"><span data-stu-id="e41d5-149">Description of each orchestration.</span></span>  
  
-   <span data-ttu-id="e41d5-150">Descripción de cada canalización.</span><span class="sxs-lookup"><span data-stu-id="e41d5-150">Description of each pipeline.</span></span>  
  
-   <span data-ttu-id="e41d5-151">Descripción de los componentes personalizados, como ensamblados .NET y componentes COM +.</span><span class="sxs-lookup"><span data-stu-id="e41d5-151">Description of custom components such as .NET assemblies and COM+ components.</span></span>  
  
 <span data-ttu-id="e41d5-152">**Diagramas de flujo de mensajes**</span><span class="sxs-lookup"><span data-stu-id="e41d5-152">**Message Flow Diagrams**</span></span>  
  
 <span data-ttu-id="e41d5-153">Crear diagramas de flujo de mensaje detallado para ayudar a evitar cualquier confusión o false suposiciones con respecto a lo que se supone que se está produciendo mensajes durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e41d5-153">Create detailed message flow diagrams to help avoid any confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span> <span data-ttu-id="e41d5-154">Al crear los diagramas de flujo de mensaje, se deben considerar los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="e41d5-154">The following details should be considered when creating the message flow diagrams:</span></span>  
  
-   <span data-ttu-id="e41d5-155">Describe el ciclo de vida de cada tipo de mensaje desde el momento en que se llega a una ubicación de recepción hasta que se envían todos los mensajes resultantes y se haya completado todo el procesamiento relacionado.</span><span class="sxs-lookup"><span data-stu-id="e41d5-155">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
-   <span data-ttu-id="e41d5-156">Describe cómo cambia el procesamiento de las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="e41d5-156">Describe how processing changes for error conditions.</span></span>  
  
-   <span data-ttu-id="e41d5-157">Incluir detalles sobre la correlación, las notificaciones de entrega y confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="e41d5-157">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
-   <span data-ttu-id="e41d5-158">Incluir información de requisito de rendimiento con respecto a la latencia y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e41d5-158">Include performance requirement information regarding latency and throughput.</span></span>  
  
 <span data-ttu-id="e41d5-159">**Detalles de Software que no sea de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="e41d5-159">**Non-Microsoft Software Details**</span></span>  
  
 <span data-ttu-id="e41d5-160">Debe estar plenamente documentado todo el software de terceros que se usa como parte del diseño de la solución detallada.</span><span class="sxs-lookup"><span data-stu-id="e41d5-160">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
 <span data-ttu-id="e41d5-161">**Pila detallado del Hardware**</span><span class="sxs-lookup"><span data-stu-id="e41d5-161">**Detailed Hardware Stack**</span></span>  
  
 <span data-ttu-id="e41d5-162">Basándose en el diagrama de hardware de alto nivel creado anteriormente, la siguiente información de hardware debe estar plenamente documentada:</span><span class="sxs-lookup"><span data-stu-id="e41d5-162">Building on the previously created high level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
-   <span data-ttu-id="e41d5-163">Procesadores</span><span class="sxs-lookup"><span data-stu-id="e41d5-163">Processors</span></span>  
  
    -   <span data-ttu-id="e41d5-164">Tipo</span><span class="sxs-lookup"><span data-stu-id="e41d5-164">Type</span></span>  
  
    -   <span data-ttu-id="e41d5-165">Velocidad</span><span class="sxs-lookup"><span data-stu-id="e41d5-165">Speed</span></span>  
  
    -   <span data-ttu-id="e41d5-166">Número de núcleos</span><span class="sxs-lookup"><span data-stu-id="e41d5-166">Number of cores</span></span>  
  
    -   <span data-ttu-id="e41d5-167">Hyperthreading</span><span class="sxs-lookup"><span data-stu-id="e41d5-167">Hyperthreading</span></span>  
  
-   <span data-ttu-id="e41d5-168">Memoria</span><span class="sxs-lookup"><span data-stu-id="e41d5-168">Memory</span></span>  
  
    -   <span data-ttu-id="e41d5-169">Amount</span><span class="sxs-lookup"><span data-stu-id="e41d5-169">Amount</span></span>  
  
    -   <span data-ttu-id="e41d5-170">Velocidad</span><span class="sxs-lookup"><span data-stu-id="e41d5-170">Speed</span></span>  
  
    -   <span data-ttu-id="e41d5-171">Paridad</span><span class="sxs-lookup"><span data-stu-id="e41d5-171">Parity</span></span>  
  
-   <span data-ttu-id="e41d5-172">Red</span><span class="sxs-lookup"><span data-stu-id="e41d5-172">Network</span></span>  
  
    -   <span data-ttu-id="e41d5-173">Número de tarjetas de interfaz de red (NIC)</span><span class="sxs-lookup"><span data-stu-id="e41d5-173">Number of network interface cards (NICs)</span></span>  
  
    -   <span data-ttu-id="e41d5-174">Velocidad de red</span><span class="sxs-lookup"><span data-stu-id="e41d5-174">Speed of network</span></span>  
  
-   <span data-ttu-id="e41d5-175">SAN</span><span class="sxs-lookup"><span data-stu-id="e41d5-175">SAN</span></span>  
  
    -   <span data-ttu-id="e41d5-176">Número de tarjetas de SAN en cada equipo</span><span class="sxs-lookup"><span data-stu-id="e41d5-176">Number of SAN cards in each computer</span></span>  
  
    -   <span data-ttu-id="e41d5-177">Número de números de unidad lógica (LUN) para cada equipo y el propósito de cada LUN</span><span class="sxs-lookup"><span data-stu-id="e41d5-177">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
    -   <span data-ttu-id="e41d5-178">Velocidad del área de almacenamiento (SAN) tarjetas de red</span><span class="sxs-lookup"><span data-stu-id="e41d5-178">Speed of storage area network (SAN) Cards</span></span>  
  
    -   <span data-ttu-id="e41d5-179">Detalles de configuración de tarjeta de SAN</span><span class="sxs-lookup"><span data-stu-id="e41d5-179">SAN card configuration details</span></span>  
  
    -   <span data-ttu-id="e41d5-180">Asignación de disco de SAN, formato y particiones</span><span class="sxs-lookup"><span data-stu-id="e41d5-180">SAN disk allocation, formatting, and partitioning</span></span>  
  
-   <span data-ttu-id="e41d5-181">Disco</span><span class="sxs-lookup"><span data-stu-id="e41d5-181">Disk</span></span>  
  
    -   <span data-ttu-id="e41d5-182">Detalles de disco local de cada equipo</span><span class="sxs-lookup"><span data-stu-id="e41d5-182">Local disk details for each computer</span></span>  
  
    -   <span data-ttu-id="e41d5-183">Formato utilizado para discos locales</span><span class="sxs-lookup"><span data-stu-id="e41d5-183">Formatting used for local disks</span></span>  
  
    -   <span data-ttu-id="e41d5-184">Detalles de creación de particiones de discos locales</span><span class="sxs-lookup"><span data-stu-id="e41d5-184">Partitioning details for local disks</span></span>  
  
-   <span data-ttu-id="e41d5-185">Cache</span><span class="sxs-lookup"><span data-stu-id="e41d5-185">Cache</span></span>  
  
    -   <span data-ttu-id="e41d5-186">Cantidad de memoria caché L2</span><span class="sxs-lookup"><span data-stu-id="e41d5-186">L2 Cache amount</span></span>  
  
    -   <span data-ttu-id="e41d5-187">Cantidad de caché L3</span><span class="sxs-lookup"><span data-stu-id="e41d5-187">L3 Cache amount</span></span>  
  
 <span data-ttu-id="e41d5-188">**Pila detallado del Software**</span><span class="sxs-lookup"><span data-stu-id="e41d5-188">**Detailed Software Stack**</span></span>  
  
 <span data-ttu-id="e41d5-189">Se debe documentar la siguiente información de software:</span><span class="sxs-lookup"><span data-stu-id="e41d5-189">The following software information should be documented:</span></span>  
  
-   <span data-ttu-id="e41d5-190">Arquitectura, ediciones y versiones de sistema operativo específico</span><span class="sxs-lookup"><span data-stu-id="e41d5-190">Specific operating system versions, editions, and architecture</span></span>  
  
-   <span data-ttu-id="e41d5-191">Características de sistema operativo específico</span><span class="sxs-lookup"><span data-stu-id="e41d5-191">Specific operating system features</span></span>  
  
-   <span data-ttu-id="e41d5-192">Software específico instalado en cada equipo</span><span class="sxs-lookup"><span data-stu-id="e41d5-192">Specific software installed on each computer</span></span>  
  
-   <span data-ttu-id="e41d5-193">Controladores específicos</span><span class="sxs-lookup"><span data-stu-id="e41d5-193">Specific drivers</span></span>  
  
-   <span data-ttu-id="e41d5-194">Service Packs y otras actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e41d5-194">Service Packs and other updates</span></span>  
  
-   <span data-ttu-id="e41d5-195">Valores de configuración para todas las características de software y sistema operativo usa si varían de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="e41d5-195">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="building-out-the-environment-for-the-solution"></a><span data-ttu-id="e41d5-196">Crear el entorno para la solución</span><span class="sxs-lookup"><span data-stu-id="e41d5-196">Building Out the Environment for the Solution</span></span>  
 <span data-ttu-id="e41d5-197">Instrucciones detalladas para instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los requisitos de software que se encuentran en el [guías de instalación de BizTalk Server](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="e41d5-197">Detailed instructions for installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the software requirements are in the [BizTalk Server Installation Guides](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e41d5-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="e41d5-198">See Also</span></span>  
 [<span data-ttu-id="e41d5-199">Planificación del nivel de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e41d5-199">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)
