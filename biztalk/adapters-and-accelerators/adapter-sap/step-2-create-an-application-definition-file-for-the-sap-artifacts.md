---
title: 'Paso 2: Crear un archivo de definición de aplicación para los artefactos SAP | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d334b885b1135fb429655200090671a2a750ec0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219828"
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a><span data-ttu-id="bbd33-102">Paso 2: Crear un archivo de definición de aplicación para los artefactos SAP</span><span class="sxs-lookup"><span data-stu-id="bbd33-102">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>
<span data-ttu-id="bbd33-103">![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="bbd33-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="bbd33-104">**Tiempo en completarse:** 15 minutos</span><span class="sxs-lookup"><span data-stu-id="bbd33-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="bbd33-105">**Objetivo:** la característica de catálogo de datos profesionales en Microsoft SharePoint Server expone y datos de aplicaciones de línea de negocio (LOB) se incorpora en portales.</span><span class="sxs-lookup"><span data-stu-id="bbd33-105">**Objective:** The Business Data Catalog feature in Microsoft SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="bbd33-106">Para incorporar estos datos en el sitio del portal, debe generar un archivo de definición de aplicación que puede utilizar Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="bbd33-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="bbd33-107">La herramienta Editor de definición de catálogo de datos profesionales, disponible con el SDK de Microsoft Office SharePoint Server 2007, permite crear un archivo de definición de aplicación para el catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="bbd33-107">The Business Data Catalog Definition Editor tool, available with Microsoft Office SharePoint Server 2007 SDK,enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="bbd33-108">Esta herramienta genera automáticamente un archivo XML para el archivo de definición, por lo que no es necesario crear manualmente el archivo en un documento XML editor.</span><span class="sxs-lookup"><span data-stu-id="bbd33-108">This tool automatically generates an XML file for the definition file, so you do not need to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="bbd33-109">El propósito de la aplicación de Microsoft Office SharePoint Server que va a crear es:</span><span class="sxs-lookup"><span data-stu-id="bbd33-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to:</span></span>  
  
-   <span data-ttu-id="bbd33-110">Buscar un cliente en el sistema SAP basándose en un nombre de cliente.</span><span class="sxs-lookup"><span data-stu-id="bbd33-110">Search for a customer in the SAP system based on a customer name.</span></span>  
  
-   <span data-ttu-id="bbd33-111">Seleccione a un cliente de la lista de clientes capturadas y recuperar los detalles para el cliente.</span><span class="sxs-lookup"><span data-stu-id="bbd33-111">Select a customer from the list of fetched customers and retrieve the details for the customer.</span></span>  
  
-   <span data-ttu-id="bbd33-112">Seleccione a un cliente de la lista de clientes capturadas y recuperar los pedidos de venta para el cliente.</span><span class="sxs-lookup"><span data-stu-id="bbd33-112">Select a customer from the list of fetched customers and retrieve the sales orders for the customer.</span></span>  
  
 <span data-ttu-id="bbd33-113">Para cada uno de estos requisitos, debe completar un conjunto de tareas en la herramienta Editor de definición de catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="bbd33-113">For each of these requirements, you must complete a set of tasks in the Business Data Catalog Definition Editor tool.</span></span> <span data-ttu-id="bbd33-114">Este tema proporciona instrucciones sobre cómo realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="bbd33-114">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bbd33-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bbd33-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="bbd33-116">Asegúrese de que dispone el Editor de definición del catálogo de datos profesionales instalado como parte del SDK de Microsoft Office SharePoint Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bbd33-116">Be sure that you have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="bbd33-117">Puede descargar el SDK de [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span><span class="sxs-lookup"><span data-stu-id="bbd33-117">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="bbd33-118">Publicar el servicio WCF como se describe en [paso 1: publicar los artefactos de SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="bbd33-118">Publish the WCF service as described in [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="bbd33-119">Crear un archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="bbd33-119">Creating an Application Definition File</span></span>  
 <span data-ttu-id="bbd33-120">Este tema proporciona instrucciones paso a paso para crear un archivo de definición de aplicación para el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="bbd33-120">This topic provides step-by-step instructions to create an application definition file for the WCF service.</span></span>  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a><span data-ttu-id="bbd33-121">Conectar con el servicio LOB de WCF y crear entidades</span><span class="sxs-lookup"><span data-stu-id="bbd33-121">Connect to the WCF LOB Service, and Create Entities</span></span>  
 <span data-ttu-id="bbd33-122">Debe conectarse al servicio de WCF para extraer el lenguaje de descripción de servicios Web (WSDL) para el servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd33-122">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="bbd33-123">Desde el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos.</span><span class="sxs-lookup"><span data-stu-id="bbd33-123">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="bbd33-124">Estos métodos se pueden utilizar para crear entidades.</span><span class="sxs-lookup"><span data-stu-id="bbd33-124">These methods can be used to create entities.</span></span> <span data-ttu-id="bbd33-125">En este ejemplo, se crean dos entidades, uno para los clientes y pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="bbd33-125">For this example, two entities are created, one each for the customer and sales orders.</span></span>  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="bbd33-126">Para conectar con el servicio WCF y crear entidades</span><span class="sxs-lookup"><span data-stu-id="bbd33-126">To connect to the WCF service and create entities</span></span>  
  
1.  <span data-ttu-id="bbd33-127">Inicie el Editor de definición del catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="bbd33-127">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="bbd33-128">En el **iniciar** menú, haga clic en **Editor de definición de catálogo de datos de Microsoft Business**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-128">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="bbd33-129">En la barra de herramientas, haga clic en **Agregar sistema LOB**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-129">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="bbd33-130">En la ventana Agregar sistema de LOB, haga clic en **conectar al servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-130">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="bbd33-131">En el **URL** cuadro, escriba la dirección URL para el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="bbd33-131">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="bbd33-132">La dirección URL debe tener el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbd33-132">The URL must be in the following format:</span></span>  
  
    ```  
    https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
    ```  
  
     <span data-ttu-id="bbd33-133">donde Rfc.svc es el archivo creado para el contrato de Rfc.</span><span class="sxs-lookup"><span data-stu-id="bbd33-133">where Rfc.svc is the file created for the Rfc contract.</span></span>  
  
     <span data-ttu-id="bbd33-134">La dirección URL está disponible cuando se prueba si el servicio WCF se publica correctamente, tal como se describe en el tema [paso 1: publicar los artefactos de SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="bbd33-134">The URL is available when you test whether the WCF service is published successfully, as described in the topic [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="bbd33-135">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-135">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="bbd33-136">Para ver las operaciones que seleccionó en el Asistente de desarrollo del servicio de adaptador de WCF, haga clic en el **Agregar método Web** ficha. Verá los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbd33-136">To see the operations you selected in the WCF Adapter Service Development Wizard, click the **Add Web Method** tab. You will see the following methods:</span></span>  
  
    -   <span data-ttu-id="bbd33-137">SD_RFC_CUSTOMER_GET</span><span class="sxs-lookup"><span data-stu-id="bbd33-137">SD_RFC_CUSTOMER_GET</span></span>  
  
    -   <span data-ttu-id="bbd33-138">BAPI_SALESORDER_GETLIST</span><span class="sxs-lookup"><span data-stu-id="bbd33-138">BAPI_SALESORDER_GETLIST</span></span>  
  
         <span data-ttu-id="bbd33-139">![Agregar métodos web a la aplicación de BDC](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span><span class="sxs-lookup"><span data-stu-id="bbd33-139">![Add web methods to the BDC application](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span></span>  
  
     <span data-ttu-id="bbd33-140">Arrastre los métodos a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="bbd33-140">Drag the methods to the Design Surface.</span></span> <span data-ttu-id="bbd33-141">Asegúrese de que ambas operaciones de arrastre para las distintas entidades.</span><span class="sxs-lookup"><span data-stu-id="bbd33-141">Make sure you drag both operations to the different entities.</span></span>  
  
     <span data-ttu-id="bbd33-142">![Crear entidades para los métodos web](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span><span class="sxs-lookup"><span data-stu-id="bbd33-142">![Create entities for the web methods](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span></span>  
  
7.  <span data-ttu-id="bbd33-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="bbd33-144">En el **escriba el nombre para el sistema LOB** cuadro de diálogo, escriba un nombre en el **nombre de sistema de LOB** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-144">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="bbd33-145">En este ejemplo, llamarlo **Customer_Order**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-145">For this example, call it **Customer_Order**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="bbd33-146">En el Editor datos profesionales catálogo definición, las dos entidades aparecen como **Entity0** y **Entity1**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-146">In the Business Data Catalog Definition Editor, the two entities are listed as **Entity0** and **Entity1**.</span></span> <span data-ttu-id="bbd33-147">Asignar nombres descriptivos a estas entidades.</span><span class="sxs-lookup"><span data-stu-id="bbd33-147">Give these entities friendly names.</span></span> <span data-ttu-id="bbd33-148">Cambiar el nombre de la entidad para SD_RFC_CUSTOMER_GET a **cliente**y cambiar el nombre de la entidad para BAPI_SALESORDER_GETLIST a **SalesOrder**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-148">Rename the entity for SD_RFC_CUSTOMER_GET to **Customer**, and rename the entity for BAPI_SALESORDER_GETLIST to **SalesOrder**.</span></span> <span data-ttu-id="bbd33-149">Realice los pasos siguientes para cambiar el nombre de las entidades:</span><span class="sxs-lookup"><span data-stu-id="bbd33-149">Perform the following steps to rename the entities:</span></span>  
  
    1.  <span data-ttu-id="bbd33-150">Expanda el **Customer_Order** nodo y, a continuación, expanda el **entidades** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-150">Expand the **Customer_Order** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-151">Seleccione el **Entity0** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-151">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="bbd33-152">En el panel Propiedades, escriba **cliente** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-152">In the Properties pane, type **Customer** in the **Name** box.</span></span>  
  
         <span data-ttu-id="bbd33-153">![Cambiar el nombre de la entidad](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span><span class="sxs-lookup"><span data-stu-id="bbd33-153">![Rename the entity](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span></span>  
  
    4.  <span data-ttu-id="bbd33-154">Seleccione el **Entity1** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-154">Select the **Entity1** node.</span></span>  
  
    5.  <span data-ttu-id="bbd33-155">En el panel Propiedades, escriba **SalesOrder** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-155">In the Properties pane, type **SalesOrder** in the **Name** box.</span></span>  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a><span data-ttu-id="bbd33-156">Especifique el nombre de usuario y contraseña encabezados para los métodos</span><span class="sxs-lookup"><span data-stu-id="bbd33-156">Specify User Name and Password Headers for the Methods</span></span>  
 <span data-ttu-id="bbd33-157">Al crear un servicio WCF para los documentos de RFC seleccionados en el sistema SAP, especificar encabezados de nombre y la contraseña de usuario como parte de la configuración de comportamiento de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbd33-157">When creating a WCF service for the selected RFCs in the SAP system, you specified user name and password headers as part of the endpoint behavior configuration.</span></span> <span data-ttu-id="bbd33-158">Vea [paso 1: publicar los artefactos SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="bbd33-158">See [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span> <span data-ttu-id="bbd33-159">Debe especificar los mismos valores para las propiedades del método.</span><span class="sxs-lookup"><span data-stu-id="bbd33-159">You must specify the same values for the method properties.</span></span>  
  
##### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="bbd33-160">Para especificar encabezados de nombre y la contraseña de usuario</span><span class="sxs-lookup"><span data-stu-id="bbd33-160">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="bbd33-161">Agregue los encabezados de nombre y la contraseña de usuario para el método SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="bbd33-161">Add the user name and password headers for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="bbd33-162">En el panel de objetos de metadatos, expanda la **cliente** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-162">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-163">Haga clic en el nodo SD_RFC_CUSTOMER_GET y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-163">Click the SD_RFC_CUSTOMER_GET node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="bbd33-164">En la ventana del Editor de colección de PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderUserName** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-164">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="bbd33-165">De forma similar, escriba **MyUserHeader** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-165">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bbd33-166">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-166">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="bbd33-167">![Agregar una propiedad](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span><span class="sxs-lookup"><span data-stu-id="bbd33-167">![Add a property](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span></span>  
  
    4.  <span data-ttu-id="bbd33-168">En la ventana del Editor de colección de PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderPassword** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-168">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="bbd33-169">De forma similar, escriba **MyPassHeader** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-169">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bbd33-170">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-170">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="bbd33-171">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-171">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="bbd33-172">Agregue los encabezados de nombre y la contraseña de usuario para el método BAPI_SALESORDER_GETLIST.</span><span class="sxs-lookup"><span data-stu-id="bbd33-172">Add the user name and password headers for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
    1.  <span data-ttu-id="bbd33-173">En el panel de objetos de metadatos, expanda la **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-173">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-174">Haga clic en el nodo BAPI_SALESORDER_GETLIST y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-174">Click the BAPI_SALESORDER_GETLIST node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="bbd33-175">En la ventana del Editor de colección de PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderUserName** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-175">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="bbd33-176">De forma similar, escriba **MyUserHeader** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-176">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bbd33-177">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-177">Select **System.String** for the **Type** box.</span></span>  
  
    4.  <span data-ttu-id="bbd33-178">En la ventana del Editor de colección de PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderPassword** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-178">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="bbd33-179">De forma similar, escriba **MyPassHeader** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-179">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bbd33-180">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-180">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="bbd33-181">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-181">Click **OK**.</span></span>  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a><span data-ttu-id="bbd33-182">Establecer seguridad de inicio de sesión único para conectarse al sistema SAP</span><span class="sxs-lookup"><span data-stu-id="bbd33-182">Set up Single Sign-On for Connecting to the SAP System</span></span>  
 <span data-ttu-id="bbd33-183">Cuando haya terminado de realizar todos los procedimientos en este tema, habrá creado un archivo de definición de aplicación que se puede importar a una aplicación de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bbd33-183">After you have finished performing all the procedures in this topic, you will have created an application definition file that can be imported into a SharePoint application.</span></span> <span data-ttu-id="bbd33-184">Desde la aplicación, se invocación los métodos SAP para recuperar datos importantes desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="bbd33-184">From the application, you invoke the SAP methods to retrieve relevant data from the SAP system.</span></span> <span data-ttu-id="bbd33-185">Para habilitar esta opción, debe crear una asignación entre un usuario en el sistema SAP y el usuario en la aplicación de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bbd33-185">To enable this, you must create a mapping between a user in the SAP system and the user in the SharePoint application.</span></span> <span data-ttu-id="bbd33-186">Crear esta asignación en la consola de Administración Central de SharePoint después de haber importado el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bbd33-186">You create this mapping in SharePoint Central Administration console after you have imported the application definition file.</span></span>  
  
 <span data-ttu-id="bbd33-187">Sin embargo, para crear la asignación debe establecer una propiedad **SecondarySsoApplicationId** en el Editor de definición de catálogo de datos de Business.</span><span class="sxs-lookup"><span data-stu-id="bbd33-187">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="bbd33-188">Para establecer la propiedad SecondarySsoApplicationId</span><span class="sxs-lookup"><span data-stu-id="bbd33-188">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="bbd33-189">En el panel de objetos de metadatos, expanda la **Customer_Order** nodo y, a continuación, expanda el **instancias** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-189">In the Metadata Objects pane, expand the **Customer_Order** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="bbd33-190">Haga clic en **Customer_Order_Instance**y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-190">Click **Customer_Order_Instance**, and in the Properties pane, click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="bbd33-191">En la ventana del Editor de colección de PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **SecondarySsoApplicationId** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-191">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** for the **Name** box.</span></span> <span data-ttu-id="bbd33-192">De forma similar, escriba **SAPSSO** para el **PropertyValue** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-192">Similarly, type **SAPSSO** for the **PropertyValue** box.</span></span> <span data-ttu-id="bbd33-193">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-193">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="bbd33-194">![Agregar la propiedad SSO](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span><span class="sxs-lookup"><span data-stu-id="bbd33-194">![Add the SSO property](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span></span>  
  
4.  <span data-ttu-id="bbd33-195">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-195">Click **OK**.</span></span>  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a><span data-ttu-id="bbd33-196">Requisito 1: Buscar los clientes basándose en el nombre del cliente</span><span class="sxs-lookup"><span data-stu-id="bbd33-196">Requirement 1: Search for Customers Based on Customer Name</span></span>  
 <span data-ttu-id="bbd33-197">Para crear un archivo de definición de aplicación que puede usarse para buscar los clientes basándose en el nombre del cliente, debe realizar el siguiente conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="bbd33-197">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="bbd33-198">En el método SD_RFC_CUSTOMER_GET, cree un filtro y asignarla al parámetro que almacena el nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="bbd33-198">In the SD_RFC_CUSTOMER_GET method, create a filter and map it to the parameter that stores the customer name.</span></span>  
  
-   <span data-ttu-id="bbd33-199">Crear un **buscador** instancia de método para el método SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="bbd33-199">Create a **Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="bbd33-200">A **buscador** método recupera una lista de registros en función del filtro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-200">A **Finder** method retrieves a list of records based on a filter.</span></span>  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a><span data-ttu-id="bbd33-201">Para crear un filtro y asignarla al parámetro de nombre de cliente</span><span class="sxs-lookup"><span data-stu-id="bbd33-201">To create a filter, and map it to the customer name parameter</span></span>  
  
1.  <span data-ttu-id="bbd33-202">Crear un filtro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-202">Create a filter.</span></span>  
  
    1.  <span data-ttu-id="bbd33-203">En el panel de objetos de metadatos, expanda la **cliente** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-203">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-204">Expanda el método SD_RFC_CUSTOMER_GET, haga clic en **filtros**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-204">Expand the SD_RFC_CUSTOMER_GET method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="bbd33-205">![Agregar filtro a un método](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span><span class="sxs-lookup"><span data-stu-id="bbd33-205">![Add filter to a method](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span></span>  
  
    3.  <span data-ttu-id="bbd33-206">En el panel Propiedades, escriba **CustomerName** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-206">In the Properties pane, type **CustomerName** in the **Name** box.</span></span>  
  
         <span data-ttu-id="bbd33-207">![Especifique un nombre para el filtro](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span><span class="sxs-lookup"><span data-stu-id="bbd33-207">![Specify a name for the filter](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span></span>  
  
    4.  <span data-ttu-id="bbd33-208">Para el **FilterType** propiedad, seleccione **WildcardFilter**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-208">For the **FilterType** property, select **WildcardFilter**.</span></span>  
  
2.  <span data-ttu-id="bbd33-209">Asignar el filtro a la **nombre1** parámetro en el método SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="bbd33-209">Map the filter to the **NAME1** parameter in the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="bbd33-210">En el panel de objetos de metadatos, expanda la **cliente** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-210">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-211">Expanda el método SD_RFC_CUSTOMER_GET y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-211">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="bbd33-212">Expanda el **nombre1** nodo y haga clic en el segundo **nombre1** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-212">Expand the **NAME1** node, and click the second **NAME1** node.</span></span> <span data-ttu-id="bbd33-213">El **nombre1** parámetro contiene el nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="bbd33-213">The **NAME1** parameter contains the name of the customer.</span></span>  
  
    4.  <span data-ttu-id="bbd33-214">En el panel Propiedades, seleccione **CustomerName** desde el **FilterDescriptor** lista.</span><span class="sxs-lookup"><span data-stu-id="bbd33-214">In the Properties pane, select **CustomerName** from the **FilterDescriptor** list.</span></span>  
  
         <span data-ttu-id="bbd33-215">![El filtro se asignan a un parámetro de método](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span><span class="sxs-lookup"><span data-stu-id="bbd33-215">![Map the filter to a method parameter](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span></span>  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="bbd33-216">Para crear una instancia de método de buscador para el método SD_RFC_CUSTOMER_GET</span><span class="sxs-lookup"><span data-stu-id="bbd33-216">To create a Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="bbd33-217">En el panel de objetos de metadatos, expanda la **cliente** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-217">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bbd33-218">Expanda el **SD_RFC_CUSTOMER_GET** nodo, haga clic en **instancias**y, a continuación, haga clic en **Agregar instancia del método** para abrir la ventana Crear instancia de método.</span><span class="sxs-lookup"><span data-stu-id="bbd33-218">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="bbd33-219">![Agregar una instancia del método](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="bbd33-219">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="bbd33-220">En la ventana Crear instancia de método, haga clic en **buscador** para **tipo de método de instancia**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-220">In the Create Method Instance window, click **Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="bbd33-221">Seleccione **CUSTOMER_T** para **devolver TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-221">Select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="bbd33-222">![Agregar una instancia de método de buscador](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span><span class="sxs-lookup"><span data-stu-id="bbd33-222">![Add a Finder method instance](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span></span>  
  
4.  <span data-ttu-id="bbd33-223">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bbd33-224">En el panel Propiedades, escriba **GetCustomerByName_Instance** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-224">In the Properties pane, type **GetCustomerByName_Instance** in the **Name** box.</span></span>  
  
     <span data-ttu-id="bbd33-225">![Especifique un nombre para la instancia de método](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span><span class="sxs-lookup"><span data-stu-id="bbd33-225">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span></span>  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="bbd33-226">Requisito 2: Recuperar los detalles de un cliente específico de la lista de clientes</span><span class="sxs-lookup"><span data-stu-id="bbd33-226">Requirement 2: Retrieve Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="bbd33-227">Para crear un archivo de definición de aplicación que puede usarse para buscar los clientes basándose en el nombre del cliente, debe realizar el siguiente conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="bbd33-227">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="bbd33-228">En el método SD_RFC_CUSTOMER_GET, crear un identificador y asignarla al parámetro que almacena el número de cliente.</span><span class="sxs-lookup"><span data-stu-id="bbd33-228">In the SD_RFC_CUSTOMER_GET method, create an identifier, and map it to the parameter that stores the customer number.</span></span>  
  
-   <span data-ttu-id="bbd33-229">Crear un **método Finder específico** instancia de método para el método SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="bbd33-229">Create a **Specific Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="bbd33-230">A **método Finder específico** método encuentra un registro específico en función de un identificador.</span><span class="sxs-lookup"><span data-stu-id="bbd33-230">A **Specific Finder** method finds a specific record based on an identifier.</span></span>  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a><span data-ttu-id="bbd33-231">Para crear un identificador y asignarla al parámetro de número de cliente</span><span class="sxs-lookup"><span data-stu-id="bbd33-231">To create an identifier, and map it to the customer number parameter</span></span>  
  
1.  <span data-ttu-id="bbd33-232">Crear un identificador para el **cliente** entidad.</span><span class="sxs-lookup"><span data-stu-id="bbd33-232">Create an identifier for the **Customer** entity.</span></span>  
  
    1.  <span data-ttu-id="bbd33-233">En el panel de objetos de metadatos, expanda la **cliente** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-233">In the Metadata Objects pane, expand the **Customer** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-234">Haga clic en el **identificadores** nodo y, a continuación, seleccione **Agregar identificador**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-234">Right-click the **Identifiers** node, and then select **Add Identifier**.</span></span>  
  
         <span data-ttu-id="bbd33-235">![Agregar un identificador a un método](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span><span class="sxs-lookup"><span data-stu-id="bbd33-235">![Add an identifier to a method](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span></span>  
  
    3.  <span data-ttu-id="bbd33-236">En el panel Propiedades, escriba **CustomerID** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-236">In the Properties pane, type **CustomerID** in the **Name** box.</span></span>  
  
    4.  <span data-ttu-id="bbd33-237">Seleccione **System.String** para el **tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-237">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="bbd33-238">![Especifique un nombre para el identificador](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span><span class="sxs-lookup"><span data-stu-id="bbd33-238">![Specify a name for the identifier](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span></span>  
  
2.  <span data-ttu-id="bbd33-239">Asignar el identificador para el parámetro de clave para el método SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="bbd33-239">Map the identifier to the key parameter for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="bbd33-240">En el panel de objetos de metadatos, expanda la **cliente** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-240">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-241">Expanda el método SD_RFC_CUSTOMER_GET y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-241">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="bbd33-242">Expanda el **KUNNR** parámetro y, a continuación, haga clic en el segundo **KUNNR** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-242">Expand the **KUNNR** parameter, and then click the second **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="bbd33-243">En el panel Propiedades, seleccione **CustomerID [Customer]** desde el **identificador** lista.</span><span class="sxs-lookup"><span data-stu-id="bbd33-243">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
         <span data-ttu-id="bbd33-244">![Asignar el identificador a un parámetro](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span><span class="sxs-lookup"><span data-stu-id="bbd33-244">![Map the identifier to a parameter](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span></span>  
  
3.  <span data-ttu-id="bbd33-245">Configurar una asociación entre los parámetros de entrada y salidas.</span><span class="sxs-lookup"><span data-stu-id="bbd33-245">Set up an association between input and return parameters.</span></span>  
  
    1.  <span data-ttu-id="bbd33-246">En el panel de objetos de metadatos, expanda la **cliente** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-246">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bbd33-247">Expanda el método SD_RFC_CUSTOMER_GET y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-247">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="bbd33-248">Expanda el **CUSTOMER_T** nodo y, a continuación, el segundo **CUSTOMER_T** nodo, la **elemento** nodo y, a continuación, haga clic en el **KUNNR** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-248">Expand the **CUSTOMER_T** node, then the second **CUSTOMER_T** node, then the **Item** node, and then click the **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="bbd33-249">En el panel Propiedades, seleccione **CustomerID [Customer]** desde el **identificador** lista.</span><span class="sxs-lookup"><span data-stu-id="bbd33-249">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="bbd33-250">Para crear una instancia del método Finder específico para el método SD_RFC_CUSTOMER_GET</span><span class="sxs-lookup"><span data-stu-id="bbd33-250">To create a Specific Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="bbd33-251">En el panel de objetos de metadatos, expanda la **cliente** nodo y, a continuación, el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-251">In the Metadata Objects pane, expand the **Customer** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bbd33-252">Expanda el **SD_RFC_CUSTOMER_GET** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.</span><span class="sxs-lookup"><span data-stu-id="bbd33-252">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="bbd33-253">![Agregar una instancia del método](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="bbd33-253">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="bbd33-254">En la ventana Crear instancia de método, seleccione **método Finder específico** para **tipo de método de instancia**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-254">In the Create Method Instance window, select **Specific Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="bbd33-255">De forma similar, seleccione **CUSTOMER_T** para **devolver TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-255">Similarly, select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="bbd33-256">![Agregar una instancia del método Finder específico](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span><span class="sxs-lookup"><span data-stu-id="bbd33-256">![Add a Specific Finder Method Instance](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span></span>  
  
4.  <span data-ttu-id="bbd33-257">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-257">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bbd33-258">En el panel Propiedades, escriba **GetCustomerByNumber_Instance** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-258">In the Properties pane, type **GetCustomerByNumber_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="bbd33-259">![Especifique un nombre para la instancia de método](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span><span class="sxs-lookup"><span data-stu-id="bbd33-259">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span></span>  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="bbd33-260">Requisito 3: Recuperar los detalles de pedido de ventas para un cliente específico de la lista de clientes</span><span class="sxs-lookup"><span data-stu-id="bbd33-260">Requirement 3: Retrieve Sales Order Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="bbd33-261">Para crear un archivo de definición de aplicación que puede usarse para recuperar los detalles de pedido de ventas para un cliente específico, debe realizar el siguiente conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="bbd33-261">To create an application definition file that can be used to retrieve sales order details for a specific customer, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="bbd33-262">Configurar una asociación entre el **cliente** y **SalesOrder** entidades.</span><span class="sxs-lookup"><span data-stu-id="bbd33-262">Set up an association between the **Customer** and **SalesOrder** entities.</span></span>  
  
-   <span data-ttu-id="bbd33-263">Crear un **asociación** método para el método BAPI_SALESORDER_GETLIST.</span><span class="sxs-lookup"><span data-stu-id="bbd33-263">Create an **Association** method for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a><span data-ttu-id="bbd33-264">Para crear una asociación entre las entidades Customer y SalesOrder</span><span class="sxs-lookup"><span data-stu-id="bbd33-264">To create an association between the Customer and SalesOrder entities</span></span>  
  
1.  <span data-ttu-id="bbd33-265">En el panel de objetos de metadatos, expanda la **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-265">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bbd33-266">Expanda el método BAPI_SALESORDER_GETLIST y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-266">Expand the BAPI_SALESORDER_GETLIST method, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="bbd33-267">Expanda el **CUSTOMER_NUMBER** nodo y, a continuación, haga clic en el segundo **CUSTOMER_NUMBER** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-267">Expand the **CUSTOMER_NUMBER** node, and then click the second **CUSTOMER_NUMBER** node.</span></span>  
  
4.  <span data-ttu-id="bbd33-268">En el panel Propiedades, seleccione **CustomerID [Customer]** desde el **identificador** lista.</span><span class="sxs-lookup"><span data-stu-id="bbd33-268">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
     <span data-ttu-id="bbd33-269">![Crear asociación entre las dos entidades](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span><span class="sxs-lookup"><span data-stu-id="bbd33-269">![Create association between the two entities](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span></span>  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a><span data-ttu-id="bbd33-270">Para crear una instancia de método de asociación para el método BAPI_SALESORDER_GETLIST</span><span class="sxs-lookup"><span data-stu-id="bbd33-270">To create an Association method instance for the BAPI_SALESORDER_GETLIST method</span></span>  
  
1.  <span data-ttu-id="bbd33-271">En el panel de objetos de metadatos, expanda la **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-271">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bbd33-272">Expanda el **BAPI_SALESORDER_GETLIST** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.</span><span class="sxs-lookup"><span data-stu-id="bbd33-272">Expand the **BAPI_SALESORDER_GETLIST** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="bbd33-273">![Debe agregar una instancia de método de asociación](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span><span class="sxs-lookup"><span data-stu-id="bbd33-273">![Add an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span></span>  
  
3.  <span data-ttu-id="bbd33-274">En la ventana Crear instancia de método, seleccione **asociación** para **tipo de método de instancia**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-274">In the Create Method Instance window, select **Association** for **Method Instance Type**.</span></span>  
  
4.  <span data-ttu-id="bbd33-275">En el **entidades de origen** lista, seleccione **cliente**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-275">In the **Source Entities** list, select **Customer**.</span></span>  
  
5.  <span data-ttu-id="bbd33-276">En el **devolver TypeDescriptor** lista, seleccione **SALES_ORDERS**...</span><span class="sxs-lookup"><span data-stu-id="bbd33-276">In the **Return TypeDescriptor** list, select **SALES_ORDERS**..</span></span>  
  
     <span data-ttu-id="bbd33-277">![Cree una instancia de método de asociación](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span><span class="sxs-lookup"><span data-stu-id="bbd33-277">![Create an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span></span>  
  
6.  <span data-ttu-id="bbd33-278">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-278">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="bbd33-279">En el panel Propiedades, escriba **SalesOrderForCustomer_Instance** para el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-279">In the Properties pane, type **SalesOrderForCustomer_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="bbd33-280">![Especifique un nombre para el método de asociación](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span><span class="sxs-lookup"><span data-stu-id="bbd33-280">![Specify a name for the Association Method](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span></span>  
  
### <a name="remove-parameters-of-systemnullable-type"></a><span data-ttu-id="bbd33-281">Quite los parámetros de tipo System.Nullable</span><span class="sxs-lookup"><span data-stu-id="bbd33-281">Remove Parameters of System.Nullable Type</span></span>  
 <span data-ttu-id="bbd33-282">Al crear el **asociación** instancia de método para el método BAPI_SALESORDER_GETLIST, ha seleccionado el tipo de valor devuelto como SALES_ORDERS.</span><span class="sxs-lookup"><span data-stu-id="bbd33-282">While creating the **Association** method instance for the BAPI_SALESORDER_GETLIST method, you selected the return type as SALES_ORDERS.</span></span> <span data-ttu-id="bbd33-283">Si expande el parámetro SALES_ORDER, observará que algunos parámetros son de tipo System. Nullable.</span><span class="sxs-lookup"><span data-stu-id="bbd33-283">If you expand the SALES_ORDER parameter, you will notice some parameters are of System.Nullable type.</span></span> <span data-ttu-id="bbd33-284">Puede ver que el parámetro de tipo, seleccione el parámetro en el Editor de definición de catálogo de datos de Business y examinando el valor de la **TypeName** propiedad.</span><span class="sxs-lookup"><span data-stu-id="bbd33-284">You can see the parameter type by selecting the parameter in the Business Data Catalog Definition Editor, and looking at the value for the **TypeName** property.</span></span>  
  
 <span data-ttu-id="bbd33-285">Para estos parámetros, el Editor de definición del catálogo de datos profesionales crea otro parámetro con el mismo nombre pero con un sufijo "Specified".</span><span class="sxs-lookup"><span data-stu-id="bbd33-285">For such parameters, the Business Data Catalog Definition Editor creates another parameter with the same name but with a “Specified” suffix.</span></span> <span data-ttu-id="bbd33-286">Por ejemplo, mirar parámetros *ITM_NUMBER* y *ITM_NUMBERSpecified*.</span><span class="sxs-lookup"><span data-stu-id="bbd33-286">For example, look at parameters *ITM_NUMBER* and *ITM_NUMBERSpecified*.</span></span> <span data-ttu-id="bbd33-287">Microsoft Office SharePoint Server no admite parámetros de System. Nullable.</span><span class="sxs-lookup"><span data-stu-id="bbd33-287">Microsoft Office SharePoint Server does not support System.Nullable parameters.</span></span> <span data-ttu-id="bbd33-288">Por lo tanto, cuando intente registros que contienen el tipo de parámetro System.Nullable, produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="bbd33-288">So, when you try records that contain the System.Nullable parameter type, it throws an exception.</span></span> <span data-ttu-id="bbd33-289">Por lo tanto, debe quitar los parámetros (con y sin el sufijo "Specified" y tener el mismo nombre) desde el Editor de definición de catálogo de datos de Business</span><span class="sxs-lookup"><span data-stu-id="bbd33-289">Therefore, you must remove both the parameters (with and without the “Specified” suffix and having the same name) from the Business Data Catalog Definition Editor</span></span>  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a><span data-ttu-id="bbd33-290">Para quitar los parámetros de tipo System.Nullable</span><span class="sxs-lookup"><span data-stu-id="bbd33-290">To remove the parameters of System.Nullable type</span></span>  
  
1.  <span data-ttu-id="bbd33-291">En el panel de objetos de metadatos, expanda la **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-291">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bbd33-292">Expanda el **BAPI_SALESORDER_GETLIST** nodo y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-292">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="bbd33-293">Expanda **SALES_ORDERS**, expanda la segunda **SALES_ORDERS**y, a continuación, expanda **elemento**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-293">Expand **SALES_ORDERS**, expand the second **SALES_ORDERS**, and then expand **Item**.</span></span>  
  
4.  <span data-ttu-id="bbd33-294">Haga clic en el parámetro que contiene el sufijo "Specified" en el nombre y, a continuación, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-294">Right-click the parameter that contains the "Specified" suffix in the name, and then select **Delete**.</span></span>  
  
5.  <span data-ttu-id="bbd33-295">Haga clic en el parámetro que tiene el mismo nombre que el parámetro que se ha eliminado, sin el sufijo, y, a continuación, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-295">Right-click the parameter that has the same name as the parameter you deleted, without the suffix, and then select **Delete**.</span></span> <span data-ttu-id="bbd33-296">Normalmente, este parámetro es correcta antes del parámetro que tiene el sufijo "Specified".</span><span class="sxs-lookup"><span data-stu-id="bbd33-296">Typically, this parameter is right before the parameter that has the "Specified" suffix.</span></span>  
  
### <a name="set-default-parameters"></a><span data-ttu-id="bbd33-297">Establecer parámetros predeterminados</span><span class="sxs-lookup"><span data-stu-id="bbd33-297">Set Default Parameters</span></span>  
 <span data-ttu-id="bbd33-298">El BAPI_SALESORDER_GETLIST toma dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="bbd33-298">The BAPI_SALESORDER_GETLIST takes two parameters.</span></span> <span data-ttu-id="bbd33-299">Uno de estos parámetros, TRANSACTION_GROUP, es el parámetro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bbd33-299">One of these parameters, TRANSACTION_GROUP, is the default parameter.</span></span> <span data-ttu-id="bbd33-300">Por lo tanto, debe establecer el valor predeterminado para este parámetro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-300">So, you must set the default value for this parameter.</span></span>  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a><span data-ttu-id="bbd33-301">Para establecer el valor predeterminado para TRANSACTION_GROUP</span><span class="sxs-lookup"><span data-stu-id="bbd33-301">To set the default value for TRANSACTION_GROUP</span></span>  
  
1.  <span data-ttu-id="bbd33-302">En el panel de objetos de metadatos, expanda la **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-302">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bbd33-303">Expanda el **BAPI_SALESORDER_GETLIST** nodo y, a continuación, expanda el **instancias** nodo.</span><span class="sxs-lookup"><span data-stu-id="bbd33-303">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="bbd33-304">Seleccione el **SalesOrderForCustomer_Instance** método de instancia y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbd33-304">Select the **SalesOrderForCustomer_Instance** method instance, and in the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
4.  <span data-ttu-id="bbd33-305">En la ventana de edición, expanda **TRANSACTION_GROUP** nodo y para la **TRANSACTION_GROUP** , especifique el valor predeterminado 0.</span><span class="sxs-lookup"><span data-stu-id="bbd33-305">In the Edit window, expand **TRANSACTION_GROUP** node, and for the **TRANSACTION_GROUP** box, specify the default value 0.</span></span>  
  
     <span data-ttu-id="bbd33-306">![Especifique un valor predeterminado para la instancia de método](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span><span class="sxs-lookup"><span data-stu-id="bbd33-306">![Specify a default value for the method instance](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span></span>  
  
5.  <span data-ttu-id="bbd33-307">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-307">Click **Close**.</span></span>  
  
### <a name="export-the-application-definition-to-a-file"></a><span data-ttu-id="bbd33-308">Exportar la definición de aplicación a un archivo</span><span class="sxs-lookup"><span data-stu-id="bbd33-308">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="bbd33-309">Ahora ha creado una definición de aplicación que contiene los metadatos de instancia de sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="bbd33-309">You have now created an application definition that contains the SAP system instance metadata.</span></span> <span data-ttu-id="bbd33-310">Debe exportar esta definición en un archivo XML, que puede importarse en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="bbd33-310">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
##### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="bbd33-311">Para exportar la definición de aplicación a un archivo</span><span class="sxs-lookup"><span data-stu-id="bbd33-311">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="bbd33-312">En el panel de objetos de metadatos, haga clic en el **Customer_Order** nodo y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="bbd33-312">In the Metadata Objects pane, right-click the **Customer_Order** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="bbd33-313">Guarde el archivo como Customer_Order.xml.</span><span class="sxs-lookup"><span data-stu-id="bbd33-313">Save the file as Customer_Order.xml.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bbd33-314">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bbd33-314">Next Steps</span></span>  
 <span data-ttu-id="bbd33-315">Ahora debe crear una aplicación de SharePoint para recuperar datos de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="bbd33-315">You must now create a SharePoint application to retrieve data from an SAP system.</span></span> <span data-ttu-id="bbd33-316">Vea [paso 3: crear una aplicación de SharePoint para recuperar datos de SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="bbd33-316">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd33-317">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbd33-317">See Also</span></span>  
 [<span data-ttu-id="bbd33-318">Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="bbd33-318">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)