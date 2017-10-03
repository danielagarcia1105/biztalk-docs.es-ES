---
title: 'Paso 8: Crear un mapa con el asignador de BizTalk | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48e2578211d65ade2a50916e909c87a6fd84bf44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a><span data-ttu-id="2e274-102">Paso 8: Crear un mapa con el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2e274-102">Step 8: Create a Map with BizTalk Mapper</span></span>
<span data-ttu-id="2e274-103">En este paso, se utiliza al asignador de BizTalk para crear un mapa.</span><span class="sxs-lookup"><span data-stu-id="2e274-103">In this step, you use the BizTalk Mapper to create a map.</span></span> <span data-ttu-id="2e274-104">Utilice este mapa para crear vínculos que asocian los datos (campos) en un documento de solicitud de reposición a los datos en una solicitud denegada documento.</span><span class="sxs-lookup"><span data-stu-id="2e274-104">You use this map to create links that associate the data (fields) in a replenishment request document to the data in a request denied document.</span></span>  
  
### <a name="to-create-a-map"></a><span data-ttu-id="2e274-105">Para crear un mapa</span><span class="sxs-lookup"><span data-stu-id="2e274-105">To create a map</span></span>  
  
1.  <span data-ttu-id="2e274-106">En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2e274-106">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="2e274-107">En el **Agregar nuevo elemento** cuadro de diálogo, en la **categorías** panel, haga clic en **archivos de asignación**.</span><span class="sxs-lookup"><span data-stu-id="2e274-107">In the **Add New Item** dialog box, in the **Categories** pane, click **Map Files**.</span></span>  
  
3.  <span data-ttu-id="2e274-108">En el **nombre** , escriba **DoorbellMap** para nombrar la asignación y, a continuación, haga clic en **agregar** para iniciar el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e274-108">In the **Name** field, type **DoorbellMap** to name the map, and then click **Add** to start BizTalk Mapper.</span></span>  
  
4.  <span data-ttu-id="2e274-109">En el **esquema de origen** panel (izquierda), haga clic en **Abrir esquema de origen**.</span><span class="sxs-lookup"><span data-stu-id="2e274-109">In the **Source Schema** pane (left side), click **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="2e274-110">En el cuadro de diálogo Selector de tipos de BizTalk, expanda **BTAHL7 proyecto**, expanda **esquemas**, haga clic en **BTAHL7_Project.Doorbell**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2e274-110">In the BizTalk Type Picker dialog box, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7_Project.Doorbell**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="2e274-111">En el **esquema de destino** panel (derecha), haga clic en **Abrir esquema de destino**.</span><span class="sxs-lookup"><span data-stu-id="2e274-111">In the **Destination Schema** pane (right side), click **Open Destination Schema**.</span></span>  
  
7.  <span data-ttu-id="2e274-112">En el selector de tipos de BizTalk, expanda **BTAHL7 proyecto**, expanda **esquemas**, haga clic en **BTAHL7Schemas.ADT_A04_22_GLO_DEF**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2e274-112">In the BizTalk Type Picker, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7Schemas.ADT_A04_22_GLO_DEF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="2e274-113">En el **esquema de destino** panel (derecha), expanda **ADT_A04_22_GLO_DEF**, expanda **PID_PatientIdentification**y expanda **PID.5_PatientName** .</span><span class="sxs-lookup"><span data-stu-id="2e274-113">In the **Destination Schema** pane (right side), expand **ADT_A04_22_GLO_DEF**, expand **PID_PatientIdentification**, and expand **PID.5_PatientName**.</span></span>  
  
9. <span data-ttu-id="2e274-114">En el **esquema de origen** panel (izquierda), expanda **DoorbellRoot**.</span><span class="sxs-lookup"><span data-stu-id="2e274-114">In the **Source Schema** pane (left side), expand **DoorbellRoot**.</span></span> <span data-ttu-id="2e274-115">Arrastre el **LastName** campo a la **PN_0_FamilyName** campo el **esquema de destino** panel.</span><span class="sxs-lookup"><span data-stu-id="2e274-115">Drag the **LastName** field to the **PN_0_FamilyName** field in the **Destination Schema** pane.</span></span>  
  
10. <span data-ttu-id="2e274-116">En el **esquema de origen** , arrastre el **FirstName** campo a la **PN_1_GivenName** campo el **esquema de destino** panel.</span><span class="sxs-lookup"><span data-stu-id="2e274-116">In the **Source Schema** pane, drag the **FirstName** field to the **PN_1_GivenName** field in the **Destination Schema** pane.</span></span>  
  
11. <span data-ttu-id="2e274-117">En el **esquema de origen** , arrastre el **MiddleName** campo a la **PN_2_MiddleInitialOrName** campo el **esquema de destino** panel .</span><span class="sxs-lookup"><span data-stu-id="2e274-117">In the **Source Schema** pane, drag the **MiddleName** field to the **PN_2_MiddleInitialOrName** field in the **Destination Schema** pane.</span></span>  
  
12. <span data-ttu-id="2e274-118">En el **esquema de destino** panel, expanda **PID_3_PatientIdInternalId**.</span><span class="sxs-lookup"><span data-stu-id="2e274-118">In the **Destination Schema** pane, expand **PID_3_PatientIdInternalId**.</span></span>  
  
13. <span data-ttu-id="2e274-119">En el **esquema de origen** , arrastre el **SSN** campo a la **CM_PAT_ID_0_PatientID** en el **esquema de destino** panel.</span><span class="sxs-lookup"><span data-stu-id="2e274-119">In the **Source Schema** pane, drag the **SSN** field to the **CM_PAT_ID_0_PatientID** in the **Destination Schema** pane.</span></span>  
  
14. <span data-ttu-id="2e274-120">En el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="2e274-120">In the **File** menu, click **Save All**.</span></span>  
  
 <span data-ttu-id="2e274-121">En un escenario de enriquecimiento del mensaje habitual, si faltara cualquier información de los pacientes, se podría realizar una llamada a una base de datos de registros de paciente en la orquestación y la información que falta, a continuación, use la información adicional para completar la asignación.</span><span class="sxs-lookup"><span data-stu-id="2e274-121">In a typical message enrichment scenario, if any patient information were missing, you would make a call to a Patient Records database in your orchestration and add the missing information, then use the additional information to complete the mapping.</span></span> <span data-ttu-id="2e274-122">Por ejemplo, puede recuperar la dirección particular de un paciente de la base de datos de registros de paciente, puesto que el mensaje de evento de desencadenador de timbre XML entrante no la proporcionó.</span><span class="sxs-lookup"><span data-stu-id="2e274-122">For example, you might retrieve the home address of a patient from the Patient Records database, since the inbound XML doorbell trigger event message did not provide it.</span></span>  
  
 <span data-ttu-id="2e274-123">Continúe con [paso 9: validar y compilar el proyecto de mapa](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md).</span><span class="sxs-lookup"><span data-stu-id="2e274-123">Proceed to [Step 9: Validate and Build the Map Project](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e274-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e274-124">See Also</span></span>  
 [<span data-ttu-id="2e274-125">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="2e274-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)