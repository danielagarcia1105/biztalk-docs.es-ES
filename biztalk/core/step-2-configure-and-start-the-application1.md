---
title: 'Paso 2: Configurar e iniciar la aplicación 1 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cb061ca-acf4-4de4-a634-b3bb98876989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc9c3c027126d3a461bf99329b70fda57b9be647
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280012"
---
# <a name="step-2-configure-and-start-the-application"></a><span data-ttu-id="fd6bf-102">Paso 2: Configurar e iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="fd6bf-102">Step 2: Configure and Start the Application</span></span>
<span data-ttu-id="fd6bf-103">![Paso 2 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="fd6bf-103">![Step 2 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="fd6bf-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="fd6bf-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="fd6bf-105">**Objetivo:** en este paso, configurará e iniciará la aplicación EAISolution.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-105">**Objective:** In this step, you configure and start the EAISolution application.</span></span>  
  
 <span data-ttu-id="fd6bf-106">**Propósito:** la configuración está relacionada principalmente con enlace.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-106">**Purpose:** The configuration is mostly about binding.</span></span>  <span data-ttu-id="fd6bf-107">Un enlace crea una asignación entre un extremo lógico, como un puerto de orquestación o un vínculo de rol, y un extremo físico, como una entidad o un puerto de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-107">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="fd6bf-108">Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-108">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="fd6bf-109">Puede crear enlaces mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-109">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd6bf-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fd6bf-110">Prerequisites</span></span>  
 <span data-ttu-id="fd6bf-111">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="fd6bf-112">Antes de comenzar este paso debe completar [paso 1: implementar los proyectos](../core/step-1-deploy-the-projects.md).</span><span class="sxs-lookup"><span data-stu-id="fd6bf-112">Before you begin this step you must complete [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md).</span></span>  
  
-   <span data-ttu-id="fd6bf-113">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd6bf-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="fd6bf-114">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fd6bf-114">Procedures</span></span>  
 <span data-ttu-id="fd6bf-115">La aplicación de BizTalk es una característica de BizTalk Server que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-115">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="fd6bf-116">Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-116">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span>  <span data-ttu-id="fd6bf-117">Para obtener más información, consulte [¿qué es una aplicación de BizTalk?](../core/what-is-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="fd6bf-117">For more information, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md).</span></span>  <span data-ttu-id="fd6bf-118">En [paso 1: implementar los proyectos](../core/step-1-deploy-the-projects.md), configuramos el nombre de la aplicación como "EAISolution" antes de implementar los proyectos.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-118">In [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md), we configure the application name to be “EAISolution” before we deploy the projects.</span></span>  <span data-ttu-id="fd6bf-119">Así pues, la aplicación EAISolution contiene la orquestación, los dos esquemas y la asignación.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-119">So the EAISolution application contains the orchestration, the two schema, and the map.</span></span>  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a><span data-ttu-id="fd6bf-120">Para abrir la aplicación EAISolution desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fd6bf-120">To open the EAISolution application from BizTalk Server Administration Console</span></span>  
  
1.  <span data-ttu-id="fd6bf-121">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd6bf-121">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="fd6bf-122">En el árbol de consola en el lado izquierdo de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-122">In the console tree on the left side of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="fd6bf-123">Expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, haga clic en **EAISolution**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-123">Expand **BizTalk Group**, expand **Applications**, and then click **EAISolution**.</span></span>  
  
 <span data-ttu-id="fd6bf-124">En [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md), hemos creado una orquestación.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-124">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), we created an orchestration.</span></span>  <span data-ttu-id="fd6bf-125">En la orquestación, se definieron los puertos lógicos.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-125">In the orchestration, we defined the logical ports.</span></span>  <span data-ttu-id="fd6bf-126">En los procedimientos siguientes, se definirán los puertos físicos y se vincularán a los puertos lógicos.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-126">In the following procedures, you will define the physical ports and bind the physical ports to the logical ports.</span></span>  
  
#### <a name="to-create-the-receiverequest-port"></a><span data-ttu-id="fd6bf-127">Para crear el puerto ReceiveRequest</span><span class="sxs-lookup"><span data-stu-id="fd6bf-127">To create the ReceiveRequest port</span></span>  
  
1.  <span data-ttu-id="fd6bf-128">Desde la consola de administración de BizTalk Server, en la **EAISolution** nodo, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **unidireccional Puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-128">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="fd6bf-129">En la ficha General, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-129">On the General tab,  do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-130">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-130">Use this</span></span>|<span data-ttu-id="fd6bf-131">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-132">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-132">**Name**</span></span>|<span data-ttu-id="fd6bf-133">Tipo de **EAISolutionReceiveRequestPort**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-133">Type **EAISolutionReceiveRequestPort**.</span></span>|  
    |<span data-ttu-id="fd6bf-134">**Habilitar enrutamiento para mensajes con errores**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-134">**Enable routing for failed messages**</span></span>|<span data-ttu-id="fd6bf-135">(clear)</span><span class="sxs-lookup"><span data-stu-id="fd6bf-135">(clear)</span></span>|  
  
3.  <span data-ttu-id="fd6bf-136">Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-136">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="fd6bf-137">Desde Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-137">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-138">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-138">Use this</span></span>|<span data-ttu-id="fd6bf-139">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-140">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-140">**Name**</span></span>|<span data-ttu-id="fd6bf-141">Tipo de **EAISolutionReceiveRequestLocation**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-141">Type **EAISolutionReceiveRequestLocation**.</span></span>|  
    |<span data-ttu-id="fd6bf-142">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-142">**Type**</span></span>|<span data-ttu-id="fd6bf-143">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-143">Select **File**.</span></span>|  
    |<span data-ttu-id="fd6bf-144">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-144">**Receive handler**</span></span>|<span data-ttu-id="fd6bf-145">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-145">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="fd6bf-146">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-146">**Receive pipeline**</span></span>|<span data-ttu-id="fd6bf-147">Seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-147">Select **XMLReceive**.</span></span>|  
  
5.  <span data-ttu-id="fd6bf-148">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-148">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="fd6bf-149">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-149">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-150">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-150">Use this</span></span>|<span data-ttu-id="fd6bf-151">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-152">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-152">**Receive folder**</span></span>|<span data-ttu-id="fd6bf-153">Tipo de **C:\BTSTutorials\WareHouse\Request**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-153">Type **C:\BTSTutorials\WareHouse\Request**.</span></span>|  
  
7.  <span data-ttu-id="fd6bf-154">Haga clic en **Aceptar** tres veces.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-154">Click **OK** three times.</span></span>  
  
#### <a name="to-create-the-senddecline-port"></a><span data-ttu-id="fd6bf-155">Para crear el puerto SendDecline</span><span class="sxs-lookup"><span data-stu-id="fd6bf-155">To create the SendDecline port</span></span>  
  
1.  <span data-ttu-id="fd6bf-156">Desde la consola de administración de BizTalk Server, en la **EAISolution** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **unidireccional estático Puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-156">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="fd6bf-157">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-157">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-158">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-158">Use this</span></span>|<span data-ttu-id="fd6bf-159">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-160">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-160">**Name**</span></span>|<span data-ttu-id="fd6bf-161">Tipo de **EAISolutionSendDeclinePort**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-161">Type **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="fd6bf-162">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-162">**Type**</span></span>|<span data-ttu-id="fd6bf-163">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-163">Select **File**.</span></span>|  
    |<span data-ttu-id="fd6bf-164">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-164">**Send handler**</span></span>|<span data-ttu-id="fd6bf-165">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-165">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="fd6bf-166">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-166">**Send pipeline**</span></span>|<span data-ttu-id="fd6bf-167">Seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-167">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="fd6bf-168">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-168">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="fd6bf-169">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-169">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-170">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-170">Use this</span></span>|<span data-ttu-id="fd6bf-171">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-171">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-172">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-172">**Receive folder**</span></span>|<span data-ttu-id="fd6bf-173">Tipo de **C:\BTSTutorials\WareHouse\RequestDecline**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-173">Type **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>|  
    |<span data-ttu-id="fd6bf-174">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-174">**File name**</span></span>|<span data-ttu-id="fd6bf-175">Tipo de **RequestDecline_%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-175">Type **RequestDecline_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="fd6bf-176">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-176">Click **OK** twice.</span></span>  
  
#### <a name="to-create-the-sendtoerp-port"></a><span data-ttu-id="fd6bf-177">Para crear el puerto SendToERP</span><span class="sxs-lookup"><span data-stu-id="fd6bf-177">To create the SendToERP port</span></span>  
  
1.  <span data-ttu-id="fd6bf-178">Desde la consola de administración de BizTalk Server, en la **EAISolution** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **unidireccional estático Puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-178">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="fd6bf-179">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-179">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-180">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-180">Use this</span></span>|<span data-ttu-id="fd6bf-181">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-181">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-182">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-182">**Name**</span></span>|<span data-ttu-id="fd6bf-183">Tipo de **EAISolutionSendToERPPort**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-183">Type **EAISolutionSendToERPPort**.</span></span>|  
    |<span data-ttu-id="fd6bf-184">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-184">**Type**</span></span>|<span data-ttu-id="fd6bf-185">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-185">Select **File**.</span></span>|  
    |<span data-ttu-id="fd6bf-186">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-186">**Send handler**</span></span>|<span data-ttu-id="fd6bf-187">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-187">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="fd6bf-188">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-188">**Send pipeline**</span></span>|<span data-ttu-id="fd6bf-189">Seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-189">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="fd6bf-190">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-190">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="fd6bf-191">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-191">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-192">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-192">Use this</span></span>|<span data-ttu-id="fd6bf-193">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-193">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-194">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-194">**Receive folder**</span></span>|<span data-ttu-id="fd6bf-195">Tipo de **C:\BTSTutorials\ERP\Request**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-195">Type **C:\BTSTutorials\ERP\Request**.</span></span>|  
    |<span data-ttu-id="fd6bf-196">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-196">**File name**</span></span>|<span data-ttu-id="fd6bf-197">Tipo de **Request_%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-197">Type **Request_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="fd6bf-198">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-198">Click **OK** twice.</span></span>  
  
#### <a name="to-bind-the-ports"></a><span data-ttu-id="fd6bf-199">Para enlazar los puertos</span><span class="sxs-lookup"><span data-stu-id="fd6bf-199">To bind the ports</span></span>  
  
1.  <span data-ttu-id="fd6bf-200">Desde la consola de administración de BizTalk Server, haga clic en **EAISolution**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-200">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="fd6bf-201">Desde Configurar aplicación, en el panel izquierdo, haga clic en **EAIProcess**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-201">From Configure Application, in the left pane, click **EAIProcess**.</span></span>  <span data-ttu-id="fd6bf-202">Esta es la orquestación que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-202">This is the orchestration we created.</span></span>  
  
3.  <span data-ttu-id="fd6bf-203">En el panel derecho, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd6bf-203">From the right pane, do the following:</span></span>  
  
    |<span data-ttu-id="fd6bf-204">Use</span><span class="sxs-lookup"><span data-stu-id="fd6bf-204">Use this</span></span>|<span data-ttu-id="fd6bf-205">Para</span><span class="sxs-lookup"><span data-stu-id="fd6bf-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd6bf-206">**Host**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-206">**Host**</span></span>|<span data-ttu-id="fd6bf-207">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-207">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="fd6bf-208">**Puerto de recepción** para **ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-208">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="fd6bf-209">Seleccione **EAISolutionReceiveReqeustPort**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-209">Select **EAISolutionReceiveReqeustPort**.</span></span>|  
    |<span data-ttu-id="fd6bf-210">**Grupos de puertos de puertos de envío** para **ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-210">**Send PortsSend Port Groups** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="fd6bf-211">Seleccione **EAISolutionSendDeclinePort**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-211">Select **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="fd6bf-212">**Puerto de recepción** para **ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="fd6bf-212">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="fd6bf-213">Seleccione **EAISolutionSendToERPPort**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-213">Select **EAISolutionSendToERPPort**.</span></span>|  
  
4.  <span data-ttu-id="fd6bf-214">Haga clic en **Aceptar** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-214">Click **OK** to save the configuration.</span></span>  
  
#### <a name="to-start-the-application"></a><span data-ttu-id="fd6bf-215">Para iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="fd6bf-215">To start the application</span></span>  
  
1.  <span data-ttu-id="fd6bf-216">Desde la consola de administración de BizTalk Server, haga clic en **EAISolution**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-216">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="fd6bf-217">En el cuadro de diálogo, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-217">From the dialog, click **Start**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="fd6bf-218">Síntesis</span><span class="sxs-lookup"><span data-stu-id="fd6bf-218">What did I just do?</span></span>  
 <span data-ttu-id="fd6bf-219">En este paso, ha configurado e iniciado la aplicación EAIApplication.</span><span class="sxs-lookup"><span data-stu-id="fd6bf-219">In this step, you configured and started the EAIApplication application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fd6bf-220">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fd6bf-220">Next Steps</span></span>  
 <span data-ttu-id="fd6bf-221">Se probará cómo la solución EAI procesa mensajes en [paso 3: probar la solución](../core/step-3-test-the-solution2.md).</span><span class="sxs-lookup"><span data-stu-id="fd6bf-221">You test how the EAI solution processes messages in [Step 3: Test the Solution](../core/step-3-test-the-solution2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd6bf-222">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd6bf-222">See Also</span></span>  
 <span data-ttu-id="fd6bf-223">[Paso 1: Implementar los proyectos](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="fd6bf-223">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="fd6bf-224">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="fd6bf-224">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)