---
title: "Tutorial: Módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, orchestrations
- Windows SharePoint Services adapter tutorials, accessing SharePoint properties
ms.assetid: 310c4002-3416-44c6-b409-1d5467063e28
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23bc9f0b1f2d350864509536a393de639e108e2d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="walkthrough-module-3---accessing-sharepoint-properties-from-an-orchestration"></a><span data-ttu-id="f7bd7-102">Tutorial: Módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-102">Walkthrough: Module 3 - Accessing SharePoint Properties from an Orchestration</span></span>
<span data-ttu-id="f7bd7-103">En este tutorial es la continuación de [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) y muestra cómo obtener acceso a las propiedades de un mensaje entrante en el contexto de Windows SharePoint Services tiempo de ejecución y, a continuación, determine el destino del mensaje, en función de una propiedad que utiliza puertos dinámicos en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-103">This walkthrough is a continuation of [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) and shows you how to access the Windows SharePoint Services context properties of an incoming message at run time and then determine the destination of that message based on a property using dynamic ports in an orchestration.</span></span> <span data-ttu-id="f7bd7-104">Para obtener una introducción al adaptador de Windows SharePoint Services, vea [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f7bd7-104">For an introduction to the Windows SharePoint Services adapter see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7bd7-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f7bd7-105">Prerequisites</span></span>  
 <span data-ttu-id="f7bd7-106">A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="f7bd7-106">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="f7bd7-107">Debe tener una implementación de servidor único con una instalación completa de BizTalk Server que se ejecutan en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7bd7-107">You must have a single server deployment with a complete installation of BizTalk Server running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span>  
  
