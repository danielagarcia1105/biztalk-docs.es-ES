---
title: 'Tutorial 2: Empleado: proceso de pedido de compra mediante el adaptador de SQL | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d14008611bfb22bf39e446e72ecb3bba4571761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010781"
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a><span data-ttu-id="af549-102">Tutorial 2: Empleado: proceso de pedido de compra mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="af549-102">Tutorial 2: Employee - Purchase Order Process using the SQL adapter</span></span>
<span data-ttu-id="af549-103">En este tutorial, va a automatizar el proceso donde el departamento de compras que coloca un equipamiento solicitar cada vez que un nuevo empleado incorpora a la organización.</span><span class="sxs-lookup"><span data-stu-id="af549-103">In this tutorial, you are automating the process where the Purchases department that places an equipment order every time a new employee joins the organization.</span></span> <span data-ttu-id="af549-104">Detalles de los empleados y los detalles de pedido de compra se mantienen en **empleado** y **Purchase_Order** tablas respectivamente, en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af549-104">Both employee details and purchase order details are maintained in **Employee** and **Purchase_Order** tables respectively, in a SQL Server database.</span></span> <span data-ttu-id="af549-105">Se informa al departamento de compras mediante la actualización de la tabla Purchase_Order en la base de datos de SQL Server y enviando un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="af549-105">The Purchases department is informed by updating the Purchase_Order table in the SQL Server database and by sending an e-mail.</span></span> <span data-ttu-id="af549-106">Dentro del proceso, se producen las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="af549-106">Within the process, the following actions occur:</span></span>  
  
1. <span data-ttu-id="af549-107">El adaptador recibe una notificación cada vez que el **empleado** se actualiza la tabla.</span><span class="sxs-lookup"><span data-stu-id="af549-107">The adapter receives a notification each time the **Employee** table is updated.</span></span> <span data-ttu-id="af549-108">El adaptador, a continuación, envía una notificación a la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="af549-108">The adapter then sends a notification to the BizTalk orchestration.</span></span>  
  
2. <span data-ttu-id="af549-109">La orquestación de BizTalk averigua si la notificación es para inserta un nuevo registro en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="af549-109">The BizTalk orchestration figures out whether the notification is for a new record inserted into the **Employee** table.</span></span> <span data-ttu-id="af549-110">Si la notificación es para ninguna otra operación en el **empleado** tabla, la orquestación no realiza ninguna operación.</span><span class="sxs-lookup"><span data-stu-id="af549-110">If the notification is for any other operation on the **Employee** table, the orchestration does not perform any operation.</span></span>  
  
3. <span data-ttu-id="af549-111">Si la notificación es para una operación de inserción en el **empleado** tabla, que le notifica que se ha agregado un nuevo registro de empleado, la orquestación utiliza el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para leer los detalles del nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="af549-111">If the notification is for an Insert operation on the **Employee** table, notifying that a new employee record was added, the orchestration uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to read the details of the new record.</span></span>  
  
4. <span data-ttu-id="af549-112">La orquestación recibe una respuesta que contiene los detalles del nuevo registro de empleado agregado.</span><span class="sxs-lookup"><span data-stu-id="af549-112">The orchestration receives a response that contains the details of the new added employee record.</span></span> <span data-ttu-id="af549-113">La orquestación se asigna el **Id_Empleado** y **designación** campos en la respuesta al mensaje de solicitud para la operación de inserción en el **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="af549-113">The orchestration maps the **Employee_ID** and **Designation** fields in the response to the request message for the Insert operation on the **Purchase_Order** table.</span></span>  
  
5. <span data-ttu-id="af549-114">La orquestación, a continuación, usa el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar una operación de inserción en el **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="af549-114">The orchestration then uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="af549-115">La respuesta para la operación de inserción se envía al departamento de compras como un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="af549-115">The response for the Insert operation is sent to the Purchases department as an e-mail.</span></span>  
  
## <a name="about-the-database-objects-used-in-this-sample"></a><span data-ttu-id="af549-116">Acerca de los objetos de base de datos utilizados en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="af549-116">About the Database Objects Used in this Sample</span></span>  
 <span data-ttu-id="af549-117">Este tutorial usa los objetos de base de datos creados por la secuencia de comandos SQL incluido con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="af549-117">This tutorial uses the database objects created by the SQL script shipped with the samples.</span></span> <span data-ttu-id="af549-118">Para obtener más información acerca de la secuencia de comandos y los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="af549-118">For more information about the script and the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="af549-119">Los objetos de base de datos que va a utilizar en este tutorial son:</span><span class="sxs-lookup"><span data-stu-id="af549-119">The database objects that you will use in this tutorial are:</span></span>  
  
- <span data-ttu-id="af549-120">**ADAPTER_SAMPLES** base de datos.</span><span class="sxs-lookup"><span data-stu-id="af549-120">**ADAPTER_SAMPLES** database.</span></span>  
  
- <span data-ttu-id="af549-121">**Empleado** y **Purchase_Order** tablas.</span><span class="sxs-lookup"><span data-stu-id="af549-121">**Employee** and **Purchase_Order** tables.</span></span>  
  
- <span data-ttu-id="af549-122">**UPDATE_EMPLOYEE** procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="af549-122">**UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
  <span data-ttu-id="af549-123">Todos estos objetos de base de datos se crean al ejecutar el script SQL proporcionado con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="af549-123">All these database objects are created when you run the SQL script provided with the sample.</span></span> <span data-ttu-id="af549-124">Asegúrese de que ejecutar el script antes de empezar con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="af549-124">Make sure you run the script before you start with the tutorial.</span></span>  
  
## <a name="sample-based-on-this-tutorial"></a><span data-ttu-id="af549-125">Ejemplo basado en este Tutorial</span><span class="sxs-lookup"><span data-stu-id="af549-125">Sample Based on This Tutorial</span></span>  
 <span data-ttu-id="af549-126">Un ejemplo, **Employee_PurchaseOrder**, que se basa en este tutorial también se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af549-126">A sample, **Employee_PurchaseOrder**, which is based on this tutorial is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="af549-127">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="af549-127">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
 <span data-ttu-id="af549-128">Se recomienda que recorra el tutorial completamente para aprender a crear proyectos de BizTalk con el adaptador y, a continuación, examine el ejemplo como referencia.</span><span class="sxs-lookup"><span data-stu-id="af549-128">We recommend that you go through the tutorial completely to understand how to create BizTalk projects using the adapter, and then look at the sample as a reference.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af549-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="af549-129">In This Section</span></span>  
  
-   [<span data-ttu-id="af549-130">Lección 1: Generar esquemas y crear mensajes</span><span class="sxs-lookup"><span data-stu-id="af549-130">Lesson 1: Generate Schemas and Create Messages</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [<span data-ttu-id="af549-131">Lección 2: Recibir y filtrar notificaciones</span><span class="sxs-lookup"><span data-stu-id="af549-131">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [<span data-ttu-id="af549-132">Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados</span><span class="sxs-lookup"><span data-stu-id="af549-132">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [<span data-ttu-id="af549-133">Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="af549-133">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [<span data-ttu-id="af549-134">Lección 5: Implementar la solución</span><span class="sxs-lookup"><span data-stu-id="af549-134">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)