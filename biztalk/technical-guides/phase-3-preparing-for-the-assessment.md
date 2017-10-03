---
title: "Fase 3: Preparar para la evaluación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 890047f6a13352d89d33d9514883dc20eacd4001
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="phase-3-preparing-for-the-assessment"></a><span data-ttu-id="4a04e-102">Fase 3: Preparar para la evaluación</span><span class="sxs-lookup"><span data-stu-id="4a04e-102">Phase 3: Preparing for the Assessment</span></span>
<span data-ttu-id="4a04e-103">Fase de una evaluación de rendimiento puede considerarse el "cómo" para la fase de ámbito "qué" y la fase de planificación de preparación 's "cuando".</span><span class="sxs-lookup"><span data-stu-id="4a04e-103">The Prepare phase of a performance assessment can be thought of as the “how” to the Scope phase’s “what” and the Plan phase’s “when.”</span></span> <span data-ttu-id="4a04e-104">En este momento en la evaluación del rendimiento, todas las partes interesadas deben acordados por el ámbito de la interacción y los planes para llevar a cabo el laboratorio.</span><span class="sxs-lookup"><span data-stu-id="4a04e-104">At this point in the performance assessment, all stakeholders should have agreed upon the scope of the engagement and the plans for conducting the lab.</span></span> <span data-ttu-id="4a04e-105">Se encuentra en la fase de preparación de la evaluación del rendimiento que se ejecutan los planes y se realizan acciones para preparar para la ejecución del laboratorio de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4a04e-105">It is in the Prepare phase of the performance assessment where the plans are executed and steps are taken to get ready for execution of the performance lab.</span></span>  
  
 <span data-ttu-id="4a04e-106">En este tema se describe los distintos aspectos de la fase de preparación de una evaluación del rendimiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4a04e-106">This topic describes the various aspects of the Prepare phase of a BizTalk Server performance assessment.</span></span>  
  
## <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="4a04e-107">Diseño detallado de la plataforma de soluciones</span><span class="sxs-lookup"><span data-stu-id="4a04e-107">Detailed design of the solution platform</span></span>  
 <span data-ttu-id="4a04e-108">Un diseño de la solución detallada facilita las comunicaciones y evita suposiciones, lo que mejorarán la agilidad y la eficacia de todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="4a04e-108">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="4a04e-109">Debe documentar completamente los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4a04e-109">You should fully document the following elements:</span></span>  
  
