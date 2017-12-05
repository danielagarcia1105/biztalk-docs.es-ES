---
title: 'Paso 1: Crear el mensaje de solicitud de UPDATE_EMPLOYEE procedimiento almacenado | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e30225b79b14ffc237798ddde6f3fe40fb4aea9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="13a26-102">Paso 1: Crear el mensaje de solicitud de UPDATE_EMPLOYEE procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="13a26-102">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>
<span data-ttu-id="13a26-103">![Paso 1 de 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="13a26-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="13a26-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="13a26-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="13a26-105">**Objetivo:** en este paso, agregará un proyecto de biblioteca de clases de C# a la solución.</span><span class="sxs-lookup"><span data-stu-id="13a26-105">**Objective:** In this step, you add a C# class library project to your solution.</span></span> <span data-ttu-id="13a26-106">Esta biblioteca crea un mensaje de solicitud en memoria para el **UPDATE_EMPLOYEE** procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="13a26-106">This library creates an in-memory request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="13a26-107">En pasos posteriores, la orquestación envía este mensaje a SQL Server para ejecutar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="13a26-107">In later steps, the orchestration sends this message to SQL Server to execute the stored procedure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="13a26-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="13a26-108">Prerequisites</span></span>  
 <span data-ttu-id="13a26-109">Debe haber completado los pasos descritos en [lección 2: recibir notificaciones de filtro y](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="13a26-109">You must have completed the steps in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="13a26-110">Para crear un mensaje de solicitud para UPDATE_EMPLOYEE de procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="13a26-110">To create a request message for UPDATE_EMPLOYEE stored procedure</span></span>  
  
1.  <span data-ttu-id="13a26-111">Agregar un proyecto de biblioteca de clases de Visual C# a la solución.</span><span class="sxs-lookup"><span data-stu-id="13a26-111">Add a Visual C# class library project to your solution.</span></span> <span data-ttu-id="13a26-112">Para el nombre del proyecto, escriba `UpdateEmployeeMessageCreator`.</span><span class="sxs-lookup"><span data-stu-id="13a26-112">For the name of the project, type `UpdateEmployeeMessageCreator`.</span></span>  
  
2.  <span data-ttu-id="13a26-113">Cambiar el nombre de **Class1.cs** a **UpdateEmployeeMessageCreator.cs**.</span><span class="sxs-lookup"><span data-stu-id="13a26-113">Rename **Class1.cs** to **UpdateEmployeeMessageCreator.cs**.</span></span>  
  
3.  <span data-ttu-id="13a26-114">Copie el código siguiente en el archivo. cs:</span><span class="sxs-lookup"><span data-stu-id="13a26-114">Copy the following code to the .cs file:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdateEmployeeMessageCreator  
    {  
        public class UpdateEmployeeMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreateEmployeeMessage";  
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
  
     <span data-ttu-id="13a26-115">Este fragmento de código espera un mensaje de solicitud para la **UPDATE_EMPLOYEE** procedimiento almacenado para estar presente en C:\TestLocation\CreateEmployeeMessage.</span><span class="sxs-lookup"><span data-stu-id="13a26-115">This code snippet expects a request message for the **UPDATE_EMPLOYEE** stored procedure to be present at C:\TestLocation\CreateEmployeeMessage.</span></span> <span data-ttu-id="13a26-116">El código usa el mensaje de solicitud para crear un mensaje de solicitud similar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="13a26-116">The code uses the request message to create a similar request message at run time.</span></span>  
  
4.  <span data-ttu-id="13a26-117">Agregue un archivo de clave de nombre seguro al proyecto.</span><span class="sxs-lookup"><span data-stu-id="13a26-117">Add a strong-name key file to the project.</span></span> <span data-ttu-id="13a26-118">Vea [los requisitos previos para crear aplicaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="13a26-118">See [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span></span>  
  
    1.  <span data-ttu-id="13a26-119">En el Explorador de soluciones, haga clic en el **UpdateEmployeeMessageCreator** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="13a26-119">In the Solution Explorer, right-click the **UpdateEmployeeMessageCreator** project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="13a26-120">En el **propiedad** ventana, haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="13a26-120">In the **Property** window, click **Signing**.</span></span>  
  
    3.  <span data-ttu-id="13a26-121">En el **firma** ficha, seleccione la **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="13a26-121">In the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
    4.  <span data-ttu-id="13a26-122">Desde el **elegir un archivo de clave de nombre seguro** lista, haga clic en  **\<examinar\>**.</span><span class="sxs-lookup"><span data-stu-id="13a26-122">From the **Choose a strong-name key file** list, click **\<Browse\>**.</span></span>  
  
    5.  <span data-ttu-id="13a26-123">Navegue hasta la carpeta donde se creó el archivo de clave de nombre seguro y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="13a26-123">Navigate to the folder where you created the strong-name key file, and then click **Open**.</span></span>  
  
    6.  <span data-ttu-id="13a26-124">Haga clic en **guardar** en la barra de menús estándar.</span><span class="sxs-lookup"><span data-stu-id="13a26-124">Click **Save** on the Standard menu bar.</span></span> <span data-ttu-id="13a26-125">Cerrar la **propiedad** ventana.</span><span class="sxs-lookup"><span data-stu-id="13a26-125">Close the **Property** window.</span></span>  
  
5.  <span data-ttu-id="13a26-126">Generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="13a26-126">Build the project.</span></span> <span data-ttu-id="13a26-127">Haga clic en el proyecto y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="13a26-127">Right-click the project, and then click **Build**.</span></span>  
  
6.  <span data-ttu-id="13a26-128">Agregue una referencia de este proyecto al proyecto de BizTalk en la solución.</span><span class="sxs-lookup"><span data-stu-id="13a26-128">Add a reference of this project to the BizTalk project in the solution.</span></span>  
  
    1.  <span data-ttu-id="13a26-129">En el Explorador de soluciones, expanda el proyecto de BizTalk, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="13a26-129">In the Solution Explorer, expand the BizTalk project, right-click **References**, and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="13a26-130">En el **Agregar referencia** cuadro de diálogo, haga clic en el **proyectos** ficha.</span><span class="sxs-lookup"><span data-stu-id="13a26-130">In the **Add Reference** dialog box, click the **Projects** tab.</span></span>  
  
    3.  <span data-ttu-id="13a26-131">En la lista de nombres de proyecto, seleccione **UpdateEmployeeMessageCreator**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13a26-131">From the list of project names, select **UpdateEmployeeMessageCreator**, click **Add**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="13a26-132">Compilar el proyecto, crea el archivo DLL del ensamblado en la carpeta \bin\Debug del proyecto.</span><span class="sxs-lookup"><span data-stu-id="13a26-132">Building the project creates the assembly DLL under \bin\Debug folder of the project.</span></span> <span data-ttu-id="13a26-133">Debe agregar este archivo DLL a la caché de ensamblados Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="13a26-133">You must add this DLL to the Global Assembly Cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="13a26-134">Inicie un símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="13a26-134">Start a Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="13a26-135">Desde el símbolo del sistema, navegue hasta la carpeta \bin\Debug\ de la **UpdateEmployeeMessageCreator** proyecto.</span><span class="sxs-lookup"><span data-stu-id="13a26-135">From the command prompt, navigate to the \bin\Debug\ folder of the **UpdateEmployeeMessageCreator** project.</span></span>  
  
    3.  <span data-ttu-id="13a26-136">Ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="13a26-136">Run the following command on the command prompt:</span></span>  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="13a26-137">Síntesis</span><span class="sxs-lookup"><span data-stu-id="13a26-137">What did I just do?</span></span>  
 <span data-ttu-id="13a26-138">En este paso, ha agregado un proyecto de biblioteca de clases de UpdateEmployeeMessageCreator que crea el mensaje de solicitud en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="13a26-138">In this step, you added an UpdateEmployeeMessageCreator class library project that creates request message at run-time.</span></span> <span data-ttu-id="13a26-139">Agregar la referencia a este proyecto en el proyecto de BizTalk y también agrega el archivo DLL del ensamblado a la GAC.</span><span class="sxs-lookup"><span data-stu-id="13a26-139">You added the reference to this project in the BizTalk project and also added the assembly DLL to the GAC.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="13a26-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="13a26-140">Next Steps</span></span>  
 <span data-ttu-id="13a26-141">Enviar el mensaje de solicitud a SQL Server y recibir la respuesta, como se describe en [paso 2: enviar el mensaje de solicitud a SQL Server y recibir respuesta](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span><span class="sxs-lookup"><span data-stu-id="13a26-141">You send the request message to SQL Server and receive the response, as described in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a26-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="13a26-142">See Also</span></span>  
 [<span data-ttu-id="13a26-143">Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados</span><span class="sxs-lookup"><span data-stu-id="13a26-143">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)