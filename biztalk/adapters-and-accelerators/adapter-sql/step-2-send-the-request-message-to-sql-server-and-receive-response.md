---
title: 'Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir respuesta | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 864d2174-d54b-4383-92bf-f6808a2a904b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce820ab6a1914e44239313588eaaefeb696e61d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224804"
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a><span data-ttu-id="607f7-102">Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir respuesta</span><span class="sxs-lookup"><span data-stu-id="607f7-102">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>
<span data-ttu-id="607f7-103">![Paso 2 de 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="607f7-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="607f7-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="607f7-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="607f7-105">**Objetivo:** en este paso, se envía el mensaje de solicitud para ejecutar el **UPDATE_EMPLOYEE** procedimiento almacenado y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="607f7-105">**Objective:** In this step, you send the request message to execute the **UPDATE_EMPLOYEE** stored procedure and receive the response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="607f7-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="607f7-106">Prerequisites</span></span>  
 <span data-ttu-id="607f7-107">Debe haber completado [paso 1: crear el mensaje de solicitud para el procedimiento almacenado de UPDATE_EMPLOYEE](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="607f7-107">You must have completed [Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="607f7-108">Para enviar el mensaje de solicitud y recibir una respuesta</span><span class="sxs-lookup"><span data-stu-id="607f7-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="607f7-109">A la orquestación existente, en la **insertar** bloquear de la **decidir** forma, agregue un **asignación de mensajes** forma.</span><span class="sxs-lookup"><span data-stu-id="607f7-109">To the existing orchestration, under the **Insert** block of the **Decide** shape, add a **Message Assignment** shape.</span></span> <span data-ttu-id="607f7-110">En el cuadro de herramientas, arrastre el **asignación de mensajes** forma para el espacio indicado.</span><span class="sxs-lookup"><span data-stu-id="607f7-110">From the Toolbox, drag the **Message Assignment** shape to the space indicated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="607f7-111">Al colocar el **asignación de mensajes** forma en la superficie de diseño, el Diseñador de orquestaciones crea los incluye **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="607f7-111">When you drop the **Message Assignment** shape onto the design surface, Orchestration Designer creates the enclosing **Construct Message** shape for you.</span></span>  
  
2.  <span data-ttu-id="607f7-112">En la superficie de diseño, haga clic en el **ConstructMessage_1** forma y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="607f7-112">On the design surface, right-click the **ConstructMessage_1** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="607f7-113">En el **propiedades** panel para la **ConstructMessage_1** forma, especifique los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="607f7-113">In the **Properties** pane for the **ConstructMessage_1** shape, specify the following values.</span></span>  
  
    |<span data-ttu-id="607f7-114">Establezca esta propiedad</span><span class="sxs-lookup"><span data-stu-id="607f7-114">Set this property</span></span>|<span data-ttu-id="607f7-115">En este valor</span><span class="sxs-lookup"><span data-stu-id="607f7-115">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="607f7-116">**Mensajes construidos**</span><span class="sxs-lookup"><span data-stu-id="607f7-116">**Messages Constructed**</span></span>|<span data-ttu-id="607f7-117">UpdateEmployee</span><span class="sxs-lookup"><span data-stu-id="607f7-117">UpdateEmployee</span></span>|  
    |<span data-ttu-id="607f7-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="607f7-118">**Name**</span></span>|<span data-ttu-id="607f7-119">ConstructRequestMessage</span><span class="sxs-lookup"><span data-stu-id="607f7-119">ConstructRequestMessage</span></span>|  
  
4.  <span data-ttu-id="607f7-120">Haga doble clic en el **MessageAssignment** forma para abrir el **Editor de expresiones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="607f7-120">Double-click the **MessageAssignment** shape to open the **BizTalk Expression Editor**.</span></span>  
  
5.  <span data-ttu-id="607f7-121">En el **Editor de expresiones de BizTalk**, agregue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="607f7-121">In the **BizTalk Expression Editor**, add the following:</span></span>  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     <span data-ttu-id="607f7-122">En este caso, **UpdateEmployee** es el mensaje que creó en [paso 2: crear mensajes de orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) para enviar mensajes de solicitud **UPDATE_EMPLOYEE** almacenados procedimiento.</span><span class="sxs-lookup"><span data-stu-id="607f7-122">Here, **UpdateEmployee** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) for sending request messages for **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="607f7-123">En el **MessageAssignment** forma, se invoca el **UpdateEmployeeMessageCreator** clase para crear un mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="607f7-123">In the **MessageAssignment** shape, you invoke the **UpdateEmployeeMessageCreator** class to create a request message.</span></span> <span data-ttu-id="607f7-124">Además, Establece la acción de WCF para el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="607f7-124">Also, you set the WCF action for the request message.</span></span>  
  
6.  <span data-ttu-id="607f7-125">Agregue las siguientes formas a la orquestación en el **asignación de mensajes** forma.</span><span class="sxs-lookup"><span data-stu-id="607f7-125">Add the following shapes to the orchestration under the **Message Assignment** shape.</span></span>  
  
    |<span data-ttu-id="607f7-126">Forma</span><span class="sxs-lookup"><span data-stu-id="607f7-126">Shape</span></span>|<span data-ttu-id="607f7-127">Tipo de forma</span><span class="sxs-lookup"><span data-stu-id="607f7-127">Shape Type</span></span>|<span data-ttu-id="607f7-128">Propiedades</span><span class="sxs-lookup"><span data-stu-id="607f7-128">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="607f7-129">SendUpdateMessage</span><span class="sxs-lookup"><span data-stu-id="607f7-129">SendUpdateMessage</span></span>|<span data-ttu-id="607f7-130">Send</span><span class="sxs-lookup"><span data-stu-id="607f7-130">Send</span></span>|<span data-ttu-id="607f7-131">-Establecer **mensaje** a *UpdateEmployee*</span><span class="sxs-lookup"><span data-stu-id="607f7-131">-   Set **Message** to *UpdateEmployee*</span></span><br /><span data-ttu-id="607f7-132">-Establecer **nombre** a *SendUpdateMessage*</span><span class="sxs-lookup"><span data-stu-id="607f7-132">-   Set **Name** to *SendUpdateMessage*</span></span>|  
    |<span data-ttu-id="607f7-133">ReceiveUpdateResponse</span><span class="sxs-lookup"><span data-stu-id="607f7-133">ReceiveUpdateResponse</span></span>|<span data-ttu-id="607f7-134">Receive</span><span class="sxs-lookup"><span data-stu-id="607f7-134">Receive</span></span>|<span data-ttu-id="607f7-135">-Establecer **activar** a *False*</span><span class="sxs-lookup"><span data-stu-id="607f7-135">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="607f7-136">-Establecer **mensaje** a *UpdateEmployeeResponse*</span><span class="sxs-lookup"><span data-stu-id="607f7-136">-   Set **Message** to *UpdateEmployeeResponse*</span></span><br /><span data-ttu-id="607f7-137">-Establecer **nombre** a *ReceiveUpdateResponse*</span><span class="sxs-lookup"><span data-stu-id="607f7-137">-   Set **Name** to *ReceiveUpdateResponse*</span></span>|  
  
7.  <span data-ttu-id="607f7-138">Agregar un puerto de envío de solicitudes y respuestas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="607f7-138">Add a request-response send port to the orchestration.</span></span> <span data-ttu-id="607f7-139">Usará este puerto para enviar mensajes de solicitud a SQL Server y recibir respuesta.</span><span class="sxs-lookup"><span data-stu-id="607f7-139">You will use this port to send request messages to the SQL Server and receive response.</span></span> <span data-ttu-id="607f7-140">Establezca las siguientes propiedades para el puerto.</span><span class="sxs-lookup"><span data-stu-id="607f7-140">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="607f7-141">Establezca esta propiedad</span><span class="sxs-lookup"><span data-stu-id="607f7-141">Set this property</span></span>|<span data-ttu-id="607f7-142">En este valor</span><span class="sxs-lookup"><span data-stu-id="607f7-142">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="607f7-143">**Dirección de comunicación**</span><span class="sxs-lookup"><span data-stu-id="607f7-143">**Communication Direction**</span></span>|<span data-ttu-id="607f7-144">Envío-Recepción</span><span class="sxs-lookup"><span data-stu-id="607f7-144">Send-Receive</span></span>|  
    |<span data-ttu-id="607f7-145">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="607f7-145">**Communication Pattern**</span></span>|<span data-ttu-id="607f7-146">Solicitudes y respuestas</span><span class="sxs-lookup"><span data-stu-id="607f7-146">Request-Response</span></span>|  
    |<span data-ttu-id="607f7-147">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="607f7-147">**Identifier**</span></span>|<span data-ttu-id="607f7-148">SQLOutboundPort</span><span class="sxs-lookup"><span data-stu-id="607f7-148">SQLOutboundPort</span></span>|  
  
     <span data-ttu-id="607f7-149">Además, cambiar el nombre de la operación de Operation_1 a **UpdateEmp**.</span><span class="sxs-lookup"><span data-stu-id="607f7-149">Also, change the operation name from Operation_1 to **UpdateEmp**.</span></span>  
  
8.  <span data-ttu-id="607f7-150">Conecte el puerto a formas de acción.</span><span class="sxs-lookup"><span data-stu-id="607f7-150">Connect the port to action shapes.</span></span> <span data-ttu-id="607f7-151">En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde para el puerto a los correspondientes indicador verde de la forma acción.</span><span class="sxs-lookup"><span data-stu-id="607f7-151">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="607f7-152">En este paso, utilizará el método de arrastrar y colocar para conectar los puertos a las formas de acción.</span><span class="sxs-lookup"><span data-stu-id="607f7-152">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="607f7-153">De forma alternativa, podría utilizar la propiedad de operación de una forma de acción para conectar esta última a un puerto.</span><span class="sxs-lookup"><span data-stu-id="607f7-153">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="607f7-154">Conectar los puertos y las formas de acción como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="607f7-154">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="607f7-155">Conectar el **SendUpdateMessage** forma acción a la **solicitar** identificador de la **SQLOutboundPort**.</span><span class="sxs-lookup"><span data-stu-id="607f7-155">Connect the **SendUpdateMessage** action shape to the **Request** handle of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="607f7-156">Conectar el **ReceiveUpdateResponse** forma acción a la **respuesta** identificador de la **SQLOutboundPort**.</span><span class="sxs-lookup"><span data-stu-id="607f7-156">Connect the **ReceiveUpdateResponse** action shape to the **Response** handle of the **SQLOutboundPort**.</span></span>  
  
9. <span data-ttu-id="607f7-157">La siguiente ilustración muestra la orquestación en curso.</span><span class="sxs-lookup"><span data-stu-id="607f7-157">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="607f7-158">![Actualiza la orquestación para enviar el mensaje de actualización](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")</span><span class="sxs-lookup"><span data-stu-id="607f7-158">![Updated orchestration to send update message](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="607f7-159">Síntesis</span><span class="sxs-lookup"><span data-stu-id="607f7-159">What did I just do?</span></span>  
 <span data-ttu-id="607f7-160">En este paso, ha actualizado la orquestación mediante la adición de un **MessageAssignment** forma, **enviar** y **recepción** formas y un puerto.</span><span class="sxs-lookup"><span data-stu-id="607f7-160">In this step, you updated the orchestration by adding a **MessageAssignment** shape, **Send** and **Receive** shapes, and a port.</span></span> <span data-ttu-id="607f7-161">Había conectado las formas y puertos para enviar el mensaje de solicitud para ejecutar el UDPATE_EMPLOYEE mensaje de solicitud y recibirán la respuesta.</span><span class="sxs-lookup"><span data-stu-id="607f7-161">You connected the shapes and ports to send request message to execute the UDPATE_EMPLOYEE request message and receive the response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="607f7-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="607f7-162">Next Steps</span></span>  
 <span data-ttu-id="607f7-163">En el paso siguiente, agregará formas de orquestación para invocar la operación de inserción en el **Purchase_Order** de tabla, como se describe en [lección 4: realizar una operación de inserción en la tabla de orden de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span><span class="sxs-lookup"><span data-stu-id="607f7-163">In the next step, you add orchestration shapes to invoke the Insert operation on the **Purchase_Order** table, as described in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607f7-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="607f7-164">See Also</span></span>  
 <span data-ttu-id="607f7-165">[Paso 1: Crear el mensaje de solicitud de UPDATE_EMPLOYEE procedimiento almacenado](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="607f7-165">[Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md) </span></span>  
 [<span data-ttu-id="607f7-166">Lección 3: Ejecutar un procedimiento almacenado para seleccionar a nuevos empleados agregados</span><span class="sxs-lookup"><span data-stu-id="607f7-166">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)