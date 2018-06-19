---
title: 'Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a8a8906-7c7d-437c-9f04-345ad4ac460e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db97afa0de19e15e5005e5647279365ea6ba023b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224092"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a><span data-ttu-id="a9d45-102">Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta</span><span class="sxs-lookup"><span data-stu-id="a9d45-102">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>
<span data-ttu-id="a9d45-103">![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="a9d45-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="a9d45-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="a9d45-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="a9d45-105">**Objetivo:** en este paso, se envía el mensaje de solicitud para insertar registros en el **Purchase_Order** de tabla y recibir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="a9d45-105">**Objective:** In this step, you send the request message to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a9d45-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a9d45-106">Prerequisites</span></span>  
 <span data-ttu-id="a9d45-107">Debe haber completado [paso 2: asignar el mensaje de respuesta de UPDATE_EMPLOYEE a insertar el mensaje de solicitud de operación](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md).</span><span class="sxs-lookup"><span data-stu-id="a9d45-107">You must have completed [Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="a9d45-108">Para enviar el mensaje de solicitud y recibir una respuesta</span><span class="sxs-lookup"><span data-stu-id="a9d45-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="a9d45-109">Agregue las siguientes formas a la orquestación en el **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="a9d45-109">Add the following shapes to the orchestration under the **Construct Message** shape.</span></span>  
  
    |<span data-ttu-id="a9d45-110">Forma</span><span class="sxs-lookup"><span data-stu-id="a9d45-110">Shape</span></span>|<span data-ttu-id="a9d45-111">Tipo de forma</span><span class="sxs-lookup"><span data-stu-id="a9d45-111">Shape Type</span></span>|<span data-ttu-id="a9d45-112">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a9d45-112">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="a9d45-113">SendInsertMessage</span><span class="sxs-lookup"><span data-stu-id="a9d45-113">SendInsertMessage</span></span>|<span data-ttu-id="a9d45-114">Send</span><span class="sxs-lookup"><span data-stu-id="a9d45-114">Send</span></span>|<span data-ttu-id="a9d45-115">-Establecer **mensaje** a *InsertPO*</span><span class="sxs-lookup"><span data-stu-id="a9d45-115">-   Set **Message** to *InsertPO*</span></span><br /><span data-ttu-id="a9d45-116">-Establecer **nombre** a *SendInsertMessage*</span><span class="sxs-lookup"><span data-stu-id="a9d45-116">-   Set **Name** to *SendInsertMessage*</span></span>|  
    |<span data-ttu-id="a9d45-117">ReceiveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="a9d45-117">ReceiveInsertResponse</span></span>|<span data-ttu-id="a9d45-118">Receive</span><span class="sxs-lookup"><span data-stu-id="a9d45-118">Receive</span></span>|<span data-ttu-id="a9d45-119">-Establecer **activar** a *False*</span><span class="sxs-lookup"><span data-stu-id="a9d45-119">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="a9d45-120">-Establecer **mensaje** a *InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="a9d45-120">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="a9d45-121">-Establecer **nombre** a *ReceiveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="a9d45-121">-   Set **Name** to *ReceiveInsertResponse*</span></span>|  
    |<span data-ttu-id="a9d45-122">SaveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="a9d45-122">SaveInsertResponse</span></span>|<span data-ttu-id="a9d45-123">Send</span><span class="sxs-lookup"><span data-stu-id="a9d45-123">Send</span></span>|<span data-ttu-id="a9d45-124">-Establecer **mensaje** a *InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="a9d45-124">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="a9d45-125">-Establecer **nombre** a *SaveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="a9d45-125">-   Set **Name** to *SaveInsertResponse*</span></span>|  
  
2.  <span data-ttu-id="a9d45-126">Modificar el **SQLOutboundPort** que creó en [paso 2: enviar el mensaje de solicitud a SQL Server y recibir respuesta](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span><span class="sxs-lookup"><span data-stu-id="a9d45-126">Modify the **SQLOutboundPort** you created in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
    1.  <span data-ttu-id="a9d45-127">Haga clic en el Diseñador de orquestaciones el puerto y, a continuación, haga clic en **nueva operación**.</span><span class="sxs-lookup"><span data-stu-id="a9d45-127">Right-click the port in the Orchestration Designer, and then click **New Operation**.</span></span> <span data-ttu-id="a9d45-128">Los cambios de la forma de puerto para agregar una nueva operación, **Operation_1**.</span><span class="sxs-lookup"><span data-stu-id="a9d45-128">The port shape changes to add a new operation, **Operation_1**.</span></span>  
  
    2.  <span data-ttu-id="a9d45-129">Haga clic en **Operation_1** y en la ventana Propiedades, cambie el valor de identificador a **InsertPO**.</span><span class="sxs-lookup"><span data-stu-id="a9d45-129">Click **Operation_1** and in the properties window, change the value of Identifier to **InsertPO**.</span></span>  
  
3.  <span data-ttu-id="a9d45-130">Agregar un puerto de envío unidireccional a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a9d45-130">Add a one-way send port to the orchestration.</span></span> <span data-ttu-id="a9d45-131">Usará este puerto para enviar el mensaje de respuesta para la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="a9d45-131">You will use this port to send the response message for the Insert operation.</span></span> <span data-ttu-id="a9d45-132">Establezca las siguientes propiedades para el puerto.</span><span class="sxs-lookup"><span data-stu-id="a9d45-132">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="a9d45-133">Establezca esta propiedad</span><span class="sxs-lookup"><span data-stu-id="a9d45-133">Set this property</span></span>|<span data-ttu-id="a9d45-134">En este valor</span><span class="sxs-lookup"><span data-stu-id="a9d45-134">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="a9d45-135">**Dirección de comunicación**</span><span class="sxs-lookup"><span data-stu-id="a9d45-135">**Communication Direction**</span></span>|<span data-ttu-id="a9d45-136">Send</span><span class="sxs-lookup"><span data-stu-id="a9d45-136">Send</span></span>|  
    |<span data-ttu-id="a9d45-137">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="a9d45-137">**Communication Pattern**</span></span>|<span data-ttu-id="a9d45-138">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a9d45-138">One-Way</span></span>|  
    |<span data-ttu-id="a9d45-139">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="a9d45-139">**Identifier**</span></span>|<span data-ttu-id="a9d45-140">SaveResponsePort</span><span class="sxs-lookup"><span data-stu-id="a9d45-140">SaveResponsePort</span></span>|  
  
     <span data-ttu-id="a9d45-141">Además, cambiar el nombre de la operación de Operation_1 a **InsertPO**.</span><span class="sxs-lookup"><span data-stu-id="a9d45-141">Also, change the operation name from Operation_1 to **InsertPO**.</span></span>  
  
4.  <span data-ttu-id="a9d45-142">Conecte el puerto a formas de acción.</span><span class="sxs-lookup"><span data-stu-id="a9d45-142">Connect the port to action shapes.</span></span> <span data-ttu-id="a9d45-143">En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde para el puerto a los correspondientes indicador verde de la forma acción.</span><span class="sxs-lookup"><span data-stu-id="a9d45-143">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a9d45-144">En este paso, utilizará el método de arrastrar y colocar para conectar los puertos a las formas de acción.</span><span class="sxs-lookup"><span data-stu-id="a9d45-144">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="a9d45-145">De forma alternativa, podría utilizar la propiedad de operación de una forma de acción para conectar esta última a un puerto.</span><span class="sxs-lookup"><span data-stu-id="a9d45-145">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="a9d45-146">Conectar los puertos y las formas de acción como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a9d45-146">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="a9d45-147">Conectar el **SendInsertMessage** forma acción a la **solicitar** identificador de la **InsertPO** el funcionamiento de la **SQLOutboundPort**.</span><span class="sxs-lookup"><span data-stu-id="a9d45-147">Connect the **SendInsertMessage** action shape to the **Request** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="a9d45-148">Conectar el **ReceiveInsertResponse** forma acción a la **respuesta** identificador de la **InsertPO** el funcionamiento de la **SQLOutboundPort**.</span><span class="sxs-lookup"><span data-stu-id="a9d45-148">Connect the **ReceiveInsertResponse** action shape to the **Response** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="a9d45-149">Conectar el **SaveInsertResponse** forma acción a la **solicitar** identificador de la **SaveResponsePort**.</span><span class="sxs-lookup"><span data-stu-id="a9d45-149">Connect the **SaveInsertResponse** action shape to the **Request** handle of the **SaveResponsePort**.</span></span>  
  
5.  <span data-ttu-id="a9d45-150">La siguiente ilustración muestra la orquestación en curso.</span><span class="sxs-lookup"><span data-stu-id="a9d45-150">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="a9d45-151">![Completar la orquestación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span><span class="sxs-lookup"><span data-stu-id="a9d45-151">![Complete orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="a9d45-152">Síntesis</span><span class="sxs-lookup"><span data-stu-id="a9d45-152">What did I just do?</span></span>  
 <span data-ttu-id="a9d45-153">Se envía la solicitud para insertar registros en el **Purchase_Order** de tabla y recibir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="a9d45-153">You sent the request to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a9d45-154">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a9d45-154">Next Steps</span></span>  
 <span data-ttu-id="a9d45-155">Compile el proyecto, como se describe en [paso 4: crear el proyecto](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md).</span><span class="sxs-lookup"><span data-stu-id="a9d45-155">You build the project, as described in [Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d45-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9d45-156">See Also</span></span>  
 <span data-ttu-id="a9d45-157">[Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE insertar el mensaje de solicitud de operación](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="a9d45-157">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 <span data-ttu-id="a9d45-158">[Paso 4: Generar el proyecto](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span><span class="sxs-lookup"><span data-stu-id="a9d45-158">[Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span></span>  
 [<span data-ttu-id="a9d45-159">Lección 4: Realizar una operación de inserción en la tabla de orden de compra</span><span class="sxs-lookup"><span data-stu-id="a9d45-159">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)