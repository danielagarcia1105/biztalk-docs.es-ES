---
title: 'Paso 2: Configurar e iniciar la aplicación 1 | Microsoft Docs'
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
ms.openlocfilehash: 8edeb1cdb1f24774ec7c1e615377d81e4393c9dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024554"
---
# <a name="step-2-configure-and-start-the-application"></a><span data-ttu-id="7f6f5-102">Paso 2: Configurar e iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="7f6f5-102">Step 2: Configure and Start the Application</span></span>
<span data-ttu-id="7f6f5-103">![Paso 2 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="7f6f5-103">![Step 2 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="7f6f5-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="7f6f5-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="7f6f5-105">**Objetivo:** en este paso, configurará e iniciará la aplicación EAISolution.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-105">**Objective:** In this step, you configure and start the EAISolution application.</span></span>  
  
 <span data-ttu-id="7f6f5-106">**Propósito:** la configuración es principalmente sobre el enlace.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-106">**Purpose:** The configuration is mostly about binding.</span></span>  <span data-ttu-id="7f6f5-107">Un enlace crea una asignación entre un extremo lógico, como un puerto de orquestación o un vínculo de rol, y un extremo físico, como una entidad o un puerto de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-107">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="7f6f5-108">Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-108">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="7f6f5-109">Puede crear enlaces mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-109">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7f6f5-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7f6f5-110">Prerequisites</span></span>  
 <span data-ttu-id="7f6f5-111">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-111">Note the following requirements before you begin this step:</span></span>  
  
- <span data-ttu-id="7f6f5-112">Antes de comenzar este paso debe completar [paso 1: implementar los proyectos](../core/step-1-deploy-the-projects.md).</span><span class="sxs-lookup"><span data-stu-id="7f6f5-112">Before you begin this step you must complete [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md).</span></span>  
  
- <span data-ttu-id="7f6f5-113">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f6f5-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7f6f5-114">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7f6f5-114">Procedures</span></span>  
 <span data-ttu-id="7f6f5-115">La aplicación de BizTalk es una característica de BizTalk Server que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-115">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="7f6f5-116">Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-116">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span>  <span data-ttu-id="7f6f5-117">Para obtener más información, consulte [¿qué es una aplicación de BizTalk?](../core/what-is-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="7f6f5-117">For more information, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md).</span></span>  <span data-ttu-id="7f6f5-118">En [paso 1: implementar los proyectos](../core/step-1-deploy-the-projects.md), configuramos el nombre de la aplicación como "EAISolution" antes de implementar los proyectos.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-118">In [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md), we configure the application name to be “EAISolution” before we deploy the projects.</span></span>  <span data-ttu-id="7f6f5-119">Así pues, la aplicación EAISolution contiene la orquestación, los dos esquemas y la asignación.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-119">So the EAISolution application contains the orchestration, the two schema, and the map.</span></span>  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a><span data-ttu-id="7f6f5-120">Para abrir la aplicación EAISolution desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7f6f5-120">To open the EAISolution application from BizTalk Server Administration Console</span></span>  
  
1. <span data-ttu-id="7f6f5-121">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f6f5-121">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="7f6f5-122">En el árbol de consola en el lado izquierdo de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-122">In the console tree on the left side of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="7f6f5-123">Expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, haga clic en **EAISolution**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-123">Expand **BizTalk Group**, expand **Applications**, and then click **EAISolution**.</span></span>  
  
   <span data-ttu-id="7f6f5-124">En [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md), hemos creado una orquestación.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-124">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), we created an orchestration.</span></span>  <span data-ttu-id="7f6f5-125">En la orquestación, se definieron los puertos lógicos.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-125">In the orchestration, we defined the logical ports.</span></span>  <span data-ttu-id="7f6f5-126">En los procedimientos siguientes, se definirán los puertos físicos y se vincularán a los puertos lógicos.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-126">In the following procedures, you will define the physical ports and bind the physical ports to the logical ports.</span></span>  
  
#### <a name="to-create-the-receiverequest-port"></a><span data-ttu-id="7f6f5-127">Para crear el puerto ReceiveRequest</span><span class="sxs-lookup"><span data-stu-id="7f6f5-127">To create the ReceiveRequest port</span></span>  
  
1.  <span data-ttu-id="7f6f5-128">Desde la consola de administración de BizTalk Server, bajo el **EAISolution** nodo, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **unidireccional Puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-128">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="7f6f5-129">En la ficha General, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-129">On the General tab,  do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-130">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-130">Use this</span></span>|<span data-ttu-id="7f6f5-131">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-132">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-132">**Name**</span></span>|<span data-ttu-id="7f6f5-133">Tipo **EAISolutionReceiveRequestPort**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-133">Type **EAISolutionReceiveRequestPort**.</span></span>|  
    |<span data-ttu-id="7f6f5-134">**Habilitar enrutamiento para mensajes con errores**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-134">**Enable routing for failed messages**</span></span>|<span data-ttu-id="7f6f5-135">(clear)</span><span class="sxs-lookup"><span data-stu-id="7f6f5-135">(clear)</span></span>|  
  
3.  <span data-ttu-id="7f6f5-136">Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-136">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="7f6f5-137">Desde Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-137">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-138">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-138">Use this</span></span>|<span data-ttu-id="7f6f5-139">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-140">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-140">**Name**</span></span>|<span data-ttu-id="7f6f5-141">Tipo **EAISolutionReceiveRequestLocation**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-141">Type **EAISolutionReceiveRequestLocation**.</span></span>|  
    |<span data-ttu-id="7f6f5-142">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-142">**Type**</span></span>|<span data-ttu-id="7f6f5-143">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-143">Select **File**.</span></span>|  
    |<span data-ttu-id="7f6f5-144">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-144">**Receive handler**</span></span>|<span data-ttu-id="7f6f5-145">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-145">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="7f6f5-146">**Canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-146">**Receive pipeline**</span></span>|<span data-ttu-id="7f6f5-147">Seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-147">Select **XMLReceive**.</span></span>|  
  
5.  <span data-ttu-id="7f6f5-148">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-148">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="7f6f5-149">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-149">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-150">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-150">Use this</span></span>|<span data-ttu-id="7f6f5-151">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-152">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-152">**Receive folder**</span></span>|<span data-ttu-id="7f6f5-153">Tipo **C:\BTSTutorials\WareHouse\Request**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-153">Type **C:\BTSTutorials\WareHouse\Request**.</span></span>|  
  
7.  <span data-ttu-id="7f6f5-154">Haga clic en **Aceptar** tres veces.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-154">Click **OK** three times.</span></span>  
  
#### <a name="to-create-the-senddecline-port"></a><span data-ttu-id="7f6f5-155">Para crear el puerto SendDecline</span><span class="sxs-lookup"><span data-stu-id="7f6f5-155">To create the SendDecline port</span></span>  
  
1.  <span data-ttu-id="7f6f5-156">Desde la consola de administración de BizTalk Server, bajo el **EAISolution** nodo, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **unidireccional estático Puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-156">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="7f6f5-157">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-157">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-158">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-158">Use this</span></span>|<span data-ttu-id="7f6f5-159">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-160">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-160">**Name**</span></span>|<span data-ttu-id="7f6f5-161">Tipo **EAISolutionSendDeclinePort**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-161">Type **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="7f6f5-162">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-162">**Type**</span></span>|<span data-ttu-id="7f6f5-163">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-163">Select **File**.</span></span>|  
    |<span data-ttu-id="7f6f5-164">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-164">**Send handler**</span></span>|<span data-ttu-id="7f6f5-165">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-165">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="7f6f5-166">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-166">**Send pipeline**</span></span>|<span data-ttu-id="7f6f5-167">Seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-167">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="7f6f5-168">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-168">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="7f6f5-169">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-169">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-170">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-170">Use this</span></span>|<span data-ttu-id="7f6f5-171">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-171">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-172">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-172">**Receive folder**</span></span>|<span data-ttu-id="7f6f5-173">Tipo **C:\BTSTutorials\WareHouse\RequestDecline**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-173">Type **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>|  
    |<span data-ttu-id="7f6f5-174">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-174">**File name**</span></span>|<span data-ttu-id="7f6f5-175">Tipo **RequestDecline_%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-175">Type **RequestDecline_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="7f6f5-176">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-176">Click **OK** twice.</span></span>  
  
#### <a name="to-create-the-sendtoerp-port"></a><span data-ttu-id="7f6f5-177">Para crear el puerto SendToERP</span><span class="sxs-lookup"><span data-stu-id="7f6f5-177">To create the SendToERP port</span></span>  
  
1.  <span data-ttu-id="7f6f5-178">Desde la consola de administración de BizTalk Server, bajo el **EAISolution** nodo, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **unidireccional estático Puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-178">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="7f6f5-179">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-179">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-180">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-180">Use this</span></span>|<span data-ttu-id="7f6f5-181">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-181">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-182">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-182">**Name**</span></span>|<span data-ttu-id="7f6f5-183">Tipo **EAISolutionSendToERPPort**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-183">Type **EAISolutionSendToERPPort**.</span></span>|  
    |<span data-ttu-id="7f6f5-184">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-184">**Type**</span></span>|<span data-ttu-id="7f6f5-185">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-185">Select **File**.</span></span>|  
    |<span data-ttu-id="7f6f5-186">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-186">**Send handler**</span></span>|<span data-ttu-id="7f6f5-187">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-187">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="7f6f5-188">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-188">**Send pipeline**</span></span>|<span data-ttu-id="7f6f5-189">Seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-189">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="7f6f5-190">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-190">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="7f6f5-191">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-191">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-192">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-192">Use this</span></span>|<span data-ttu-id="7f6f5-193">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-193">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-194">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-194">**Receive folder**</span></span>|<span data-ttu-id="7f6f5-195">Tipo **C:\BTSTutorials\ERP\Request**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-195">Type **C:\BTSTutorials\ERP\Request**.</span></span>|  
    |<span data-ttu-id="7f6f5-196">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-196">**File name**</span></span>|<span data-ttu-id="7f6f5-197">Tipo **Request_%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-197">Type **Request_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="7f6f5-198">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-198">Click **OK** twice.</span></span>  
  
#### <a name="to-bind-the-ports"></a><span data-ttu-id="7f6f5-199">Para enlazar los puertos</span><span class="sxs-lookup"><span data-stu-id="7f6f5-199">To bind the ports</span></span>  
  
1.  <span data-ttu-id="7f6f5-200">Desde la consola de administración de BizTalk Server, haga clic en **EAISolution**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-200">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="7f6f5-201">Desde Configurar aplicación, en el panel izquierdo, haga clic en **EAIProcess**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-201">From Configure Application, in the left pane, click **EAIProcess**.</span></span>  <span data-ttu-id="7f6f5-202">Esta es la orquestación que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-202">This is the orchestration we created.</span></span>  
  
3.  <span data-ttu-id="7f6f5-203">En el panel derecho, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6f5-203">From the right pane, do the following:</span></span>  
  
    |<span data-ttu-id="7f6f5-204">Use</span><span class="sxs-lookup"><span data-stu-id="7f6f5-204">Use this</span></span>|<span data-ttu-id="7f6f5-205">Para</span><span class="sxs-lookup"><span data-stu-id="7f6f5-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f6f5-206">**Host**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-206">**Host**</span></span>|<span data-ttu-id="7f6f5-207">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-207">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="7f6f5-208">**Puerto de recepción** para **ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-208">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="7f6f5-209">Seleccione **EAISolutionReceiveReqeustPort**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-209">Select **EAISolutionReceiveReqeustPort**.</span></span>|  
    |<span data-ttu-id="7f6f5-210">**Grupos de puertos de puertos de envío** para **ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-210">**Send PortsSend Port Groups** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="7f6f5-211">Seleccione **EAISolutionSendDeclinePort**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-211">Select **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="7f6f5-212">**Puerto de recepción** para **ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="7f6f5-212">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="7f6f5-213">Seleccione **EAISolutionSendToERPPort**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-213">Select **EAISolutionSendToERPPort**.</span></span>|  
  
4.  <span data-ttu-id="7f6f5-214">Haga clic en **Aceptar** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-214">Click **OK** to save the configuration.</span></span>  
  
#### <a name="to-start-the-application"></a><span data-ttu-id="7f6f5-215">Para iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="7f6f5-215">To start the application</span></span>  
  
1.  <span data-ttu-id="7f6f5-216">Desde la consola de administración de BizTalk Server, haga clic en **EAISolution**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-216">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="7f6f5-217">En el cuadro de diálogo, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-217">From the dialog, click **Start**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="7f6f5-218">Síntesis</span><span class="sxs-lookup"><span data-stu-id="7f6f5-218">What did I just do?</span></span>  
 <span data-ttu-id="7f6f5-219">En este paso, ha configurado e iniciado la aplicación EAIApplication.</span><span class="sxs-lookup"><span data-stu-id="7f6f5-219">In this step, you configured and started the EAIApplication application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7f6f5-220">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7f6f5-220">Next Steps</span></span>  
 <span data-ttu-id="7f6f5-221">Probar cómo procesa los mensajes en la solución EAI [paso 3: probar la solución](../core/step-3-test-the-solution2.md).</span><span class="sxs-lookup"><span data-stu-id="7f6f5-221">You test how the EAI solution processes messages in [Step 3: Test the Solution](../core/step-3-test-the-solution2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f6f5-222">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f6f5-222">See Also</span></span>  
 <span data-ttu-id="7f6f5-223">[Paso 1: Implementar los proyectos](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="7f6f5-223">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="7f6f5-224">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="7f6f5-224">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)