-   <span data-ttu-id="f7bd7-108">Debe completar los siguientes tutoriales: [Tutorial: módulo 1 – enviar y recibir mensajes con el adaptador de Windows SharePoint Services](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) y [Tutorial: módulo 2: integrar Office con las ventanas Adaptador de SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)</span><span class="sxs-lookup"><span data-stu-id="f7bd7-108">You must complete the following walkthroughs: [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) and [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)</span></span>  
  
 <span data-ttu-id="f7bd7-109">Para obtener información acerca de cómo utilizar el adaptador de Windows SharePoint Services en una implementación de varios servidores, vea [configurar e implementar el adaptador de Windows SharePoint Services](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f7bd7-109">For information about using the Windows SharePoint Services Adapter in a multi server deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="modify-the-biztalk-project"></a><span data-ttu-id="f7bd7-110">Modificar el proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f7bd7-110">Modify the BizTalk project</span></span>  
 <span data-ttu-id="f7bd7-111">En este procedimiento, modificará el esquema PurchaseOrder de [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md).</span><span class="sxs-lookup"><span data-stu-id="f7bd7-111">In this procedure you modify the PurchaseOrder schema from [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md).</span></span> <span data-ttu-id="f7bd7-112">En este procedimiento se muestra cómo promocionar una propiedad de esquema para facilitar el acceso en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-112">This procedure illustrates how to promote a schema property for easy access in a BizTalk orchestration.</span></span>  
  
#### <a name="modify-the-purchaseorderxsd-schema"></a><span data-ttu-id="f7bd7-113">Modificar el esquema PurchaseOrder.xsd</span><span class="sxs-lookup"><span data-stu-id="f7bd7-113">Modify the PurchaseOrder.xsd schema</span></span>  
  
1.  <span data-ttu-id="f7bd7-114">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-114">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="f7bd7-115">Haga clic en **archivo**, haga clic en **abiertos**y, a continuación, haga clic en **proyecto/solución**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-115">Click **File**, click **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-116">Vaya a la `OrderProcess.sln` de archivos y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-116">Browse to the `OrderProcess.sln` file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-117">En **el Explorador de soluciones**, haga clic en el `OrderProcessSchema.xsd` de archivos y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-117">In **Solution Explorer**, right-click the `OrderProcessSchema.xsd` file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f7bd7-118">En **el Editor de BizTalk**, expanda `PurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-118">In **BizTalk Editor**, expand `PurchaseOrder`.</span></span>  
  
6.  <span data-ttu-id="f7bd7-119">Haga clic en `Amount`, haga clic en **promover**y, a continuación, haga clic en **promoción rápida**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-119">Right-click `Amount`, click **Promote**, and then click **Quick Promotion**.</span></span>  
  
7.  <span data-ttu-id="f7bd7-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-120">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="f7bd7-121"> crea un esquema de propiedades para esto en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-121"> creates a property schema for this in the current project.</span></span>  
  
8.  <span data-ttu-id="f7bd7-122">Guarde `PurchaseOrder.xsd`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-122">Save `PurchaseOrder.xsd`.</span></span>  
  
## <a name="create-an-orchestration"></a><span data-ttu-id="f7bd7-123">Crear una orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-123">Create an orchestration</span></span>  
 <span data-ttu-id="f7bd7-124">En este procedimiento, se creará una nueva orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-124">In this procedure you create a new BizTalk orchestration.</span></span> <span data-ttu-id="f7bd7-125">En él, se crea la orquestación que se utiliza para procesar un mensaje recibido por el adaptador de Windows Sharepoint Services.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-125">This procedure creates the orchestration that is used to process a message received by the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="add-a-biztalk-orchestration"></a><span data-ttu-id="f7bd7-126">Agregar una orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f7bd7-126">Add a BizTalk orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-127">En **el Explorador de soluciones**, haga clic en el `OrderProcess` proyecto de equipo y haga clic en **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-127">In **Solution Explorer**, right-click the `OrderProcess` project, click **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="f7bd7-128">En **categorías**, seleccione **archivos de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-128">Under **Categories**, select **Orchestration Files**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-129">En **plantillas**, seleccione **orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-129">Under **Templates**, select **BizTalk Orchestration**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-130">Tipo de `MyCompanyOrderProcessing` en el **nombre** campo y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-130">Type `MyCompanyOrderProcessing` in the **Name** field, and then click **Add**.</span></span>  
  
## <a name="create-receive-information"></a><span data-ttu-id="f7bd7-131">Crear información de recepción</span><span class="sxs-lookup"><span data-stu-id="f7bd7-131">Create receive information</span></span>  
 <span data-ttu-id="f7bd7-132">En este procedimiento, creará un mensaje, un puerto de recepción y una forma de recepción nuevos para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-132">In this procedure you create a new message, receive port, and receive shape for the orchestration.</span></span> <span data-ttu-id="f7bd7-133">En él se muestra cómo configurar una orquestación para recibir un mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7bd7-133">This procedure illustrates how to configure an orchestration to receive a message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="create-a-new-message"></a><span data-ttu-id="f7bd7-134">Crear un nuevo mensaje</span><span class="sxs-lookup"><span data-stu-id="f7bd7-134">Create a new message</span></span>  
  
1.  <span data-ttu-id="f7bd7-135">En **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-135">In **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="f7bd7-136">Con esto, se generará un nuevo mensaje con el nombre `Message_1`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-136">This will generate a new message with the name `Message_1`.</span></span>  
  
2.  <span data-ttu-id="f7bd7-137">Haga clic en `Message_1`, haga clic en **cambiar el nombre de**y, a continuación, escriba `Message_PO`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-137">Right-click `Message_1`, click **Rename**, and then type `Message_PO`.</span></span>  
  
3.  <span data-ttu-id="f7bd7-138">Haga clic en `Message_PO`y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-138">Right-click `Message_PO`, and then click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-139">En el **tipo de mensaje** propiedad, expanda **esquemas**y, a continuación, seleccione `OrderProcess.OrderProcessSchema` esquema.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-139">In the **Message Type** property, expand **Schemas**, and then select `OrderProcess.OrderProcessSchema` schema.</span></span>  
  
#### <a name="add-a-receive-port-to-the-orchestration"></a><span data-ttu-id="f7bd7-140">Agregar un puerto de recepción a la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-140">Add a receive port to the orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-141">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **puerto** forma a la superficie del puerto.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-141">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="f7bd7-142">Se iniciará el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-142">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="f7bd7-143">En la pantalla de bienvenida, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-143">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-144">Tipo de `ReceivePurchaseOrder` en el **nombre** campo y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-144">Type `ReceivePurchaseOrder` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-145">Seleccione **crear un nuevo tipo de puerto**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-145">Select **Create a new Port Type**.</span></span>  
  
5.  <span data-ttu-id="f7bd7-146">Tipo de `PurchaseOrderPT` en el **nombre de tipo de puerto** campo y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-146">Type `PurchaseOrderPT` in the **Port Type Name** field, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f7bd7-147">En el **enlace de puerto pantalla**, deje los valores predeterminados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-147">On the **Port Binding screen**, leave the default values, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="f7bd7-148">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-148">Click **Finish**.</span></span>  
  
8.  <span data-ttu-id="f7bd7-149">En **Vista orquestación**, en **tipos de puerto**, expanda el `PurchaseOrderPT` tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-149">In **Orchestration View**, under **Port Types**, expand the `PurchaseOrderPT` port type.</span></span>  
  
9. <span data-ttu-id="f7bd7-150">Haga clic en `Operation_1`, haga clic en **cambiar el nombre de**y, a continuación, escriba `PurchaseOrderOperation`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-150">Right-click `Operation_1`, click **Rename**, and then type `PurchaseOrderOperation`.</span></span>  
  
#### <a name="add-a-receive-shape-to-the-orchestration"></a><span data-ttu-id="f7bd7-151">Agregar una forma Recepción a la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-151">Add a Receive shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-152">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **recepción** forma a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-152">Under **BizTalk Orchestrations** in the Toolbox, drag a **Receive** shape to the Orchestration.</span></span>  
  
2.  <span data-ttu-id="f7bd7-153">Haga clic en la forma recepción y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-153">Right-click the Receive shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-154">Establecer el **activar** propiedad `True`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-154">Set the **Activate** property to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7bd7-155">Si la propiedad Activar está establecida en False, obtendrá el siguiente error: "error X2214: debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado"</span><span class="sxs-lookup"><span data-stu-id="f7bd7-155">If the activate property is set to false, you will get the following error: "error X2214: you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
4.  <span data-ttu-id="f7bd7-156">Tipo de `Receive_PO` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-156">Type `Receive_PO` in the **Name** field.</span></span>  
  
5.  <span data-ttu-id="f7bd7-157">En el **ventana propiedades**, seleccione `Message_PO` para la propiedad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-157">In the **Properties Window**, select `Message_PO` for the Message property.</span></span>  
  
6.  <span data-ttu-id="f7bd7-158">Seleccione `ReceivePurchaseOrder.PurchaseOrderOperation.Request` para el **operación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-158">Select `ReceivePurchaseOrder.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="f7bd7-159">Con esto, se asociará el puerto a la forma Recepción en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-159">This will tie the port to the Receive shape in the Orchestration Designer.</span></span>  
  
## <a name="create-send-information"></a><span data-ttu-id="f7bd7-160">Crear información de envío</span><span class="sxs-lookup"><span data-stu-id="f7bd7-160">Create send information</span></span>  
 <span data-ttu-id="f7bd7-161">En este procedimiento, creará un mensaje, puertos de envío y una estructura de decisión nuevos en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-161">In this procedure you create a new message, send ports, and decision structure to the orchestration.</span></span> <span data-ttu-id="f7bd7-162">En él, se muestra cómo configurar una orquestación con lógica de decisiones, además de cómo configurar una orquestación para enviar un mensaje a un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-162">This procedure illustrates how to configure an orchestration with decision logic and how to configure an orchestration to send a message to a send port.</span></span>  
  
#### <a name="create-a-new-message"></a><span data-ttu-id="f7bd7-163">Crear un nuevo mensaje</span><span class="sxs-lookup"><span data-stu-id="f7bd7-163">Create a new message</span></span>  
  
1.  <span data-ttu-id="f7bd7-164">En **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-164">In **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="f7bd7-165">Con esto, se generará un nuevo mensaje con el nombre `Message_1`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-165">This will generate a new message with the name `Message_1`.</span></span>  
  
2.  <span data-ttu-id="f7bd7-166">Haga clic en `Message_1`, haga clic en **cambiar el nombre de**y, a continuación, escriba `Message_Task`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-166">Right-click `Message_1`, click **Rename**, and then type `Message_Task`.</span></span>  
  
3.  <span data-ttu-id="f7bd7-167">Haga clic en `Message_Task`y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-167">Right-click `Message_Task`, and then click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-168">En el **tipo de mensaje** propiedad, expanda **esquemas**y, a continuación, seleccione `OrderProcess.OrderProcessSchema` esquema.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-168">In the **Message Type** property, expand **Schemas**, and then select `OrderProcess.OrderProcessSchema` schema.</span></span>  
  
#### <a name="add-a-send-port-to-the-orchestration"></a><span data-ttu-id="f7bd7-169">Agregar un puerto de envío a la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-169">Add a send port to the orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-170">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **puerto** forma a la superficie del puerto.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-170">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="f7bd7-171">Se iniciará el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-171">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="f7bd7-172">En la pantalla de bienvenida, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-172">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-173">Tipo de `SendPurchaseOrder` en el **nombre** campo y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-173">Type `SendPurchaseOrder` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-174">Seleccione **utilizar un tipo de puerto existente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-174">Select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="f7bd7-175">En **tipos de puertos disponibles**, seleccione `OrderProcess.PurchaseOrderPT`y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-175">Under **Available Port Types**, select `OrderProcess.PurchaseOrderPT`, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f7bd7-176">En el **enlace de puerto pantalla**, en **dirección de puerto de comunicación**, seleccione `I'll always be sending messages on this port`y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-176">On the **Port Binding screen**, under **Port direction of communication**, select `I'll always be sending messages on this port`, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="f7bd7-177">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-177">Click **Finish**.</span></span>  
  
#### <a name="add-a-send-shape-to-the-orchestration"></a><span data-ttu-id="f7bd7-178">Agregar una forma Envío a la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-178">Add a Send shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-179">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **enviar** forma para el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-179">Under **BizTalk Orchestrations** in the Toolbox, drag a **Send** shape to the Orchestration Designer.</span></span> <span data-ttu-id="f7bd7-180">Colóquela bajo la forma de recepción `Receive_PO`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-180">Place it below the `Receive_PO` Receive shape.</span></span>  
  
2.  <span data-ttu-id="f7bd7-181">Haga clic en la forma de envío y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-181">Right-click the Send shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-182">Tipo de `Send_PO` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-182">Type `Send_PO` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f7bd7-183">Seleccione `Message_PO` para el **mensaje** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-183">Select `Message_PO` for the **Message** property.</span></span>  
  
5.  <span data-ttu-id="f7bd7-184">Seleccione `SendPurchaseOrder.PurchaseOrderOperation.Request` para el **operación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-184">Select `SendPurchaseOrder.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="f7bd7-185">Con esto, se asociará el puerto a la forma Envío en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-185">This will tie the port to the Send shape in the Orchestration Designer.</span></span>  
  
#### <a name="add-a-decide-shape-to-the-orchestration"></a><span data-ttu-id="f7bd7-186">Agregar una forma Decidir a la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-186">Add a Decide shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-187">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **decidir** forma para el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-187">Under **BizTalk Orchestrations** in the Toolbox, drag a **Decide** shape to the Orchestration Designer.</span></span> <span data-ttu-id="f7bd7-188">Colóquela bajo la forma de envío `Send_PO`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-188">Place it below the `Send_PO` Send shape.</span></span>  
  
2.  <span data-ttu-id="f7bd7-189">Haga clic en la forma decidir y, a continuación, haga clic en **ventana Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f7bd7-189">Right-click the Decide shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="f7bd7-190">Tipo de `NeedsApproval` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-190">Type `NeedsApproval` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f7bd7-191">En el Diseñador de orquestaciones, haga clic en **Rule_1** en la forma decidir.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-191">In Orchestration Designer, click **Rule_1** on the Decide shape.</span></span>  
  
5.  <span data-ttu-id="f7bd7-192">En la ventana Propiedades, escriba `ApprovalRequired` para el **nombre** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-192">In the Properties Windows, type `ApprovalRequired` for the **Name** property.</span></span>  
  
6.  <span data-ttu-id="f7bd7-193">Haga clic en el **expresión** propiedad de campo y, a continuación, haga clic en los puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-193">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
7.  <span data-ttu-id="f7bd7-194">En el Editor de expresiones de BizTalk, escriba o copie lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7bd7-194">In the BizTalk Expression Editor, type or copy the following:</span></span>  
  
    ```  
    Message_PO(OrderProcess.PropertySchema.Amount) > 1000  
    ```  
  
8.  <span data-ttu-id="f7bd7-195">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-195">Click **OK**.</span></span>  
  
#### <a name="add-another-send-port-to-the-orchestration"></a><span data-ttu-id="f7bd7-196">Agregar otro puerto de envío a la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-196">Add another send port to the orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-197">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **puerto** forma a la superficie del puerto.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-197">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="f7bd7-198">Se iniciará el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-198">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="f7bd7-199">En la pantalla de bienvenida, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-199">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-200">Tipo de `SendToTasksList` en el **nombre** campo y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-200">Type `SendToTasksList` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-201">Seleccione **utilizar un tipo de puerto existente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-201">Select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="f7bd7-202">En **tipos de puertos disponibles**, seleccione `OrderProcess.PurchaseOrderPT`y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-202">Under **Available Port Types**, select `OrderProcess.PurchaseOrderPT`, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f7bd7-203">En el **enlace de puerto pantalla**, en **dirección de puerto de comunicación**, seleccione `I'll always be sending messages on this port`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-203">On the **Port Binding screen**, under **Port direction of communication**, select `I'll always be sending messages on this port`.</span></span>  
  
7.  <span data-ttu-id="f7bd7-204">En **enlace de puerto**, seleccione `Dynamic`y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-204">Under **Port binding**, select `Dynamic`, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="f7bd7-205">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-205">Click **Finish**.</span></span>  
  
#### <a name="add-a-send-shape-to-the-decide-shape"></a><span data-ttu-id="f7bd7-206">Agregar una forma Envío a la forma Decidir</span><span class="sxs-lookup"><span data-stu-id="f7bd7-206">Add a Send shape to the Decide shape</span></span>  
  
1.  <span data-ttu-id="f7bd7-207">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **enviar** forma para el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-207">Under **BizTalk Orchestrations** in the Toolbox, drag a **Send** shape to the Orchestration Designer.</span></span> <span data-ttu-id="f7bd7-208">Colóquela bajo la forma `ApprovalRequired`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-208">Place it below the `ApprovalRequired` shape.</span></span>  
  
2.  <span data-ttu-id="f7bd7-209">Haga clic en la forma de envío y, a continuación, haga clic en **ventana Propiedades**</span><span class="sxs-lookup"><span data-stu-id="f7bd7-209">Right-click the Send shape, and then click **Properties Window**</span></span>  
  
3.  <span data-ttu-id="f7bd7-210">Tipo de `CreateApprovalTask` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-210">Type `CreateApprovalTask` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f7bd7-211">Seleccione `Message_Task` para el **mensaje** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-211">Select `Message_Task` for the **Message** property.</span></span>  
  
5.  <span data-ttu-id="f7bd7-212">Seleccione `SendToTasksList.PurchaseOrderOperation.Request` para el **operación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-212">Select `SendToTasksList.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="f7bd7-213">Con esto, se asociará el puerto a la forma Envío en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-213">This will tie the port to the Send shape in the Orchestration Designer.</span></span>  
  
## <a name="create-an-expression"></a><span data-ttu-id="f7bd7-214">Crear una expresión</span><span class="sxs-lookup"><span data-stu-id="f7bd7-214">Create an expression</span></span>  
 <span data-ttu-id="f7bd7-215">En este procedimiento, agregará una forma Expresión a la solución, con lo que se asignará la ruta de acceso de Tareas a una variable.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-215">In this procedure you add an Expression shape to your solution which assigns the Tasks path value to a variable.</span></span> <span data-ttu-id="f7bd7-216">En él, se muestra cómo agregar lógica a una orquestación para modificar las propiedades de un puerto de envío dinámico.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-216">This procedure illustrates how to add logic to an orchestration to modify the properties of a dynamic send port.</span></span>  
  
#### <a name="create-a-new-expression"></a><span data-ttu-id="f7bd7-217">Crear una nueva expresión</span><span class="sxs-lookup"><span data-stu-id="f7bd7-217">Create a new expression</span></span>  
  
1.  <span data-ttu-id="f7bd7-218">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **expresión** forma antes de la `CreateApprovalTask` forma de envío.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-218">Under **BizTalk Orchestrations** in the Toolbox, drag an **Expression** shape before the `CreateApprovalTask` Send shape.</span></span>  
  
2.  <span data-ttu-id="f7bd7-219">Haga clic en la forma de expresión y, a continuación, haga clic en **ventana Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f7bd7-219">Right-click the Expression shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="f7bd7-220">Tipo de `SetPortDestination` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-220">Type `SetPortDestination` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f7bd7-221">Haga clic en el **expresión** propiedad de campo y, a continuación, haga clic en los puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-221">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
5.  <span data-ttu-id="f7bd7-222">En el **Editor de expresiones de BizTalk**, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7bd7-222">In the **BizTalk Expression Editor**, type the following:</span></span>  
  
    ```  
    SendToTasksList(Microsoft.XLANGs.BaseTypes.Address) = "wss://localhost/sites/WSSAdapterWalkthrough/Lists/Tasks/";  
    ```  
  
6.  <span data-ttu-id="f7bd7-223">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-223">Click **OK**.</span></span>  
  
## <a name="construct-a-new-message"></a><span data-ttu-id="f7bd7-224">Construir un nuevo mensaje</span><span class="sxs-lookup"><span data-stu-id="f7bd7-224">Construct a new message</span></span>  
 <span data-ttu-id="f7bd7-225">En este procedimiento, agregará una forma Construir a la solución, con lo que se construirá una nueva instancia de un tipo de mensaje en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-225">In this procedure you add a Construct shape to the solution which will construct a new instance of a message type within the orchestration.</span></span> <span data-ttu-id="f7bd7-226">En él, se muestra cómo crear un mensaje nuevo que sea una copia del mensaje de entrada y, seguidamente, modificar las propiedades de contexto del nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-226">This procedure illustrates how to create a new message that is a copy of the inbound message and then modify the context properties of the new message.</span></span> <span data-ttu-id="f7bd7-227">Este paso es necesario porque los mensajes son inmutables en BizTalk; es decir, una vez construido el mensaje, no es posible modificar el original.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-227">This step is required because messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span>  
  
#### <a name="add-a-construct-shape"></a><span data-ttu-id="f7bd7-228">Agregar una forma Construir</span><span class="sxs-lookup"><span data-stu-id="f7bd7-228">Add a Construct Shape</span></span>  
  
1.  <span data-ttu-id="f7bd7-229">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **construir mensaje** forma antes de la `SetPortDestination` forma expresión.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-229">Under **BizTalk Orchestrations** in the Toolbox, drag a **Construct Message** shape before the `SetPortDestination` Expression shape.</span></span>  
  
2.  <span data-ttu-id="f7bd7-230">Haga clic en la forma construir mensaje y, a continuación, haga clic en **ventana Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f7bd7-230">Right-click the Construct Message shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="f7bd7-231">Tipo de `ConstructTaskMessage`en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-231">Type `ConstructTaskMessage`in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f7bd7-232">Seleccione `Message_Task` para el **mensajes construidos** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-232">Select `Message_Task` for the **Messages Constructed** property.</span></span>  
  
5.  <span data-ttu-id="f7bd7-233">En **orquestaciones de BizTalk** en el cuadro de herramientas, arrastre un **asignación de mensajes** forma la `ConstructTaskMessage` **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-233">Under **BizTalk Orchestrations** in the Toolbox, drag a **Message Assignment** shape into the `ConstructTaskMessage`**Construct Message** shape.</span></span>  
  
6.  <span data-ttu-id="f7bd7-234">En el **ventana propiedades**, tipo `InitTaskMessage` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-234">In the **Properties Window**, type `InitTaskMessage` in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="f7bd7-235">Haga clic en el **expresión** propiedad de campo y, a continuación, haga clic en los puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-235">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
8.  <span data-ttu-id="f7bd7-236">En el **Editor de expresiones de BizTalk**, escriba o copie lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7bd7-236">In the **BizTalk Expression Editor**, type or copy the following:</span></span>  
  
    ```  
    Message_Task = Message_PO;  
    Message_Task(WSS.ConfigOverwrite) = "no";  
    Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";  
    Message_Task(WSS.ConfigPropertiesXml) = "<ConfigPropertiesXml><PropertyName1>Title</PropertyName1><PropertySource1>Approve %XPATH=//orchns:PurchaseOrder/orchns:PurchaseOrderID%</PropertySource1><PropertyName3>Status</PropertyName3><PropertySource3>Not Started</PropertySource3><PropertyName4>Priority</PropertyName4><PropertySource4>(1) High</PropertySource4></ConfigPropertiesXml>";  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f7bd7-237">Al especificar los valores para estas propiedades de contexto, es preciso distinguir entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-237">These values supplied for these context properties are case sensitive.</span></span> <span data-ttu-id="f7bd7-238">Al establecer los valores de configuración para un puerto dinámico con propiedades de contexto, es necesario asegurarse de que se utilizan las mayúsculas y minúsculas del modo apropiado o, de lo contrario, se producirá un error cuando BizTalk intente enrutar el documento al puerto de envío designado.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-238">When setting configuration values for a dynamic port with context properties you must ensure that you use the proper case or an error will occur when BizTalk attempts to route the document to the designated send port.</span></span>  
  
9. <span data-ttu-id="f7bd7-239">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-239">Click **OK**.</span></span>  
  
10. <span data-ttu-id="f7bd7-240">Haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-240">Click **File**, and then click **Save All**.</span></span>  
  
## <a name="build-the-biztalk-project"></a><span data-ttu-id="f7bd7-241">Generar el proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f7bd7-241">Build the BizTalk project</span></span>  
 <span data-ttu-id="f7bd7-242">En este procedimiento, generará e implementará el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-242">In this procedure you build and deploy the BizTalk project.</span></span> <span data-ttu-id="f7bd7-243">Este paso resulta necesario para crear e implementar el ensamblado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-243">This step is required to create and deploy the assembly that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses at runtime.</span></span>  
  
#### <a name="build-and-deploy-the-solution"></a><span data-ttu-id="f7bd7-244">Compilar e implementar la solución</span><span class="sxs-lookup"><span data-stu-id="f7bd7-244">Build and deploy the solution</span></span>  
  
1.  <span data-ttu-id="f7bd7-245">Haga clic en **generar**y, a continuación, haga clic en **generar OrderProcess**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-245">Click **Build**, and then click **Build OrderProcess**.</span></span>  
  
2.  <span data-ttu-id="f7bd7-246">Haga clic en **generar**y, a continuación, haga clic en **implementar OrderProcess**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-246">Click **Build**, and then click **Deploy OrderProcess**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-247">Cierre Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7bd7-247">Close Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="modify-the-receive-location-and-send-port"></a><span data-ttu-id="f7bd7-248">Modificar la ubicación de recepción y el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="f7bd7-248">Modify the receive location and send port</span></span>  
 <span data-ttu-id="f7bd7-249">En este procedimiento, modificará la ubicación de recepción y el puerto de envío existentes para utilizar el procesamiento XML para las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-249">In this procedure you modify the existing receive location and send port to use XML processing for the pipelines.</span></span> <span data-ttu-id="f7bd7-250">La canalización XML de recepción almacena las propiedades de mensaje utilizadas durante el procesamiento de la orquestación, mientras que la canalización XML de envío almacena las propiedades de mensaje que se aplican en la orquestación y que se utilizarán posteriormente para el enrutamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-250">The receive XML pipeline persists message properties used during orchestration processing and the send XML pipeline persists the message properties that were applied in the orchestration which are subsequently used for message routing.</span></span>  
  
#### <a name="modify-the-receive-location"></a><span data-ttu-id="f7bd7-251">Modificar la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="f7bd7-251">Modify the receive location</span></span>  
  
1.  <span data-ttu-id="f7bd7-252">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="f7bd7-252">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="f7bd7-253">Expanda **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **complemento Administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda  **BizTalk Application 1**y, a continuación, haga clic en el **ubicaciones de recepción** nodo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-253">Expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration SnapIn**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and then click the **Receive Locations** node.</span></span>  
  
3.  <span data-ttu-id="f7bd7-254">Haga clic en `SourceLocation`y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-254">Right-click `SourceLocation`, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f7bd7-255">En el **propiedades de la ubicación de recepción** cuadro de diálogo **General**, seleccione `XMLReceive` para el **canalización de recepción** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-255">In the **Receive Location Properties** dialog box, under **General**, select `XMLReceive` for the **Receive pipeline** property.</span></span>  
  
5.  <span data-ttu-id="f7bd7-256">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-256">Click **OK**.</span></span>  
  
#### <a name="modify-the-send-port"></a><span data-ttu-id="f7bd7-257">Modificar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="f7bd7-257">Modify the send port</span></span>  
  
1.  <span data-ttu-id="f7bd7-258">Haga clic en el **puertos de envío** nodo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-258">Click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="f7bd7-259">Haga clic en `SendToDestination`y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-259">Right-click `SendToDestination`, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-260">En el **propiedades de puerto de envío** cuadro de diálogo **General**, seleccione `XMLTransmit` para el **canalización de envío** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-260">In the **Send Port Properties** dialog box, under **General**, select `XMLTransmit` for the **Send pipeline** property.</span></span>  
  
4.  <span data-ttu-id="f7bd7-261">Seleccione el **filtros** ficha.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-261">Select the **Filters** tab.</span></span>  
  
5.  <span data-ttu-id="f7bd7-262">Seleccione la condición existente, presione la tecla SUPR y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-262">Select the existing condition, press DELETE, and then click **OK**.</span></span>  
  
#### <a name="start-a-new-send-port"></a><span data-ttu-id="f7bd7-263">Iniciar un nuevo puerto de envío</span><span class="sxs-lookup"><span data-stu-id="f7bd7-263">Start a new send port</span></span>  
  
1.  <span data-ttu-id="f7bd7-264">Haga clic en el **puertos de envío** nodo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-264">Click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="f7bd7-265">Haga clic en `OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-265">Right-click `OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`, and then click **Start**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7bd7-266">Puede que sea necesario actualizar la consola si no resulta visible.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-266">You may have to refresh the console if this is not visible.</span></span>  
  
## <a name="bind-the-orchestration"></a><span data-ttu-id="f7bd7-267">Enlazar la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-267">Bind the orchestration</span></span>  
 <span data-ttu-id="f7bd7-268">En este procedimiento, enlazará la orquestación a los puertos especificados.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-268">In this procedure you bind the orchestration to the specified ports.</span></span> <span data-ttu-id="f7bd7-269">Este procedimiento resulta necesario para asociar puertos físicos a la orquestación generada e implementada.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-269">This procedure is required to tie physical ports to the orchestration that you built and deployed.</span></span>  
  
#### <a name="bind-the-orchestration"></a><span data-ttu-id="f7bd7-270">Enlazar la orquestación</span><span class="sxs-lookup"><span data-stu-id="f7bd7-270">Bind the orchestration</span></span>  
  
1.  <span data-ttu-id="f7bd7-271">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **orquestaciones** nodo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-271">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Orchestrations** node.</span></span>  
  
2.  <span data-ttu-id="f7bd7-272">Haga clic en el `OrderProcess.MyCompanyOrderProcessing` orquestación y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-272">Right-click the `OrderProcess.MyCompanyOrderProcessing` orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f7bd7-273">Seleccione el **enlaces** ficha.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-273">Select the **Bindings** tab.</span></span>  
  
4.  <span data-ttu-id="f7bd7-274">En **Host**, seleccione `BizTalkServerApplication` en el **Host** campo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-274">Under **Host**, select `BizTalkServerApplication` in the **Host** field.</span></span>  
  
5.  <span data-ttu-id="f7bd7-275">En **enlaces**, seleccione `FromSource` para el `ReceivePurchaseOrder` puerto lógico de entrada.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-275">Under **Bindings**, select `FromSource` for the `ReceivePurchaseOrder` Inbound Logical Port.</span></span>  
  
6.  <span data-ttu-id="f7bd7-276">En **enlaces**, seleccione `SendToDestination` para el `SendPurchaseOrder` puerto lógico de salida.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-276">Under **Bindings**, select `SendToDestination` for the `SendPurchaseOrder` Outbound Logical Port.</span></span>  
  
7.  <span data-ttu-id="f7bd7-277">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-277">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="f7bd7-278">Haga clic en `OrderProcess.MyCompanyOrderProcessing` orquestación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-278">Right click `OrderProcess.MyCompanyOrderProcessing` orchestration, and then click **Start**.</span></span>  
  
## <a name="send-a-message-through-the-system"></a><span data-ttu-id="f7bd7-279">Enviar un mensaje a través del sistema</span><span class="sxs-lookup"><span data-stu-id="f7bd7-279">Send a message through the system</span></span>  
 <span data-ttu-id="f7bd7-280">En este procedimiento, creará un formulario de InfoPath y lo cargará en el sitio web de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-280">In this procedure you create an InfoPath form and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="f7bd7-281">El adaptador de Windows SharePoint Services tomará el mensaje, lo archivará en la biblioteca de documentos de archivo y, a continuación, lo enviará a la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-281">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="f7bd7-282">Durante el procesamiento del mensaje, se obtendrá acceso a las propiedades de contexto de Windows SharePoint Services que ayudan a determinar el destino.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-282">During the processing of this message, Windows SharePoint Services context properties will be accessed that help determine the destination.</span></span>  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a><span data-ttu-id="f7bd7-283">Crear un formulario de InfoPath para su envío a través del sistema</span><span class="sxs-lookup"><span data-stu-id="f7bd7-283">Create an InfoPath form to send through the system</span></span>  
  
1.  <span data-ttu-id="f7bd7-284">Abra un explorador web y vaya a la dirección URL del sitio creado.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-284">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="f7bd7-285">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-285">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="f7bd7-286">En el menú Inicio rápido, haga clic en `InfoPathSolutions`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-286">In the Quick Launch menu, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="f7bd7-287">Haga clic en el `PurchaseOrder` archivo para mostrar el **descarga de archivos** cuadro de diálogo y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-287">Click the `PurchaseOrder` file to display the **File Download** dialog box, and then click **Open**.</span></span> <span data-ttu-id="f7bd7-288">InfoPath cargará el formulario.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-288">InfoPath will load the form.</span></span>  
  
4.  <span data-ttu-id="f7bd7-289">En el **Purchase Order ID** , escriba `1003`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-289">In the **Purchase Order ID** field, type `1003`.</span></span>  
  
5.  <span data-ttu-id="f7bd7-290">En el **facturar a** , escriba `John Doe`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-290">In the **Bill To** field, type `John Doe`.</span></span>  
  
6.  <span data-ttu-id="f7bd7-291">En el **cantidad** , escriba `1750`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-291">In the **Amount** field, type `1750`.</span></span>  
  
7.  <span data-ttu-id="f7bd7-292">En el **fecha del pedido de compra** , escriba `1/3/2005`.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-292">In the **Purchase Order Date** field, type `1/3/2005`.</span></span>  
  
8.  <span data-ttu-id="f7bd7-293">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-293">Click **Save**.</span></span>  
  
9. <span data-ttu-id="f7bd7-294">En el **Guardar como** cuadro de diálogo, escriba `http://<server_name>/sites/WSSAdapterWalkthrough/Source`en el **nombre de archivo** campo y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-294">In the **Save As** dialog box, type `http://<server_name>/sites/WSSAdapterWalkthrough/Source`in the **file name** field, and then press ENTER.</span></span>  
  
10. <span data-ttu-id="f7bd7-295">Tipo de `PurchaseOrder3.xml` en el **nombre de archivo** campo y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-295">Type `PurchaseOrder3.xml` in the **file name** field, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="f7bd7-296">Cierre InfoPath.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-296">Close InfoPath.</span></span>  
  
12. <span data-ttu-id="f7bd7-297">En el explorador Web, haga clic en **documentos y listas**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-297">In the Web browser, click **Documents and Lists**.</span></span>  
  
13. <span data-ttu-id="f7bd7-298">En **las bibliotecas de documentos**, haga clic en **destino**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-298">Under **Document Libraries**, click **Destination**.</span></span>  
  
14. <span data-ttu-id="f7bd7-299">En la biblioteca de documentos de destino, verá ahora el mensaje incluido en esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-299">In the Destination document library, you will now see your message listed in this library.</span></span> <span data-ttu-id="f7bd7-300">También encontrará una copia archivada en la biblioteca de documentos de archivo.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-300">You will also find a copy archived in the Archive document library.</span></span>  
  
15. <span data-ttu-id="f7bd7-301">Haga clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-301">Click **Home**.</span></span>  
  
16. <span data-ttu-id="f7bd7-302">En **enumera**, haga clic en **tareas**.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-302">Under **Lists**, click **Tasks**.</span></span>  
  
17. <span data-ttu-id="f7bd7-303">En la lista Tareas, verá la tarea de aprobación recién creada.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-303">In the Tasks list you will see the newly created approval task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7bd7-304">Puesto que el importe del pedido superaba los 1.000,00 dólares, se creó la tarea.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-304">Since the amount of the purchase order was over $1,000.00, the task was created.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="f7bd7-305">Resumen</span><span class="sxs-lookup"><span data-stu-id="f7bd7-305">Summary</span></span>  
 <span data-ttu-id="f7bd7-306">En este tutorial, ha visto cómo obtener acceso a las propiedades de contexto de Windows SharePoint Services y cómo determinar el destino de los mensajes que circulan a través de puertos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-306">In this walkthrough you have seen how to access the Windows SharePoint Services context properties and how to determine the destination of messages going through dynamic ports.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f7bd7-307">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f7bd7-307">Next Steps</span></span>  
 <span data-ttu-id="f7bd7-308">Continúe revisando el resto de la sección del adaptador de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-308">Continue to review the rest of the Windows SharePoint Services adapter section.</span></span> <span data-ttu-id="f7bd7-309">Para obtener más información, vea los temas de Vea también.</span><span class="sxs-lookup"><span data-stu-id="f7bd7-309">For more information, see the topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7bd7-310">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7bd7-310">See Also</span></span>  
 <span data-ttu-id="f7bd7-311">[¿Qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f7bd7-311">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="f7bd7-312">Tutoriales del adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="f7bd7-312">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)