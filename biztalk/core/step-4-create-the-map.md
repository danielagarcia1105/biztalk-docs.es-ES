---
title: 'Paso 4: Crear el mapa | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7f1f6d-0e57-4a65-b91d-c81fcc832961
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67128880233a04b6b1573f11ff5229cebe328b25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-the-map"></a><span data-ttu-id="b5e8b-102">Paso 4: Crear la asignación</span><span class="sxs-lookup"><span data-stu-id="b5e8b-102">Step 4: Create the Map</span></span>
<span data-ttu-id="b5e8b-103">![Paso 4 de 5](../core/media/step-4of5.gif "Step_4of5")</span><span class="sxs-lookup"><span data-stu-id="b5e8b-103">![Step 4 of 5](../core/media/step-4of5.gif "Step_4of5")</span></span>  
  
 <span data-ttu-id="b5e8b-104">**Tiempo en completarse:** 6 minutos</span><span class="sxs-lookup"><span data-stu-id="b5e8b-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="b5e8b-105">**Objetivo:** en este paso, se creará una asignación que transforma el mensaje de solicitud en un mensaje RequestDecline.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-105">**Objective:** In this step, you create a map that transforms Request message to RequestDecline message.</span></span>  
  
 <span data-ttu-id="b5e8b-106">**Propósito:** la asignación garantiza que el número de Id. de solicitud y el total general se incluyen en el mensaje de rechazo de solicitud devuelve al sistema de inventario de almacén.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-106">**Purpose:** The map ensures that the request ID number and the grand total are included in the request decline message returned to the warehouse inventory system.</span></span> <span data-ttu-id="b5e8b-107">El Asignador de BizTalk se emplea para vincular los campos de un mensaje entrante a los campos definidos en el mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-107">You use BizTalk Mapper to link fields in an incoming message to fields defined for the outgoing message.</span></span> <span data-ttu-id="b5e8b-108">Este proceso resulta necesario porque los dos mensajes no tienen la misma estructura de esquema.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-108">This is necessary because these two messages do not have the same schema structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b5e8b-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b5e8b-109">Prerequisites</span></span>  
 <span data-ttu-id="b5e8b-110">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="b5e8b-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="b5e8b-111">Antes de comenzar este paso debe completar [paso 2: crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) y [paso 3: crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md).</span><span class="sxs-lookup"><span data-stu-id="b5e8b-111">Before you begin this step you must complete [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) and [Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b5e8b-112">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="b5e8b-112">Procedures</span></span>  
 <span data-ttu-id="b5e8b-113">La asignación depende del esquema de solicitud y del esquema RequestDecline.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-113">The map depends on the Request schema and the RequestDecline schema.</span></span>  <span data-ttu-id="b5e8b-114">Debe compilar el proyecto con el esquema antes de poder utilizarlo en una asignación.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-114">You much compile the project with the schema before you can use them on a map.</span></span>  
  
#### <a name="to-compile-the-eaischemas-project"></a><span data-ttu-id="b5e8b-115">Para compilar el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="b5e8b-115">To compile the EAISchemas project</span></span>  
  
-   <span data-ttu-id="b5e8b-116">En el Explorador de soluciones, haga clic en **EAISchemas**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-116">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
#### <a name="to-create-the-map"></a><span data-ttu-id="b5e8b-117">Para crear la asignación</span><span class="sxs-lookup"><span data-stu-id="b5e8b-117">To create the map</span></span>  
  
1.  <span data-ttu-id="b5e8b-118">En el Explorador de soluciones, haga clic en el **EAISchemas** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-118">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="b5e8b-119">En el **Agregar nuevo elemento - EAISchemas** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5e8b-119">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b5e8b-120">Use</span><span class="sxs-lookup"><span data-stu-id="b5e8b-120">Use this</span></span>|<span data-ttu-id="b5e8b-121">Para</span><span class="sxs-lookup"><span data-stu-id="b5e8b-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b5e8b-122">**Plantillas instaladas**</span><span class="sxs-lookup"><span data-stu-id="b5e8b-122">**Installed Templates**</span></span>|<span data-ttu-id="b5e8b-123">Haga clic en **archivos de asignación**y, a continuación, haga clic en **mapa**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-123">Click **Map Files**, and then click **Map**.</span></span>|  
    |<span data-ttu-id="b5e8b-124">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="b5e8b-124">**Name**</span></span>|<span data-ttu-id="b5e8b-125">Tipo de **MapToReqDecline.btm**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-125">Type **MapToReqDecline.btm**.</span></span>|  
  
