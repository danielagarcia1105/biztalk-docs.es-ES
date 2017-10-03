---
title: "Importación de esquemas en BizTalk Server Projects1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0e67ef4e47b62e0381d882739b2fdc012ba621
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="6909f-102">Importación de esquemas en proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6909f-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="6909f-103">La información siguiente describe cómo importar esquemas en un proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6909f-103">The following information describes how to import schemas into a BizTalk Server project.</span></span>  
  
## <a name="importing-schemas"></a><span data-ttu-id="6909f-104">Importación de esquemas</span><span class="sxs-lookup"><span data-stu-id="6909f-104">Importing Schemas</span></span>  
  
#### <a name="to-import-schemas"></a><span data-ttu-id="6909f-105">Para importar esquemas</span><span class="sxs-lookup"><span data-stu-id="6909f-105">To import schemas</span></span>  
  
1.  <span data-ttu-id="6909f-106">En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="6909f-106">In Solution Explorer, right-click the project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="6909f-107">Haga clic en **agregar adaptador**y, a continuación, seleccione **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="6909f-107">Click **Add adapter**, and then select **Open**.</span></span>  
  
3.  <span data-ttu-id="6909f-108">Seleccione el adaptador**, J.D. Edwards OneWorld XE**.</span><span class="sxs-lookup"><span data-stu-id="6909f-108">Select the adapter**, J.D. Edwards OneWorld XE**.</span></span>  
  
4.  <span data-ttu-id="6909f-109">En la lista desplegable, seleccione el puerto **SSOSendToJD Edwards OneWorld XE**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6909f-109">In the drop-down list, select the port **SSOSendToJD Edwards OneWorld XE**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="6909f-110">MyJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-110">The myJ.D.</span></span> <span data-ttu-id="6909f-111">Sistema lógico Edwards OneWorld XESSO aparece en el explorador (este sistema lógico se creó con la SSOSendToJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-111">Edwards OneWorld XESSO logical system appears in the browser (this logical system was created with the SSOSendToJ.D.</span></span> <span data-ttu-id="6909f-112">Puerto Edwards OneWorld XE).</span><span class="sxs-lookup"><span data-stu-id="6909f-112">Edwards OneWorld XE port).</span></span>  
  
5.  <span data-ttu-id="6909f-113">Expanda **myJ.D. Edwards OneWorld XESSO**.</span><span class="sxs-lookup"><span data-stu-id="6909f-113">Expand **myJ.D. Edwards OneWorld XESSO**.</span></span>  
  
6.  <span data-ttu-id="6909f-114">Haga clic en el icono de flecha para mover el elemento (o simplemente arrástrelo) en el **transmisión** ventana y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6909f-114">Click the arrow icon to move the item (or simply drag it) into the **Transmit** window, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6909f-115">Los esquemas se agregan al proyecto SSOSchedule.</span><span class="sxs-lookup"><span data-stu-id="6909f-115">The schemas are added to the SSOSchedule project.</span></span>  
  
7.  <span data-ttu-id="6909f-116">En el Explorador de soluciones, expanda **proyecto SSOSchedule**.</span><span class="sxs-lookup"><span data-stu-id="6909f-116">In Solution Explorer, expand **SSOSchedule project**.</span></span>  
  
8.  <span data-ttu-id="6909f-117">Haga clic en **BizTalk orchestration.odx**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6909f-117">Right-click **BizTalk orchestration.odx**, and then click **Delete**.</span></span>  
  
9. <span data-ttu-id="6909f-118">En el Explorador de soluciones, haga doble clic en **GetList.odx** para inspeccionar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6909f-118">In Solution Explorer, double-click **GetList.odx** to inspect the orchestration.</span></span>  
  
## <a name="orchestration-types---port-types"></a><span data-ttu-id="6909f-119">Tipos de orquestaciones: tipos de puertos</span><span class="sxs-lookup"><span data-stu-id="6909f-119">Orchestration Types - Port Types</span></span>  
  
-   <span data-ttu-id="6909f-120">**PortTypeIn / / solicitud:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-120">**PortTypeIn/In/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="6909f-121">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="6909f-121">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="6909f-122">**PortTypeOut/Out/respuesta:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-122">**PortTypeOut/Out/response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="6909f-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="6909f-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
-   <span data-ttu-id="6909f-124">**PortTypeInOut/InOut/solicitud:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-124">**PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="6909f-125">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="6909f-125">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="6909f-126">**PortTypeInOut/InOut/respuesta:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-126">**PortTypeInOut/InOut/Response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="6909f-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="6909f-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="orchestration-variables---messages"></a><span data-ttu-id="6909f-128">Variables de orquestación: mensajes</span><span class="sxs-lookup"><span data-stu-id="6909f-128">Orchestration Variables - Messages</span></span>  
  
-   <span data-ttu-id="6909f-129">**MessageIn:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-129">**MessageIn:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="6909f-130">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="6909f-130">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="6909f-131">**MessageOut:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="6909f-131">**MessageOut:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="6909f-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="6909f-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6909f-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6909f-133">See Also</span></span>  
 [<span data-ttu-id="6909f-134">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="6909f-134">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)