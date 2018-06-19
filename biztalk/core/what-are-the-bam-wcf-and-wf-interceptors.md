---
title: ¿Qué son los interceptores de WF y de WCF de BAM? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c819d219a9796b485434101ee1c2f2d4be136ae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288892"
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="02a01-103">¿Qué son los interceptores de WF y de WCF de BAM?</span><span class="sxs-lookup"><span data-stu-id="02a01-103">What Are the BAM WCF and WF Interceptors?</span></span>
<span data-ttu-id="02a01-104">Supervisión de la actividad económica (BAM) es un conjunto de herramientas, API y servicios que le permiten administrar agregaciones, alertas y perfiles, y enviar eventos a los procesos automatizados de instrumentos para supervisar métricas empresariales pertinentes.</span><span class="sxs-lookup"><span data-stu-id="02a01-104">Business Activity Monitoring (BAM) is a collection of tools, APIs, and services that allow you to manage aggregations, alerts, and profiles, and to instrument automated processes to send events to monitor relevant business metrics.</span></span> <span data-ttu-id="02a01-105">En conjunto, proporcionan visibilidad en tiempo real en los procesos empresariales y le permiten conocer el estado de los procesos empresariales y resultados.</span><span class="sxs-lookup"><span data-stu-id="02a01-105">Together, these provide end-to-end visibility into business processes and enable you to stay abreast of business process status and results.</span></span>  
  
 <span data-ttu-id="02a01-106">Los interceptores de BAM amplían esta misma funcionalidad a Windows Workflow Foundation (WF), Windows Communication Foundation (WCF) y a otros entornos en tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="02a01-106">BAM interceptors extend this same functionality into Windows Workflow Foundation (WF), Windows Communication Foundation (WCF), and other runtime environments.</span></span> <span data-ttu-id="02a01-107">El interceptor de BAM le permite llevar el seguimiento de los procesos empresariales sin volver a compilar la solución WF o WCF: la integración se efectúa a través de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="02a01-107">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution—integration is done through a configuration file.</span></span>  
  
 <span data-ttu-id="02a01-108">Mediante el interceptor de WF o WCF de BAM en el proyecto, puede:</span><span class="sxs-lookup"><span data-stu-id="02a01-108">By using the BAM WF or WCF interceptor in your project, you can:</span></span>  
  
-   <span data-ttu-id="02a01-109">Usar el portal BAM para ver información acerca de los procesos empresariales que se ejecutan en la aplicación WF o WCF.</span><span class="sxs-lookup"><span data-stu-id="02a01-109">Use the BAM portal to view information about the business processes running in your WF or WCF application.</span></span>  
  
-   <span data-ttu-id="02a01-110">Usar la funcionalidad BAM sin agregar código adicional a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02a01-110">Use BAM functionality without adding additional code to your application.</span></span>  
  
-   <span data-ttu-id="02a01-111">Implementar la solución con las utilidades y herramientas de BizTalk Server que ya conoce.</span><span class="sxs-lookup"><span data-stu-id="02a01-111">Deploy your solution using familiar BizTalk Server tools and utilities.</span></span>  
  
-   <span data-ttu-id="02a01-112">Aprovechar el entorno de BizTalk Server que ya existe para las aplicaciones WF y WCF nuevas y existentes.</span><span class="sxs-lookup"><span data-stu-id="02a01-112">Leverage your existing BizTalk Server environment for existing and new WF and WCF applications.</span></span>  
  
## <a name="interceptor-components"></a><span data-ttu-id="02a01-113">Componentes del interceptor</span><span class="sxs-lookup"><span data-stu-id="02a01-113">Interceptor Components</span></span>  
 <span data-ttu-id="02a01-114">En el núcleo de cada interceptor de BAM se encuentra Common Interceptor Foundation, un conjunto de componentes que proporciona las directrices para generar interceptores personalizados para entornos heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="02a01-114">At the core of each BAM interceptor is the Common Interceptor Foundation, a set of components that provide the foundation for building custom interceptors for heterogeneous environments.</span></span> <span data-ttu-id="02a01-115">Common Interceptor Foundation consta de los siguientes componentes compartidos:</span><span class="sxs-lookup"><span data-stu-id="02a01-115">The Common Interceptor Foundation contains the following shared components:</span></span>  
  
-   <span data-ttu-id="02a01-116">**bm.exe**, una versión mejorada de la utilidad de implementación de BAM extendida para modificar las configuraciones de interceptor incluidos add, remove, actualización y funcionalidad de la lista.</span><span class="sxs-lookup"><span data-stu-id="02a01-116">**bm.exe**, an enhanced version of the BAM deployment utility extended to modify interceptor configurations including add, remove, update, and list functionality.</span></span>  
  
