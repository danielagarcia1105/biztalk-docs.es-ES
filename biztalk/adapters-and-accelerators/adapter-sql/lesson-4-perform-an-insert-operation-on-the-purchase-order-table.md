---
title: 'Lección 4: Realizar una operación de inserción en la tabla de orden de compra | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66fc64c5-a3da-4014-8545-f34e6577bd73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c966e3c10f18424b2cfb1fde0235caedbb5f58f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222692"
---
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a><span data-ttu-id="2cae5-102">Lección 4: Realizar una operación de inserción en la tabla de orden de compra</span><span class="sxs-lookup"><span data-stu-id="2cae5-102">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>
<span data-ttu-id="2cae5-103">En [lección 3: ejecutar un procedimiento almacenado que seleccione a nuevos empleados agregar](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md), que ha ejecutado el **UPDATE_EMPLOYEE** procedimiento almacenado y recibe un mensaje de respuesta que contiene los detalles de la recién Inserta el registro del empleado.</span><span class="sxs-lookup"><span data-stu-id="2cae5-103">In [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md), you executed the **UPDATE_EMPLOYEE** stored procedure and received a response message that contains the details of the newly inserted employee record.</span></span> <span data-ttu-id="2cae5-104">En esta lección, se basan en la lección anterior y actualizar la orquestación para llevar a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2cae5-104">In this lesson, you will build on the previous lesson and update the orchestration to perform the following steps:</span></span>  
  
1.  <span data-ttu-id="2cae5-105">En la orquestación, se genera el mensaje para realizar una operación de inserción en el **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="2cae5-105">Within the orchestration, you build the message to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="2cae5-106">Este paso es similar a [paso 1: crear el mensaje de solicitud para el procedimiento almacenado de UPDATE_EMPLOYEE](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="2cae5-106">This step is similar to [Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span></span>  
  
2.  <span data-ttu-id="2cae5-107">Después de crear el mensaje de solicitud, asignar el mensaje de respuesta de la **UPDATE_EMPLOYEE** procedimiento almacenado para el mensaje de solicitud para la operación de inserción en el **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="2cae5-107">After you build the request message, you map the response message of the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="2cae5-108">Mediante la asignación de los mensajes, pasar los valores procedentes de los mensajes de respuesta al mensaje de solicitud para la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="2cae5-108">By mapping the messages, you pass the values received from the response messages to the request message for Insert operation.</span></span>  
  
3.  <span data-ttu-id="2cae5-109">Enviar el mensaje para insertar un registro en el **Purchase_Order** de tabla y recibir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="2cae5-109">You send the message to insert a record in the **Purchase_Order** table and receive a response.</span></span>  
  
4.  <span data-ttu-id="2cae5-110">Enviar la respuesta a un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="2cae5-110">You send the response to a send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cae5-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2cae5-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2cae5-112">Paso 1: Crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order</span><span class="sxs-lookup"><span data-stu-id="2cae5-112">Step 1: Create the Request Message for Insert Operation on Purchase_Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [<span data-ttu-id="2cae5-113">Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE insertar el mensaje de solicitud de operación</span><span class="sxs-lookup"><span data-stu-id="2cae5-113">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [<span data-ttu-id="2cae5-114">Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta</span><span class="sxs-lookup"><span data-stu-id="2cae5-114">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [<span data-ttu-id="2cae5-115">Paso 4: Generar el proyecto</span><span class="sxs-lookup"><span data-stu-id="2cae5-115">Step 4: Build the Project</span></span>](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)