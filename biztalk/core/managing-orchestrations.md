---
title: Administración de orquestaciones | Microsoft Docs
description: Vínculos para trabajar con las orquestaciones de BizTalk Server, incluido el inicio, detener, enlazar, configurar, habilitar el seguimiento, suspender y mucho más
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a989cb7853e63e1e603febf44db45288276ecd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976485"
---
# <a name="manage-orchestrations"></a><span data-ttu-id="64ecd-103">Administrar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="64ecd-103">Manage Orchestrations</span></span>

## <a name="overview"></a><span data-ttu-id="64ecd-104">Información general</span><span class="sxs-lookup"><span data-stu-id="64ecd-104">Overview</span></span>
<span data-ttu-id="64ecd-105">En esta sección, se proporcionan instrucciones acerca de la utilización de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="64ecd-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage orchestrations.</span></span> <span data-ttu-id="64ecd-106">Una orquestación es un proceso empresarial ejecutable.</span><span class="sxs-lookup"><span data-stu-id="64ecd-106">An orchestration is an executable business process.</span></span> <span data-ttu-id="64ecd-107">Para obtener información general acerca de las orquestaciones, consulte [orquestaciones](../core/orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="64ecd-107">For background information about orchestrations, see [Orchestrations](../core/orchestrations.md).</span></span>  

## <a name="add-to-application"></a><span data-ttu-id="64ecd-108">Agregar a la aplicación</span><span class="sxs-lookup"><span data-stu-id="64ecd-108">Add to application</span></span>  
 <span data-ttu-id="64ecd-109">Las orquestaciones se compilan [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="64ecd-109">Orchestrations are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="64ecd-110">No se puede agregar una orquestación a una aplicación de forma individual; una orquestación se agrega a una aplicación del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64ecd-110">You cannot add an orchestration to an application individually; an orchestration is added to an application as follows:</span></span>  
  
- <span data-ttu-id="64ecd-111">Cuando agrega un ensamblado de BizTalk que contiene una orquestación a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="64ecd-111">When you add a BizTalk assembly containing an orchestration to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="64ecd-112">Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene una orquestación, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="64ecd-112">When you import an .msi file into an application that includes a BizTalk assembly containing an orchestration, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="64ecd-113">Cuando un programador implementa en una aplicación un ensamblado que contiene una orquestación desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="64ecd-113">When a developer deploys into an application an assembly containing an orchestration from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="biztalk-administration-tasks"></a><span data-ttu-id="64ecd-114">Tareas de administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="64ecd-114">BizTalk Administration tasks</span></span>  
 <span data-ttu-id="64ecd-115">La consola de administración se utiliza para llevar a cabo las acciones siguientes, tal como se describe en esta sección:</span><span class="sxs-lookup"><span data-stu-id="64ecd-115">You use the administration console to perform the following actions, as described in this section:</span></span>  
  
-   <span data-ttu-id="64ecd-116">Configurar enlaces para la orquestación enlazando la orquestación al host y a los puertos de recepción y envío apropiados, o quitar estos enlaces de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="64ecd-116">Configure bindings for the orchestration by binding the orchestration to the appropriate send and receive ports and host, or remove these bindings from the orchestration.</span></span>  
  
-   <span data-ttu-id="64ecd-117">Configurar el seguimiento de mensajes para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="64ecd-117">Configure message tracking for the orchestration.</span></span>  
  
-   <span data-ttu-id="64ecd-118">Ver información de instancia de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="64ecd-118">View instance information for the orchestration.</span></span>  
  
-   <span data-ttu-id="64ecd-119">Dar de alta la orquestación en el host adecuado o darla de baja de éste.</span><span class="sxs-lookup"><span data-stu-id="64ecd-119">Enlist the orchestration to the appropriate host or unenlist the orchestration from the host.</span></span>  
  
-   <span data-ttu-id="64ecd-120">Iniciar o detener la orquestación para que inicie o detenga el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="64ecd-120">Start or stop the orchestration so that it starts or stops processing messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64ecd-121">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="64ecd-121">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="64ecd-122">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="64ecd-122">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
> 
> [!NOTE]
>  <span data-ttu-id="64ecd-123">El programador utiliza el Diseñador de orquestaciones para crear las orquestaciones, como se describe en [crear orquestaciones usar diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md).</span><span class="sxs-lookup"><span data-stu-id="64ecd-123">The developer uses Orchestration Designer to create orchestrations, as described in [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span> <span data-ttu-id="64ecd-124">El programador puede administrar orquestaciones durante el proceso de desarrollo mediante el uso de la consola de administración, como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="64ecd-124">The developer can manage orchestrations during the development process by using the administration console, as described in this section.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="64ecd-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="64ecd-125">Next steps</span></span>
  
-   [<span data-ttu-id="64ecd-126">Configurar enlaces para una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-126">Configure Bindings for an Orchestration</span></span>](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-127">Desenlazar una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-127">Unbind an Orchestration</span></span>](../core/how-to-unbind-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-128">Configurar el seguimiento para una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-128">Configure Tracking for an Orchestration</span></span>](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-129">Ver la información de instancias para una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-129">View Instance Information for an Orchestration</span></span>](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-130">Quitar una orquestación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="64ecd-130">Remove an Orchestration from an Application</span></span>](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [<span data-ttu-id="64ecd-131">Dar de alta una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-131">Enlist an Orchestration</span></span>](../core/how-to-enlist-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-132">Dar de baja una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-132">Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-133">Iniciar una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-133">Start an Orchestration</span></span>](../core/how-to-start-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-134">Detener una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-134">Stop an Orchestration</span></span>](../core/how-to-stop-an-orchestration.md)  
  
-   [<span data-ttu-id="64ecd-135">Suspender, reanudar y finalizar instancias de orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-135">Suspend, Resume, and Terminate Orchestration Instances</span></span>](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [<span data-ttu-id="64ecd-136">Actualizar una orquestación</span><span class="sxs-lookup"><span data-stu-id="64ecd-136">Upgrade an Orchestration</span></span>](../core/how-to-upgrade-an-orchestration.md)