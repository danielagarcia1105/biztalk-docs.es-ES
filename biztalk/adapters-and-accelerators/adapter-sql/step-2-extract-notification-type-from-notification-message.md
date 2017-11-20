---
title: "Paso 2: Extraer el tipo de notificación de mensaje de notificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72f3e805-0f5f-42fa-8fe3-78ccbb375f74
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a4fd5e96c3593d3f47ed3c7dfc1875efca7c52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-extract-notification-type-from-notification-message"></a><span data-ttu-id="7f2b4-102">Paso 2: Extraer el tipo de notificación de mensaje de notificación</span><span class="sxs-lookup"><span data-stu-id="7f2b4-102">Step 2: Extract Notification Type from Notification Message</span></span>
<span data-ttu-id="7f2b4-103">![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="7f2b4-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="7f2b4-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="7f2b4-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="7f2b4-105">**Objetivo:** en este paso, agregará una forma de expresión para extraer el tipo de notificación recibida de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-105">**Objective:** In this step, you add an expression shape to extract the type of notification received from the SQL Server database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7f2b4-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7f2b4-106">Prerequisites</span></span>  
 <span data-ttu-id="7f2b4-107">Debe haber completado [paso 1: agregar formas de orquestación para recibir notificación](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span><span class="sxs-lookup"><span data-stu-id="7f2b4-107">You must have completed [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
### <a name="to-extract-the-notification-type-from-the-notification-message"></a><span data-ttu-id="7f2b4-108">Para extraer el tipo de notificación desde el mensaje de notificación</span><span class="sxs-lookup"><span data-stu-id="7f2b4-108">To extract the notification type from the notification message</span></span>  
  
1.  <span data-ttu-id="7f2b4-109">Agregar una variable a la orquestación de BizTalk que creó en [paso 1: agregar formas de orquestación para recibir notificación](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span><span class="sxs-lookup"><span data-stu-id="7f2b4-109">Add a variable to the BizTalk orchestration you created in [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
    1.  <span data-ttu-id="7f2b4-110">Desde la Vista orquestación, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-110">From the Orchestration View, right-click **Variables**, and then click **New Variable**.</span></span>  
  
    2.  <span data-ttu-id="7f2b4-111">Haga clic en la nueva variable, **Variable_1**y haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-111">Right-click the new variable, **Variable_1**, and click **Properties Window**.</span></span> <span data-ttu-id="7f2b4-112">Establezca las siguientes propiedades para la variable.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-112">Set the following properties for the variable.</span></span>  
  
        |<span data-ttu-id="7f2b4-113">Establezca esta propiedad</span><span class="sxs-lookup"><span data-stu-id="7f2b4-113">Set this property</span></span>|<span data-ttu-id="7f2b4-114">En este valor</span><span class="sxs-lookup"><span data-stu-id="7f2b4-114">To this value</span></span>|  
        |-----------------------|-------------------|  
        |<span data-ttu-id="7f2b4-115">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="7f2b4-115">**Identifier**</span></span>|<span data-ttu-id="7f2b4-116">NotificationType</span><span class="sxs-lookup"><span data-stu-id="7f2b4-116">NotificationType</span></span>|  
        |<span data-ttu-id="7f2b4-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f2b4-117">**Type**</span></span>|<span data-ttu-id="7f2b4-118">System.String</span><span class="sxs-lookup"><span data-stu-id="7f2b4-118">System.String</span></span>|  
  
2.  <span data-ttu-id="7f2b4-119">Agregar un **expresión** forma a la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-119">Add an **Expression** shape to the BizTalk orchestration.</span></span> <span data-ttu-id="7f2b4-120">En el cuadro de herramientas de orquestaciones, arrastre la **expresión** dar forma a la superficie de diseño de orquestación y colóquela después la **recepción** forma</span><span class="sxs-lookup"><span data-stu-id="7f2b4-120">From the orchestration Toolbox, drag the **Expression** shape to the orchestration design surface, and drop it after the **Receive** shape</span></span>  
  
     <span data-ttu-id="7f2b4-121">En el **expresión** forma, se agregará una consulta xpath para extraer el tipo de mensaje de notificación recibido de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-121">Within the **Expression** shape, you will add an xpath query to extract the type of notification message received from SQL Server.</span></span> <span data-ttu-id="7f2b4-122">Antes de crear una consulta xpath, echemos un vistazo en el formato de un mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-122">Before creating an xpath query, let us look at the format of a notification message.</span></span> <span data-ttu-id="7f2b4-123">Un mensaje de notificación típico es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f2b4-123">A typical notification message resembles the following:</span></span>  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
3.  <span data-ttu-id="7f2b4-124">Como verá, la información sobre el tipo de la notificación está disponible dentro de la `<info>` etiqueta dentro del elemento primario `<Notification>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-124">As you see, the information about the type of the notification is available within the `<info>` tag, within the parent `<Notification>` tag.</span></span> <span data-ttu-id="7f2b4-125">Por lo tanto, agregue la siguiente consulta de xpath en el **expresión** forma:</span><span class="sxs-lookup"><span data-stu-id="7f2b4-125">So, add the following xpath query within the **Expression** shape:</span></span>  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     <span data-ttu-id="7f2b4-126">En este caso, **NotificationType** es la variable que creó para almacenar el valor extraído por la consulta xpath.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-126">Here, **NotificationType** is the variable you created to store the value extracted by the xpath query.</span></span> <span data-ttu-id="7f2b4-127">**NotifyReceive** es el mensaje que creó en [paso 2: crear mensajes de orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) para recibir mensajes de notificación.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-127">**NotifyReceive** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) to receive notification messages.</span></span>  
  
4.  <span data-ttu-id="7f2b4-128">En la siguiente ilustración muestra la orquestación en curso con el **expresión** forma incluido.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-128">The following figure shows the in-progress orchestration with the **Expression** shape included.</span></span>  
  
     <span data-ttu-id="7f2b4-129">![Agregar una forma expresión a la orquestación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span><span class="sxs-lookup"><span data-stu-id="7f2b4-129">![Add an Expression shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="7f2b4-130">Síntesis</span><span class="sxs-lookup"><span data-stu-id="7f2b4-130">What did I just do?</span></span>  
 <span data-ttu-id="7f2b4-131">En este paso, ha agregado un **expresión** forma para extraer el tipo de notificación recibida de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f2b4-131">In this step, you added an **Expression** shape to extract the kind of notification received from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7f2b4-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7f2b4-132">Next Steps</span></span>  
 <span data-ttu-id="7f2b4-133">Agregar una forma decidir para filtrar las notificaciones de inserción, tal y como se describe en [paso 3: agregar un filtro para las notificaciones de inserción](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="7f2b4-133">You add a Decide shape to filter for Insert notifications, as described in [Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f2b4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f2b4-134">See Also</span></span>  
 <span data-ttu-id="7f2b4-135">[Paso 1: Agregar formas de orquestación para recibir una notificación](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span><span class="sxs-lookup"><span data-stu-id="7f2b4-135">[Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span></span>  
 <span data-ttu-id="7f2b4-136">[Paso 3: Agregar un filtro para las notificaciones de inserción](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="7f2b4-136">[Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span></span>  
 [<span data-ttu-id="7f2b4-137">Lección 2: Recibir y filtrar notificaciones</span><span class="sxs-lookup"><span data-stu-id="7f2b4-137">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)