-   <span data-ttu-id="02a01-117">**CommonInterceptorConfiguration.xsd**, el esquema XML de configuración de Common Interceptor Foundation.</span><span class="sxs-lookup"><span data-stu-id="02a01-117">**CommonInterceptorConfiguration.xsd**, the Common Interceptor Foundation configuration XML schema.</span></span> <span data-ttu-id="02a01-118">Como mínimo, la configuración de los interceptores debe validarse con este esquema.</span><span class="sxs-lookup"><span data-stu-id="02a01-118">At minimum, all interceptor configurations must validate against this schema.</span></span>  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a><span data-ttu-id="02a01-119">Interceptor de Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="02a01-119">Windows Workflow Foundation (WF) Interceptor</span></span>  
 <span data-ttu-id="02a01-120">El interceptor de Windows Workflow Foundation interceptor permite agregar de forma transparente la funcionalidad de seguimiento de BAM a aplicaciones WF existentes y nuevas.</span><span class="sxs-lookup"><span data-stu-id="02a01-120">The Windows Workflow Foundation interceptor enables you to transparently add BAM tracking functionality to new and existing WF applications.</span></span> <span data-ttu-id="02a01-121">Después de que se haya implementado la configuración del interceptor en la base de datos Importación principal de BAM y cada instancia de la aplicación WF se haya configurado para cargar el interceptor de WF de BAM, se escribirá los datos de flujo en BAM sin código adicional.</span><span class="sxs-lookup"><span data-stu-id="02a01-121">After the interceptor configuration has been deployed to the BAM Primary Import database and each instance of the WF application has been configured to load the BAM WF Interceptor, workflow data will be written to BAM with no additional code.</span></span> <span data-ttu-id="02a01-122">El interceptor de WF proporciona la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a01-122">The WF interceptor provides the following functionality:</span></span>  
  
-   <span data-ttu-id="02a01-123">Se conecta a aplicaciones WF existentes sin necesidad de cambios de código o recompilación.</span><span class="sxs-lookup"><span data-stu-id="02a01-123">Plugs into existing WF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="02a01-124">Habilita la detección en tiempo de ejecución y compatibilidad para archivos de configuración modificados.</span><span class="sxs-lookup"><span data-stu-id="02a01-124">Enables run-time detection and support for changed configuration files.</span></span> <span data-ttu-id="02a01-125">Si se detecta una nueva versión de un archivo de configuración de interceptor, las instancias de flujo de trabajo nuevas utilizarán la nueva configuración mientras que las instancias de flujo de trabajo antiguas se completarán mediante la configuración antigua.</span><span class="sxs-lookup"><span data-stu-id="02a01-125">If a new version of an interceptor configuration file is detected, new workflow instances will use the new configuration while old workflow instances will complete using the old configuration.</span></span>  
  
-   <span data-ttu-id="02a01-126">Admite transacciones.</span><span class="sxs-lookup"><span data-stu-id="02a01-126">Supports transactions.</span></span> <span data-ttu-id="02a01-127">El interceptor de WF guarda los elementos de los que se ha realizado el seguimiento de forma transaccionalmente coherente con transacciones WF.</span><span class="sxs-lookup"><span data-stu-id="02a01-127">The WF interceptor persists tracked items in a transactionally consistent way with WF transactions.</span></span> <span data-ttu-id="02a01-128">Los elementos de los que se ha realizado el seguimiento sólo se guardan cuando la transacción WF y la transacción de interceptor se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="02a01-128">Tracked items are only persisted when the WF transaction and the interceptor trasaction complete successfully.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02a01-129">El interceptor de Windows Workflow no es compatible con SharedConnectionWorkflowCommitWorkBatchService que utiliza la misma conexión SQL para los servicios de persistencia y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="02a01-129">The Windows Workflow interceptor does not support SharedConnectionWorkflowCommitWorkBatchService which uses the same SQL connection for both the tracking and persistence services.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02a01-130">En BizTalk Server, el interceptor de Windows Workflow Foundation (WF) no funcionará con el nuevo motor WF en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="02a01-130">In BizTalk Server, the Windows Workflow Foundation (WF) interceptor will not work with the new WF engine in .NET Framework 4.</span></span> <span data-ttu-id="02a01-131">El interceptor de WF continuarán funcionando en .NET Framework 3.5 Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="02a01-131">The WF interceptor will continue to work in .NET Framework 3.5 SP2.</span></span>  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a><span data-ttu-id="02a01-132">Interceptor de Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="02a01-132">Windows Communication Foundation (WCF) Interceptor</span></span>  
 <span data-ttu-id="02a01-133">El interceptor de Windows Communication Foundation proporciona la funcionalidad de seguimiento de BAM a las aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="02a01-133">The Windows Communication Foundation interceptor provides BAM tracking functionality to your WCF applications.</span></span> <span data-ttu-id="02a01-134">Proporciona la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="02a01-134">It provides the following functionality:</span></span>  
  
-   <span data-ttu-id="02a01-135">Se conecta a aplicaciones WCF existentes sin necesidad de cambios de código o recompilación.</span><span class="sxs-lookup"><span data-stu-id="02a01-135">Plugs into existing WCF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="02a01-136">Realiza el seguimiento de mensajes contenidos en las llamadas del Servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="02a01-136">Tracks messages contained in WCF service calls.</span></span>  
  
-   <span data-ttu-id="02a01-137">Realiza el seguimiento de la información procedente de mensajes en llamadas del Servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="02a01-137">Tracks information from messages in WCF service calls.</span></span>  
  
-   <span data-ttu-id="02a01-138">Participa en transacciones procedentes del cliente o iniciadas internamente para llamadas de servicio con transacciones.</span><span class="sxs-lookup"><span data-stu-id="02a01-138">Participates in transactions flowed from the client or initiated internally for transacted service calls.</span></span>