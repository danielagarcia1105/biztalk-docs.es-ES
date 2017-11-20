---
title: "Paso 4: Probar la aplicación de SharePoint | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427235d27e4e783111ccdb60f799c228737cd008
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="f69d2-102">Paso 4: Probar la aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f69d2-102">Step 4: Test your SharePoint application</span></span>
<span data-ttu-id="f69d2-103">![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="f69d2-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="f69d2-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="f69d2-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="f69d2-105">**Objetivo:** después de haber agregado elementos Web en el sitio de SharePoint y crea una aplicación, debe probar la aplicación al recuperar algunos datos de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="f69d2-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Oracle E-Business Suite.</span></span> <span data-ttu-id="f69d2-106">Este tema proporciona instrucciones sobre cómo usar la aplicación para recuperar los datos de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="f69d2-106">This topic provides instructions on how to use the application to retrieve the data from the Oracle E-Business Suite.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f69d2-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f69d2-107">Prerequisites</span></span>  
 <span data-ttu-id="f69d2-108">Deberá haber creado la página de elementos Web que contiene los elementos Web adecuado para recuperar los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="f69d2-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="f69d2-109">Vea [paso 3: crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span><span class="sxs-lookup"><span data-stu-id="f69d2-109">See [Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a><span data-ttu-id="f69d2-110">Escenario 1: Para probar la aplicación de SharePoint creado mediante el elemento de Web de lista de datos económicos</span><span class="sxs-lookup"><span data-stu-id="f69d2-110">Scenario 1: To test the SharePoint application created using Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="f69d2-111">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="f69d2-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="f69d2-112">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="f69d2-113">En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f69d2-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="f69d2-114">En el panel izquierdo, haga clic en **ver todo el contenido del sitio**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="f69d2-115">En el panel derecho, haga clic en **plantillas de formulario**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="f69d2-116">En el **formulario categoría** lista, haga clic en **MS_SAMPLE_EMPLOYEE**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-116">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE**.</span></span> <span data-ttu-id="f69d2-117">Ha especificado este nombre cuando creaste la página de elementos Web en [escenario 1: mostrar datos mediante el elemento web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span><span class="sxs-lookup"><span data-stu-id="f69d2-117">You specified this name when you created the Web Part page in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
5.  <span data-ttu-id="f69d2-118">Búsqueda de empleados basada en una cadena de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f69d2-118">Search for employees based on a search string.</span></span> <span data-ttu-id="f69d2-119">Por ejemplo, para buscar todos los empleados, escriba  **%**  en el cuadro de texto y haga clic en **recuperar datos**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-119">For example, to search for all the employees, type **%** in the text box, and click **Retrieve Data**.</span></span> <span data-ttu-id="f69d2-120">La siguiente ilustración muestra los archivos recuperados de Oracle E-Business Suite:</span><span class="sxs-lookup"><span data-stu-id="f69d2-120">The following figure shows the records retrieved from Oracle E-Business Suite:</span></span>  
  
     <span data-ttu-id="f69d2-121">![Resultado de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span><span class="sxs-lookup"><span data-stu-id="f69d2-121">![Search result](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span></span>  
  
6.  <span data-ttu-id="f69d2-122">También puede buscar un empleado concreto mediante la especificación de su nombre o apellido:</span><span class="sxs-lookup"><span data-stu-id="f69d2-122">You can also search for a specific employee by entering their first name or last name:</span></span>  
  
    -   <span data-ttu-id="f69d2-123">Para buscar mediante el nombre, escriba las letras iniciales de un nombre de empleado seguido por el  **%**  símbolos para devolver registros de todos los empleados que cumpla los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f69d2-123">To search using the first name, type the initial letters of an employee name followed by the **%** symbol to return records of all the employees matching the search criteria.</span></span>  
  
    -   <span data-ttu-id="f69d2-124">Para buscar con el apellido, escriba  **%**  seguido por el apellido del empleado.</span><span class="sxs-lookup"><span data-stu-id="f69d2-124">To search using the last name, type **%** followed by employee’s last name.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f69d2-125">La cadena de búsqueda distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f69d2-125">The search string is case sensitive.</span></span>  
  
     <span data-ttu-id="f69d2-126">![Buscar por nombre de un empleado](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span><span class="sxs-lookup"><span data-stu-id="f69d2-126">![Searching by first name of an employee](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span></span>  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a><span data-ttu-id="f69d2-127">Escenario 2: Para probar la aplicación de SharePoint creado para realizar una búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="f69d2-127">Scenario 2: To test the SharePoint application created to perform a full-text search</span></span>  
  
1.  <span data-ttu-id="f69d2-128">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="f69d2-128">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="f69d2-129">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-129">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="f69d2-130">En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f69d2-130">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="f69d2-131">En el panel izquierdo, haga clic en **ver todo el contenido del sitio**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-131">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="f69d2-132">En el panel derecho, haga clic en **plantillas de formulario**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-132">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="f69d2-133">En el **formulario categoría** lista, haga clic en **MS_SAMPLE_EMPLOYEE_Search**.</span><span class="sxs-lookup"><span data-stu-id="f69d2-133">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="f69d2-134">Ha especificado este nombre cuando creaste la página de elementos Web en [escenario 2: realizar una búsqueda mediante el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md) en [escenario 2: realizar una búsqueda mediante el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span><span class="sxs-lookup"><span data-stu-id="f69d2-134">You specified this name when you created the Web Part page in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md) in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span></span>  
  
5.  <span data-ttu-id="f69d2-135">La página MS_SAMPLE_EMPLOYEE_Search muestra el cuadro de búsqueda que puede realizar una búsqueda de texto completo en la tabla de empleados de MS_SAMPLE.</span><span class="sxs-lookup"><span data-stu-id="f69d2-135">The MS_SAMPLE_EMPLOYEE_Search page displays the search box where you can perform a full-text search on the MS_SAMPLE EMPLOYEE table.</span></span> <span data-ttu-id="f69d2-136">Por ejemplo, si desea buscar todos los empleados que viven en Nueva York, escriba `New York` en el cuadro de búsqueda y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="f69d2-136">For example, if you want to search for all the employees who live in New York, type `New York` in the search box, and press ENTER.</span></span>  
  
     <span data-ttu-id="f69d2-137">![Especifique un parámetro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span><span class="sxs-lookup"><span data-stu-id="f69d2-137">![Specify a search parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span></span>  
  
6.  <span data-ttu-id="f69d2-138">Aparece una página con los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f69d2-138">A page appears with the search results.</span></span> <span data-ttu-id="f69d2-139">Cada registros coincidentes se muestra como un vínculo en la página de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f69d2-139">Each matching records is displayed as a link in the search results page.</span></span>  
  
     <span data-ttu-id="f69d2-140">![Resultados de la búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span><span class="sxs-lookup"><span data-stu-id="f69d2-140">![Search results](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span></span>  
  
7.  <span data-ttu-id="f69d2-141">Haga clic en un vínculo en el resultado de la búsqueda para ver el registro de empleado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f69d2-141">Click a link in the search result to view the respective employee record.</span></span>  
  
     <span data-ttu-id="f69d2-142">![Registro de empleado detallado](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span><span class="sxs-lookup"><span data-stu-id="f69d2-142">![Detailed employee record](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="f69d2-143">Resumen</span><span class="sxs-lookup"><span data-stu-id="f69d2-143">Summary</span></span>  
 <span data-ttu-id="f69d2-144">En este tutorial, ha creado un servicio WCF para los artefactos de Oracle E-Business Suite que desea tener acceso desde un SharePoint Portal.</span><span class="sxs-lookup"><span data-stu-id="f69d2-144">In this tutorial, you created a WCF service for the Oracle E-Business Suite artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="f69d2-145">También se crea una definición de aplicación para los artefactos de Oracle E-Business Suite que se importa en un portal de SharePoint para crear elementos Web para presentar y buscar datos en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="f69d2-145">You also created an application definition for the Oracle E-Business Suite artifacts that is imported into a SharePoint portal to create Web Parts to present and search data in Oracle E-Business Suite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f69d2-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="f69d2-146">See Also</span></span>  
 [<span data-ttu-id="f69d2-147">Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f69d2-147">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)