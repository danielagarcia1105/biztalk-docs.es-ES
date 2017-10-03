---
title: "Paso 3: Agregar un filtro para las notificaciones de inserción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fc32fe7dd657bb45edca91fda0eddaa537b32a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a><span data-ttu-id="ad5dc-102">Paso 3: Agregar un filtro para las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="ad5dc-102">Step 3: Add a Filter for Insert Notifications</span></span>
<span data-ttu-id="ad5dc-103">![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="ad5dc-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="ad5dc-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="ad5dc-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="ad5dc-105">**Objetivo:** en este paso, agregará una forma decidir a la orquestación para filtrar los mensajes de notificación para la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-105">**Objective:** In this step, you add a Decide shape to the orchestration to filter for notification messages for Insert operation.</span></span> <span data-ttu-id="ad5dc-106">Las operaciones posteriores de la orquestación se realizan solo si la notificación recibida es del tipo de inserción.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-106">Subsequent operations in the orchestration are performed only if the notification received is of Insert type.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ad5dc-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ad5dc-107">Prerequisites</span></span>  
 <span data-ttu-id="ad5dc-108">Debe haber completado [paso 2: extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span><span class="sxs-lookup"><span data-stu-id="ad5dc-108">You must have completed [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
### <a name="to-filter-for-notification-messages"></a><span data-ttu-id="ad5dc-109">Para filtrar los mensajes de notificación</span><span class="sxs-lookup"><span data-stu-id="ad5dc-109">To filter for notification messages</span></span>  
  
1.  <span data-ttu-id="ad5dc-110">Agregar un **decidir** dar forma a la orquestación, después de la **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-110">Add a **Decide** shape to the orchestration, after the **Expression** shape.</span></span> <span data-ttu-id="ad5dc-111">En el cuadro de herramientas, arrastre el **decidir** forma en la línea de conexión directamente debajo del **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-111">From the Toolbox, drag the **Decide** shape onto the connecting line directly below the **Expression** shape.</span></span>  
  
     <span data-ttu-id="ad5dc-112">El **decidir** forma se expande para mostrar una bifurcación para el **si** instrucción **(Rule_1)** y una bifurcación para el **Else** instrucción.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-112">The **Decide** shape expands to show a branch for the **If** statement **(Rule_1)** and a branch for the **Else** statement.</span></span>  
  
2.  <span data-ttu-id="ad5dc-113">En la superficie de diseño, haga clic en el **decidir** forma y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-113">On the design surface, right-click the **Decide** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="ad5dc-114">En el **propiedades** panel para la **decidir** forma, en la **nombre** propiedad, escriba `CheckNotification`.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-114">In the **Properties** pane for the **Decide** shape, in the **Name** property, type `CheckNotification`.</span></span>  
  
4.  <span data-ttu-id="ad5dc-115">En la superficie de diseño, haga clic en el **Rule_1** forma (dentro de la **decidir** forma) y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-115">On the design surface, right-click the **Rule_1** shape (inside of the **Decide** shape), and then click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="ad5dc-116">En el **propiedades** panel para **Rule_1**, en la **nombre** propiedad, escriba **insertar**.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-116">In the **Properties** pane for **Rule_1**, in the **Name** property, type **Insert**.</span></span>  
  
6.  <span data-ttu-id="ad5dc-117">Haga clic en el **insertar** forma y, a continuación, haga clic en **Editar expresión booleana**.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-117">Right-click the **Insert** shape, and then click **Edit Boolean Expression**.</span></span>  
  
7.  <span data-ttu-id="ad5dc-118">En el Editor de expresiones de BizTalk, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad5dc-118">In the BizTalk Expression Editor, type the following:</span></span>  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     <span data-ttu-id="ad5dc-119">Esta condición informa a la orquestación para realizar las operaciones posteriores solo si el valor de la **NotificationType** variable es **insertar**.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-119">This condition tells the orchestration to perform subsequent operations only if the value in the **NotificationType** variable is **Insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad5dc-120">Agrega esta variable en [paso 2: extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) para extraer el tipo de notificación del mensaje de notificación recibido desde la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-120">You added this variable in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) to extract the type of notification from the notification message received from the SQL Server database.</span></span>  
  
8.  <span data-ttu-id="ad5dc-121">En la siguiente ilustración muestra la orquestación en curso con el **decidir** forma incluido.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-121">The following figure shows the in-progress orchestration with the **Decide** shape included.</span></span>  
  
     <span data-ttu-id="ad5dc-122">![Agregar una forma decidir a la orquestación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span><span class="sxs-lookup"><span data-stu-id="ad5dc-122">![Add a Decide shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="ad5dc-123">Síntesis</span><span class="sxs-lookup"><span data-stu-id="ad5dc-123">What did I just do?</span></span>  
 <span data-ttu-id="ad5dc-124">En este paso, ha agregado un **decidir** forma para filtrar los mensajes de notificación para realizar las operaciones posteriores solo si la notificación recibida es para las operaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="ad5dc-124">In this step, you added a **Decide** shape to filter the notification messages to perform subsequent operations only if the notification received is for Insert operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ad5dc-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ad5dc-125">Next Steps</span></span>  
 <span data-ttu-id="ad5dc-126">En el paso siguiente, agregará formas de orquestación para invocar el UPDATE_EMPLOYE el procedimiento almacenan en la tabla de empleados, como se describe en [lección 3: ejecutar un procedimiento almacenado que seleccione a nuevos empleados agregar](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span><span class="sxs-lookup"><span data-stu-id="ad5dc-126">In the next step, you add orchestration shapes to invoke the UPDATE_EMPLOYE stored procedure on the Employee table, as described in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5dc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad5dc-127">See Also</span></span>  
 <span data-ttu-id="ad5dc-128">[Paso 2: Extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="ad5dc-128">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="ad5dc-129">Lección 2: Recibir y filtrar notificaciones</span><span class="sxs-lookup"><span data-stu-id="ad5dc-129">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)