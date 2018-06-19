---
title: 'Paso 1: Crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fde018d8-9d9a-42ea-8ee9-e3632450b9d7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71021bb0a9bbb71f17f0899e625ac184f9087429
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966010"
---
# <a name="step-1-create-the-request-message-for-insert-operation-on-purchaseorder-table"></a><span data-ttu-id="1c084-102">Paso 1: Crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order</span><span class="sxs-lookup"><span data-stu-id="1c084-102">Step 1: Create the Request Message for Insert Operation on Purchase_Order Table</span></span>
<span data-ttu-id="1c084-103">![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="1c084-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="1c084-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="1c084-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="1c084-105">**Objetivo:** en este paso, agregará un proyecto de biblioteca de clases de C# a la solución.</span><span class="sxs-lookup"><span data-stu-id="1c084-105">**Objective:** In this step, you add a C# class library project to your solution.</span></span> <span data-ttu-id="1c084-106">Esta biblioteca crea un mensaje de solicitud en memoria para la operación de inserción en el **Purchase_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="1c084-106">This library creates an in-memory request message for the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="1c084-107">En pasos posteriores, la orquestación envía este mensaje a SQL Server para insertar registros en la tabla.</span><span class="sxs-lookup"><span data-stu-id="1c084-107">In later steps, the orchestration sends this message to SQL Server to insert records in the table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1c084-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1c084-108">Prerequisites</span></span>  
 <span data-ttu-id="1c084-109">Debe haber completado los pasos descritos en [lección 3: ejecutar un procedimiento almacenado que seleccione a nuevos empleados agregar](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span><span class="sxs-lookup"><span data-stu-id="1c084-109">You must have completed the steps in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
### <a name="to-create-a-request-message-for-insert-operation"></a><span data-ttu-id="1c084-110">Para crear un mensaje de solicitud para la operación de inserción</span><span class="sxs-lookup"><span data-stu-id="1c084-110">To create a request message for Insert operation</span></span>  
  
1.  <span data-ttu-id="1c084-111">Agregar un proyecto de biblioteca de clases de Visual C# a la solución.</span><span class="sxs-lookup"><span data-stu-id="1c084-111">Add a Visual C# class library project to your solution.</span></span> <span data-ttu-id="1c084-112">Para el nombre del proyecto, escriba `UpdatePOMessageCreator`.</span><span class="sxs-lookup"><span data-stu-id="1c084-112">For the name of the project, type `UpdatePOMessageCreator`.</span></span>  
  
2.  <span data-ttu-id="1c084-113">Cambiar el nombre de **Class1.cs** a **UpdatePOMessageCreator.cs**.</span><span class="sxs-lookup"><span data-stu-id="1c084-113">Rename **Class1.cs** to **UpdatePOMessageCreator.cs**.</span></span>  
  
3.  <span data-ttu-id="1c084-114">Copie el código siguiente en el archivo. cs:</span><span class="sxs-lookup"><span data-stu-id="1c084-114">Copy the following code to the .cs file:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdatePOMessageCreator  
    {  
        public class UpdatePOMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreatePOMessage";  
                try  
                {  
                    ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                    Console.WriteLine("EXCEPTION: " + ex.ToString());  
                    throw ex;  
                }  
  
                //Create Message From XML  
                Message = new XmlDocument();  
  
                Message.PreserveWhitespace = true;  
  
                Message.Load(ResponseDoc);  
  
                return Message;  
            }  
        }  
    }  
  
    ```  
  
     <span data-ttu-id="1c084-115">Este fragmento de código, espera un mensaje de solicitud para la operación de inserción en el **Purchase_Order** tabla esté presente en C:\TestLocation\CreatePOMessage.</span><span class="sxs-lookup"><span data-stu-id="1c084-115">This code snippet expects a request message for the Insert operation on the **Purchase_Order** table to be present at C:\TestLocation\CreatePOMessage.</span></span> <span data-ttu-id="1c084-116">El código usa el mensaje de solicitud para crear un mensaje de solicitud similar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c084-116">The code uses the request message to create a similar request message at run time.</span></span>  
  
4.  <span data-ttu-id="1c084-117">Agregue un archivo de clave de nombre seguro al proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c084-117">Add a strong-name key file to the project.</span></span> <span data-ttu-id="1c084-118">Para obtener instrucciones sobre cómo crear un archivo de clave de nombre seguro, vea [los requisitos previos para crear aplicaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="1c084-118">For instructions on creating a strong-name key file, see [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span></span>  
  
    1.  <span data-ttu-id="1c084-119">En el Explorador de soluciones, haga clic en el **UpdatePOMessageCreator** del proyecto y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1c084-119">In the Solution Explorer, right-click the **UpdatePOMessageCreator** project and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="1c084-120">En el **propiedad** ventana, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="1c084-120">In the **Property** window, click **Signing**.</span></span>  
  
    3.  <span data-ttu-id="1c084-121">En el **firma** ficha, seleccione la **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="1c084-121">In the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
    4.  <span data-ttu-id="1c084-122">Desde el **elegir un archivo de clave de nombre seguro** lista, haga clic en  **\<examinar\>**.</span><span class="sxs-lookup"><span data-stu-id="1c084-122">From the **Choose a strong-name key file** list, click **\<Browse\>**.</span></span>  
  
    5.  <span data-ttu-id="1c084-123">Navegue hasta la carpeta donde se creó el archivo de clave de nombre seguro y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="1c084-123">Navigate to the folder where you created the strong-name key file, and then click **Open**.</span></span>  
  
    6.  <span data-ttu-id="1c084-124">Haga clic en **guardar** en el **estándar** barra de menús.</span><span class="sxs-lookup"><span data-stu-id="1c084-124">Click **Save** on the **Standard** menu bar.</span></span> <span data-ttu-id="1c084-125">Cerrar la **propiedad** ventana.</span><span class="sxs-lookup"><span data-stu-id="1c084-125">Close the **Property** window.</span></span>  
  
5.  <span data-ttu-id="1c084-126">Generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c084-126">Build the project.</span></span> <span data-ttu-id="1c084-127">Haga clic en el proyecto y haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="1c084-127">Right-click the project and click **Build**.</span></span>  
  
6.  <span data-ttu-id="1c084-128">Agregue una referencia de este proyecto al proyecto de BizTalk en la solución.</span><span class="sxs-lookup"><span data-stu-id="1c084-128">Add a reference of this project to the BizTalk project in the solution.</span></span>  
  
    1.  <span data-ttu-id="1c084-129">En el Explorador de soluciones, expanda el proyecto de BizTalk, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="1c084-129">In the Solution Explorer, expand the BizTalk project, right-click **References**, and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="1c084-130">En el **Agregar referencia** cuadro de diálogo, haga clic en el **proyectos** ficha.</span><span class="sxs-lookup"><span data-stu-id="1c084-130">In the **Add Reference** dialog box, click the **Projects** tab.</span></span>  
  
    3.  <span data-ttu-id="1c084-131">En la lista de nombres de proyecto, seleccione **UpdatePOMessageCreator**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1c084-131">From the list of project names, select **UpdatePOMessageCreator**, click **Add**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="1c084-132">Compilar el proyecto, crea el archivo DLL del ensamblado en la carpeta \bin\Debug del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c084-132">Building the project creates the assembly DLL under \bin\Debug folder of the project.</span></span> <span data-ttu-id="1c084-133">Debe agregar este archivo DLL a la caché de ensamblados Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="1c084-133">You must add this DLL to the Global Assembly Cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="1c084-134">Inicie un símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c084-134">Start a Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="1c084-135">Desde el símbolo del sistema, navegue hasta la carpeta \bin\Debug\ de la **UpdatePOMessageCreator** proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c084-135">From the command prompt, navigate to the \bin\Debug\ folder of the **UpdatePOMessageCreator** project.</span></span>  
  
    3.  <span data-ttu-id="1c084-136">Ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="1c084-136">Run the following command on the command prompt:</span></span>  
  
        ```  
        gacutil /i UpdatePOMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="1c084-137">Síntesis</span><span class="sxs-lookup"><span data-stu-id="1c084-137">What did I just do?</span></span>  
 <span data-ttu-id="1c084-138">En este paso, ha agregado un proyecto de biblioteca de clases de UpdatePOMessageCreator que crea el mensaje de solicitud en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c084-138">In this step, you added an UpdatePOMessageCreator class library project that creates request message at run-time.</span></span> <span data-ttu-id="1c084-139">Agregar la referencia a este proyecto en el proyecto de BizTalk y también agrega el archivo DLL del ensamblado a la GAC.</span><span class="sxs-lookup"><span data-stu-id="1c084-139">You added the reference to this project in the BizTalk project and also added the assembly DLL to the GAC.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1c084-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1c084-140">Next Steps</span></span>  
 <span data-ttu-id="1c084-141">Asignar el mensaje de respuesta para el procedimiento almacenado de UPDATE_EMPLOYEE al mensaje de solicitud para la operación de inserción en **Purchaser_Order** tabla.</span><span class="sxs-lookup"><span data-stu-id="1c084-141">You map the response message for the UPDATE_EMPLOYEE stored procedure to the request message for the Insert operation on **Purchaser_Order** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c084-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c084-142">See Also</span></span>  
 <span data-ttu-id="1c084-143">[Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE insertar el mensaje de solicitud de operación](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="1c084-143">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 [<span data-ttu-id="1c084-144">Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="1c084-144">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)