---
title: 'Paso 2: Crear mensajes para orquestaciones de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47a4fb98-6085-4aeb-ab39-2f2c3858d4e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bad2f052efa561020ba04060a8290137a08f542
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995365"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a><span data-ttu-id="0f179-102">Paso 2: Crear mensajes para orquestaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0f179-102">Step 2: Create Messages for BizTalk Orchestrations</span></span>
<span data-ttu-id="0f179-103">![Paso 2 de 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="0f179-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="0f179-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="0f179-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="0f179-105">**Objetivo:** en este paso, podrá agregar una orquestación al proyecto de BizTalk y crear mensajes para los esquemas que generó en [paso 1: generar el esquema para las operaciones](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0f179-105">**Objective:** In this step, you add an orchestration to the BizTalk project and create messages for the schemas you generated in [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f179-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f179-106">Prerequisites</span></span>  
 <span data-ttu-id="0f179-107">Debe haber completado [paso 1: generar el esquema para las operaciones](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0f179-107">You must have completed [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
### <a name="to-create-messages-in-an-orchestration"></a><span data-ttu-id="0f179-108">Para crear mensajes en una orquestación</span><span class="sxs-lookup"><span data-stu-id="0f179-108">To create messages in an orchestration</span></span>  
  
1. <span data-ttu-id="0f179-109">Agregar una orquestación de BizTalk para el proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0f179-109">Add a BizTalk orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span></span>  
  
   1.  <span data-ttu-id="0f179-110">Desde el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f179-110">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span>  
  
   2.  <span data-ttu-id="0f179-111">En el **Agregar nuevo elemento** cuadro de diálogo desde el **categorías** cuadro, haga clic en **archivos de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="0f179-111">In the **Add New Item** dialog box, from the **Categories** box, click **Orchestration Files**.</span></span> <span data-ttu-id="0f179-112">Desde el **plantillas** cuadro, haga clic en **orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="0f179-112">From the **Templates** box, click **BizTalk Orchestration**.</span></span>  
  
   3.  <span data-ttu-id="0f179-113">Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="0f179-113">Type a name for the BizTalk orchestration, and then click **Add**.</span></span> <span data-ttu-id="0f179-114">Para este tutorial, escriba el nombre `EmployeeOrch.odx`.</span><span class="sxs-lookup"><span data-stu-id="0f179-114">For this tutorial, enter the name `EmployeeOrch.odx`.</span></span>  
  
2. <span data-ttu-id="0f179-115">Abra el **Vista orquestación** ventana del proyecto de BizTalk, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="0f179-115">Open the **Orchestration View** window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="0f179-116">Para ello, haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="0f179-116">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3. <span data-ttu-id="0f179-117">Agregar mensajes a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0f179-117">Add messages to the orchestration.</span></span>  
  
   1.  <span data-ttu-id="0f179-118">En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="0f179-118">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
   2.  <span data-ttu-id="0f179-119">Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0f179-119">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
   3.  <span data-ttu-id="0f179-120">En el **propiedades** panel **Message_1**, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f179-120">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
       |<span data-ttu-id="0f179-121">Use</span><span class="sxs-lookup"><span data-stu-id="0f179-121">Use this</span></span>|<span data-ttu-id="0f179-122">Para</span><span class="sxs-lookup"><span data-stu-id="0f179-122">To do this</span></span>|  
       |--------------|----------------|  
       |<span data-ttu-id="0f179-123">Identificador</span><span class="sxs-lookup"><span data-stu-id="0f179-123">Identifier</span></span>|<span data-ttu-id="0f179-124">Tipo `NotifyReceive`.</span><span class="sxs-lookup"><span data-stu-id="0f179-124">Type `NotifyReceive`.</span></span>|  
       |<span data-ttu-id="0f179-125">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="0f179-125">Message Type</span></span>|<span data-ttu-id="0f179-126">En la lista desplegable, expanda **esquemas**y seleccione **Employee_PurchaseOrder.Notification**, donde Employee_PurchaseOrder es el nombre de su proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0f179-126">From the drop-down list, expand **Schemas**, and select **Employee_PurchaseOrder.Notification**, where Employee_PurchaseOrder is the name of your BizTalk project.</span></span> <span data-ttu-id="0f179-127">Notificación es el esquema generado para el **notificación** operación.</span><span class="sxs-lookup"><span data-stu-id="0f179-127">Notification is the schema generated for the **Notification** operation.</span></span>|  
  
   4.  <span data-ttu-id="0f179-128">Repita el paso anterior para agregar cuatro nuevos mensajes, un mensaje de solicitud y respuesta establecida para invocar el update_employee al procedimiento almacenado y establece otro mensaje de solicitud y respuesta para llevar a cabo la **insertar** operación en  **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="0f179-128">Repeat the previous step to add four new messages—a request-response message set for invoking the UPDATE_EMPLOYEE stored procedure and another request-response message set for performing the **Insert** operation on **Purchase_Order** table.</span></span>  
  
       |<span data-ttu-id="0f179-129">Identificador de conjunto para</span><span class="sxs-lookup"><span data-stu-id="0f179-129">Set Identifier to</span></span>|<span data-ttu-id="0f179-130">Establecer el tipo de mensaje en</span><span class="sxs-lookup"><span data-stu-id="0f179-130">Set Message Type to</span></span>|  
       |-----------------------|-------------------------|  
       |<span data-ttu-id="0f179-131">UpdateEmployee</span><span class="sxs-lookup"><span data-stu-id="0f179-131">UpdateEmployee</span></span>|<span data-ttu-id="0f179-132">*Employee_PurchaseOrder.TypedProcedure_dbo. UPDATE_EMPLOYEE*, donde TypedProcedure_dbo. UPDATE_EMPLOYEE es que el esquema para el update_employee al procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0f179-132">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEE*, where TypedProcedure_dbo.UPDATE_EMPLOYEE is the schema for the UPDATE_EMPLOYEE stored procedure.</span></span>|  
       |<span data-ttu-id="0f179-133">UpdateEmployeeResponse</span><span class="sxs-lookup"><span data-stu-id="0f179-133">UpdateEmployeeResponse</span></span>|<span data-ttu-id="0f179-134">*Employee_PurchaseOrder.TypedProcedure_dbo. UPDATE_EMPLOYEEResponse*</span><span class="sxs-lookup"><span data-stu-id="0f179-134">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEEResponse*</span></span>|  
       |<span data-ttu-id="0f179-135">InsertPO</span><span class="sxs-lookup"><span data-stu-id="0f179-135">InsertPO</span></span>|<span data-ttu-id="0f179-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*, donde TableOperation_dbo_Purchase_Order.Insert es el esquema para la operación de inserción en la tabla Purchase_Order.</span><span class="sxs-lookup"><span data-stu-id="0f179-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*, where TableOperation_dbo_Purchase_Order.Insert is the schema for the Insert operation on the Purchase_Order table.</span></span>|  
       |<span data-ttu-id="0f179-137">InsertPOResponse</span><span class="sxs-lookup"><span data-stu-id="0f179-137">InsertPOResponse</span></span>|<span data-ttu-id="0f179-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span><span class="sxs-lookup"><span data-stu-id="0f179-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span></span>|  
  
   5.  <span data-ttu-id="0f179-139">Guarde el archivo de orquestación y proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0f179-139">Save the orchestration file and the BizTalk project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="0f179-140">Síntesis</span><span class="sxs-lookup"><span data-stu-id="0f179-140">What did I just do?</span></span>  
 <span data-ttu-id="0f179-141">En este paso, ha creado los mensajes para invocar la realización de operaciones de entrada y salida en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f179-141">In this step, you created messages for invoking performing inbound and outbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0f179-142">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0f179-142">Next Steps</span></span>  
 <span data-ttu-id="0f179-143">Agregar formas de orquestación para recibir una notificación de SQL Server y filtrar notificaciones para la operación de inserción, como se describe en [lección 2: recibir notificaciones de filtro y](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="0f179-143">You add orchestration shapes to receive notification from SQL Server and filter notifications for Insert operation, as described in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f179-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f179-144">See Also</span></span>  
 <span data-ttu-id="0f179-145">[Lección 1: Generar esquemas y crear mensajes](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0f179-145">[Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span></span>  
 [<span data-ttu-id="0f179-146">Paso 1: Generar el esquema para las operaciones</span><span class="sxs-lookup"><span data-stu-id="0f179-146">Step 1: Generate Schema for Operations</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)