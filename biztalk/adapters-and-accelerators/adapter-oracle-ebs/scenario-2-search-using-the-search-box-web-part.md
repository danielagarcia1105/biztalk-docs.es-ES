---
title: 'Escenario 2: Realizar búsquedas mediante el elemento web de cuadro de búsqueda | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a233772f-7577-4ac5-b55a-cb1ba2f464c7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03e536df00499e8965632a3952eb3ae50e3f83df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218548"
---
# <a name="scenario-2--search-using-the-search-box-web-part"></a><span data-ttu-id="1138f-102">Escenario 2: Realizar búsquedas mediante el elemento web de cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1138f-102">Scenario 2:  Search using the search box web part</span></span>
<span data-ttu-id="1138f-103">Se va a configurar la configuración de búsqueda en Microsoft Office SharePoint Server para configurar una aplicación de búsqueda con la que puede realizar una búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="1138f-103">We will configure the search settings in Microsoft Office SharePoint Server to configure a search application using which you can perform a full text search on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite.</span></span> <span data-ttu-id="1138f-104">Más adelante, agregaremos un elemento de Web de cuadro de búsqueda para desde donde puede realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1138f-104">Later, we will add a Search Box Web Part to from where you can perform the search.</span></span>  
  
 
  
##  <a name="Define"></a><span data-ttu-id="1138f-105">Definir el origen de contenido</span><span class="sxs-lookup"><span data-stu-id="1138f-105">Define the Content Source</span></span>  
 <span data-ttu-id="1138f-106">Esta sección trata acerca de cómo definir un origen de contenido desde donde Microsoft Office SharePoint Server puede rastrear los datos.</span><span class="sxs-lookup"><span data-stu-id="1138f-106">This section talks about defining a content source from where Microsoft Office SharePoint Server can crawl the data.</span></span> <span data-ttu-id="1138f-107">Esto consiste en asignar el contenido para el enumerador de Id. de instancia de método creado en [paso 2: crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="1138f-107">This involves mapping the content to the Id Enumerator method instance created in [Step 2: Create an application definition file for the Oracle E-Business Suite artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span></span>  
  
#### <a name="to-define-a-content-source"></a><span data-ttu-id="1138f-108">Para definir un origen de contenido</span><span class="sxs-lookup"><span data-stu-id="1138f-108">To define a content source</span></span>  
  
1.  <span data-ttu-id="1138f-109">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="1138f-109">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="1138f-110">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="1138f-110">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="1138f-111">En el panel de navegación izquierdo, haga clic en el nombre de los servicio proveedor compartidos (SSP) que va a configurar la aplicación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1138f-111">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="1138f-112">En la página principal, en la **búsqueda** sección, haga clic en **configuración de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="1138f-112">On the Home page, in the **Search** section, click **Search settings**.</span></span>  
  
4.  <span data-ttu-id="1138f-113">En la página Configurar opciones de búsqueda, en el panel izquierdo bajo **rellenando**, haga clic en **cuenta de acceso al contenido predeterminada** para especificar una cuenta para utilizarla como la cuenta predeterminada cuando se rastrea contenido.</span><span class="sxs-lookup"><span data-stu-id="1138f-113">On the Configure Search Settings page, in the left pane under **Crawling**, click **Default content access account** to specify an account to use as the default account when crawling content.</span></span>  
  
5.  <span data-ttu-id="1138f-114">En la página cuenta de acceso al contenido predeterminado, especifique las credenciales de contraseña y nombre de usuario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1138f-114">On the Default Content Access Account page, specify the user name and password credentials, and click **OK**.</span></span> <span data-ttu-id="1138f-115">Volverá a la página de administración de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1138f-115">You will return to the Search Administration page.</span></span>  
  
6.  <span data-ttu-id="1138f-116">En el panel izquierdo bajo **rellenando**, haga clic en **orígenes de contenido**.</span><span class="sxs-lookup"><span data-stu-id="1138f-116">In the left pane under **Crawling**, click **Content Sources**.</span></span>  
  
7.  <span data-ttu-id="1138f-117">En la página Administrar orígenes de contenido, haga clic en **nuevo origen de contenido**.</span><span class="sxs-lookup"><span data-stu-id="1138f-117">On the Manage Content Sources page, click **New Content Source**.</span></span>  
  
8.  <span data-ttu-id="1138f-118">En la página Administrar orígenes de contenido, haga clic en **nuevo origen de contenido**.</span><span class="sxs-lookup"><span data-stu-id="1138f-118">On the Manage Content Sources page, click **New Content Source**.</span></span>  
  
9. <span data-ttu-id="1138f-119">En la página Agregar origen de contenido:</span><span class="sxs-lookup"><span data-stu-id="1138f-119">On the Add Content Source page:</span></span>  
  
    1.  <span data-ttu-id="1138f-120">Tipo de `MS_SAMPLE_EMPLOYEE` en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="1138f-120">Type `MS_SAMPLE_EMPLOYEE` in the **Name** box.</span></span>  
  
    2.  <span data-ttu-id="1138f-121">En el **tipo de origen de contenido** área, haga clic en **datos económicos**.</span><span class="sxs-lookup"><span data-stu-id="1138f-121">In the **Content Source Type** area, click **Business Data**.</span></span>  
  
    3.  <span data-ttu-id="1138f-122">En el **aplicaciones** área, haga clic en **las aplicaciones seleccionadas de rastreo**y, a continuación, seleccione la **MS_SAMPLE_EMPLOYEE_Instance** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="1138f-122">In the **Applications** area, click **Crawl selected applications**, and then select the **MS_SAMPLE_EMPLOYEE_Instance** check box.</span></span>  
  
    4.  <span data-ttu-id="1138f-123">En el **Iniciar rastreo completo** área, seleccione la **Iniciar rastreo completo de este origen de contenido** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1138f-123">In the **Start Full Crawl** area, select the **Start full crawl of this content source** check box, and then click **OK**.</span></span>  
  
         <span data-ttu-id="1138f-124">![Agregar origen de contenido](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27_Add_Content_Source")</span><span class="sxs-lookup"><span data-stu-id="1138f-124">![Add content source](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27_Add_Content_Source")</span></span>  
  
10. <span data-ttu-id="1138f-125">Volverá a la página Administrar orígenes de contenido con el nuevo origen de contenido agregado.</span><span class="sxs-lookup"><span data-stu-id="1138f-125">You will return to the Manage Content Sources page with the new content source added.</span></span> <span data-ttu-id="1138f-126">El origen de contenido se rastreará a través de los datos en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="1138f-126">The content source will crawl through the data in the MS_SAMPLE_EMPLOYEE interface table in the Oracle E-Business Suite.</span></span> <span data-ttu-id="1138f-127">Espere hasta que el rastreo se ha completado.</span><span class="sxs-lookup"><span data-stu-id="1138f-127">Wait until the crawling is completed.</span></span>  
  
11. <span data-ttu-id="1138f-128">En el panel izquierdo bajo **rellenando**, haga clic en **registro de rastreo**y, a continuación, compruebe el archivo de registro para asegurarse que el rastreo se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="1138f-128">In the left pane under **Crawling**, click **Crawl Log**, and then verify the log file to ensure that the crawling is successful.</span></span>  
  
##  <a name="Scope"></a><span data-ttu-id="1138f-129">Definir un ámbito para el contenido rastreado</span><span class="sxs-lookup"><span data-stu-id="1138f-129">Define a Scope for the Crawled Content</span></span>  
  
1.  <span data-ttu-id="1138f-130">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="1138f-130">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="1138f-131">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="1138f-131">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="1138f-132">En el panel de navegación izquierdo, haga clic en el nombre de los servicio proveedor compartidos (SSP) que va a configurar la aplicación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1138f-132">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="1138f-133">En la página principal, en la **búsqueda** sección, haga clic en **configuración de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="1138f-133">On the Home page, in the **Search** section, click **Search settings**.</span></span>  
  
4.  <span data-ttu-id="1138f-134">En la página Configurar opciones de búsqueda, en el panel izquierdo bajo **consulta y resultados**, haga clic en **ámbitos** para definir un ámbito para el rastreo de datos.</span><span class="sxs-lookup"><span data-stu-id="1138f-134">On the Configure Search Settings page, in the left pane under **Queries and Results**, click **Scopes** to define a scope for the crawling of data.</span></span>  
  
5.  <span data-ttu-id="1138f-135">En la página Ver ámbitos, haga clic en **nuevo ámbito**.</span><span class="sxs-lookup"><span data-stu-id="1138f-135">On the View Scopes page, click **New Scope**.</span></span>  
  
6.  <span data-ttu-id="1138f-136">En la página Crear ámbito, escriba `MS_SAMPLE_EMPLOYEE_Search` en el **título** cuadro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1138f-136">On the Create Scope page, type `MS_SAMPLE_EMPLOYEE_Search` in the **Title** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="1138f-137">![Crear un ámbito](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28_Create_Scope")</span><span class="sxs-lookup"><span data-stu-id="1138f-137">![Create a scope](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28_Create_Scope")</span></span>  
  
7.  <span data-ttu-id="1138f-138">Volverá a la página Ver ámbitos con el nuevo ámbito agregado.</span><span class="sxs-lookup"><span data-stu-id="1138f-138">You will return to the View Scopes page with the new scope added.</span></span> <span data-ttu-id="1138f-139">En el **estado de actualización** columna para el ámbito recién agregado, haga clic en el **agregar reglas** vínculo.</span><span class="sxs-lookup"><span data-stu-id="1138f-139">In the **Update Status** column for the newly added scope, click the **Add rules** link.</span></span>  
  
8.  <span data-ttu-id="1138f-140">En la página Agregar regla de ámbito:</span><span class="sxs-lookup"><span data-stu-id="1138f-140">On the Add Scope Rule page:</span></span>  
  
    1.  <span data-ttu-id="1138f-141">En el **tipo de regla de ámbito** área, haga clic en **origen de contenido**.</span><span class="sxs-lookup"><span data-stu-id="1138f-141">In the **Scope Rule Type** area, click **Content Source**.</span></span>  
  
    2.  <span data-ttu-id="1138f-142">En el **origen de contenido** lista, haga clic en **MS_SAMPLE_EMPLOYEE**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1138f-142">In the **Content Source** list, click **MS_SAMPLE_EMPLOYEE**, and then click **OK**.</span></span>  
  
         <span data-ttu-id="1138f-143">![Agregar una regla de ámbito](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29_Add_Scope_Rule")</span><span class="sxs-lookup"><span data-stu-id="1138f-143">![Add a scope rule](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29_Add_Scope_Rule")</span></span>  
  
9. <span data-ttu-id="1138f-144">Volverá a la página Ver ámbitos con la regla agregada para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="1138f-144">You will return to the View Scopes page with the rule added for the scope.</span></span> <span data-ttu-id="1138f-145">En el panel izquierdo, haga clic en **administración de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="1138f-145">In the left pane, click **Search Administration**.</span></span>  
  
10. <span data-ttu-id="1138f-146">En la página de administración de búsqueda, busque el **ámbitos que requieren actualización** de fila y haga clic en el **Iniciar actualización ahora** vínculo.</span><span class="sxs-lookup"><span data-stu-id="1138f-146">On the Search Administration page, locate the **Scopes needing update** row, and click the **Start update now** link.</span></span>  
  
 <span data-ttu-id="1138f-147">El **estado de actualización de ámbito** fila mostrará el estado de la actualización de ámbito.</span><span class="sxs-lookup"><span data-stu-id="1138f-147">The **Scope update status** row will display the status of the scope update.</span></span> <span data-ttu-id="1138f-148">Espere hasta que finalice la actualización.</span><span class="sxs-lookup"><span data-stu-id="1138f-148">Wait until the update is complete.</span></span> <span data-ttu-id="1138f-149">Una vez completada la actualización, el ámbito está listo para usarse.</span><span class="sxs-lookup"><span data-stu-id="1138f-149">After the updated is completed, the scope is ready to be used.</span></span>  
  
##  <a name="AddScope"></a><span data-ttu-id="1138f-150">Agregar el ámbito a la lista desplegable de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1138f-150">Add the Scope to the Search Dropdown</span></span>  
 <span data-ttu-id="1138f-151">Después de haber creado el ámbito de búsqueda, debe agregar el ámbito a la lista desplegable de búsqueda en Microsoft Office SharePoint Server para que se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="1138f-151">After you have created the search scope, you must add the scope to the search dropdown in Microsoft Office SharePoint Server so that it can be used.</span></span>  
  
#### <a name="to-add-the-scope-to-the-search-dropdown"></a><span data-ttu-id="1138f-152">Para agregar el ámbito a la lista desplegable de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1138f-152">To add the scope to the search dropdown</span></span>  
  
1.  <span data-ttu-id="1138f-153">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="1138f-153">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="1138f-154">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="1138f-154">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="1138f-155">En el panel de navegación izquierdo, haga clic en el nombre de los servicio proveedor compartidos (SSP) que va a configurar la aplicación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1138f-155">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="1138f-156">En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="1138f-156">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="1138f-157">En la página Configuración del sitio, en la **administración de colección de sitios** sección, haga clic en **ámbitos de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="1138f-157">On the Site Settings page, in the **Site Collection Administration** section, click **Search scopes**.</span></span>  
  
5.  <span data-ttu-id="1138f-158">En la página Ver ámbitos, haga clic en el **cuadro desplegable de búsqueda** vínculo.</span><span class="sxs-lookup"><span data-stu-id="1138f-158">On the View Scopes page, click the **Search Dropdown** link.</span></span>  
  
     <span data-ttu-id="1138f-159">![Ver ámbitos](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")</span><span class="sxs-lookup"><span data-stu-id="1138f-159">![View scopes](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")</span></span>  
  
6.  <span data-ttu-id="1138f-160">En la página Editar grupo de presentación de ámbito:</span><span class="sxs-lookup"><span data-stu-id="1138f-160">On the Edit Scope Display Group page:</span></span>  
  
    1.  <span data-ttu-id="1138f-161">En el **ámbitos** área, seleccione la **MS_SAMPLE_EMPLOYEE_Search** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="1138f-161">In the **Scopes** area, select the **MS_SAMPLE_EMPLOYEE_Search** check box.</span></span>  
  
    2.  <span data-ttu-id="1138f-162">En el **ámbito predeterminado** área, haga clic en **MS_SAMPLE_EMPLOYEE_Search** en el **ámbito predeterminado** lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1138f-162">In the **Default Scope** area, click **MS_SAMPLE_EMPLOYEE_Search** in the **Default Scope** list, and then click **OK**.</span></span>  
  
         <span data-ttu-id="1138f-163">![Página Editar grupo de presentación de ámbito](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31_Edit_Scope_Display_Group")</span><span class="sxs-lookup"><span data-stu-id="1138f-163">![Edit Scope Display Group page](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31_Edit_Scope_Display_Group")</span></span>  
  
7.  <span data-ttu-id="1138f-164">Volverá a la página Ver ámbitos con el ámbito de MS_SAMPLE_EMPLOYEE_Search agregado en el grupo de presentación de la lista desplegable de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1138f-164">You will return to the View Scopes page with the MS_SAMPLE_EMPLOYEE_Search scope added in the Search Dropdown display group.</span></span>  
  
##  <a name="SearchWebPart"></a><span data-ttu-id="1138f-165">Agregar el elemento Web de cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1138f-165">Add the Search Box Web Part</span></span>  
 <span data-ttu-id="1138f-166">Para permitir a los usuarios a realizar una búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite, ahora debe crear una página de elementos Web y agregar un elemento Web de cuadro de búsqueda a él.</span><span class="sxs-lookup"><span data-stu-id="1138f-166">To enable the users to perform a full-text search on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite, you must now create a Web part page, and add a Search Box Web Part to it.</span></span>  
  
#### <a name="to-add-the-search-box-web-part"></a><span data-ttu-id="1138f-167">Para agregar el elemento Web de cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1138f-167">To add the Search Box Web Part</span></span>  
  
1.  <span data-ttu-id="1138f-168">Cree una página de elemento Web denominada **MS_SAMPLE_EMPLOYEE_Search**.</span><span class="sxs-lookup"><span data-stu-id="1138f-168">Create a Web Part page called **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="1138f-169">Para conocer los pasos para crear una página de elementos Web, consulte [escenario 1: mostrar datos mediante el elemento web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md) en [escenario 1: mostrar datos mediante el elemento web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span><span class="sxs-lookup"><span data-stu-id="1138f-169">To know the steps for creating a Web Part page, see [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md) in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
2.  <span data-ttu-id="1138f-170">En la página MS_SAMPLE_EMPLOYEE_Search, haga clic en **agregar un elemento Web**.</span><span class="sxs-lookup"><span data-stu-id="1138f-170">On the MS_SAMPLE_EMPLOYEE_Search page, click **Add a Web Part**.</span></span>  
  
3.  <span data-ttu-id="1138f-171">En el **agregar elementos Web** cuadro de diálogo, en la **búsqueda** sección, seleccione la **cuadro de búsqueda** casilla de verificación y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="1138f-171">In the **Add Web Parts** dialog box, in the **Search** section, select the **Search Box** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="1138f-172">![Agregar el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32_Search_Web_Part")</span><span class="sxs-lookup"><span data-stu-id="1138f-172">![Add the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32_Search_Web_Part")</span></span>  
  
4.  <span data-ttu-id="1138f-173">El elemento Web cuadro de búsqueda se agrega a la página MS_SAMPLE_EMPLOYEE_Search.</span><span class="sxs-lookup"><span data-stu-id="1138f-173">The Search Box Web part is added to the MS_SAMPLE_EMPLOYEE_Search page.</span></span>  
  
     <span data-ttu-id="1138f-174">![Elemento Web cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33_Search_Web_Part_Final")</span><span class="sxs-lookup"><span data-stu-id="1138f-174">![Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33_Search_Web_Part_Final")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1138f-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="1138f-175">See Also</span></span>  
 [<span data-ttu-id="1138f-176">Paso 3: Crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="1138f-176">Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
 [<span data-ttu-id="1138f-177">Escenario 1: Mostrar datos mediante el elemento web de lista de datos económicos</span><span class="sxs-lookup"><span data-stu-id="1138f-177">Scenario 1: Display data using Business Data List web part</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)