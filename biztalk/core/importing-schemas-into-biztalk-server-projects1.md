---
title: Importación de esquemas en BizTalk Server Projects1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70eff140259cd7cf815e8e05125f9ade78bf5493
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982365"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="78c25-102">Importación de esquemas en proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="78c25-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="78c25-103">La información siguiente describe cómo importar esquemas en un proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="78c25-103">The following information describes how to import schemas into a BizTalk Server project.</span></span>  
  
## <a name="importing-schemas"></a><span data-ttu-id="78c25-104">Importación de esquemas</span><span class="sxs-lookup"><span data-stu-id="78c25-104">Importing Schemas</span></span>  
  
#### <a name="to-import-schemas"></a><span data-ttu-id="78c25-105">Para importar esquemas</span><span class="sxs-lookup"><span data-stu-id="78c25-105">To import schemas</span></span>  
  
1. <span data-ttu-id="78c25-106">En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="78c25-106">In Solution Explorer, right-click the project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="78c25-107">Haga clic en **agregar adaptador**y, a continuación, seleccione **abierto**.</span><span class="sxs-lookup"><span data-stu-id="78c25-107">Click **Add adapter**, and then select **Open**.</span></span>  
  
3. <span data-ttu-id="78c25-108">Seleccione el adaptador<strong>, J.D. Edwards OneWorld XE</strong>.</span><span class="sxs-lookup"><span data-stu-id="78c25-108">Select the adapter<strong>, J.D. Edwards OneWorld XE</strong>.</span></span>  
  
4. <span data-ttu-id="78c25-109">En la lista desplegable, seleccione el puerto **SSOSendToJD Edwards OneWorld XE**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78c25-109">In the drop-down list, select the port **SSOSendToJD Edwards OneWorld XE**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="78c25-110">El myJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-110">The myJ.D.</span></span> <span data-ttu-id="78c25-111">Sistema lógico Edwards OneWorld XESSO aparece en el explorador (este sistema lógico se creó con la SSOSendToJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-111">Edwards OneWorld XESSO logical system appears in the browser (this logical system was created with the SSOSendToJ.D.</span></span> <span data-ttu-id="78c25-112">Puerto Edwards OneWorld XE).</span><span class="sxs-lookup"><span data-stu-id="78c25-112">Edwards OneWorld XE port).</span></span>  
  
5. <span data-ttu-id="78c25-113">Expanda **myJ.D. Edwards OneWorld XESSO**.</span><span class="sxs-lookup"><span data-stu-id="78c25-113">Expand **myJ.D. Edwards OneWorld XESSO**.</span></span>  
  
6. <span data-ttu-id="78c25-114">Haga clic en el icono de flecha para mover el elemento (o simplemente arrástrelo) en el **transmisión** ventana y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78c25-114">Click the arrow icon to move the item (or simply drag it) into the **Transmit** window, and then click **OK**.</span></span>  
  
    <span data-ttu-id="78c25-115">Los esquemas se agregan al proyecto SSOSchedule.</span><span class="sxs-lookup"><span data-stu-id="78c25-115">The schemas are added to the SSOSchedule project.</span></span>  
  
7. <span data-ttu-id="78c25-116">En el Explorador de soluciones, expanda **proyecto SSOSchedule**.</span><span class="sxs-lookup"><span data-stu-id="78c25-116">In Solution Explorer, expand **SSOSchedule project**.</span></span>  
  
8. <span data-ttu-id="78c25-117">Haga clic en **BizTalk orchestration.odx**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="78c25-117">Right-click **BizTalk orchestration.odx**, and then click **Delete**.</span></span>  
  
9. <span data-ttu-id="78c25-118">En el Explorador de soluciones, haga doble clic en **GetList.odx** para inspeccionar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="78c25-118">In Solution Explorer, double-click **GetList.odx** to inspect the orchestration.</span></span>  
  
## <a name="orchestration-types---port-types"></a><span data-ttu-id="78c25-119">Tipos de orquestaciones: tipos de puertos</span><span class="sxs-lookup"><span data-stu-id="78c25-119">Orchestration Types - Port Types</span></span>  
  
-   <span data-ttu-id="78c25-120">**PortTypeIn / / solicitud:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-120">**PortTypeIn/In/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="78c25-121">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="78c25-121">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="78c25-122">**PortTypeOut/Out/respuesta:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-122">**PortTypeOut/Out/response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="78c25-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="78c25-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
-   <span data-ttu-id="78c25-124">**PortTypeInOut/InOut/solicitud:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-124">**PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="78c25-125">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="78c25-125">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="78c25-126">**PortTypeInOut/InOut/respuesta:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-126">**PortTypeInOut/InOut/Response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="78c25-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="78c25-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="orchestration-variables---messages"></a><span data-ttu-id="78c25-128">Variables de orquestación: mensajes</span><span class="sxs-lookup"><span data-stu-id="78c25-128">Orchestration Variables - Messages</span></span>  
  
-   <span data-ttu-id="78c25-129">**MessageIn:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-129">**MessageIn:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="78c25-130">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="78c25-130">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="78c25-131">**MessageOut:** SSOSchedule.myJ.D.</span><span class="sxs-lookup"><span data-stu-id="78c25-131">**MessageOut:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="78c25-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="78c25-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c25-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="78c25-133">See Also</span></span>  
 [<span data-ttu-id="78c25-134">Seguridad en el adaptador</span><span class="sxs-lookup"><span data-stu-id="78c25-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)