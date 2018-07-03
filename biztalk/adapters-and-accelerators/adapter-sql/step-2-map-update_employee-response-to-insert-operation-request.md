---
title: 'Paso 2: Asignar el mensaje de respuesta update_employee al mensaje de solicitud de operación de insertar | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d12014a-0147-4227-88fa-0b290eff4cce
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d158e0f7eed50a40d2696712bacee65a8de946a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009021"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a><span data-ttu-id="39786-102">Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE al mensaje de solicitud de operación de inserción</span><span class="sxs-lookup"><span data-stu-id="39786-102">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>
<span data-ttu-id="39786-103">![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="39786-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  

 <span data-ttu-id="39786-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="39786-104">**Time to complete:** 10 minutes</span></span>  

 <span data-ttu-id="39786-105">**Objetivo:** en este paso, creará el mensaje de solicitud para realizar una operación de inserción en el **Purchase_Order** de tabla y, a continuación, asignar el mensaje de respuesta para la **UPDATE_EMPLOYEE** almacenados procedimiento para el mensaje de solicitud para la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="39786-105">**Objective:** In this step, you create the request message to perform an Insert operation on the **Purchase_Order** table and then map the response message for the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span> <span data-ttu-id="39786-106">Al hacerlo, se pasa en los valores en el mensaje de respuesta que deben insertarse en el **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="39786-106">By doing so, you pass on the values in the response message to be inserted in the **Purchase_Order** table.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="39786-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="39786-107">Prerequisites</span></span>  
 <span data-ttu-id="39786-108">Debe haber completado [paso 1: crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md).</span><span class="sxs-lookup"><span data-stu-id="39786-108">You must have completed [Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md).</span></span>  

### <a name="to-map-the-messages"></a><span data-ttu-id="39786-109">Para asignar los mensajes</span><span class="sxs-lookup"><span data-stu-id="39786-109">To map the messages</span></span>  

1. <span data-ttu-id="39786-110">A la orquestación existente, en el **insertar** bloquear de la **decidir** dar forma, en el **ReceiveUpdateResponse** forma, agregue un **deasignacióndemensajes** forma.</span><span class="sxs-lookup"><span data-stu-id="39786-110">To the existing orchestration, in the **Insert** block of the **Decide** shape, under the **ReceiveUpdateResponse** shape, add a **Message Assignment** shape.</span></span> <span data-ttu-id="39786-111">En el cuadro de herramientas, arrastre el **asignación de mensajes** forma para el espacio indicado.</span><span class="sxs-lookup"><span data-stu-id="39786-111">From the Toolbox, drag the **Message Assignment** shape to the space indicated.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="39786-112">Al colocar el **asignación de mensajes** forma a la superficie de diseño, el Diseñador de orquestaciones crea la envolvente **construir mensaje** forma para usted.</span><span class="sxs-lookup"><span data-stu-id="39786-112">When you drop the **Message Assignment** shape onto the design surface, Orchestration Designer creates the enclosing **Construct Message** shape for you.</span></span>  

2. <span data-ttu-id="39786-113">En la superficie de diseño, haga clic en el **ConstructMessage_1** dar forma y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="39786-113">On the design surface, right-click the **ConstructMessage_1** shape, and then click **Properties Window**.</span></span>  

3. <span data-ttu-id="39786-114">En el **propiedades** panel para el **ConstructMessage_1** forma, especifique los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="39786-114">In the **Properties** pane for the **ConstructMessage_1** shape, specify the following values.</span></span>  


   |    <span data-ttu-id="39786-115">Establezca esta propiedad</span><span class="sxs-lookup"><span data-stu-id="39786-115">Set this property</span></span>     |     <span data-ttu-id="39786-116">En este valor.</span><span class="sxs-lookup"><span data-stu-id="39786-116">To this value</span></span>      |
   |--------------------------|------------------------|
   | <span data-ttu-id="39786-117">**Mensajes construidos**</span><span class="sxs-lookup"><span data-stu-id="39786-117">**Messages Constructed**</span></span> |        <span data-ttu-id="39786-118">InsertPO</span><span class="sxs-lookup"><span data-stu-id="39786-118">InsertPO</span></span>        |
   |         <span data-ttu-id="39786-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="39786-119">**Name**</span></span>         | <span data-ttu-id="39786-120">ConstructInsertMessage</span><span class="sxs-lookup"><span data-stu-id="39786-120">ConstructInsertMessage</span></span> |


4. <span data-ttu-id="39786-121">Haga doble clic en el **MessageAssignment** forma para abrir el **Editor de expresiones de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="39786-121">Double-click the **MessageAssignment** shape to open the **BizTalk Expression Editor**.</span></span>  

5. <span data-ttu-id="39786-122">En el **Editor de expresiones de BizTalk**, agregue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39786-122">In the **BizTalk Expression Editor**, add the following:</span></span>  

   ```  
   InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
   InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
   ```  

    <span data-ttu-id="39786-123">En este caso, **InsertPO** es el mensaje que creó en [paso 2: creación de mensajes para orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) para enviar mensajes de solicitud de operación de inserción el **Purchase_Order**tabla.</span><span class="sxs-lookup"><span data-stu-id="39786-123">Here, **InsertPO** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) for sending request messages for Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="39786-124">En el **MessageAssignment** forma, se invoca el **UpdatePOMessageCreator** clase para crear un mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="39786-124">In the **MessageAssignment** shape, you invoke the **UpdatePOMessageCreator** class to create a request message.</span></span> <span data-ttu-id="39786-125">Además, establezca la acción de WCF para el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="39786-125">Also, you set the WCF action for the request message.</span></span>  

