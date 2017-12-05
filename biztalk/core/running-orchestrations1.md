---
title: Ejecuta Orchestrations1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- host instances, stopping and restarting
- orchestrations, compiling
- orchestrations, deploying
ms.assetid: b992bdba-630d-4f28-aca8-c568f3c27968
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c215009d6b911831c74ac22b2c03ceae45e74a62
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="running-orchestrations"></a><span data-ttu-id="f77f4-102">Orquestaciones en ejecución</span><span class="sxs-lookup"><span data-stu-id="f77f4-102">Running Orchestrations</span></span>
<span data-ttu-id="f77f4-103">Los procedimientos siguientes describen cómo generar, implementar, enlazar e iniciar una orquestación.</span><span class="sxs-lookup"><span data-stu-id="f77f4-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="f77f4-104">Creación de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="f77f4-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="f77f4-105">Para crear una clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="f77f4-105">To create a strong name key</span></span>  
  
1.  <span data-ttu-id="f77f4-106">Inicie un símbolo del sistema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f77f4-106">Start a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2.  <span data-ttu-id="f77f4-107">Cambie los directorios a un proyecto existente, por ejemplo, \<unidad\>: \Adapter_Install\biztalk2010\my_project.</span><span class="sxs-lookup"><span data-stu-id="f77f4-107">Change directories to an existing project, for example, \<drive\>:\Adapter_Install\biztalk2010\my_project.</span></span>  
  
3.  <span data-ttu-id="f77f4-108">Escriba lo siguiente en el símbolo del sistema y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="f77f4-108">Type the following in the command prompt and press ENTER:</span></span>  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="f77f4-109">Compilación e implementación de una orquestación</span><span class="sxs-lookup"><span data-stu-id="f77f4-109">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="f77f4-110">Para compilar e implementar una orquestación</span><span class="sxs-lookup"><span data-stu-id="f77f4-110">To compile and deploy an orchestration</span></span>  
  
1.  <span data-ttu-id="f77f4-111">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto SSOSchedule y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-111">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the SSOSchedule project, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f77f4-112">Haga clic en **propiedades comunes**y expanda el **ensamblado** nodo.</span><span class="sxs-lookup"><span data-stu-id="f77f4-112">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3.  <span data-ttu-id="f77f4-113">Escriba la ruta de acceso a SSOSchedule.snk en el **archivo de clave de ensamblado** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="f77f4-113">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4.  <span data-ttu-id="f77f4-114">Compruebe que Configuration Properties\Deployment\Server contiene un punto (.) o el nombre del equipo y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-114">Verify that Configuration Properties\Deployment\Server contains a dot (.) or your computer name, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="f77f4-115">En el Explorador de soluciones, haga clic en **SSOSchedule**y haga clic en **volver a generar**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-115">In Solution Explorer, right-click **SSOSchedule**, and click **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="f77f4-116">Haga clic en el **SSOSchedule**y haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-116">Right-click the **SSOSchedule**, and click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="f77f4-117">Inicio de la orquestación</span><span class="sxs-lookup"><span data-stu-id="f77f4-117">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="f77f4-118">Para iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="f77f4-118">To start the orchestration</span></span>  
  
1.  <span data-ttu-id="f77f4-119">En la consola de administración de BizTalk, seleccione la orquestación que desea iniciar.</span><span class="sxs-lookup"><span data-stu-id="f77f4-119">In the BizTalk Administration console, select the orchestration you want to start.</span></span>  
  
2.  <span data-ttu-id="f77f4-120">Haga clic en la orquestación y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-120">Right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="f77f4-121">Detención y reinicio de una instancia de host</span><span class="sxs-lookup"><span data-stu-id="f77f4-121">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="f77f4-122">Después de implementar el ejemplo, debe reiniciar la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="f77f4-122">After deploying the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="f77f4-123">Para detener y reiniciar una instancia de host</span><span class="sxs-lookup"><span data-stu-id="f77f4-123">To stop and restart a host instance</span></span>  
  
1.  <span data-ttu-id="f77f4-124">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y seleccione **administración de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="f77f4-124">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and select **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="f77f4-125">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en el **Microsoft BizTalk Server (local)** nodo y expanda **Hosts**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-125">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the **Microsoft BizTalk Server (local)** node, and expand **Hosts**.</span></span>  
  
3.  <span data-ttu-id="f77f4-126">En el panel izquierdo, seleccione la **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-126">In the left pane, select the **BizTalkServerApplication**.</span></span>  
  
4.  <span data-ttu-id="f77f4-127">En el panel derecho, haga clic en la instancia de host (por ejemplo, el nombre del equipo) y haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-127">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
     <span data-ttu-id="f77f4-128">El estado de la instancia de host cambia a **detenido**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-128">The status of the host instance changes to **Stopped**.</span></span>  
  
5.  <span data-ttu-id="f77f4-129">En el panel derecho, haga clic en la instancia de host y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-129">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
     <span data-ttu-id="f77f4-130">El estado de la instancia de host cambia a **Inicio pendiente**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-130">The status of the host instance changes to **Start pending**.</span></span>  
  
     <span data-ttu-id="f77f4-131">Para cambiar el estado a **ejecutando**, haga clic en **actualizar**, o haga clic en la instancia de host y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="f77f4-131">To change the status to **Running**, click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f77f4-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f77f4-132">See Also</span></span>  
 [<span data-ttu-id="f77f4-133">Seguridad en el adaptador</span><span class="sxs-lookup"><span data-stu-id="f77f4-133">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)