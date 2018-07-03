---
title: 'Paso 3: Crear un archivo de definición de aplicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 843fafdb-571e-4da4-ad04-7dc7f23e03ac
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7a5e2919a4cfed649342fda82435211b059206d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988221"
---
# <a name="step-3-create-an-application-definition-file"></a><span data-ttu-id="ca3f3-102">Paso 3: Crear un archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="ca3f3-102">Step 3: Create an Application Definition File</span></span>
<span data-ttu-id="ca3f3-103">![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="ca3f3-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="ca3f3-104">**Tiempo en completarse:** 15 minutos</span><span class="sxs-lookup"><span data-stu-id="ca3f3-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="ca3f3-105">La característica de catálogo de datos empresariales en Microsoft Office SharePoint Server expone e incorpora datos desde aplicaciones de línea de negocio (LOB) en los portales.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-105">The Business Data Catalog feature in Microsoft Office SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="ca3f3-106">Para incorporar estos datos en el sitio del portal, debe crear un archivo de definición de aplicación que pueden usar Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="ca3f3-107">En este paso, usará la herramienta Editor de definición de catálogo de datos empresariales, disponible con el SDK de Microsoft Office SharePoint Server 2007, para crear un archivo de definición de aplicación para el catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-107">In this step you use the Business Data Catalog Definition Editor tool, available with the Microsoft Office SharePoint Server 2007 SDK, to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="ca3f3-108">Este archivo de definición describe el método EchoGreetings del adaptador de Echo y se usará en pasos posteriores para habilitar SharePoint para establecer comunicación con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-108">This definition file describes the EchoGreetings method of the Echo adapter, and will be used in later steps to enable SharePoint to communicate with the adapter.</span></span>  
  
 <span data-ttu-id="ca3f3-109">El propósito de la aplicación de Microsoft Office SharePoint Server que se va a crear es para que pueda invocar el método EchoGreetings del adaptador de Echo y devolver la respuesta mediante un elemento Web de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to allow you to invoke the EchoGreetings method of the Echo adapter and return the response using a SharePoint Web Part.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca3f3-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ca3f3-110">Prerequisites</span></span>  
 <span data-ttu-id="ca3f3-111">Debe haber completado [paso 2: implementar el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md).</span><span class="sxs-lookup"><span data-stu-id="ca3f3-111">You should have completed [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md).</span></span> <span data-ttu-id="ca3f3-112">También debe tener acceso a Business Data Catalog definición Editor, que se instala como parte del SDK de Microsoft Office SharePoint Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-112">You must also have access to the Business Data Catalog Definition Editor, which is installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="ca3f3-113">Puede descargar el SDK desde [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130).</span><span class="sxs-lookup"><span data-stu-id="ca3f3-113">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="ca3f3-114">Creación de un archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="ca3f3-114">Creating an Application Definition File</span></span>  
 <span data-ttu-id="ca3f3-115">Este tema proporciona instrucciones paso a paso para crear un archivo de definición de aplicación para conectar el catálogo de datos profesionales de SharePoint con el adaptador de WCF hospedado en IIS.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-115">This topic provides step-by-step instructions to create an application definition file for connecting the SharePoint Business Data Catalog with the WCF adapter hosted in IIS.</span></span>  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a><span data-ttu-id="ca3f3-116">Para conectarse al servicio de adaptador WCF y crear entidades</span><span class="sxs-lookup"><span data-stu-id="ca3f3-116">To connect to the WCF adapter service and create entities</span></span>  
  
1.  <span data-ttu-id="ca3f3-117">Desde el **menú Inicio**, apunte a **todos los programas**y, a continuación, haga clic en **Editor de definición de catálogo de datos de Microsoft Business**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-117">From the **Start menu**, point to **All Programs**, and then click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="ca3f3-118">En la barra de herramientas, haga clic en **Agregar sistema LOB**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-118">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="ca3f3-119">En la ventana Agregar sistema LOB, haga clic en **conectar al servicio Web**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-119">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="ca3f3-120">En el **URL** cuadro, escriba la dirección URL del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-120">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="ca3f3-121">La dirección URL debe tener el formato siguiente: `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span><span class="sxs-lookup"><span data-stu-id="ca3f3-121">The URL must be in the following format: `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span></span>  
  
5.  <span data-ttu-id="ca3f3-122">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-122">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="ca3f3-123">Para ver las operaciones disponibles, haga clic en el **Agregar método Web** ficha. Debería ver el método EchoGreetings.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-123">To see the available operations, click the **Add Web Method** tab. You should see the EchoGreetings method.</span></span> <span data-ttu-id="ca3f3-124">Arrastre el método a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-124">Drag the method to the Design Surface.</span></span>  
  
7.  <span data-ttu-id="ca3f3-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-125">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="ca3f3-126">En el **escriba el nombre para el sistema LOB** cuadro de diálogo, escriba un nombre en el **nombre del sistema de LOB** cuadro.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-126">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="ca3f3-127">En este ejemplo, escriba **EchoWSLOB**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-127">For this example, enter **EchoWSLOB**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="ca3f3-128">Expanda el **EchoWSLob** nodo y, a continuación, expanda el **entidades** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-128">Expand the **EchoWSLob** node, and then expand the **Entities** node.</span></span> <span data-ttu-id="ca3f3-129">Seleccione **Entity0** y en el panel Propiedades, escriba **EchoGreetings** como el valor de la **nombre** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-129">Select **Entity0** and in the Properties pane type **EchoGreetings** as the value for the **Name** property.</span></span>  
  
     <span data-ttu-id="ca3f3-130">![Nombre de la entidad](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span><span class="sxs-lookup"><span data-stu-id="ca3f3-130">![Entity Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span></span>  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a><span data-ttu-id="ca3f3-131">Especifique el nombre de usuario y los encabezados de la contraseña para el método</span><span class="sxs-lookup"><span data-stu-id="ca3f3-131">Specify User Name and Password Headers for the Method</span></span>  
 <span data-ttu-id="ca3f3-132">Al llamar a un adaptador de WCF, es posible que deba proporcionar credenciales de usuario que se pasa al sistema de LOB.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-132">When calling a WCF adapter, you may have to provide user credentials that will be passed to the LOB system.</span></span> <span data-ttu-id="ca3f3-133">En [paso 1: usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md), configura el adaptador de Echo para requerir que se proporciona información de nombre y la contraseña de usuario en los campos MyUserHeader y MyPassHeader.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-133">In [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md), you configured the Echo adapter to require that user name and password information be provided in the MyUserHeader and MyPassHeader fields.</span></span> <span data-ttu-id="ca3f3-134">Ahora debe usar los mismos nombres de campo para este archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-134">You must now use the same field names for this application definition file.</span></span>  
  
#### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="ca3f3-135">Para especificar encabezados de nombre y la contraseña de usuario</span><span class="sxs-lookup"><span data-stu-id="ca3f3-135">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="ca3f3-136">En el panel de objetos de metadatos, expanda el **EchoGreetings** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-136">In the Metadata Objects pane, expand the **EchoGreetings** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="ca3f3-137">Haga clic en el **EchoGreetings** nodo y, en el panel Propiedades, haga clic en el botón de puntos suspensivos **(...)**  situado en la **propiedades** campo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-137">Click the **EchoGreetings** node and, in the Properties pane, click the ellipsis **(…)** button in the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="ca3f3-138">En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el **nombre** campo del panel de propiedades, tipo **HttpHeaderUserName**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-138">In the PropertyView Collection Editor window, click **Add**, and in the **Name** field of the Property pane, type  **HttpHeaderUserName**.</span></span>  
  
     <span data-ttu-id="ca3f3-139">![Especificar campos de encabezado de nombre de usuario](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span><span class="sxs-lookup"><span data-stu-id="ca3f3-139">![Specify Username Header Fields](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span></span>  
  
4.  <span data-ttu-id="ca3f3-140">En el **PropertyValue**, escriba **MyUserHeader**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-140">In the **PropertyValue**field, type **MyUserHeader**.</span></span>  
  
5.  <span data-ttu-id="ca3f3-141">Haga clic en **agregar**y en el tipo de panel propiedad **HttpHeaderPassword** para el campo nombre, a continuación, escriba **MyPassHeader** para el **PropertyValue**campo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-141">Click **Add**, and in the Property pane type **HttpHeaderPassword** for the Name field, then type **MyPassHeader** for the **PropertyValue** field.</span></span>  
  
6.  <span data-ttu-id="ca3f3-142">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-142">Click **OK**.</span></span>  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a><span data-ttu-id="ca3f3-143">Establecer seguridad Single Sign-On para conectar con el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="ca3f3-143">Set up Single Sign-On for Connecting to the Echo Adapter</span></span>  
 <span data-ttu-id="ca3f3-144">SharePoint utiliza información desde el inicio de sesión único para rellenar el MyUserHeader y MyPassHeader con los valores de autenticación.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-144">SharePoint uses information from Single Sign-On to populate the MyUserHeader and MyPassHeader with authentication values.</span></span> <span data-ttu-id="ca3f3-145">Para vincular este archivo de definición de aplicación para el inicio de sesión único, debe proporcionar un SecondarySsoApplicationId.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-145">To link this application definition file to Single Sign-On, you must provide a SecondarySsoApplicationId.</span></span>  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="ca3f3-146">Para establecer la propiedad SecondarySsoApplicationId</span><span class="sxs-lookup"><span data-stu-id="ca3f3-146">To set the SecondarySsoApplicationId property</span></span>  
  
1. <span data-ttu-id="ca3f3-147">En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **instancias** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-147">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Instances** node.</span></span>  
  
2. <span data-ttu-id="ca3f3-148">Haga clic en **EchoWSLOB_Instance**y en el panel Propiedades, haga clic en el botón de puntos suspensivos <strong>(...)</strong> situado en la **propiedades** campo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-148">Click **EchoWSLOB_Instance**, and in the Properties pane, click the ellipsis <strong>(…)</strong>button in the **Properties** field.</span></span>  
  
3. <span data-ttu-id="ca3f3-149">En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **SecondarySsoApplicationId** en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-149">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="ca3f3-150">En el **PropertyValue** , escriba **EchoSSO**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-150">In the **PropertyValue** field, type **EchoSSO**.</span></span>  
  
    <span data-ttu-id="ca3f3-151">![Establecer SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span><span class="sxs-lookup"><span data-stu-id="ca3f3-151">![Set the SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span></span>  
  
5. <span data-ttu-id="ca3f3-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-152">Click **OK**.</span></span>  
  
## <a name="create-input-filters-and-default-values"></a><span data-ttu-id="ca3f3-153">Crear filtros de entrada y los valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="ca3f3-153">Create Input Filters and Default Values</span></span>  
 <span data-ttu-id="ca3f3-154">El archivo de definición de aplicación debe ser capaz de aceptar entradas de usuario que se pueden pasar a un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-154">The application definition file must be able to  accept user input that can be passed to a Web service.</span></span> <span data-ttu-id="ca3f3-155">Para ello, debe realizar el siguiente conjunto de tareas:</span><span class="sxs-lookup"><span data-stu-id="ca3f3-155">To accomplish this, you must perform the following set of tasks:</span></span>  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a><span data-ttu-id="ca3f3-156">Para crear un filtro y asignarla al parámetro saludo</span><span class="sxs-lookup"><span data-stu-id="ca3f3-156">To create a filter, and map it to the greeting parameter</span></span>  
  
1.  <span data-ttu-id="ca3f3-157">En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-157">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="ca3f3-158">Expanda el **EchoGreetings** método, haga clic en **filtros**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-158">Expand the **EchoGreetings** method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
3.  <span data-ttu-id="ca3f3-159">En el panel Propiedades, escriba **saludo** en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-159">In the Properties pane, type **Greeting** in the **Name** field.</span></span>  
  
     <span data-ttu-id="ca3f3-160">![Establece el nombre del filtro](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span><span class="sxs-lookup"><span data-stu-id="ca3f3-160">![Set the Filter Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span></span>  
  
4.  <span data-ttu-id="ca3f3-161">En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo</span><span class="sxs-lookup"><span data-stu-id="ca3f3-161">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node</span></span>  
  
5.  <span data-ttu-id="ca3f3-162">Expanda el **EchoGreetings** método y, a continuación, expanda el **parámetros** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-162">Expand the **EchoGreetings** method, and then expand the **Parameters** node.</span></span>  
  
6.  <span data-ttu-id="ca3f3-163">Expanda el **saludo** nodo y, a continuación, expanda el segundo **saludo** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-163">Expand the **greeting** node, and then expand the second **greeting** node.</span></span>  
  
7.  <span data-ttu-id="ca3f3-164">Haga clic en el **greetingText** nodo y en el panel Propiedades, seleccione **saludo** desde el **FilterDescriptor** lista.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-164">Click the **greetingText** node, and in the Properties pane, select **Greeting** from the **FilterDescriptor** list.</span></span>  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a><span data-ttu-id="ca3f3-165">Para crear una instancia de método de buscador para el método EchoGreetings</span><span class="sxs-lookup"><span data-stu-id="ca3f3-165">To create a Finder method instance for the EchoGreetings method</span></span>  
  
1.  <span data-ttu-id="ca3f3-166">En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-166">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="ca3f3-167">Expanda el **EchoGreetings** método, haga clic en **instancias**y, a continuación, haga clic en **Agregar instancia del método** para abrir la ventana Crear instancia de método.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-167">Expand the **EchoGreetings** method, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
3.  <span data-ttu-id="ca3f3-168">En la ventana Crear instancia de método, haga clic en **buscador** para **tipo de método de instancia**y, a continuación, seleccione **devolver** para **TypeDescriptor de devolución**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-168">In the Create Method Instance window, click **Finder** for **Method Instance Type**, and then select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="ca3f3-169">![Crear la instancia de método](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span><span class="sxs-lookup"><span data-stu-id="ca3f3-169">![Create the Method Instance](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span></span>  
  
4.  <span data-ttu-id="ca3f3-170">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-170">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ca3f3-171">En el panel Propiedades, escriba **EchoGreetings_Instance** en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-171">In the Properties pane, type **EchoGreetings_Instance** in the **Name** field.</span></span>  
  
#### <a name="to-set-default-parameters"></a><span data-ttu-id="ca3f3-172">Para establecer los parámetros predeterminados</span><span class="sxs-lookup"><span data-stu-id="ca3f3-172">To set default parameters</span></span>  
  
1.  <span data-ttu-id="ca3f3-173">En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-173">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="ca3f3-174">Expanda el **EchoGreetings** método y, a continuación, expanda el **instancias** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-174">Expand the **EchoGreetings** method, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="ca3f3-175">Seleccione el **EchoGreetings_Instance** método de instancia y, en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** campo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-175">Select the **EchoGreetings_Instance** method instance, and in the Properties pane, click the ellipsis button (…) in the **DefaultValues** field.</span></span>  
  
4.  <span data-ttu-id="ca3f3-176">En la ventana de edición, expanda el **saludo** nodo y, a continuación, expanda el segundo **saludo** nodo.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-176">In the Edit window, expand the **greeting** node, and then expand the second **greeting** node.</span></span> <span data-ttu-id="ca3f3-177">Expanda el **nombre** nodo hasta que se muestre por completo la estructura de árbol.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-177">Expand the **name** node, until the tree structure is fully displayed.</span></span>  
  
5.  <span data-ttu-id="ca3f3-178">En la ventana de edición, establezca los valores de campo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ca3f3-178">In the Edit window, set the field values as follows:</span></span>  
  
    |<span data-ttu-id="ca3f3-179">Establezca</span><span class="sxs-lookup"><span data-stu-id="ca3f3-179">Set this</span></span>|<span data-ttu-id="ca3f3-180">A este</span><span class="sxs-lookup"><span data-stu-id="ca3f3-180">To this</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="ca3f3-181">**id**</span><span class="sxs-lookup"><span data-stu-id="ca3f3-181">**id**</span></span>|<span data-ttu-id="ca3f3-182">Un valor GUID, por ejemplo 27829ed4-583a - 40c 4-ad87-fb8cdd9dc98d.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-182">A GUID value, for example 27829ed4-583a-40c4-ad87-fb8cdd9dc98d.</span></span>|  
    |<span data-ttu-id="ca3f3-183">**sentDateTime**</span><span class="sxs-lookup"><span data-stu-id="ca3f3-183">**sentDateTime**</span></span>|<span data-ttu-id="ca3f3-184">La fecha y hora actuales, por ejemplo 05/15/08 9:12 A.M.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-184">The current date and time, for example 05/15/08 9:12 AM</span></span>|  
    |<span data-ttu-id="ca3f3-185">**firstName**</span><span class="sxs-lookup"><span data-stu-id="ca3f3-185">**firstName**</span></span>|<span data-ttu-id="ca3f3-186">Primero</span><span class="sxs-lookup"><span data-stu-id="ca3f3-186">First</span></span>|  
    |<span data-ttu-id="ca3f3-187">**middleName**</span><span class="sxs-lookup"><span data-stu-id="ca3f3-187">**middleName**</span></span>|<span data-ttu-id="ca3f3-188">Middle</span><span class="sxs-lookup"><span data-stu-id="ca3f3-188">Middle</span></span>|  
    |<span data-ttu-id="ca3f3-189">**Apellidos**</span><span class="sxs-lookup"><span data-stu-id="ca3f3-189">**lastName**</span></span>|<span data-ttu-id="ca3f3-190">Último</span><span class="sxs-lookup"><span data-stu-id="ca3f3-190">Last</span></span>|  
  
     <span data-ttu-id="ca3f3-191">![Parámetros predeterminados](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span><span class="sxs-lookup"><span data-stu-id="ca3f3-191">![Default Parameters](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span></span>  
  
6.  <span data-ttu-id="ca3f3-192">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-192">Click **Close**.</span></span>  
  
### <a name="to-export-the-application-definition-file"></a><span data-ttu-id="ca3f3-193">Para exportar el archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="ca3f3-193">To export the application definition file</span></span>  
  
1.  <span data-ttu-id="ca3f3-194">En el panel de objetos de metadatos, haga clic en el **EchoWSLOB** nodo y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-194">In the Metadata Objects pane, right-click the **EchoWSLOB** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="ca3f3-195">Guarde el archivo como EchoWS.xml.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-195">Save the file as EchoWS.xml.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="ca3f3-196">Síntesis</span><span class="sxs-lookup"><span data-stu-id="ca3f3-196">What did I just do?</span></span>  
 <span data-ttu-id="ca3f3-197">Ha usado la herramienta Editor de definición del catálogo de datos de negocio para crear un archivo de definición de aplicación que puede importarse en Microsoft Office SharePoint Server 2007 para habilitar la conectividad con el adaptador que se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-197">You have used the Business Data Catalog Definition Editor tool to create an application definition file that can be imported into Microsoft Office SharePoint Server 2007 to enable connectivity with your adapter that is hosted in IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ca3f3-198">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ca3f3-198">Next Steps</span></span>  
 <span data-ttu-id="ca3f3-199">Ahora debe crear una aplicación de SharePoint basada en el archivo de definición de la aplicación creado en este paso.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-199">You must now create a SharePoint application based on the application definition file created in this step.</span></span> <span data-ttu-id="ca3f3-200">Consulte [paso 4: crear una aplicación de Sharepoint para tener acceso al adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ca3f3-200">See [Step 4: Create a Sharepoint Application to Access the Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3f3-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca3f3-201">See Also</span></span>  
 [<span data-ttu-id="ca3f3-202">Tutorial 3: Hospedar el adaptador de Echo en IIS</span><span class="sxs-lookup"><span data-stu-id="ca3f3-202">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)