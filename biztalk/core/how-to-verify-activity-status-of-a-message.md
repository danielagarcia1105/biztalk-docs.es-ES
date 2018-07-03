---
title: Cómo comprobar el estado de actividad de un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities, verifying status
- PeopleSoft Integration Broker
- verifying message status in PeopleSoft
- messages, verifying status
ms.assetid: b8cee6f9-0f65-4228-a87a-3f3aca6182bf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af3a77b9bb169e394571444c7eb7e3984f7f7c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013045"
---
# <a name="how-to-verify-activity-status-of-a-message"></a><span data-ttu-id="87a47-102">Cómo comprobar el estado de actividad de un  mensaje</span><span class="sxs-lookup"><span data-stu-id="87a47-102">How to Verify Activity Status of a Message</span></span>
<span data-ttu-id="87a47-103">Para crear un host y un puerto HTTP de PeopleSoft donde PeopleSoft envíe los eventos, se usa el Agente de integración de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="87a47-103">You use the PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="87a47-104">Para asegurarse de que el mensaje esté activo y enrutado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="87a47-104">You make sure that the message is active and routed by following these steps.</span></span>  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a><span data-ttu-id="87a47-105">Para verificar que un mensaje esté activo y se haya enrutado correctamente</span><span class="sxs-lookup"><span data-stu-id="87a47-105">To verify that a Message is active and routed correctly</span></span>  
  
1. <span data-ttu-id="87a47-106">Haga clic en **iniciar**, apunte a **programas**, apunte a **PeopleSoft Application Name**y, a continuación, seleccione **Application Designer**.</span><span class="sxs-lookup"><span data-stu-id="87a47-106">Click **Start**, point to **Programs**, point to **PeopleSoft Application Name**, and then select **Application Designer**.</span></span>  
  
2. <span data-ttu-id="87a47-107">En el **PeopleSoft Sign-on** pantalla, escriba el **Id. de usuario** y **contraseña**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="87a47-107">On the **PeopleSoft Sign-on** screen, enter the **User ID** and **Password**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="87a47-108">![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")</span><span class="sxs-lookup"><span data-stu-id="87a47-108">![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")</span></span>  
  
    <span data-ttu-id="87a47-109">![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")</span><span class="sxs-lookup"><span data-stu-id="87a47-109">![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")</span></span>  
  
3. <span data-ttu-id="87a47-110">En el Diseñador de aplicaciones, en la **archivo** menú, elija **abierto**y, a continuación, seleccione **mensaje**.</span><span class="sxs-lookup"><span data-stu-id="87a47-110">In the Application Designer, on the **File** menu, point to **Open**, and then select **Message**.</span></span>  
  
    <span data-ttu-id="87a47-111">![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")</span><span class="sxs-lookup"><span data-stu-id="87a47-111">![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")</span></span>  
  
4. <span data-ttu-id="87a47-112">En el **Abrir definición** pantalla, en el **nombre** , introduzca `LOCATION_SYNC`y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="87a47-112">In the **Open Definition** screen, in the **Name** field, enter `LOCATION_SYNC`, and then click **Open**.</span></span>  
  
    <span data-ttu-id="87a47-113">![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")</span><span class="sxs-lookup"><span data-stu-id="87a47-113">![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")</span></span>  
  
5. <span data-ttu-id="87a47-114">En el **definiciones que coinciden con los criterios de selección** sección, haga doble clic en el **LOCATION_SYNC** mensaje para ver las propiedades.</span><span class="sxs-lookup"><span data-stu-id="87a47-114">In the **Definitions matching selection criteria** section, double-click the **LOCATION_SYNC** message to view the properties.</span></span>  
  
    <span data-ttu-id="87a47-115">![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")</span><span class="sxs-lookup"><span data-stu-id="87a47-115">![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")</span></span>  
  
6. <span data-ttu-id="87a47-116">En el Diseñador de aplicaciones, haga clic en **LOCATION_TBL**y seleccione **propiedades de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="87a47-116">In the Application Designer, right-click **LOCATION_TBL**, and select **Message Properties**.</span></span>  
  
    <span data-ttu-id="87a47-117">![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")</span><span class="sxs-lookup"><span data-stu-id="87a47-117">![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")</span></span>  
  
7. <span data-ttu-id="87a47-118">En el **propiedades de mensaje** pantalla, haga clic en el **Use** ficha.</span><span class="sxs-lookup"><span data-stu-id="87a47-118">On the **Message Properties** screen, click the **Use** tab.</span></span>  
  
    <span data-ttu-id="87a47-119">Compruebe lo siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="87a47-119">Verify the following, and then click **OK**.</span></span>  
  
   1. <span data-ttu-id="87a47-120">**Mensaje:** activo</span><span class="sxs-lookup"><span data-stu-id="87a47-120">**Message:** Active</span></span>  
  
   2. <span data-ttu-id="87a47-121">**Canal de mensaje:** ENTERPRISE_SETUP</span><span class="sxs-lookup"><span data-stu-id="87a47-121">**Message Channel:** ENTERPRISE_SETUP</span></span>  
  
   3. <span data-ttu-id="87a47-122">**Versión predeterminada:** VERSION_1</span><span class="sxs-lookup"><span data-stu-id="87a47-122">**Default Version:** VERSION_1</span></span>  
  
      <span data-ttu-id="87a47-123">![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")</span><span class="sxs-lookup"><span data-stu-id="87a47-123">![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")</span></span>  
  
8. <span data-ttu-id="87a47-124">Salga de Application Designer.</span><span class="sxs-lookup"><span data-stu-id="87a47-124">Exit the Application Designer.</span></span>  
  
    <span data-ttu-id="87a47-125">De este modo, se asegura de que el estado del mensaje sea activo, de que usa VERSION_1 y de que se transmite a través del canal ENTERPRISE_SETUP en PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="87a47-125">This makes sure that the Message is in an active state, uses VERSION_1, and flows through the ENTERPRISE_SETUP channel in PeopleSoft.</span></span>  
  
9. <span data-ttu-id="87a47-126">Configure el archivo Integration.Gateway.properties para establecer comunicación con la aplicación de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="87a47-126">Configure the Integration.Gateway.properties file to communicate with the PeopleSoft application.</span></span>  
  
     <span data-ttu-id="87a47-127">Compruebe que se hayan configurado las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="87a47-127">Verify that the following properties are set:</span></span>  
  
    -   <span data-ttu-id="87a47-128">**Ig.ISC.ServerURL:** //server:9000</span><span class="sxs-lookup"><span data-stu-id="87a47-128">**ig.isc.serverurl:** //server:9000</span></span>  
  
    -   <span data-ttu-id="87a47-129">**Ig.ISC.UserID:** Id. para PS</span><span class="sxs-lookup"><span data-stu-id="87a47-129">**ig.isc.userid:** ID for PS</span></span>  
  
    -   <span data-ttu-id="87a47-130">**Ig.ISC.Password:** contraseña para PS</span><span class="sxs-lookup"><span data-stu-id="87a47-130">**ig.isc.password:** Password for PS</span></span>  
  
    -   <span data-ttu-id="87a47-131">**Ig.ISC.toolsrel:** versión específica</span><span class="sxs-lookup"><span data-stu-id="87a47-131">**ig.isc.toolsrel:** Specific Release</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a47-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="87a47-132">See Also</span></span>  
 [<span data-ttu-id="87a47-133">Creación de puertos y hosts HTTP de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="87a47-133">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)