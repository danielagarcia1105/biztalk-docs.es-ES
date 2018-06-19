---
title: Cómo comprobar el estado de actividad de un mensaje | Documentos de Microsoft
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
ms.openlocfilehash: 872c1a1fcfcc905caf926c8299f56d49178a8448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256548"
---
# <a name="how-to-verify-activity-status-of-a-message"></a><span data-ttu-id="1e1cb-102">Cómo comprobar el estado de actividad de un  mensaje</span><span class="sxs-lookup"><span data-stu-id="1e1cb-102">How to Verify Activity Status of a Message</span></span>
<span data-ttu-id="1e1cb-103">Para crear un host y un puerto HTTP de PeopleSoft donde PeopleSoft envíe los eventos, se usa el Agente de integración de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-103">You use the PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="1e1cb-104">Para asegurarse de que el mensaje esté activo y enrutado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-104">You make sure that the message is active and routed by following these steps.</span></span>  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a><span data-ttu-id="1e1cb-105">Para verificar que un mensaje esté activo y se haya enrutado correctamente</span><span class="sxs-lookup"><span data-stu-id="1e1cb-105">To verify that a Message is active and routed correctly</span></span>  
  
1.  <span data-ttu-id="1e1cb-106">Haga clic en **iniciar**, seleccione **programas**, seleccione **PeopleSoft Application Name**y, a continuación, seleccione **Application Designer**.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-106">Click **Start**, point to **Programs**, point to **PeopleSoft Application Name**, and then select **Application Designer**.</span></span>  
  
2.  <span data-ttu-id="1e1cb-107">En el **PeopleSoft Sign-on** pantalla, escriba la **Id. de usuario** y **contraseña**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-107">On the **PeopleSoft Sign-on** screen, enter the **User ID** and **Password**, and then click **OK**.</span></span>  
  
     ![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")  
  
     ![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")  
  
3.  <span data-ttu-id="1e1cb-108">En el Diseñador de aplicaciones, en la **archivo** menú, elija **abiertos**y, a continuación, seleccione **mensaje**.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-108">In the Application Designer, on the **File** menu, point to **Open**, and then select **Message**.</span></span>  
  
     ![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")  
  
4.  <span data-ttu-id="1e1cb-109">En el **Abrir definición** pantalla, en la **nombre** , escriba `LOCATION_SYNC`y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-109">In the **Open Definition** screen, in the **Name** field, enter `LOCATION_SYNC`, and then click **Open**.</span></span>  
  
     ![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")  
  
5.  <span data-ttu-id="1e1cb-110">En el **definiciones que coinciden con los criterios de selección** sección, haga doble clic en el **LOCATION_SYNC** mensaje para ver las propiedades.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-110">In the **Definitions matching selection criteria** section, double-click the **LOCATION_SYNC** message to view the properties.</span></span>  
  
     ![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")  
  
6.  <span data-ttu-id="1e1cb-111">En el Diseñador de aplicaciones, haga clic en **LOCATION_TBL**y seleccione **propiedades de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-111">In the Application Designer, right-click **LOCATION_TBL**, and select **Message Properties**.</span></span>  
  
     ![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")  
  
7.  <span data-ttu-id="1e1cb-112">En el **propiedades de mensaje** pantalla, haga clic en el **Use** ficha.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-112">On the **Message Properties** screen, click the **Use** tab.</span></span>  
  
     <span data-ttu-id="1e1cb-113">Compruebe lo siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-113">Verify the following, and then click **OK**.</span></span>  
  
    1.  <span data-ttu-id="1e1cb-114">**Mensaje:** Active</span><span class="sxs-lookup"><span data-stu-id="1e1cb-114">**Message:** Active</span></span>  
  
    2.  <span data-ttu-id="1e1cb-115">**Canal de mensaje:** ENTERPRISE_SETUP</span><span class="sxs-lookup"><span data-stu-id="1e1cb-115">**Message Channel:** ENTERPRISE_SETUP</span></span>  
  
    3.  <span data-ttu-id="1e1cb-116">**Versión predeterminada:** VERSION_1</span><span class="sxs-lookup"><span data-stu-id="1e1cb-116">**Default Version:** VERSION_1</span></span>  
  
     ![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")  
  
8.  <span data-ttu-id="1e1cb-117">Salga de Application Designer.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-117">Exit the Application Designer.</span></span>  
  
     <span data-ttu-id="1e1cb-118">De este modo, se asegura de que el estado del mensaje sea activo, de que usa VERSION_1 y de que se transmite a través del canal ENTERPRISE_SETUP en PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-118">This makes sure that the Message is in an active state, uses VERSION_1, and flows through the ENTERPRISE_SETUP channel in PeopleSoft.</span></span>  
  
9. <span data-ttu-id="1e1cb-119">Configure el archivo Integration.Gateway.properties para establecer comunicación con la aplicación de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="1e1cb-119">Configure the Integration.Gateway.properties file to communicate with the PeopleSoft application.</span></span>  
  
     <span data-ttu-id="1e1cb-120">Compruebe que se hayan configurado las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e1cb-120">Verify that the following properties are set:</span></span>  
  
    -   <span data-ttu-id="1e1cb-121">**Ig.ISC.ServerURL:** //server:9000</span><span class="sxs-lookup"><span data-stu-id="1e1cb-121">**ig.isc.serverurl:** //server:9000</span></span>  
  
    -   <span data-ttu-id="1e1cb-122">**Ig.ISC.UserID:** Id. para PS</span><span class="sxs-lookup"><span data-stu-id="1e1cb-122">**ig.isc.userid:** ID for PS</span></span>  
  
    -   <span data-ttu-id="1e1cb-123">**Ig.ISC.Password:** contraseña para PS</span><span class="sxs-lookup"><span data-stu-id="1e1cb-123">**ig.isc.password:** Password for PS</span></span>  
  
    -   <span data-ttu-id="1e1cb-124">**Ig.ISC.toolsrel:** versión específica</span><span class="sxs-lookup"><span data-stu-id="1e1cb-124">**ig.isc.toolsrel:** Specific Release</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e1cb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e1cb-125">See Also</span></span>  
 [<span data-ttu-id="1e1cb-126">Crear un Host de HTTP de PeopleSoft y puerto</span><span class="sxs-lookup"><span data-stu-id="1e1cb-126">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)