---
title: 'Paso 2: Crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2665afde-0337-4795-ab4c-6223d39fdf9c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0bd73da129e978bfe2d4ad5af2b4f26fb9bcc16
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970757"
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a><span data-ttu-id="91697-102">Paso 2: Crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="91697-102">Step 2: Create an application definition file for the Oracle E-Business Suite artifacts</span></span>
<span data-ttu-id="91697-103">![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="91697-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="91697-104">**Tiempo en completarse:** 15 minutos</span><span class="sxs-lookup"><span data-stu-id="91697-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="91697-105">**Objetivo:** la característica catálogo de datos empresariales en Microsoft SharePoint Server expone e incorpora datos desde aplicaciones de línea de negocio (LOB) en los portales.</span><span class="sxs-lookup"><span data-stu-id="91697-105">**Objective:** The Business Data Catalog feature in Microsoft SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="91697-106">Para incorporar estos datos en el sitio del portal, debe crear un archivo de definición de aplicación que pueden usar Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="91697-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="91697-107">La herramienta Editor de definición de catálogo de datos empresariales, disponible con el SDK de Microsoft Office SharePoint Server 2007, permite crear un archivo de definición de aplicación para el catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="91697-107">The Business Data Catalog Definition Editor tool, available with Microsoft Office SharePoint Server 2007 SDK, enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="91697-108">Esta herramienta genera automáticamente un archivo XML para el archivo de definición, por lo que no es necesario crear manualmente el archivo en un documento XML editor.</span><span class="sxs-lookup"><span data-stu-id="91697-108">This tool automatically generates an XML file for the definition file, so you do not need to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="91697-109">El propósito de la aplicación de Microsoft Office SharePoint Server que se va a crear es:</span><span class="sxs-lookup"><span data-stu-id="91697-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to:</span></span>  
  
- <span data-ttu-id="91697-110">Consulta de un empleado en la tabla de interfaz MS_SAMPLE_EMPLOYEE mediante un elemento de Web de lista de datos de negocio se basa en un nombre de empleado.</span><span class="sxs-lookup"><span data-stu-id="91697-110">Query for an employee in the MS_SAMPLE_EMPLOYEE interface table using a Business Data List Web Part based on an employee name.</span></span>  
  
- <span data-ttu-id="91697-111">Realizar una búsqueda de texto completo de Microsoft Office SharePoint Server en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="91697-111">Perform a full-text search from Microsoft Office SharePoint Server on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
  <span data-ttu-id="91697-112">Para cada uno de estos requisitos, debe completar un conjunto de tareas en la herramienta Editor de definición de catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="91697-112">For each of these requirements, you must complete a set of tasks in the Business Data Catalog Definition Editor tool.</span></span> <span data-ttu-id="91697-113">Este tema proporciona instrucciones sobre cómo realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="91697-113">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="91697-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="91697-114">Prerequisites</span></span>  
  
-   <span data-ttu-id="91697-115">Asegúrese de que tiene el Editor de definición del catálogo de datos profesionales instalado como parte del SDK de Microsoft Office SharePoint Server 2007.</span><span class="sxs-lookup"><span data-stu-id="91697-115">Be sure that you have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="91697-116">Puede descargar el SDK desde [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130).</span><span class="sxs-lookup"><span data-stu-id="91697-116">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="91697-117">Publicar el servicio WCF, como se describe en [paso 1: usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="91697-117">Publish the WCF service as described in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span>  
  

  
##  <a name="Connect"></a> <span data-ttu-id="91697-118">Conectar con el servicio WCF LOB y crear entidad</span><span class="sxs-lookup"><span data-stu-id="91697-118">Connect to the WCF LOB Service and Create Entity</span></span>  
 <span data-ttu-id="91697-119">Debe conectarse al servicio WCF para extraer el lenguaje de descripción de servicios Web (WSDL) para el servicio.</span><span class="sxs-lookup"><span data-stu-id="91697-119">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="91697-120">Desde el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos.</span><span class="sxs-lookup"><span data-stu-id="91697-120">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="91697-121">Estos métodos se pueden usar para crear entidades.</span><span class="sxs-lookup"><span data-stu-id="91697-121">These methods can be used to create entities.</span></span> <span data-ttu-id="91697-122">Para este tutorial, se crea una entidad.</span><span class="sxs-lookup"><span data-stu-id="91697-122">For this tutorial, an entity is created.</span></span>  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="91697-123">Para conectarse al servicio WCF y crear entidades</span><span class="sxs-lookup"><span data-stu-id="91697-123">To connect to the WCF service and create entities</span></span>  
  
1.  <span data-ttu-id="91697-124">Inicie el Editor de definición del catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="91697-124">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="91697-125">En el **iniciar** menú, haga clic en **Editor de definición de catálogo de datos de Microsoft Business**.</span><span class="sxs-lookup"><span data-stu-id="91697-125">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="91697-126">En la barra de herramientas, haga clic en **Agregar sistema LOB**.</span><span class="sxs-lookup"><span data-stu-id="91697-126">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="91697-127">En la ventana Agregar sistema LOB, haga clic en **conectar al servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="91697-127">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="91697-128">En el **URL** cuadro, escriba la dirección URL del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="91697-128">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="91697-129">Para este tutorial, la dirección URL será:</span><span class="sxs-lookup"><span data-stu-id="91697-129">For this tutorial, the URL will be:</span></span>  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     <span data-ttu-id="91697-130">La dirección URL está disponible cuando se prueba si se publica correctamente, como se describe en el servicio WCF [paso 1: usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="91697-130">The URL is available when you test whether the WCF service is published successfully, as described in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="91697-131">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="91697-131">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="91697-132">Para ver las operaciones que seleccionó en el Asistente para desarrollo de servicio de adaptador de WCF, haga clic en el **Agregar método Web** ficha. Verá el siguiente método: **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="91697-132">To see the operations you selected in the WCF Adapter Service Development Wizard, click the **Add Web Method** tab. You will see the following method: **Select**.</span></span>  
  
7.  <span data-ttu-id="91697-133">Arrastre el **seleccione** métodos a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="91697-133">Drag the **Select** methods to the Design Surface.</span></span> <span data-ttu-id="91697-134">El método de arrastrar a la superficie de diseño, se crea una entidad y el método pasa a formar parte de la entidad.</span><span class="sxs-lookup"><span data-stu-id="91697-134">As you drag the method to the Design Surface, an entity is created, and the method becomes part of that entity.</span></span>  
  
     <span data-ttu-id="91697-135">![Agregar método Select a la superficie de diseño](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")</span><span class="sxs-lookup"><span data-stu-id="91697-135">![Add Select method to the Design Surface](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")</span></span>  
  
8.  <span data-ttu-id="91697-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-136">Click **OK**.</span></span>  
  
9. <span data-ttu-id="91697-137">En el **escriba el nombre para el sistema LOB** cuadro de diálogo, escriba un nombre en el **nombre del sistema de LOB** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-137">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="91697-138">En este ejemplo, llámelo **MS_SAMPLE_EMPLOYEE**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-138">For this example, call it **MS_SAMPLE_EMPLOYEE**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="91697-139">En el Editor datos profesionales catálogo definición, la entidad recién creada aparece como **Entity0**.</span><span class="sxs-lookup"><span data-stu-id="91697-139">In the Business Data Catalog Definition Editor, the newly created entity is listed as **Entity0**.</span></span> <span data-ttu-id="91697-140">Cambiar el nombre de la entidad a **empleado**.</span><span class="sxs-lookup"><span data-stu-id="91697-140">Rename the entity to **Employee**.</span></span> <span data-ttu-id="91697-141">Realice los pasos siguientes para cambiar el nombre de la entidad:</span><span class="sxs-lookup"><span data-stu-id="91697-141">Perform the following steps to rename the entity:</span></span>  
  
    1.  <span data-ttu-id="91697-142">Expanda el **MS_SAMPLE_EMPLOYEE** nodo y, a continuación, expanda el **entidades** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-142">Expand the **MS_SAMPLE_EMPLOYEE** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="91697-143">Seleccione el **Entity0** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-143">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="91697-144">En el panel Propiedades, escriba **empleado** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-144">In the Properties pane, type **Employee** in the **Name** box.</span></span>  
  
         <span data-ttu-id="91697-145">![Cambiar el nombre de la entidad](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")</span><span class="sxs-lookup"><span data-stu-id="91697-145">![Rename the entity](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")</span></span>  
  
##  <a name="Headers"></a> <span data-ttu-id="91697-146">Especifique el nombre de usuario y contraseña encabezados para los métodos</span><span class="sxs-lookup"><span data-stu-id="91697-146">Specify User Name and Password Headers for the Methods</span></span>  
 <span data-ttu-id="91697-147">Al crear un servicio WCF para la operación Select en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite, especifica los encabezados de nombre y la contraseña del usuario como parte de la configuración de comportamiento de punto de conexión en [paso 1: usar Oracle Adaptador de comercio electrónico para crear y publicar un servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="91697-147">When creating a WCF service for the Select operation on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite, you specified user name and password headers as part of the endpoint behavior configuration in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span> <span data-ttu-id="91697-148">Debe especificar los mismos valores para la propiedad método de selección.</span><span class="sxs-lookup"><span data-stu-id="91697-148">You must specify the same values for the Select method property.</span></span>  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a><span data-ttu-id="91697-149">Para especificar los encabezados de nombre y la contraseña de usuario para el método Select</span><span class="sxs-lookup"><span data-stu-id="91697-149">To specify user name and password headers for the Select method</span></span>  
  
1.  <span data-ttu-id="91697-150">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-150">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="91697-151">Haga clic en el **seleccione** nodo y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-151">Click the **Select** node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="91697-152">En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderUserName** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-152">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="91697-153">Tipo **MyUserHeader** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-153">Type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="91697-154">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-154">Select **System.String** for the **Type** box.</span></span>  
  
4.  <span data-ttu-id="91697-155">En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderPassword** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-155">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="91697-156">De forma similar, escriba **MyPasswordHeader** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-156">Similarly, type **MyPasswordHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="91697-157">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-157">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="91697-158">![Agregar una propiedad](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")</span><span class="sxs-lookup"><span data-stu-id="91697-158">![Add a property](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")</span></span>  
  
5.  <span data-ttu-id="91697-159">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-159">Click **OK**.</span></span>  
  
##  <a name="Scenario1"></a> <span data-ttu-id="91697-160">Escenario 1: Consulta de los empleados mediante un elemento Web de lista de datos de Business</span><span class="sxs-lookup"><span data-stu-id="91697-160">Scenario 1: Query for Employees using a Business Data List Web Part</span></span>  
 <span data-ttu-id="91697-161">Para crear un archivo de definición de aplicación que puede usarse para buscar los empleados de un elemento de Web de lista de datos de negocio y según el nombre de empleado, debe realizar el siguiente conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="91697-161">To create an application definition file that can be used to search for employees from a Business Data List Web Part and based on employee name, you must perform the following set of tasks.</span></span>  
  
1.  <span data-ttu-id="91697-162">En el **seleccione** método, cree un filtro y asignarlo a la **filtro** parámetro.</span><span class="sxs-lookup"><span data-stu-id="91697-162">In the **Select** method, create a filter and map it to the **FILTER** parameter.</span></span>  
  
2.  <span data-ttu-id="91697-163">Crear un **buscador** instancia de método para el **seleccione** método.</span><span class="sxs-lookup"><span data-stu-id="91697-163">Create a **Finder** method instance for the **Select** method.</span></span> <span data-ttu-id="91697-164">Un **buscador** método recupera una lista de registros basada en un filtro.</span><span class="sxs-lookup"><span data-stu-id="91697-164">A **Finder** method retrieves a list of records based on a filter.</span></span>  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a><span data-ttu-id="91697-165">Para crear un filtro y asignarla al parámetro de filtro</span><span class="sxs-lookup"><span data-stu-id="91697-165">To create a filter, and map it to the FILTER parameter</span></span>  
  
1.  <span data-ttu-id="91697-166">Crear un filtro.</span><span class="sxs-lookup"><span data-stu-id="91697-166">Create a filter.</span></span>  
  
    1.  <span data-ttu-id="91697-167">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-167">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="91697-168">Expanda el **seleccione** método, haga clic en **filtros**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="91697-168">Expand the **Select** method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="91697-169">![Agregar un filtro para el método SELECT](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")</span><span class="sxs-lookup"><span data-stu-id="91697-169">![Add a filter to the SELECT method](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")</span></span>  
  
    3.  <span data-ttu-id="91697-170">En el panel de propiedades para el **FilterType** propiedad, seleccione **es igual a**.</span><span class="sxs-lookup"><span data-stu-id="91697-170">In the Properties pane, for the **FilterType** property, select **Equals**.</span></span>  
  
    4.  <span data-ttu-id="91697-171">En el panel Propiedades, escriba **EmployeeName** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-171">In the Properties pane, type **EmployeeName** in the **Name** box.</span></span>  
  
         <span data-ttu-id="91697-172">![Especificar propiedades de filtro](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")</span><span class="sxs-lookup"><span data-stu-id="91697-172">![Specify filter properties](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")</span></span>  
  
2.  <span data-ttu-id="91697-173">Asignar el filtro para el **filtro** parámetro en el **seleccione** método.</span><span class="sxs-lookup"><span data-stu-id="91697-173">Map the filter to the **FILTER** parameter in the **Select** method.</span></span>  
  
    1.  <span data-ttu-id="91697-174">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-174">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="91697-175">Expanda el **seleccione** método y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-175">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="91697-176">Expanda el **filtro** nodo y haga clic en el segundo **filtro** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-176">Expand the **FILTER** node, and click the second **FILTER** node.</span></span>  
  
    4.  <span data-ttu-id="91697-177">En el panel Propiedades, seleccione **EmployeeName** desde el **FilterDescriptor** lista.</span><span class="sxs-lookup"><span data-stu-id="91697-177">In the Properties pane, select **EmployeeName** from the **FilterDescriptor** list.</span></span>  
  
         <span data-ttu-id="91697-178">![Asignar el filtro al parámetro del método Select](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")</span><span class="sxs-lookup"><span data-stu-id="91697-178">![Map the filter to the Select method parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")</span></span>  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a><span data-ttu-id="91697-179">Para crear una instancia de método de buscador para el método Select</span><span class="sxs-lookup"><span data-stu-id="91697-179">To create a Finder method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="91697-180">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-180">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="91697-181">Expanda el **seleccione** nodo, haga clic en **instancias**y, a continuación, haga clic en **Agregar instancia del método**.</span><span class="sxs-lookup"><span data-stu-id="91697-181">Expand the **Select** node, right-click **Instances**, and then click **Add Method Instance**.</span></span>  
  
     <span data-ttu-id="91697-182">![Agregar una instancia de método](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="91697-182">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="91697-183">En la ventana Crear instancia de método, haga clic en **buscador** para **tipo de método de instancia**.</span><span class="sxs-lookup"><span data-stu-id="91697-183">In the Create Method Instance window, click **Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="91697-184">Seleccione **devolver** para **devolver TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="91697-184">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="91697-185">![Crear una instancia de método de buscador](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="91697-185">![Create a Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")</span></span>  
  
4.  <span data-ttu-id="91697-186">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-186">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="91697-187">En el panel Propiedades, escriba **Finder_Instance** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-187">In the Properties pane, type **Finder_Instance** in the **Name** box.</span></span>  
  
     <span data-ttu-id="91697-188">![Especifique un nombre para la instancia de método de buscador](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")</span><span class="sxs-lookup"><span data-stu-id="91697-188">![Specify a name for the Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")</span></span>  
  
##  <a name="Scenario2"></a> <span data-ttu-id="91697-189">Escenario 2: Búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE desde Microsoft Office SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="91697-189">Scenario 2: Full-Text Search on MS_SAMPLE_EMPLOYEE Interface Table from Microsoft Office SharePoint Server</span></span>  
 <span data-ttu-id="91697-190">Para crear un archivo de definición de aplicación que puede usarse para realizar una búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE desde Microsoft Office SharePoint Server, debe realizar el siguiente conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="91697-190">To create an application definition file that can be used to perform a full-text search on MS_SAMPLE_EMPLOYEE interface table from Microsoft Office SharePoint Server, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="91697-191">En el **seleccione** método, crear un identificador y asignarlo a los parámetros de filtro y el valor devuelto que almacena el nombre del empleado.</span><span class="sxs-lookup"><span data-stu-id="91697-191">In the **Select** method, create an identifier, and map it to the FILTER parameter and the return value that stores the employee name.</span></span>  
  
-   <span data-ttu-id="91697-192">Crear un **buscador específico** instancia de método para el **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="91697-192">Create a **Specific Finder** method instance for the **Select**.</span></span> <span data-ttu-id="91697-193">El **buscador específico** método encontrará un registro específico en función del identificador, es decir, un nombre de empleado.</span><span class="sxs-lookup"><span data-stu-id="91697-193">The **Specific Finder** method will find a specific record based on the identifier, that is, an employee name.</span></span>  
  
-   <span data-ttu-id="91697-194">Cree una instancia de método de enumerador de identificador.</span><span class="sxs-lookup"><span data-stu-id="91697-194">Create an ID Enumerator method instance.</span></span>  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a><span data-ttu-id="91697-195">Para crear un identificador y asignarlo al valor de filtro empleado y de parámetro de nombre devuelto</span><span class="sxs-lookup"><span data-stu-id="91697-195">To create an identifier, and map it to the FILTER parameter and employee name return value</span></span>  
  
1.  <span data-ttu-id="91697-196">Crear un identificador de la **empleado** entidad.</span><span class="sxs-lookup"><span data-stu-id="91697-196">Create an identifier for the **Employee** entity.</span></span>  
  
    1.  <span data-ttu-id="91697-197">En el panel de objetos de metadatos, expanda el **empleado** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-197">In the Metadata Objects pane, expand the **Employee** node.</span></span>  
  
    2.  <span data-ttu-id="91697-198">Haga clic en el **identificadores** nodo y, a continuación, seleccione **Agregar identificador**.</span><span class="sxs-lookup"><span data-stu-id="91697-198">Right-click the **Identifiers** node, and then select **Add Identifier**.</span></span>  
  
         <span data-ttu-id="91697-199">![Crear un identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")</span><span class="sxs-lookup"><span data-stu-id="91697-199">![Create an Identifier](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")</span></span>  
  
    3.  <span data-ttu-id="91697-200">En el panel Propiedades, escriba **EmployeeName** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-200">In the Properties pane, type **EmployeeName** in the **Name** box.</span></span>  
  
    4.  <span data-ttu-id="91697-201">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-201">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="91697-202">![Especificar propiedades del identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")</span><span class="sxs-lookup"><span data-stu-id="91697-202">![Specify identifier properties](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")</span></span>  
  
2.  <span data-ttu-id="91697-203">Asignar el identificador para el parámetro de filtro para el **seleccione** método.</span><span class="sxs-lookup"><span data-stu-id="91697-203">Map the identifier to the FILTER parameter for the **Select** method.</span></span>  
  
    1.  <span data-ttu-id="91697-204">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-204">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="91697-205">Expanda el **seleccione** método y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-205">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="91697-206">Expanda el **filtro** parámetro y, a continuación, haga clic en el segundo **filtro** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-206">Expand the **FILTER** parameter, and then click the second **FILTER** node.</span></span>  
  
    4.  <span data-ttu-id="91697-207">En el panel Propiedades, seleccione **EmployeeName [Employee]** desde el **identificador** lista.</span><span class="sxs-lookup"><span data-stu-id="91697-207">In the Properties pane, select **EmployeeName[Employee]** from the **Identifier** list.</span></span>  
  
         <span data-ttu-id="91697-208">![Configurar el identificador para el parámetro FILTER](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")</span><span class="sxs-lookup"><span data-stu-id="91697-208">![Setting identifier for the FILTER parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")</span></span>  
  
3.  <span data-ttu-id="91697-209">Asignar el identificador para el valor devuelto del nombre de empleado.</span><span class="sxs-lookup"><span data-stu-id="91697-209">Map the identifier to the employee name return value.</span></span>  
  
    1.  <span data-ttu-id="91697-210">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-210">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="91697-211">Expanda el **seleccione** método y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-211">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="91697-212">Expanda el **devolver** nodo y, a continuación, el segundo **devolver** nodo, el **elemento** nodo y, a continuación, haga clic en el **nombre** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-212">Expand the **Return** node, then the second **Return** node, then the **Item** node, and then click the **Name** node.</span></span>  
  
    4.  <span data-ttu-id="91697-213">En el panel Propiedades, seleccione **EmployeeName [Employee]** desde el **identificador** lista.</span><span class="sxs-lookup"><span data-stu-id="91697-213">In the Properties pane, select **EmployeeName[Employee]** from the **Identifier** list.</span></span>  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a><span data-ttu-id="91697-214">Para crear una instancia de método de buscador específico para el método Select</span><span class="sxs-lookup"><span data-stu-id="91697-214">To create a Specific Finder method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="91697-215">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-215">In the Metadata Objects pane, expand the **Employee** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="91697-216">Expanda el **seleccione** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.</span><span class="sxs-lookup"><span data-stu-id="91697-216">Expand the **Select** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="91697-217">![Agregar una instancia de método](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="91697-217">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="91697-218">En la ventana Crear instancia de método, seleccione **buscador específico** para **tipo de método de instancia**.</span><span class="sxs-lookup"><span data-stu-id="91697-218">In the Create Method Instance window, select **Specific Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="91697-219">Seleccione **devolver** para **devolver TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="91697-219">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="91697-220">![Agregar una instancia de método de buscador específico](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")</span><span class="sxs-lookup"><span data-stu-id="91697-220">![Add a Specific Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")</span></span>  
  
4.  <span data-ttu-id="91697-221">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-221">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="91697-222">En el panel Propiedades, escriba **SpeciFinder_Instance** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-222">In the Properties pane, type **SpeciFinder_Instance** for the **Name** box.</span></span>  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a><span data-ttu-id="91697-223">Para crear una instancia de método de enumerador de identificador para el método Select</span><span class="sxs-lookup"><span data-stu-id="91697-223">To create an Id Enumerator method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="91697-224">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-224">In the Metadata Objects pane, expand the **Employee** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="91697-225">Expanda el **seleccione** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.</span><span class="sxs-lookup"><span data-stu-id="91697-225">Expand the **Select** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="91697-226">![Agregar una instancia de método](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="91697-226">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="91697-227">En la ventana Crear instancia de método, seleccione **enumerador de identificador** para **tipo de método de instancia**.</span><span class="sxs-lookup"><span data-stu-id="91697-227">In the Create Method Instance window, select **Id Enumerator** for **Method Instance Type**.</span></span> <span data-ttu-id="91697-228">Seleccione **devolver** para **devolver TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="91697-228">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="91697-229">![Cree una instancia de método de enumerador de identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")</span><span class="sxs-lookup"><span data-stu-id="91697-229">![Create an Id Enumerator method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")</span></span>  
  
4.  <span data-ttu-id="91697-230">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-230">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="91697-231">En el panel Propiedades, escriba **IDEnumerator_Instance** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-231">In the Properties pane, type **IDEnumerator_Instance** for the **Name** box.</span></span>  
  
##  <a name="Defaults"></a> <span data-ttu-id="91697-232">Establecer parámetros predeterminados para las instancias de método</span><span class="sxs-lookup"><span data-stu-id="91697-232">Set Default Parameters for the Method Instances</span></span>  
 <span data-ttu-id="91697-233">El método Select requiere que especifique los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="91697-233">The Select method requires you to specify the column names.</span></span> <span data-ttu-id="91697-234">Por lo tanto, debe especificar un valor predeterminado para el **COLUMN_NAMES** parámetro para las instancias de método de buscador de buscador específico y enumerador de Id. se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="91697-234">Therefore, you need to specify a default value for the **COLUMN_NAMES** parameter for the Finder, Specific Finder, and Id Enumerator method instances created earlier.</span></span> <span data-ttu-id="91697-235">Además, también debe especificar un valor predeterminado para el **filtro** parámetro para la instancia de método de enumerador de identificador.</span><span class="sxs-lookup"><span data-stu-id="91697-235">Additionally, you should also specify a default value for the **FILTER** parameter for the Id Enumerator method instance.</span></span>  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a><span data-ttu-id="91697-236">Para establecer los parámetros predeterminados para las instancias de método</span><span class="sxs-lookup"><span data-stu-id="91697-236">To set the default parameters for the method instances</span></span>  
  
1.  <span data-ttu-id="91697-237">En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-237">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="91697-238">Expanda el **seleccione** nodo y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-238">Expand the **Select** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="91697-239">Expanda el **COLUMN_NAMES** nodo y, a continuación, seleccione el **COLUMN_NAMES** parámetro.</span><span class="sxs-lookup"><span data-stu-id="91697-239">Expand the **COLUMN_NAMES** node, and then select the **COLUMN_NAMES** parameter.</span></span>  
  
4.  <span data-ttu-id="91697-240">En el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-240">In the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
5.  <span data-ttu-id="91697-241">En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **agregar**y haga clic en el panel de propiedades, **Finder_Instance** en el  **SelectMethodInstance** lista.</span><span class="sxs-lookup"><span data-stu-id="91697-241">In the **DefaultValueView Collection Editor** dialog box, click **Add**, and in the property pane, click **Finder_Instance** in the **SelectMethodInstance** list.</span></span>  
  
     <span data-ttu-id="91697-242">![Especifica el valor predeterminado para la instancia de buscador](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")</span><span class="sxs-lookup"><span data-stu-id="91697-242">![Specifying default value for the Finder instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")</span></span>  
  
6.  <span data-ttu-id="91697-243">Tipo `*` en el **valor** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-243">Type `*` in the **Value** box.</span></span>  
  
7.  <span data-ttu-id="91697-244">De forma similar, repita los pasos 5 y 6 para agregar los valores predeterminados para el **SpecificFinder_Instance** y **IDEnumerator_Instance** instancias de método.</span><span class="sxs-lookup"><span data-stu-id="91697-244">Similarly, repeat steps 5 and 6 to add default values for the **SpecificFinder_Instance** and **IDEnumerator_Instance** method instances.</span></span>  
  
8.  <span data-ttu-id="91697-245">En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-245">In the **DefaultValueView Collection Editor** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="91697-246">A continuación, agregue un valor predeterminado para el **filtro** parámetro para el **IDEnumerator_Instance** instancia de método.</span><span class="sxs-lookup"><span data-stu-id="91697-246">Next, add a default value for the **FILTER** parameter for the **IDEnumerator_Instance** method instance.</span></span> <span data-ttu-id="91697-247">Expanda el **filtro** nodo y, a continuación, seleccione el **filtro** parámetro.</span><span class="sxs-lookup"><span data-stu-id="91697-247">Expand the **FILTER** node, and then select the **FILTER** parameter.</span></span>  
  
10. <span data-ttu-id="91697-248">En el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-248">In the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
11. <span data-ttu-id="91697-249">En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **agregar**y haga clic en el panel de propiedades, **IDEnumerator_Instance** en el  **SelectMethodInstance** lista.</span><span class="sxs-lookup"><span data-stu-id="91697-249">In the **DefaultValueView Collection Editor** dialog box, click **Add**, and in the property pane, click **IDEnumerator_Instance** in the **SelectMethodInstance** list.</span></span>  
  
12. <span data-ttu-id="91697-250">Tipo `%` en el **valor** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-250">Type `%` in the **Value** box.</span></span>  
  
     <span data-ttu-id="91697-251">![Valores predeterminados para la instancia de enumerador de identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")</span><span class="sxs-lookup"><span data-stu-id="91697-251">![Default values for the Id Enumerator instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")</span></span>  
  
13. <span data-ttu-id="91697-252">En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-252">In the **DefaultValueView Collection Editor** dialog box, click **OK**.</span></span>  
  
##  <a name="SSO"></a> <span data-ttu-id="91697-253">Establecer la seguridad de Single Sign-On para conectarse a Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="91697-253">Set up Single Sign-On for Connecting to Oracle E-Business Suite</span></span>  
 <span data-ttu-id="91697-254">Cuando haya terminado de realizar todos los procedimientos de este tema, habrá creado un archivo de definición de aplicación que se puede importar a una aplicación de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="91697-254">After you have finished performing all the procedures in this topic, you will have created an application definition file that can be imported into a SharePoint application.</span></span> <span data-ttu-id="91697-255">Desde la aplicación, invoca los métodos para recuperar los datos pertinentes de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="91697-255">From the application, you invoke the methods to retrieve relevant data from Oracle E-Business Suite.</span></span> <span data-ttu-id="91697-256">Para habilitar esta opción, debe crear una asignación entre un usuario de Oracle E-Business Suite y el usuario en la aplicación de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="91697-256">To enable this, you must create a mapping between a user in the Oracle E-Business Suite and the user in the SharePoint application.</span></span> <span data-ttu-id="91697-257">Cree esta asignación en la consola de Administración Central de SharePoint después de importar el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="91697-257">You create this mapping in SharePoint Central Administration console after you have imported the application definition file.</span></span>  
  
 <span data-ttu-id="91697-258">Sin embargo, para crear la asignación, debe establecer una propiedad **SecondarySsoApplicationId** en el Editor de definición de catálogo de datos de Business.</span><span class="sxs-lookup"><span data-stu-id="91697-258">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="91697-259">Para establecer la propiedad SecondarySsoApplicationId</span><span class="sxs-lookup"><span data-stu-id="91697-259">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="91697-260">En el panel de objetos de metadatos, expanda el **MS_SAMPLE_EMPLOYEE** nodo y, a continuación, expanda el **instancias** nodo.</span><span class="sxs-lookup"><span data-stu-id="91697-260">In the Metadata Objects pane, expand the **MS_SAMPLE_EMPLOYEE** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="91697-261">Haga clic en **MS_SAMPLE_EMPLOYEE_Instance**y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-261">Click **MS_SAMPLE_EMPLOYEE_Instance**, and in the Properties pane, click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="91697-262">En el **Editor de la colección PropertyView** cuadro de diálogo, haga clic en **agregar**y en el panel de propiedades, escriba **SecondarySsoApplicationId** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-262">In the **PropertyView Collection Editor** dialog box, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** for the **Name** box.</span></span> <span data-ttu-id="91697-263">De forma similar, escriba **OracleSSO** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-263">Similarly, type **OracleSSO** for the **PropertyValue** box.</span></span> <span data-ttu-id="91697-264">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91697-264">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="91697-265">![Agregue la propiedad SSO](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")</span><span class="sxs-lookup"><span data-stu-id="91697-265">![Add the SSO Property](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")</span></span>  
  
4.  <span data-ttu-id="91697-266">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91697-266">Click **OK**.</span></span>  
  
##  <a name="Export"></a> <span data-ttu-id="91697-267">Exportar la definición de aplicación a un archivo</span><span class="sxs-lookup"><span data-stu-id="91697-267">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="91697-268">Ahora ha creado una definición de aplicación que contiene los metadatos de instancia de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="91697-268">You have now created an application definition that contains Oracle E-Business Suite instance metadata.</span></span> <span data-ttu-id="91697-269">Esta definición se debe exportar a un archivo XML, que puede importarse en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="91697-269">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
#### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="91697-270">Para exportar la definición de aplicación a un archivo</span><span class="sxs-lookup"><span data-stu-id="91697-270">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="91697-271">En el panel de objetos de metadatos, haga clic en el **MS_SAMPLE_EMPLOYEE** nodo y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="91697-271">In the Metadata Objects pane, right-click the **MS_SAMPLE_EMPLOYEE** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="91697-272">Guarde el archivo como empleado.Xml.</span><span class="sxs-lookup"><span data-stu-id="91697-272">Save the file as Employee.xml.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="91697-273">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="91697-273">Next Steps</span></span>  
 <span data-ttu-id="91697-274">Ahora debe crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="91697-274">You must now create a SharePoint application to retrieve data from Oracle E-Business Suite.</span></span> <span data-ttu-id="91697-275">Para obtener instrucciones, consulte [paso 3: crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span><span class="sxs-lookup"><span data-stu-id="91697-275">For instructions, see [Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91697-276">Vea también</span><span class="sxs-lookup"><span data-stu-id="91697-276">See Also</span></span>  
 [<span data-ttu-id="91697-277">Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="91697-277">Tutorial: Present Data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)