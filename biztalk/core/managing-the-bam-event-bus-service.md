---
title: Administrar el servicio de Bus de eventos BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MessageBox database, migrating data
- Primary Import database [BAM], migrating data
- migrating, data [BAM]
- managing [BAM], Event Bus Service
- Event Bus Service [BAM], managing
- Tracking Data Decode Service (TDDS)
ms.assetid: 556e7fe2-4a7d-46f6-8e55-f41be4e666dc
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f265201e371a86072c06b336b4d00bb1742f5f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-the-bam-event-bus-service"></a><span data-ttu-id="7db5c-102">Administrar el servicio de bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="7db5c-102">Managing the BAM Event Bus Service</span></span>
<span data-ttu-id="7db5c-103">El servicio de bus de eventos BAM, al que también se conoce como Servicio de descodificación de datos de seguimiento (TDDS), procesa datos de seguimiento (secuencias) almacenados en una base de datos de origen y los conserva de tal forma que resulte fácil solicitarlos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7db5c-103">The BAM Event Bus Service, also known as the Tracking Data Decode Service (TDDS), processes tracking data (streams) stored in a source database and persists that data in such a way that it is easy to query it at a later date.</span></span>  
  
 <span data-ttu-id="7db5c-104">El servicio de bus de eventos BAM mueve los datos de inteligencia empresarial a la base de datos de importación principal de BAM y los datos de supervisión de estado de BizTalk a la base de datos DTA.</span><span class="sxs-lookup"><span data-stu-id="7db5c-104">The BAM Event Bus service moves Business intelligence data to the BAM Primary Import database and BizTalk Health Monitoring data to the DTA database.</span></span> <span data-ttu-id="7db5c-105">El servicio de bus de eventos BAM se ejecuta como un subservicio del servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7db5c-105">The BAM Event Bus service runs as a sub-service within the BizTalk service.</span></span>  
  
 <span data-ttu-id="7db5c-106">Supervisar las actividades de una aplicación transaccional, por ejemplo, Microsoft BizTalk® Server, recopilar datos de eventos durante la ejecución y, a continuación, almacena temporalmente los datos en la misma base de datos como el estado de la aplicación, por ejemplo, la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="7db5c-106">You monitor the activities of a transactional application, such as Microsoft BizTalk® Server, by collecting event data during execution, and then temporarily storing the data in the same database as the application state—for example, the MessageBox database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7db5c-107">Evite crear más de una instancia de aplicación que aloje el seguimiento para grupos de BizTalk diferentes en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="7db5c-107">Avoid creating more than one application instance that hosts tracking for different BizTalk Groups on the same computer.</span></span> <span data-ttu-id="7db5c-108">Si existen instancias que realizan el seguimiento de diferentes grupos de BizTalk en el mismo equipo, no será posible distinguir qué eventos pertenecen a cada grupo de BizTalk en la consola de administración de BizTalk o en el registro de eventos como se muestran todos los grupos de BizTalk con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="7db5c-108">If instances that track different BizTalk Groups exist on the same computer, you will not be able to distinguish which events belong to which BizTalk Groups in the BizTalk Administration Console or in the event log because all BizTalk Groups are displayed with the same name.</span></span>  
  
 <span data-ttu-id="7db5c-109">El servicio de bus de eventos BAM lee los datos de eventos, los descodifica y los almacena en una base de datos de Microsoft SQL Server™ en la que puede consultar los datos fácilmente.</span><span class="sxs-lookup"><span data-stu-id="7db5c-109">The BAM Event Bus service reads the event data, decodes it, and then stores it in a Microsoft SQL Server™ database, where you can easily query the data.</span></span>  
  
 <span data-ttu-id="7db5c-110">El servicio de bus de eventos BAM proporciona las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7db5c-110">The BAM Event Bus service provides the following advantages:</span></span>  
  
-   <span data-ttu-id="7db5c-111">Los datos de eventos siempre coinciden con el estado de la aplicación y no muestran nunca un progreso sin confirmar.</span><span class="sxs-lookup"><span data-stu-id="7db5c-111">Event data always matches the state of the application, and it never exposes uncommitted progress.</span></span>  
  
-   <span data-ttu-id="7db5c-112">El impacto del rendimiento en la aplicación que se está ejecutando es mínimo ya que los datos de eventos guardan tan pocos registros en la misma transacción local como el cambio de estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7db5c-112">Performance impact on the running application is minimal because the event data saves as few records in the same local transaction as the application state change.</span></span>  
  
-   <span data-ttu-id="7db5c-113">El almacenamiento del servidor SQL Server para el estado de la aplicación se optimiza aún más para el rendimiento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="7db5c-113">SQL Server storage for the application state is further optimized for execution performance.</span></span> <span data-ttu-id="7db5c-114">TDDS descodifica los datos y los almacena en una base de datos independiente, ya sea la base de datos de importación principal de BAM o la base de datos DTA.</span><span class="sxs-lookup"><span data-stu-id="7db5c-114">The data is decoded by TDDS and stored in a separate database, either the BAM Primary import database or the DTA database.</span></span> <span data-ttu-id="7db5c-115">Cuando se generan informes, los datos se solicitan desde la base de datos, lo que tiene su repercusión en la base de datos de cuadro de mensajes, que es la que almacena el estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7db5c-115">When reports are generated the data is queried from the database and does impact the Message Box database, which stores the application state.</span></span>  
  
