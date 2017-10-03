---
title: Ejecuta Orchestrations2 | Documentos de Microsoft
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
- creating strong name keys
- compiling orchestrations
- host instances, stopping and restarting
- deployment, orchestrations
- orchestrations, compiling
- orchestrations, deploying
- stopping host instances
- restarting host instances
ms.assetid: a098d552-d302-44f6-9af9-d77d16549fd3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d8e16b7af574a73dc8fc813c29ecd5917ce4d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-orchestrations"></a><span data-ttu-id="24205-102">Orquestaciones en ejecución</span><span class="sxs-lookup"><span data-stu-id="24205-102">Running Orchestrations</span></span>
<span data-ttu-id="24205-103">Los procedimientos siguientes describen cómo generar, implementar, enlazar e iniciar una orquestación.</span><span class="sxs-lookup"><span data-stu-id="24205-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="24205-104">Creación de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="24205-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="24205-105">Para crear una clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="24205-105">To create a strong name key</span></span>  
  
1.  <span data-ttu-id="24205-106">Abra un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="24205-106">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2.  <span data-ttu-id="24205-107">Vaya al directorio de un proyecto existente y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="24205-107">Change directories to an existing project and press ENTER.</span></span>  
  
     <span data-ttu-id="24205-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24205-108">For example:</span></span>  
  
     <span data-ttu-id="24205-109">**\<unidad >: \Adapter_Install\biztalk\my_project**</span><span class="sxs-lookup"><span data-stu-id="24205-109">**\<drive>:\Adapter_Install\biztalk\my_project**</span></span>  
  
3.  <span data-ttu-id="24205-110">Escriba lo siguiente en el símbolo del sistema y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="24205-110">Type the following at the command prompt and press ENTER:</span></span>  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="24205-111">Compilación e implementación de una orquestación</span><span class="sxs-lookup"><span data-stu-id="24205-111">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="24205-112">Para compilar e implementar una orquestación</span><span class="sxs-lookup"><span data-stu-id="24205-112">To compile and deploy an orchestration</span></span>  
  
1.  <span data-ttu-id="24205-113">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el **SSOSchedule** de proyecto y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="24205-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the **SSOSchedule** project, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="24205-114">Haga clic en **propiedades comunes**y expanda el **ensamblado** nodo.</span><span class="sxs-lookup"><span data-stu-id="24205-114">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3.  <span data-ttu-id="24205-115">Escriba la ruta de acceso a SSOSchedule.snk en el **archivo de clave de ensamblado** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="24205-115">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4.  <span data-ttu-id="24205-116">Compruebe que Configuration Properties\Deployment\Server sea un punto (.) o el nombre del equipo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24205-116">Verify that Configuration Properties\Deployment\Server is a dot (.) or your computer name, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="24205-117">En el Explorador de soluciones, haga clic en **SSOSchedule**y, a continuación, haga clic en **volver a generar**.</span><span class="sxs-lookup"><span data-stu-id="24205-117">In Solution Explorer, right-click **SSOSchedule**, and then click **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="24205-118">Haga clic en **SSOSchedule**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="24205-118">Right-click **SSOSchedule**, and then click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="24205-119">Inicio de la orquestación</span><span class="sxs-lookup"><span data-stu-id="24205-119">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="24205-120">Para iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="24205-120">To start the orchestration</span></span>  
  
1.  <span data-ttu-id="24205-121">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="24205-121">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="24205-122">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda el deseado aplicación y, a continuación, haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="24205-122">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand the desired application, and then click **Orchestrations**.</span></span>  
  
3.  <span data-ttu-id="24205-123">En el panel de detalles, haga clic en la orquestación y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="24205-123">In the details pane, right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="24205-124">Detención y reinicio de una instancia de host</span><span class="sxs-lookup"><span data-stu-id="24205-124">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="24205-125">Después de implementar el ejemplo, debe reiniciar la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="24205-125">After you deploy the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="24205-126">Para detener y reiniciar una instancia de host</span><span class="sxs-lookup"><span data-stu-id="24205-126">To stop and restart a host instance</span></span>  
  
1.  <span data-ttu-id="24205-127">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="24205-127">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="24205-128">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Instancias de host**.</span><span class="sxs-lookup"><span data-stu-id="24205-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="24205-129">En el panel derecho, haga clic en la instancia de host (por ejemplo, el nombre del equipo) y haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="24205-129">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
     <span data-ttu-id="24205-130">El estado de la instancia de host cambia a **detenido**.</span><span class="sxs-lookup"><span data-stu-id="24205-130">The status of the host instance changes to **Stopped**.</span></span>  
  
4.  <span data-ttu-id="24205-131">En el panel derecho, haga clic en la instancia de host y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="24205-131">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
     <span data-ttu-id="24205-132">El estado de la instancia de host cambia a **Inicio pendiente**.</span><span class="sxs-lookup"><span data-stu-id="24205-132">The status of the host instance changes to **Start pending**.</span></span>  
  
     <span data-ttu-id="24205-133">Para cambiar el estado a **ejecutando** y haga clic en **actualizar**, o haga clic en la instancia de host y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="24205-133">To change the status to **Running** and click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24205-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="24205-134">See Also</span></span>  
 [<span data-ttu-id="24205-135">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="24205-135">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)