3.  <span data-ttu-id="b5e8b-126">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-126">Click **Add**.</span></span>  
  
     <span data-ttu-id="b5e8b-127">La siguiente ilustración muestra el Esquema de origen, el Esquema de destino y la Cuadrícula del Asignador.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-127">The following figure shows the Source Schema, Destination Schema, and Mapper Grid.</span></span>  
  
     <span data-ttu-id="b5e8b-128">![Mapa MapToReqDenied](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span><span class="sxs-lookup"><span data-stu-id="b5e8b-128">![MapToReqDenied map](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span></span>  
  
4.  <span data-ttu-id="b5e8b-129">En el **esquema de origen** panel, haga clic en **Abrir esquema de origen**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-129">In the **Source Schema** pane, click **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="b5e8b-130">En el **selector de tipos de BizTalk** cuadro de diálogo, expanda **EAISchemas**, expanda **esquemas**, haga clic en **EAISchemas.Request**y, a continuación, haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-130">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.Request**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b5e8b-131">En el **esquema de origen** panel, haga clic en  **\<esquema >**y, a continuación, haga clic en **Expandir nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-131">In the **Source Schema** pane, right-click **\<Schema>**, and then click **Expand Tree Node**.</span></span>  
  
7.  <span data-ttu-id="b5e8b-132">En el **esquema de destino** panel, haga clic en **Abrir esquema de destino**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-132">In the **Destination Schema** pane, click **Open Destination Schema**.</span></span>  
  
8.  <span data-ttu-id="b5e8b-133">En el **selector de tipos de BizTalk** cuadro de diálogo, expanda **EAISchemas**, expanda **esquemas**, haga clic en **EAISchemas.RequestDecline**y, a continuación, Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-133">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.RequestDecline**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="b5e8b-134">En el **esquema de destino** panel, haga clic en  **\<esquema >**y, a continuación, haga clic en **Expandir nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-134">In the **Destination Schema** pane, right-click **\<Schema>**, and then click **Expand Tree Node**.</span></span>  
  
10. <span data-ttu-id="b5e8b-135">En el **esquema de origen** , arrastre el **ReqID** campo a la **ReqID** en el **esquema de destino** panel.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-135">In the **Source Schema** pane, drag the **ReqID** field to the **ReqID** in the **Destination Schema** pane.</span></span> <span data-ttu-id="b5e8b-136">Aparece una línea que conecta los dos elementos.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-136">A line appears connecting the two elements.</span></span>  
  
11. <span data-ttu-id="b5e8b-137">En el **esquema de origen** , arrastre el **GrandTotal** campo a la **GrandTotal** campo el **esquema de destino** panel para asignar los datos de un esquema a otro.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-137">In the **Source Schema** pane, drag the **GrandTotal** field to the **GrandTotal** field in the **Destination Schema** pane to map the data from one schema to the other.</span></span>  
  
12. <span data-ttu-id="b5e8b-138">En el **archivo** menú, haga clic en **guardar todo** para guardar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-138">On the **File** menu, click **Save All** to save your work.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b5e8b-139">Síntesis</span><span class="sxs-lookup"><span data-stu-id="b5e8b-139">What did I just do?</span></span>  
 <span data-ttu-id="b5e8b-140">En este paso, creó una asignación que transforma el mensaje de solicitud en un mensaje RequestDecline.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-140">In this step, you created a map that transforms Request message to RequestDecline message.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b5e8b-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b5e8b-141">Next Steps</span></span>  
 <span data-ttu-id="b5e8b-142">Generar el proyecto EAISchemas.</span><span class="sxs-lookup"><span data-stu-id="b5e8b-142">You build the EAISchemas project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e8b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5e8b-143">See Also</span></span>  
 <span data-ttu-id="b5e8b-144">[Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="b5e8b-144">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="b5e8b-145">[Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="b5e8b-145">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="b5e8b-146">[Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="b5e8b-146">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="b5e8b-147">[Paso 4: Crear el mapa](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="b5e8b-147">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="b5e8b-148">[Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="b5e8b-148">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 [<span data-ttu-id="b5e8b-149">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b5e8b-149">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)