---
title: 'Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados | Documentos de Microsoft'
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
ms.openlocfilehash: 7af49c026b443fb1ca6a0fb7f35b64cdf1e377f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222628"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a><span data-ttu-id="fc253-102">Lección 3: Ejecutar un procedimiento almacenado para seleccionar a nuevos empleados agregados</span><span class="sxs-lookup"><span data-stu-id="fc253-102">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>
<span data-ttu-id="fc253-103">Antes de la descripción de las tareas realizadas en esta lección, primero debe entender qué son necesarias estas tareas.</span><span class="sxs-lookup"><span data-stu-id="fc253-103">Before understanding the tasks performed in this lesson, you must first understand why these tasks are required.</span></span> <span data-ttu-id="fc253-104">El **empleado** tabla a la que se insertan los registros para agregar un nuevo empleado se define de tal manera que un **estado** columna siempre se establece en "0" cada vez que se agrega un nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="fc253-104">The **Employee** table to which the records are inserted to add a new employee is defined in such a way that a **Status** column is always set to “0” every time a new employee is added.</span></span> <span data-ttu-id="fc253-105">Esto se hace para que puedan utilizar esta columna para consultar los empleados recién agregados y obtener notificaciones.</span><span class="sxs-lookup"><span data-stu-id="fc253-105">This is done so that you can use this column to query for newly added employees and also get notifications.</span></span> <span data-ttu-id="fc253-106">En SQL Server, debería consultar ejecutando la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="fc253-106">In SQL Server, you would query this by running the following SQL statement:</span></span>  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 <span data-ttu-id="fc253-107">Después de recibir la lista de recién agregado empleados, también debe actualizar el **estado** columna a "1" para que la próxima vez que se agregan nuevos empleados y ejecutar la misma consulta, no obtener registros de empleados antiguos así.</span><span class="sxs-lookup"><span data-stu-id="fc253-107">After receiving the list of newly added employees, you must also update the **Status** column to “1” so that the next time new employees are added and you run the same query, you do not get records for old employees as well.</span></span> <span data-ttu-id="fc253-108">Para asegurarse de que la instrucción Select anterior le proporciona solo los empleados recién agregados, actualizará el **empleado** tabla utilizando la instrucción SQL siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc253-108">To make sure that the above Select statement gives only the newly added employees, you will update the **Employee** table using the following SQL statement:</span></span>  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 <span data-ttu-id="fc253-109">Por lo tanto, la **estado** columna para los empleados anteriores se establece en "1", mientras que los empleados nuevos siempre es "0".</span><span class="sxs-lookup"><span data-stu-id="fc253-109">So, the **Status** column for the old employees is set to “1” while new employees will always be “0.”</span></span>  
  
 <span data-ttu-id="fc253-110">En esta lección, se ejecutará un procedimiento almacenado, **UPDATE_EMPLOYEE**, que a su vez ejecuta las instrucciones Select y Update.</span><span class="sxs-lookup"><span data-stu-id="fc253-110">In this lesson, you will execute a stored procedure, **UPDATE_EMPLOYEE**, which in turn executes the Select and Update statements.</span></span> <span data-ttu-id="fc253-111">Cuando haya terminado de esta lección, la orquestación hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc253-111">After you have finished this lesson, your orchestration will do the following:</span></span>  
  
1.  <span data-ttu-id="fc253-112">Recibe la notificación de los cambios realizados en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="fc253-112">Receives notification for any changes to the **Employee** table.</span></span>  
  
2.  <span data-ttu-id="fc253-113">Extrae el tipo de notificación recibe el mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="fc253-113">Extracts the type of notification from the notification message received.</span></span>  
  
3.  <span data-ttu-id="fc253-114">Si el mensaje de notificación es para una operación de inserción, la orquestación ejecuta la **UPDATE_EMPLOYEE** procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="fc253-114">If the notification message is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
4.  <span data-ttu-id="fc253-115">El procedimiento almacenado lee los registros recién especificados en la **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="fc253-115">The stored procedure reads the newly entered records in the **Employee** table.</span></span> <span data-ttu-id="fc253-116">Después de leer los nuevos registros, el procedimiento almacenado también establece la **estado** columna para dichos registros a "1".</span><span class="sxs-lookup"><span data-stu-id="fc253-116">After reading the new records, the stored procedure also sets the **Status** column for those records to “1.”</span></span>  
  
 <span data-ttu-id="fc253-117">Ahora ya sabe por qué necesita ejecutar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="fc253-117">Now you know why you need to execute the stored procedure.</span></span> <span data-ttu-id="fc253-118">Debe pensar en cómo se ejecuta como parte de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="fc253-118">You now need to think about how to execute this as part of the orchestration.</span></span> <span data-ttu-id="fc253-119">La orquestación necesita un mensaje de solicitud para la **UPDATE_EMPLOYEE** procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="fc253-119">The orchestration needs a request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="fc253-120">En este tutorial, creará una biblioteca de clases personalizadas que creará el mensaje sobre la marcha y, a continuación, se proporcionan a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="fc253-120">In this tutorial, you will create a custom class library that will create the message on the fly and then provide it to the orchestration.</span></span> <span data-ttu-id="fc253-121">Después de que la orquestación recibe el mensaje, enviará el mensaje a SQL Server mediante el adaptador de SQL y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="fc253-121">After the orchestration receives the message, it will send the message to the SQL Server using the SQL adapter and receive the response.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc253-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fc253-122">In This Section</span></span>  
  
-   [<span data-ttu-id="fc253-123">Paso 1: Crear el mensaje de solicitud de UPDATE_EMPLOYEE procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="fc253-123">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [<span data-ttu-id="fc253-124">Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir respuesta</span><span class="sxs-lookup"><span data-stu-id="fc253-124">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)