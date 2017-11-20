---
title: "Paso 4: Probar la aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 488b13fa-7a71-4430-bbf5-dbf47ba55562
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 347c2bcf459d7e9ce7b1fb9efc07579be81d989d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-application"></a><span data-ttu-id="c72b2-102">Paso 4: Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="c72b2-102">Step 4: Test the Application</span></span>
<span data-ttu-id="c72b2-103">![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="c72b2-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="c72b2-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="c72b2-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="c72b2-105">**Objetivo:** en este paso, probará la aplicación mediante la inserción de un registro en el **empleado** tabla de la **ADAPTER_SAMPLES** base de datos.</span><span class="sxs-lookup"><span data-stu-id="c72b2-105">**Objective:** In this step, you test the application by inserting a record in the **Employee** table of the **ADAPTER_SAMPLES** database.</span></span> <span data-ttu-id="c72b2-106">Si la aplicación funciona correctamente, la orquestación recibe una notificación de cambios en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="c72b2-106">If the application is working properly, the orchestration receives a notification for changes to the **Employee** table.</span></span> <span data-ttu-id="c72b2-107">A continuación, la orquestación extrae el tipo de notificación recibida.</span><span class="sxs-lookup"><span data-stu-id="c72b2-107">The orchestration then extracts the type of notification received.</span></span> <span data-ttu-id="c72b2-108">Si la notificación es para una operación de inserción, la orquestación ejecuta la **UPDATE_EMPLOYEE** procedimiento almacenado y recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="c72b2-108">If the notification is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure and receives a response.</span></span> <span data-ttu-id="c72b2-109">La orquestación extrae los valores de **Id_Empleado** y **nombre** de la respuesta y los inserta en la **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="c72b2-109">The orchestration extracts the values of **Employee_ID** and **Name** from the response and inserts them into the **Purchase_Order** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c72b2-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c72b2-110">Prerequisites</span></span>  
 <span data-ttu-id="c72b2-111">Antes de comenzar con este paso, debe asegurarse de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c72b2-111">Before starting with this step, you must ensure the following:</span></span>  
  
-   <span data-ttu-id="c72b2-112">Un mensaje de solicitud para invocar la **UPDATE_EMPLOYEE** procedimiento almacenado está disponible en C:\TestLocation\CreateEmployeeMessage.</span><span class="sxs-lookup"><span data-stu-id="c72b2-112">A request message to invoke the **UPDATE_EMPLOYEE** stored procedure is available at C:\TestLocation\CreateEmployeeMessage.</span></span> <span data-ttu-id="c72b2-113">El mensaje de solicitud tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c72b2-113">The request message looks like the following:</span></span>  
  
    ```  
    <UPDATE_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/dbo" />  
    ```  
  
-   <span data-ttu-id="c72b2-114">Un mensaje de solicitud para invocar la operación de inserción en el **Purchase_Order** tabla está disponible en C:\TestLocation\CreatePOMessage.</span><span class="sxs-lookup"><span data-stu-id="c72b2-114">A request message to invoke the Insert operation on the **Purchase_Order** table is available at C:\TestLocation\CreatePOMessage.</span></span> <span data-ttu-id="c72b2-115">El mensaje de solicitud tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c72b2-115">The request message looks like the following:</span></span>  
  
    ```  
    <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Purchase_Order">  
      <Rows>  
        <Purchase_Order xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10</Employee_ID><Employee_Name>Employee_Name</Employee_Name>  
        </Purchase_Order>  
      </Rows>  
    </Insert>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c72b2-116">Los valores para la **Id_Empleado** y **Nombre_Empleado** campos son marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="c72b2-116">The values for the **Employee_ID** and **Employee_Name** fields are placeholders.</span></span> <span data-ttu-id="c72b2-117">Los valores reales se insertan por la orquestación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c72b2-117">The actual values are inserted by the orchestration at run-time.</span></span>  
  
-   <span data-ttu-id="c72b2-118">Debe haber completado [paso 3: configurar e iniciar la aplicación](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).</span><span class="sxs-lookup"><span data-stu-id="c72b2-118">You must have completed [Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="c72b2-119">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="c72b2-119">To test the application</span></span>  
  
1.  <span data-ttu-id="c72b2-120">Insertar un registro en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="c72b2-120">Insert a record in the **Employee** table.</span></span> <span data-ttu-id="c72b2-121">Puede hacerlo ejecutando la siguiente instrucción de SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c72b2-121">You can do so by running the following statement from SQL Server Management Studio.</span></span>  
  
    ```  
    INSERT INTO [ADAPTER_SAMPLES].[dbo].[Employee] ([Name] ,[Designation] ,[Salary])  
    VALUES('John Smith' ,'Manager' ,500000)  
    ```  
  
2.  <span data-ttu-id="c72b2-122">Compruebe el **empleado** tabla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c72b2-122">Check the **Employee** table in the database.</span></span> <span data-ttu-id="c72b2-123">Observará que el nuevo registro se agrega mediante la **estado** columna es "0".</span><span class="sxs-lookup"><span data-stu-id="c72b2-123">You will notice that the new record is added by the **Status** column is “0.”</span></span>  
  
3.  <span data-ttu-id="c72b2-124">Mantener actualizando el **empleado** registros de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c72b2-124">Keep refreshing the **Employee** table records.</span></span> <span data-ttu-id="c72b2-125">Observará que la **estado** columna para el nuevo registro ahora está establecido en "1".</span><span class="sxs-lookup"><span data-stu-id="c72b2-125">You will notice that the **Status** column for the new record is now set to “1.”</span></span>  
  
4.  <span data-ttu-id="c72b2-126">Compruebe el **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="c72b2-126">Check the **Purchase_Order** table.</span></span> <span data-ttu-id="c72b2-127">Observará que un registro con el mismo nombre de empleado y designación, como se indica en la instrucción Insert, se agrega a la tabla.</span><span class="sxs-lookup"><span data-stu-id="c72b2-127">You will notice that a record with the same employee name and designation, as you provided in the Insert statement, is added to the table.</span></span>  
  
5.  <span data-ttu-id="c72b2-128">Si proporciona el alias de correo electrónico en la configuración del puerto SMTP, también recibirá un correo electrónico con el mensaje de respuesta para la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="c72b2-128">If you provided your e-mail alias in the SMTP port configuration, you will also receive an e-mail with the response message for the Insert operation.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="c72b2-129">Síntesis</span><span class="sxs-lookup"><span data-stu-id="c72b2-129">What did I just do?</span></span>  
 <span data-ttu-id="c72b2-130">Probar la aplicación SampleApplication insertando un registro en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="c72b2-130">Tested the SampleApplication application by inserting a record in the **Employee** table.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c72b2-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c72b2-131">Next Steps</span></span>  
 <span data-ttu-id="c72b2-132">Si la prueba ha funcionado, enhorabuena.</span><span class="sxs-lookup"><span data-stu-id="c72b2-132">If the test worked, congratulations!</span></span> <span data-ttu-id="c72b2-133">Ha completado la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tutorial.</span><span class="sxs-lookup"><span data-stu-id="c72b2-133">You have completed the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tutorial.</span></span>  
  
 <span data-ttu-id="c72b2-134">Si no ha funcionado la prueba, compruebe con detenimiento el trabajo realizado para asegurarse de que ha agregado todos los objetos necesarios y de que ha establecido las propiedades de éstos correctamente.</span><span class="sxs-lookup"><span data-stu-id="c72b2-134">If the test did not work, carefully check your work to make sure that you added all of the necessary objects and set their properties correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c72b2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c72b2-135">See Also</span></span>  
 <span data-ttu-id="c72b2-136">[Paso 3: Configurar e iniciar la aplicación](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="c72b2-136">[Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span></span>  
 [<span data-ttu-id="c72b2-137">Lección 5: Implementar la solución</span><span class="sxs-lookup"><span data-stu-id="c72b2-137">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)