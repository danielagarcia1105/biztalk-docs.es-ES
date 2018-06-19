---
title: 'Paso 1: Agregar formas de orquestación para recibir una notificación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a33693a09d89acc5d1ad9e4514c7907b789cc75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223132"
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a><span data-ttu-id="0fd6a-102">Paso 1: Agregar formas de orquestación para recibir una notificación</span><span class="sxs-lookup"><span data-stu-id="0fd6a-102">Step 1: Add Orchestration Shapes to Receive Notification</span></span>
<span data-ttu-id="0fd6a-103">![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="0fd6a-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="0fd6a-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="0fd6a-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="0fd6a-105">**Objetivo:** en este paso, agregará formas de orquestación para recibir la notificación de cambios en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-105">**Objective:** In this step, you add orchestration shapes to receive notification for changes to the **Employee** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0fd6a-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0fd6a-106">Prerequisites</span></span>  
 <span data-ttu-id="0fd6a-107">Debe haber completado los pasos descritos en [lección 1: generar esquemas y crear mensajes](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0fd6a-107">You must have completed the steps in [Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md).</span></span>  
  
### <a name="to-receive-notification-messages"></a><span data-ttu-id="0fd6a-108">Para recibir mensajes de notificación</span><span class="sxs-lookup"><span data-stu-id="0fd6a-108">To receive notification messages</span></span>  
  
1.  <span data-ttu-id="0fd6a-109">Abra la orquestación de BizTalk, **EmployeeOrch.odx**, se agregó en [paso 2: crear mensajes de orquestaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="0fd6a-109">Open the BizTalk orchestration, **EmployeeOrch.odx**, you added in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).</span></span>  
  
2.  <span data-ttu-id="0fd6a-110">Agregar un **recepción** forma a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-110">Add a **Receive** shape to the orchestration.</span></span> <span data-ttu-id="0fd6a-111">En el cuadro de herramientas de orquestaciones, arrastre la **recepción** dar forma a la superficie de diseño de orquestación y colóquela en el espacio indicado entre el **comenzar** (círculo verde) y **final**formas (octágono rojo).</span><span class="sxs-lookup"><span data-stu-id="0fd6a-111">From the orchestration Toolbox, drag the **Receive** shape to the orchestration design surface, and drop it into the space indicated between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
    |<span data-ttu-id="0fd6a-112">Establezca esta propiedad</span><span class="sxs-lookup"><span data-stu-id="0fd6a-112">Set this property</span></span>|<span data-ttu-id="0fd6a-113">En este valor</span><span class="sxs-lookup"><span data-stu-id="0fd6a-113">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="0fd6a-114">**Activate**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-114">**Activate**</span></span>|<span data-ttu-id="0fd6a-115">True</span><span class="sxs-lookup"><span data-stu-id="0fd6a-115">True</span></span>|  
    |<span data-ttu-id="0fd6a-116">**de mensaje**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-116">**Message**</span></span>|<span data-ttu-id="0fd6a-117">NotifyReceive</span><span class="sxs-lookup"><span data-stu-id="0fd6a-117">NotifyReceive</span></span>|  
    |<span data-ttu-id="0fd6a-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-118">**Name**</span></span>|<span data-ttu-id="0fd6a-119">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="0fd6a-119">ReceiveNotification</span></span>|  
  
3.  <span data-ttu-id="0fd6a-120">Agregar un unidireccional puerto de recepción para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-120">Add a one-way receive port to the orchestration.</span></span> <span data-ttu-id="0fd6a-121">Usará este puerto para recibir mensajes de notificación de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-121">You will use this port to receive notification messages from the SQL Server database.</span></span> <span data-ttu-id="0fd6a-122">Establezca las siguientes propiedades para el puerto.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-122">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="0fd6a-123">Establezca esta propiedad</span><span class="sxs-lookup"><span data-stu-id="0fd6a-123">Set this property</span></span>|<span data-ttu-id="0fd6a-124">En este valor</span><span class="sxs-lookup"><span data-stu-id="0fd6a-124">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="0fd6a-125">**Dirección de comunicación**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-125">**Communication Direction**</span></span>|<span data-ttu-id="0fd6a-126">Receive</span><span class="sxs-lookup"><span data-stu-id="0fd6a-126">Receive</span></span>|  
    |<span data-ttu-id="0fd6a-127">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-127">**Communication Pattern**</span></span>|<span data-ttu-id="0fd6a-128">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="0fd6a-128">One-Way</span></span>|  
    |<span data-ttu-id="0fd6a-129">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-129">**Identifier**</span></span>|<span data-ttu-id="0fd6a-130">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="0fd6a-130">ReceiveNotification</span></span>|  
  
     <span data-ttu-id="0fd6a-131">Además, cambiar el nombre de la operación de Operation_1 a **notificación**.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-131">Also, change the operation name from Operation_1 to **Notification**.</span></span>  
  
4.  <span data-ttu-id="0fd6a-132">Conectar el **ReceiveNotification** puerto a la **ReceiveNotification** forma acción.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-132">Connect the **ReceiveNotification** port to the **ReceiveNotification** action shape.</span></span> <span data-ttu-id="0fd6a-133">En el Diseñador de orquestaciones, en la superficie de diseño, arrastre el indicador con forma de flecha verde para el puerto a los correspondientes indicador verde de la forma acción.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-133">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fd6a-134">En este paso, utilizará el método de arrastrar y colocar para conectar los puertos a las formas de acción.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-134">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="0fd6a-135">De forma alternativa, podría utilizar la propiedad de operación de una forma de acción para conectar esta última a un puerto.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-135">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
5.  <span data-ttu-id="0fd6a-136">La siguiente ilustración muestra la orquestación en curso.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-136">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="0fd6a-137">![Orquestación para recibir mensajes de notificación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span><span class="sxs-lookup"><span data-stu-id="0fd6a-137">![Orchestration to receive notification messages](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="0fd6a-138">Síntesis</span><span class="sxs-lookup"><span data-stu-id="0fd6a-138">What did I just do?</span></span>  
 <span data-ttu-id="0fd6a-139">En este paso, se agregan formas de orquestación y puerto de recepción para recibir una notificación de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-139">In this step, you added orchestration shapes and receive port to receive notification from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0fd6a-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0fd6a-140">Next Steps</span></span>  
 <span data-ttu-id="0fd6a-141">Agregar una forma expresión a la orquestación para extraer el tipo de notificación recibida de la base de datos de SQL Server, como se describe en [paso 2: extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span><span class="sxs-lookup"><span data-stu-id="0fd6a-141">You add an expression shape to the orchestration to extract the type of notification received from the SQL Server database, as described in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd6a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fd6a-142">See Also</span></span>  
 <span data-ttu-id="0fd6a-143">[Paso 2: Extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="0fd6a-143">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="0fd6a-144">Lección 2: Recibir y filtrar notificaciones</span><span class="sxs-lookup"><span data-stu-id="0fd6a-144">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)