-   <span data-ttu-id="4a04e-110">**Bases de datos de BizTalk Server y cómo se distribuirán en varios equipos** -rendimiento de SQL Server es uno de los factores clave en el rendimiento general de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4a04e-110">**BizTalk Server databases and how they will be distributed across computers** - SQL Server performance is one of the key factors in overall BizTalk Server performance.</span></span> <span data-ttu-id="4a04e-111">Si SQL Server tiene las restricciones de recursos, esto afectará a la capacidad de BizTalk Server para procesar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a04e-111">If SQL Server is experiencing resource constraints, this will impact the ability of BizTalk Server to process messages.</span></span> <span data-ttu-id="4a04e-112">El factor principal que influye en el rendimiento de la base de datos de BizTalk es la velocidad de los discos que se hospedan en.</span><span class="sxs-lookup"><span data-stu-id="4a04e-112">The main factor that influences BizTalk database performance is the speed of disks that they are hosted on.</span></span> <span data-ttu-id="4a04e-113">Separar los archivos de base de datos y registros de transacciones para cada BizTalk base de datos en unidades independientes o LUN de SAN se ha demostrado que mejorar notablemente el rendimiento general del servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4a04e-113">Separating the transaction log and database files for each BizTalk database onto separate drives or SAN LUN’s has been shown to remarkably improve the overall performance of BizTalk Server.</span></span> <span data-ttu-id="4a04e-114">Por lo tanto, es importante que esta información se registra de forma fácilmente accesible.</span><span class="sxs-lookup"><span data-stu-id="4a04e-114">Therefore, it is important that this information be recorded in an easily accessible manner.</span></span> <span data-ttu-id="4a04e-115">Los valores que se utilizarán en el entorno de producción se deben documentar en el diseño de la solución detallada.</span><span class="sxs-lookup"><span data-stu-id="4a04e-115">The values that will be used in the production environment should be documented in the detailed solution design.</span></span> <span data-ttu-id="4a04e-116">En la tabla siguiente proporciona un ejemplo de cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4a04e-116">The following table provides an example of how this can be done.</span></span>  
  
    |<span data-ttu-id="4a04e-117">Base de datos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4a04e-117">BizTalk Database</span></span>|<span data-ttu-id="4a04e-118">Nombre del volumen</span><span class="sxs-lookup"><span data-stu-id="4a04e-118">Volume Name</span></span>|<span data-ttu-id="4a04e-119">Archivos</span><span class="sxs-lookup"><span data-stu-id="4a04e-119">Files</span></span>|<span data-ttu-id="4a04e-120">LUN # o ML_ #</span><span class="sxs-lookup"><span data-stu-id="4a04e-120">LUN# or ML_#</span></span>|<span data-ttu-id="4a04e-121">Tamaño LUN físico (GB)</span><span class="sxs-lookup"><span data-stu-id="4a04e-121">Physical LUN Size (GB)</span></span>|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |<span data-ttu-id="4a04e-122">Cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="4a04e-122">MessageBox</span></span>|<span data-ttu-id="4a04e-123">Data_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="4a04e-123">Data_TempDb_1</span></span>|<span data-ttu-id="4a04e-124">Archivos de datos TEMPDB, maestra y MSDB</span><span class="sxs-lookup"><span data-stu-id="4a04e-124">TEMPDB,  MASTER, and MSDB data files</span></span>|<span data-ttu-id="4a04e-125">1</span><span class="sxs-lookup"><span data-stu-id="4a04e-125">1</span></span>|<span data-ttu-id="4a04e-126">134</span><span class="sxs-lookup"><span data-stu-id="4a04e-126">134</span></span>|  
    ||<span data-ttu-id="4a04e-127">Logs_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="4a04e-127">Logs_TempDb_1</span></span>|<span data-ttu-id="4a04e-128">Archivos de registro de transacciones de TEMPDB, maestra y MSDB</span><span class="sxs-lookup"><span data-stu-id="4a04e-128">TEMPDB,  MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="4a04e-129">2</span><span class="sxs-lookup"><span data-stu-id="4a04e-129">2</span></span>|<span data-ttu-id="4a04e-130">134</span><span class="sxs-lookup"><span data-stu-id="4a04e-130">134</span></span>|  
    ||<span data-ttu-id="4a04e-131">Data_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="4a04e-131">Data_BtsMsgBox</span></span>|<span data-ttu-id="4a04e-132">Archivo de datos de BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="4a04e-132">BizTalkMsgBoxDb data file</span></span>|<span data-ttu-id="4a04e-133">3</span><span class="sxs-lookup"><span data-stu-id="4a04e-133">3</span></span>|<span data-ttu-id="4a04e-134">134</span><span class="sxs-lookup"><span data-stu-id="4a04e-134">134</span></span>|  
    ||<span data-ttu-id="4a04e-135">Logs_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="4a04e-135">Logs_BtsMsgBox</span></span>|<span data-ttu-id="4a04e-136">Archivo de registro de transacciones BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="4a04e-136">BizTalkMsgBoxDb transaction log file</span></span>|<span data-ttu-id="4a04e-137">4</span><span class="sxs-lookup"><span data-stu-id="4a04e-137">4</span></span>|<span data-ttu-id="4a04e-138">134</span><span class="sxs-lookup"><span data-stu-id="4a04e-138">134</span></span>|  
    |<span data-ttu-id="4a04e-139">BAM</span><span class="sxs-lookup"><span data-stu-id="4a04e-139">BAM</span></span>|<span data-ttu-id="4a04e-140">Data_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="4a04e-140">Data_TempDb_2</span></span>|<span data-ttu-id="4a04e-141">Archivos de datos TEMPDB, maestra y MSDB</span><span class="sxs-lookup"><span data-stu-id="4a04e-141">TEMPDB, MASTER, and MSDB data files</span></span>|<span data-ttu-id="4a04e-142">5</span><span class="sxs-lookup"><span data-stu-id="4a04e-142">5</span></span>|<span data-ttu-id="4a04e-143">67</span><span class="sxs-lookup"><span data-stu-id="4a04e-143">67</span></span>|  
    ||<span data-ttu-id="4a04e-144">Logs_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="4a04e-144">Logs_TempDb_2</span></span>|<span data-ttu-id="4a04e-145">Archivos de registro de transacciones de TEMPDB, maestra y MSDB</span><span class="sxs-lookup"><span data-stu-id="4a04e-145">TEMPDB, MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="4a04e-146">6</span><span class="sxs-lookup"><span data-stu-id="4a04e-146">6</span></span>|<span data-ttu-id="4a04e-147">67</span><span class="sxs-lookup"><span data-stu-id="4a04e-147">67</span></span>|  
    ||<span data-ttu-id="4a04e-148">Data_BAM</span><span class="sxs-lookup"><span data-stu-id="4a04e-148">Data_BAM</span></span>|<span data-ttu-id="4a04e-149">Archivo de datos BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="4a04e-149">BAMPrimaryImport data file</span></span>|<span data-ttu-id="4a04e-150">7</span><span class="sxs-lookup"><span data-stu-id="4a04e-150">7</span></span>|<span data-ttu-id="4a04e-151">134</span><span class="sxs-lookup"><span data-stu-id="4a04e-151">134</span></span>|  
    ||<span data-ttu-id="4a04e-152">Logs_BAM</span><span class="sxs-lookup"><span data-stu-id="4a04e-152">Logs_BAM</span></span>|<span data-ttu-id="4a04e-153">Archivo de registro de transacciones BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="4a04e-153">BAMPrimaryImport transaction log file</span></span>|<span data-ttu-id="4a04e-154">8</span><span class="sxs-lookup"><span data-stu-id="4a04e-154">8</span></span>|<span data-ttu-id="4a04e-155">134</span><span class="sxs-lookup"><span data-stu-id="4a04e-155">134</span></span>|  
    |<span data-ttu-id="4a04e-156">Bases de datos de seguimiento de BizTalk, administración, Single Sign-On y motor de reglas</span><span class="sxs-lookup"><span data-stu-id="4a04e-156">BizTalk Tracking, Management, Single Sign-On, and Rule Engine databases</span></span>|<span data-ttu-id="4a04e-157">Data_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="4a04e-157">Data_TempDb_3</span></span>|<span data-ttu-id="4a04e-158">Archivos de datos TEMPDB, maestra, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO y BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="4a04e-158">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb data files</span></span>|<span data-ttu-id="4a04e-159">9</span><span class="sxs-lookup"><span data-stu-id="4a04e-159">9</span></span>|<span data-ttu-id="4a04e-160">67</span><span class="sxs-lookup"><span data-stu-id="4a04e-160">67</span></span>|  
    ||<span data-ttu-id="4a04e-161">Logs_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="4a04e-161">Logs_TempDb_3</span></span>|<span data-ttu-id="4a04e-162">Archivos de registro de transacciones de TEMPDB, maestra, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO y BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="4a04e-162">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb transaction log files</span></span>|<span data-ttu-id="4a04e-163">10</span><span class="sxs-lookup"><span data-stu-id="4a04e-163">10</span></span>|<span data-ttu-id="4a04e-164">67</span><span class="sxs-lookup"><span data-stu-id="4a04e-164">67</span></span>|  
  