6. <span data-ttu-id="39786-126">Dentro de la **construir mensaje** forma y después la **asignación de mensajes** forma, agregue un **transformar** forma.</span><span class="sxs-lookup"><span data-stu-id="39786-126">Within the **Construct Message** shape and after the **Message Assignment** shape, add a **Transform** shape.</span></span>  

7. <span data-ttu-id="39786-127">En el **configuración de transformación** cuadro de diálogo, en el panel izquierdo, bajo el **transformar** etiquetar, haga clic en **origen**.</span><span class="sxs-lookup"><span data-stu-id="39786-127">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Source**.</span></span>  

8. <span data-ttu-id="39786-128">Desde el **transformación del origen** cuadro a la derecha, haga clic en el espacio en el **nombre de Variable**y, a continuación, seleccione **UpdateEmployeeResponse**.</span><span class="sxs-lookup"><span data-stu-id="39786-128">From the **Source Transform** box on the right, click the space under the **Variable Name**, and then select **UpdateEmployeeResponse**.</span></span>  

    <span data-ttu-id="39786-129">![Seleccionar el esquema de origen para la asignación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span><span class="sxs-lookup"><span data-stu-id="39786-129">![Pick the source schema for the mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span></span>  

9. <span data-ttu-id="39786-130">En el **configuración de transformación** cuadro de diálogo, en el panel izquierdo, bajo el **transformar** etiquetar, haga clic en **destino**.</span><span class="sxs-lookup"><span data-stu-id="39786-130">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Destination**.</span></span>  

10. <span data-ttu-id="39786-131">Desde el **transformación de destino** cuadro a la derecha, haga clic en el espacio en el **nombre de Variable**y, a continuación, seleccione **InsertPO**.</span><span class="sxs-lookup"><span data-stu-id="39786-131">From the **Destination Transform** box on the right, click the space under the **Variable Name**, and then select **InsertPO**.</span></span>  

     <span data-ttu-id="39786-132">![Seleccionar el esquema de destino para la asignación de](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span><span class="sxs-lookup"><span data-stu-id="39786-132">![Pick the destination schema for mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span></span>  

11. <span data-ttu-id="39786-133">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39786-133">Click **OK**.</span></span> <span data-ttu-id="39786-134">Se abre el archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="39786-134">The map file opens.</span></span>  

12. <span data-ttu-id="39786-135">Expanda los nodos en los esquemas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="39786-135">Expand the nodes in the source and destination schemas.</span></span>  

13. <span data-ttu-id="39786-136">Asigne el Id_Empleado y asígnele el nombre de los campos en los esquemas.</span><span class="sxs-lookup"><span data-stu-id="39786-136">Map the Employee_ID and name fields in both the schemas.</span></span>  

    - <span data-ttu-id="39786-137">Mapa del **Id_Empleado** nodo en el esquema de origen (UPDATE_EMPLOYEEResponse) el **Id_Empleado** nodo del esquema de destino (Insertar).</span><span class="sxs-lookup"><span data-stu-id="39786-137">Map the **Employee_ID** node in the source schema (UPDATE_EMPLOYEEResponse) to the **Employee_ID** node in the destination schema (Insert).</span></span>  

    - <span data-ttu-id="39786-138">Mapa del **nombre** nodo del esquema de origen a la **Nombre_Empleado** del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="39786-138">Map the **Name** node in the source schema to the **Employee_Name** in the destination schema.</span></span>  

      <span data-ttu-id="39786-139">La siguiente ilustración muestra los esquemas asignados.</span><span class="sxs-lookup"><span data-stu-id="39786-139">The following figure shows the mapped schemas.</span></span>  

      <span data-ttu-id="39786-140">![Asignar los esquemas de origen y destino](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span><span class="sxs-lookup"><span data-stu-id="39786-140">![Map the source and destination schemas](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span></span>  

      <span data-ttu-id="39786-141">Guarde y cierre el mapa.</span><span class="sxs-lookup"><span data-stu-id="39786-141">Save and close the map.</span></span>  

14. <span data-ttu-id="39786-142">La siguiente ilustración muestra la orquestación en curso.</span><span class="sxs-lookup"><span data-stu-id="39786-142">The following figure shows the in-progress orchestration.</span></span>  

     <span data-ttu-id="39786-143">![Orquestación con la forma transformación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span><span class="sxs-lookup"><span data-stu-id="39786-143">![Orchestration with the transform shape](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="39786-144">Síntesis</span><span class="sxs-lookup"><span data-stu-id="39786-144">What did I just do?</span></span>  
 <span data-ttu-id="39786-145">En este paso, ha creado un mensaje para insertar registros en el **Purchase_Order** de tabla y, a continuación, asigna el mensaje de respuesta de la **UPDATE_EMPLOYEE** procedimiento almacenado para el mensaje de solicitud para la inserción operación.</span><span class="sxs-lookup"><span data-stu-id="39786-145">In this step, you created a message to insert records into the **Purchase_Order** table and then mapped the response message from the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="39786-146">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="39786-146">Next Steps</span></span>  
 <span data-ttu-id="39786-147">Enviar el mensaje de solicitud para realizar una operación de inserción en el **Purchase_Order** de tabla y recibir una respuesta, como se describe en [paso 3: enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span><span class="sxs-lookup"><span data-stu-id="39786-147">You send the request message to perform an Insert operation on the **Purchase_Order** table and receive a response, as described in [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="39786-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="39786-148">See Also</span></span>  
 <span data-ttu-id="39786-149">[Paso 1: Crear el mensaje de solicitud de operación de inserción en la tabla Purchase_Order](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span><span class="sxs-lookup"><span data-stu-id="39786-149">[Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span></span>  
 [<span data-ttu-id="39786-150">Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="39786-150">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)