---
title: 'Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec7897e9-0c77-41b2-8cc2-61745bd3b028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3021a5e3ead821a0f3c8d0372d48ae469a834c1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001861"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a><span data-ttu-id="0f074-102">Lección 3: Ejecutar un procedimiento almacenado para seleccionar a nuevos empleados agregados</span><span class="sxs-lookup"><span data-stu-id="0f074-102">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>
<span data-ttu-id="0f074-103">Antes de la descripción de las tareas realizadas en esta lección, primero debe comprender por qué se requieren estas tareas.</span><span class="sxs-lookup"><span data-stu-id="0f074-103">Before understanding the tasks performed in this lesson, you must first understand why these tasks are required.</span></span> <span data-ttu-id="0f074-104">El **empleado** tabla a la que se insertan los registros para agregar un nuevo empleado se define de tal manera que un **estado** columna siempre se establece en "0" cada vez que se agrega un nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="0f074-104">The **Employee** table to which the records are inserted to add a new employee is defined in such a way that a **Status** column is always set to “0” every time a new employee is added.</span></span> <span data-ttu-id="0f074-105">Esto se hace para que pueda usar esta columna para consultar los empleados recién agregados y también recibir notificaciones.</span><span class="sxs-lookup"><span data-stu-id="0f074-105">This is done so that you can use this column to query for newly added employees and also get notifications.</span></span> <span data-ttu-id="0f074-106">En SQL Server, podría consultar mediante la ejecución de la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="0f074-106">In SQL Server, you would query this by running the following SQL statement:</span></span>  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 <span data-ttu-id="0f074-107">Después de recibir la lista de recién agregado empleados, también debe actualizar el **estado** columna en "1" para que la próxima vez que se agregan nuevos empleados y ejecutar la misma consulta, no podrá obtener registros de antiguos empleados también.</span><span class="sxs-lookup"><span data-stu-id="0f074-107">After receiving the list of newly added employees, you must also update the **Status** column to “1” so that the next time new employees are added and you run the same query, you do not get records for old employees as well.</span></span> <span data-ttu-id="0f074-108">Para asegurarse de que la instrucción Select anterior le proporciona solo los empleados recién agregados, se actualizará la **empleado** tabla mediante la instrucción SQL siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f074-108">To make sure that the above Select statement gives only the newly added employees, you will update the **Employee** table using the following SQL statement:</span></span>  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 <span data-ttu-id="0f074-109">Por lo tanto, el **estado** columna para los empleados antiguos se establece en "1" mientras que los empleados nuevos siempre es "0".</span><span class="sxs-lookup"><span data-stu-id="0f074-109">So, the **Status** column for the old employees is set to “1” while new employees will always be “0.”</span></span>  
  
 <span data-ttu-id="0f074-110">En esta lección, ejecutará un procedimiento almacenado, **UPDATE_EMPLOYEE**, que a su vez ejecuta las instrucciones Select y Update.</span><span class="sxs-lookup"><span data-stu-id="0f074-110">In this lesson, you will execute a stored procedure, **UPDATE_EMPLOYEE**, which in turn executes the Select and Update statements.</span></span> <span data-ttu-id="0f074-111">Cuando haya terminado esta lección, la orquestación hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f074-111">After you have finished this lesson, your orchestration will do the following:</span></span>  
  
1. <span data-ttu-id="0f074-112">Recibe la notificación de los cambios realizados en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="0f074-112">Receives notification for any changes to the **Employee** table.</span></span>  
  
2. <span data-ttu-id="0f074-113">Extrae el mensaje de notificación que recibe el tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="0f074-113">Extracts the type of notification from the notification message received.</span></span>  
  
3. <span data-ttu-id="0f074-114">Si el mensaje de notificación es para una operación de inserción, la orquestación ejecuta la **UPDATE_EMPLOYEE** procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0f074-114">If the notification message is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
4. <span data-ttu-id="0f074-115">El procedimiento almacenado lee los registros recién introducidos en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="0f074-115">The stored procedure reads the newly entered records in the **Employee** table.</span></span> <span data-ttu-id="0f074-116">Después de leer los nuevos registros, el procedimiento almacenado también establece la **estado** columna para aquellos registros en "1".</span><span class="sxs-lookup"><span data-stu-id="0f074-116">After reading the new records, the stored procedure also sets the **Status** column for those records to “1.”</span></span>  
  
   <span data-ttu-id="0f074-117">Ahora ya sabe por qué necesita ejecutar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0f074-117">Now you know why you need to execute the stored procedure.</span></span> <span data-ttu-id="0f074-118">Ahora deberá pensar en cómo se ejecuta como parte de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0f074-118">You now need to think about how to execute this as part of the orchestration.</span></span> <span data-ttu-id="0f074-119">La orquestación necesita un mensaje de solicitud para el **UPDATE_EMPLOYEE** procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0f074-119">The orchestration needs a request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="0f074-120">En este tutorial, creará una biblioteca de clases personalizadas que se creará el mensaje sobre la marcha y, a continuación, se proporcionan a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0f074-120">In this tutorial, you will create a custom class library that will create the message on the fly and then provide it to the orchestration.</span></span> <span data-ttu-id="0f074-121">Después de que la orquestación recibe el mensaje, enviará el mensaje a SQL Server mediante el adaptador de SQL y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="0f074-121">After the orchestration receives the message, it will send the message to the SQL Server using the SQL adapter and receive the response.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f074-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0f074-122">In This Section</span></span>  
  
-   [<span data-ttu-id="0f074-123">Paso 1: Crear el mensaje de solicitud para el procedimiento almacenado UPDATE_EMPLOYEE</span><span class="sxs-lookup"><span data-stu-id="0f074-123">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [<span data-ttu-id="0f074-124">Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir la respuesta</span><span class="sxs-lookup"><span data-stu-id="0f074-124">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)