-   <span data-ttu-id="4a04e-165">**Diseño de Host de BizTalk y las descripciones de cada host y sus instancias.**</span><span class="sxs-lookup"><span data-stu-id="4a04e-165">**BizTalk Host design and descriptions of each host and their instances.**</span></span>  
  
-   <span data-ttu-id="4a04e-166">**Descripción de cada orquestación.**</span><span class="sxs-lookup"><span data-stu-id="4a04e-166">**Description of each orchestration.**</span></span>  
  
-   <span data-ttu-id="4a04e-167">**Descripción de cada canalización.**</span><span class="sxs-lookup"><span data-stu-id="4a04e-167">**Description of each pipeline.**</span></span>  
  
-   <span data-ttu-id="4a04e-168">**Descripción de los componentes personalizados, como ensamblados .NET y componentes COM +.**</span><span class="sxs-lookup"><span data-stu-id="4a04e-168">**Description of custom components such as .NET assemblies and COM+ components.**</span></span>  
  
## <a name="detailed-architecture-diagram"></a><span data-ttu-id="4a04e-169">Diagrama de arquitectura detallada</span><span class="sxs-lookup"><span data-stu-id="4a04e-169">Detailed architecture diagram</span></span>  
 <span data-ttu-id="4a04e-170">El siguiente diagrama muestra un diagrama de arquitectura que podría utilizarse para una evaluación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4a04e-170">The following diagram illustrates an architecture diagram that could be used for a performance assessment.</span></span>  
  
 <span data-ttu-id="4a04e-171">![Diagrama de arquitectura de BizTalk](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span><span class="sxs-lookup"><span data-stu-id="4a04e-171">![BizTalk Architecture Diagram](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span></span>  
<span data-ttu-id="4a04e-172">Diagrama de arquitectura de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4a04e-172">BizTalk Architecture Diagram</span></span>  
  
## <a name="message-flow-diagrams"></a><span data-ttu-id="4a04e-173">Diagramas de flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="4a04e-173">Message flow diagrams</span></span>  
 <span data-ttu-id="4a04e-174">Crear diagramas de flujo de mensaje detallado para ayudar a evitar confusiones o false suposiciones sobre lo que se supone que se está produciendo mensajes durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4a04e-174">Create detailed message flow diagrams to help prevent confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span>  
  
 <span data-ttu-id="4a04e-175">Al pensar en una solución de BizTalk completo, se tiende a pensar en el flujo de mensajes a través del sistema.</span><span class="sxs-lookup"><span data-stu-id="4a04e-175">When thinking about a BizTalk solution holistically, we tend to think of the message flow through the system.</span></span> <span data-ttu-id="4a04e-176">Esta perspectiva de flujo de mensajes es especialmente importante al realizar pruebas debido a que todas las partes del flujo de deben considerarse como posibles cuellos de botella de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4a04e-176">This Message Flow perspective is especially important when doing performance testing because all parts of the flow must be considered as potential bottlenecks.</span></span> <span data-ttu-id="4a04e-177">Tener un diagrama de flujo de mensaje evita cualquier confusión o ejecutan suposiciones falsas con respecto a lo que se supone que se está produciendo mensajes durante cada prueba.</span><span class="sxs-lookup"><span data-stu-id="4a04e-177">Having a message flow diagram prevents any confusion or false assumptions regarding what is supposed to be happening to messages during each test run.</span></span>  
  
 <span data-ttu-id="4a04e-178">En el ejemplo siguiente, creado con formas de Visio simples, todos los usuarios en el proyecto independientemente del fondo pueden comprender rápidamente cómo se obtiene un mensaje en el sistema qué partes de las soluciones de interactuar con el mensaje y, por último, donde el mensaje aterriza después de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4a04e-178">In the following example, created using simple Visio shapes, everyone on the project regardless of background can quickly understand how a message gets into the system, what parts of the solutions interact with the message, and finally where the message lands after processing.</span></span>  
  
 <span data-ttu-id="4a04e-179">![Diagrama de flujo de mensajes](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span><span class="sxs-lookup"><span data-stu-id="4a04e-179">![Message Flow Diagram](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span></span>  
<span data-ttu-id="4a04e-180">Diagrama de flujo de mensaje</span><span class="sxs-lookup"><span data-stu-id="4a04e-180">Message Flow Diagram</span></span>  
  
 <span data-ttu-id="4a04e-181">Al crear los diagramas de flujo de mensaje, se deben considerar los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="4a04e-181">The following details should be considered when creating the message flow diagrams:</span></span>  
  
-   <span data-ttu-id="4a04e-182">Describe el ciclo de vida de cada tipo de mensaje desde el momento en que se llega a una ubicación de recepción hasta que se envían todos los mensajes resultantes y se haya completado todo el procesamiento relacionado.</span><span class="sxs-lookup"><span data-stu-id="4a04e-182">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
-   <span data-ttu-id="4a04e-183">Describe cómo cambia el procesamiento de las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="4a04e-183">Describe how processing changes for error conditions.</span></span>  
  
-   <span data-ttu-id="4a04e-184">Incluir detalles sobre la correlación, las notificaciones de entrega y confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="4a04e-184">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
-   <span data-ttu-id="4a04e-185">Incluir detalles sobre la dependencia de sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="4a04e-185">Include details about dependence on external systems.</span></span>  
  
-   <span data-ttu-id="4a04e-186">Incluir información de requisito de rendimiento con respecto a la latencia y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4a04e-186">Include performance requirement information regarding latency and throughput.</span></span>  
  
## <a name="third-party-software-details"></a><span data-ttu-id="4a04e-187">Detalles de software de terceros</span><span class="sxs-lookup"><span data-stu-id="4a04e-187">Third-party software details</span></span>  
 <span data-ttu-id="4a04e-188">Debe estar plenamente documentado todo el software de terceros que se usa como parte del diseño de la solución detallada.</span><span class="sxs-lookup"><span data-stu-id="4a04e-188">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
## <a name="detailed-lab-hardware-stack"></a><span data-ttu-id="4a04e-189">Pila de hardware de laboratorio detallada</span><span class="sxs-lookup"><span data-stu-id="4a04e-189">Detailed lab hardware stack</span></span>  
 <span data-ttu-id="4a04e-190">Basándose en el diagrama de hardware de alto nivel creado anteriormente, la siguiente información de hardware debe estar plenamente documentada:</span><span class="sxs-lookup"><span data-stu-id="4a04e-190">Building on the previously created high-level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
-   <span data-ttu-id="4a04e-191">Procesadores</span><span class="sxs-lookup"><span data-stu-id="4a04e-191">Processors</span></span>  
  
    -   <span data-ttu-id="4a04e-192">Tipo</span><span class="sxs-lookup"><span data-stu-id="4a04e-192">Type</span></span>  
  
    -   <span data-ttu-id="4a04e-193">Velocidad</span><span class="sxs-lookup"><span data-stu-id="4a04e-193">Speed</span></span>  
  
    -   <span data-ttu-id="4a04e-194">Número de núcleos</span><span class="sxs-lookup"><span data-stu-id="4a04e-194">Number of cores</span></span>  
  
    -   <span data-ttu-id="4a04e-195">Hyperthreading</span><span class="sxs-lookup"><span data-stu-id="4a04e-195">Hyperthreading</span></span>  
  
-   <span data-ttu-id="4a04e-196">Memoria</span><span class="sxs-lookup"><span data-stu-id="4a04e-196">Memory</span></span>  
  
    -   <span data-ttu-id="4a04e-197">Amount</span><span class="sxs-lookup"><span data-stu-id="4a04e-197">Amount</span></span>  
  
    -   <span data-ttu-id="4a04e-198">Velocidad</span><span class="sxs-lookup"><span data-stu-id="4a04e-198">Speed</span></span>  
  
    -   <span data-ttu-id="4a04e-199">Paridad</span><span class="sxs-lookup"><span data-stu-id="4a04e-199">Parity</span></span>  
  
-   <span data-ttu-id="4a04e-200">Red</span><span class="sxs-lookup"><span data-stu-id="4a04e-200">Network</span></span>  
  
    -   <span data-ttu-id="4a04e-201">Número de tarjetas de interfaz de red (NIC)</span><span class="sxs-lookup"><span data-stu-id="4a04e-201">Number of network interface cards (NICs)</span></span>  
  
    -   <span data-ttu-id="4a04e-202">Velocidad de red</span><span class="sxs-lookup"><span data-stu-id="4a04e-202">Speed of network</span></span>  
  
-   <span data-ttu-id="4a04e-203">SAN</span><span class="sxs-lookup"><span data-stu-id="4a04e-203">SAN</span></span>  
  
    -   <span data-ttu-id="4a04e-204">Número de tarjetas de SAN en cada equipo</span><span class="sxs-lookup"><span data-stu-id="4a04e-204">Number of SAN cards in each computer</span></span>  
  
    -   <span data-ttu-id="4a04e-205">Número de números de unidad lógica (LUN) para cada equipo y el propósito de cada LUN</span><span class="sxs-lookup"><span data-stu-id="4a04e-205">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
    -   <span data-ttu-id="4a04e-206">Velocidad del área de almacenamiento (SAN) tarjetas de red</span><span class="sxs-lookup"><span data-stu-id="4a04e-206">Speed of storage area network (SAN) Cards</span></span>  
  
    -   <span data-ttu-id="4a04e-207">Detalles de configuración de tarjeta de SAN</span><span class="sxs-lookup"><span data-stu-id="4a04e-207">SAN card configuration details</span></span>  
  
    -   <span data-ttu-id="4a04e-208">Asignación de disco de SAN, formato y particiones</span><span class="sxs-lookup"><span data-stu-id="4a04e-208">SAN disk allocation, formatting, and partitioning</span></span>  
  
-   <span data-ttu-id="4a04e-209">Disco</span><span class="sxs-lookup"><span data-stu-id="4a04e-209">Disk</span></span>  
  
    -   <span data-ttu-id="4a04e-210">Detalles de disco local de cada equipo</span><span class="sxs-lookup"><span data-stu-id="4a04e-210">Local disk details for each computer</span></span>  
  
    -   <span data-ttu-id="4a04e-211">Formato utilizado para discos locales</span><span class="sxs-lookup"><span data-stu-id="4a04e-211">Formatting used for local disks</span></span>  
  
    -   <span data-ttu-id="4a04e-212">Detalles de creación de particiones de discos locales</span><span class="sxs-lookup"><span data-stu-id="4a04e-212">Partitioning details for local disks</span></span>  
  
-   <span data-ttu-id="4a04e-213">Cache</span><span class="sxs-lookup"><span data-stu-id="4a04e-213">Cache</span></span>  
  
    -   <span data-ttu-id="4a04e-214">Cantidad de memoria caché L2</span><span class="sxs-lookup"><span data-stu-id="4a04e-214">L2 Cache amount</span></span>  
  
    -   <span data-ttu-id="4a04e-215">Cantidad de caché L3</span><span class="sxs-lookup"><span data-stu-id="4a04e-215">L3 Cache amount</span></span>  
  
## <a name="detailed-lab-software-stack"></a><span data-ttu-id="4a04e-216">Pila de software de laboratorio detallada</span><span class="sxs-lookup"><span data-stu-id="4a04e-216">Detailed lab software stack</span></span>  
 <span data-ttu-id="4a04e-217">Se debe documentar la siguiente información de software:</span><span class="sxs-lookup"><span data-stu-id="4a04e-217">The following software information should be documented:</span></span>  
  
-   <span data-ttu-id="4a04e-218">Arquitectura, ediciones y versiones de sistema operativo específico</span><span class="sxs-lookup"><span data-stu-id="4a04e-218">Specific operating system versions, editions, and architecture</span></span>  
  
-   <span data-ttu-id="4a04e-219">Características de sistema operativo específico</span><span class="sxs-lookup"><span data-stu-id="4a04e-219">Specific operating system features</span></span>  
  
-   <span data-ttu-id="4a04e-220">Software específico instalado en cada equipo</span><span class="sxs-lookup"><span data-stu-id="4a04e-220">Specific software installed on each computer</span></span>  
  
-   <span data-ttu-id="4a04e-221">Controladores específicos</span><span class="sxs-lookup"><span data-stu-id="4a04e-221">Specific drivers</span></span>  
  
-   <span data-ttu-id="4a04e-222">Service Packs y otras actualizaciones</span><span class="sxs-lookup"><span data-stu-id="4a04e-222">Service Packs and other updates</span></span>  
  
-   <span data-ttu-id="4a04e-223">Valores de configuración para todas las características de software y sistema operativo usa si varían de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="4a04e-223">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a04e-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a04e-224">See Also</span></span>  
 [<span data-ttu-id="4a04e-225">Fases de una evaluación del rendimiento</span><span class="sxs-lookup"><span data-stu-id="4a04e-225">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)