-   <span data-ttu-id="7db5c-116">No se realiza el trabajo que almacena los datos de eventos en un formulario que puede consultar en los servidores y bases de datos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7db5c-116">The work to store the event data in a form that you can query is not done in the application servers and databases.</span></span> <span data-ttu-id="7db5c-117">Se descarga en los equipos que ejecutan el servicio de bus de eventos BAM y en la base de datos de destino del servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7db5c-117">It is offloaded to the machines that run the BAM Event Bus service and the Destination SQL Server database.</span></span>  
  
-   <span data-ttu-id="7db5c-118">Los datos de eventos se procesan con una latencia baja, lo que permite un procesamiento más rápido de las solicitudes de TDDS.</span><span class="sxs-lookup"><span data-stu-id="7db5c-118">Event data is processed with low latency which allows TDDS queries process faster.</span></span> <span data-ttu-id="7db5c-119">Los servicios de bus de eventos BAM coordinan sus recursos para conseguir la latencia mínima posible.</span><span class="sxs-lookup"><span data-stu-id="7db5c-119">The BAM Event Bus services coordinate their resources to achieve the minimum possible latency.</span></span>  
  
 <span data-ttu-id="7db5c-120">El servidor de bus de eventos BAM coordina sus recursos al utilizar una conexión a una base de datos central que contiene la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="7db5c-120">The BAM Event Bus server coordinates its resources by using a connection to a central database, which contains the configuration information.</span></span> <span data-ttu-id="7db5c-121">Cada servicio de bus de eventos BAM envía un mensaje cada minuto a la base de datos central, que contiene el estado del servicio de bus de eventos BAM en ese momento en particular.</span><span class="sxs-lookup"><span data-stu-id="7db5c-121">Every minute, each active BAM Event Bus service sends a message to the central database, which contains the state of the BAM Event Bus service at that point in time.</span></span>  
  
 <span data-ttu-id="7db5c-122">Este mensaje suele denominarse “mensaje de latido”.</span><span class="sxs-lookup"><span data-stu-id="7db5c-122">This message is referred to as a heartbeat message.</span></span> <span data-ttu-id="7db5c-123">Cada servicio de bus de eventos BAM también comprueba si hay trabajos nuevos que se tengan que realizar.</span><span class="sxs-lookup"><span data-stu-id="7db5c-123">Each BAM Event Bus service also checks for new work that needs to be done.</span></span> <span data-ttu-id="7db5c-124">Por ejemplo, el servicio de bus de eventos BAM comprueba sesiones que no tienen propietario, como la base de datos de cuadro de mensajes que se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="7db5c-124">For example, the BAM Event Bus service checks for sessions that are not owned, such as a MessageBox database that has been added.</span></span>  
  
 <span data-ttu-id="7db5c-125">La sesión de bus de eventos BAM es el movimiento de los datos de eventos de la base de datos de origen, como la de cuadro de mensajes, a la base de datos de destino que contiene los datos de eventos en un formato que puede consultar.</span><span class="sxs-lookup"><span data-stu-id="7db5c-125">The BAM Event Bus session is the movement of the event data from the source database, such as the MessageBox, to the destination database that contains the event data in a format that you can query.</span></span> <span data-ttu-id="7db5c-126">El mismo servicio de bus de eventos BAM puede procesar una o más sesiones.</span><span class="sxs-lookup"><span data-stu-id="7db5c-126">The same BAM Event Bus service can process one or more sessions.</span></span>  
  
 <span data-ttu-id="7db5c-127">La ilustración siguiente muestra un grupo de servidores de bus de eventos BAM, que crea un grupo de servidores de bus de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="7db5c-127">The following figure shows a group of BAM Event Bus servers, which make up a BAM Event Bus server pool.</span></span>  
  
 ![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")  
<span data-ttu-id="7db5c-128">Diagrama de un conjunto de servidores de bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="7db5c-128">Diagram of a BAM Event Bus server pool</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7db5c-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7db5c-129">In This Section</span></span>  
  
-   [<span data-ttu-id="7db5c-130">Contadores de rendimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="7db5c-130">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)  
  
-   [<span data-ttu-id="7db5c-131">Procedimientos almacenados del servicio de Bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="7db5c-131">BAM Event Bus Service Stored Procedures</span></span>](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [<span data-ttu-id="7db5c-132">Conmutación por error el servidor de servicio BAM eventos Bus</span><span class="sxs-lookup"><span data-stu-id="7db5c-132">BAM Event Bus Service Server Failover</span></span>](../core/bam-event-bus-service-server-failover.md)  
  
-   [<span data-ttu-id="7db5c-133">Creación de instancias del servicio de Bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="7db5c-133">Creating Instances of the BAM Event Bus Service</span></span>](../core/creating-instances-of-the-bam-event-bus-service.md)