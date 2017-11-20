---
title: 'Paso 2: Probar el controlador de entrada del adaptador de eco | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dede9b-6b7e-4901-9c79-b75bfee9155f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73c2c7c97777df8c0875a1735899d9eb739572cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-test-inbound-handler-of-the-echo-adapter"></a><span data-ttu-id="650a4-102">Paso 2: Probar el controlador de entrada del adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="650a4-102">Step 2: Test Inbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="650a4-103">![Paso 2 de 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="650a4-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="650a4-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="650a4-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="650a4-105">En este paso, pruebe el servicio de entrada proporcionado por el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="650a4-105">In this step, you test the inbound service provided by the Echo Adapter.</span></span> <span data-ttu-id="650a4-106">Para ello, mediante Visual Studio, agregar adaptador de servicio de referencia de complemento de Visual Studio y código personalizado.</span><span class="sxs-lookup"><span data-stu-id="650a4-106">You do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="650a4-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="650a4-107">Prerequisites</span></span>  
 <span data-ttu-id="650a4-108">Para completar este paso, debe haber completado [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="650a4-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="650a4-109">Este paso se puede realizar independientemente de [paso 1: controlador de salida de prueba del adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="650a4-109">This step can be completed independent of [Step 1: Test Outbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="650a4-110">Crear un proyecto de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="650a4-110">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="650a4-111">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="650a4-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="650a4-112">En Visual Studio, en el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="650a4-112">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="650a4-113">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="650a4-113">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="650a4-114">Use</span><span class="sxs-lookup"><span data-stu-id="650a4-114">Use this</span></span>|<span data-ttu-id="650a4-115">Para</span><span class="sxs-lookup"><span data-stu-id="650a4-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="650a4-116">**Tipos de proyecto**</span><span class="sxs-lookup"><span data-stu-id="650a4-116">**Project types**</span></span>|<span data-ttu-id="650a4-117">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="650a4-117">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="650a4-118">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="650a4-118">**Templates**</span></span>|<span data-ttu-id="650a4-119">Haga clic en **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="650a4-119">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="650a4-120">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="650a4-120">**Name**</span></span>|<span data-ttu-id="650a4-121">Tipo de **ConsumeEchoAdapter_Inbound**.</span><span class="sxs-lookup"><span data-stu-id="650a4-121">Type **ConsumeEchoAdapter_Inbound**.</span></span>|  
    |<span data-ttu-id="650a4-122">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="650a4-122">**Location**</span></span>|<span data-ttu-id="650a4-123">Tipo de **C:\Tutorials**.</span><span class="sxs-lookup"><span data-stu-id="650a4-123">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="650a4-124">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="650a4-124">**Solution Name**</span></span>|<span data-ttu-id="650a4-125">Tipo de **ConsumeEchoAdapter_Inbound**.</span><span class="sxs-lookup"><span data-stu-id="650a4-125">Type **ConsumeEchoAdapter_Inbound**.</span></span>|  
  
4.  <span data-ttu-id="650a4-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="650a4-126">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="650a4-127">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="650a4-127">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-service"></a><span data-ttu-id="650a4-128">Examinar, buscar y generar el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="650a4-128">Browse, search, and generate the WCF service</span></span>  
  
1.  <span data-ttu-id="650a4-129">En el panel de la solución de Visual Studio, haga clic en **ConsumeEchoAdapter_Inbound** del proyecto y luego elija **Agregar referencia de servicio de adaptador** para iniciar el complemento de agregar Adapter Service Reference.</span><span class="sxs-lookup"><span data-stu-id="650a4-129">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Inbound** project then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="650a4-130">En el **Agregar referencia de servicio de adaptador** , elija un enlace.</span><span class="sxs-lookup"><span data-stu-id="650a4-130">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="650a4-131">Para ello, elija **echoAdapterBindingV2**.</span><span class="sxs-lookup"><span data-stu-id="650a4-131">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="650a4-132">A continuación, configure las propiedades de conexión y adaptador, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="650a4-132">Next, configure the adapter and connection properties by clicking **Configure**.</span></span>  <span data-ttu-id="650a4-133">Se abrirá la **configurar el adaptador** pantalla.</span><span class="sxs-lookup"><span data-stu-id="650a4-133">This opens the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="650a4-134">En el **configurar el adaptador** pantalla, seleccione la **propiedades de enlace** ficha para configurar las propiedades del adaptador.</span><span class="sxs-lookup"><span data-stu-id="650a4-134">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="650a4-135">Tenga en cuenta que las categorías de eco adaptador personalizadas **entrada** y **varios** se muestran.</span><span class="sxs-lookup"><span data-stu-id="650a4-135">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="650a4-136">En el **varios** categoría, haga clic en **InboundFileSystemWatcherFolder** y, a continuación, escriba el directorio que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="650a4-136">Under the **Misc** category, click **InboundFileSystemWatcherFolder** and then enter the directory you want to monitor.</span></span>  
  
5.  <span data-ttu-id="650a4-137">Haga clic en **Aceptar** para cerrar el **configurar el adaptador** pantalla y volver a la **Agregar referencia de servicio de adaptador** pantalla.</span><span class="sxs-lookup"><span data-stu-id="650a4-137">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
6.  <span data-ttu-id="650a4-138">A continuación, haga clic en **conectar** para conectar con el adaptador de eco (y el sistema de línea de negocio hipotético admite).</span><span class="sxs-lookup"><span data-stu-id="650a4-138">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="650a4-139">Transcurridos unos instantes, debería cambiar el estado de la conexión a **conectado** y el árbol de categorías (en **seleccione una categoría**) se debe rellenar.</span><span class="sxs-lookup"><span data-stu-id="650a4-139">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
7.  <span data-ttu-id="650a4-140">Para ver las operaciones de entrada disponibles, cambie la **tipo de contrato de servicio** a **(operaciones de entrada) de servicio**.</span><span class="sxs-lookup"><span data-stu-id="650a4-140">To view available inbound operations, change the **Service contract type** to **Service (Inbound operations)**.</span></span>  
  
8.  <span data-ttu-id="650a4-141">En el árbol de categorías, haga clic en **categoría principal**.</span><span class="sxs-lookup"><span data-stu-id="650a4-141">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="650a4-142">Esto rellenará la lista de categorías y operaciones con una sola operación de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="650a4-142">This populates the list of available categories and operations with a single inbound operation.</span></span> <span data-ttu-id="650a4-143">No hay ninguna categoría.</span><span class="sxs-lookup"><span data-stu-id="650a4-143">There are no categories.</span></span>  
  
9. <span data-ttu-id="650a4-144">En el **categorías y operaciones disponibles**, seleccione la **OnReceiveEcho** operación.</span><span class="sxs-lookup"><span data-stu-id="650a4-144">In the **Available Categories and Operations**, select the **OnReceiveEcho** operation.</span></span> <span data-ttu-id="650a4-145">Haga clic en **agregar** para realizar la parte de operaciones seleccionadas de la interfaz WCF generada.</span><span class="sxs-lookup"><span data-stu-id="650a4-145">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="650a4-146">Haga clic en **Aceptar** para generar la interfaz WCF.</span><span class="sxs-lookup"><span data-stu-id="650a4-146">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="650a4-147">Esto agrega un archivo de configuración de aplicación (app.config), una interfaz WCF (EchoAdapterBindingInterface.cs) y un servicio WCF (EchoAdapterBindingService.cs) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="650a4-147">This adds an application configuration file (app.config), a WCF interface (EchoAdapterBindingInterface.cs) and a WCF service (EchoAdapterBindingService.cs) to the project.</span></span>  
  
11. <span data-ttu-id="650a4-148">Haga clic en **archivo** en el **Visual Studio** menú y elija **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="650a4-148">Click **File** on the **Visual Studio** menu and choose **Save All**.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="650a4-149">Probar el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="650a4-149">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="650a4-150">En el Explorador de soluciones, haga doble clic en el **EchoAdapterBindingService.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="650a4-150">In Solution Explorer, double-click the **EchoAdapterBindingService.cs** file.</span></span>  
  
2.  <span data-ttu-id="650a4-151">En el editor de Visual Studio, dentro de la **OnReceiveEcho** método, reemplace la implementación existente con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="650a4-151">In the Visual Studio editor, inside the **OnReceiveEcho** method, replace the existing implementation with the following:</span></span>  
  
    ```csharp  
    System.Console.WriteLine("path = " + path + ", len = " + length);  
    ```  
  
3.  <span data-ttu-id="650a4-152">En el Explorador de soluciones, haga doble clic en el **Program.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="650a4-152">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
4.  <span data-ttu-id="650a4-153">En el editor de Visual Studio, dentro del método principal, agregue el código siguiente para hospedar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="650a4-153">In the Visual Studio editor, inside the Main method, add the following code to host the WCF service.</span></span>  
  
    ```csharp  
    try  
    {  
        // Create a ServiceHost for the EchoServiceImpl type  
        // and use the base address from app.config  
        System.ServiceModel.ServiceHost host = new System.ServiceModel.ServiceHost(typeof(EchoAdapterBindingNamespace.EchoAdapterBindingService));  
  
        // Open the ServiceHost to start listening for messages  
        host.Open();  
  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost  
        host.Close();  
    }  
    catch (TimeoutException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    catch (System.ServiceModel.CommunicationException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    ```  
  
5.  <span data-ttu-id="650a4-154">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="650a4-154">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="650a4-155">Presione F5 para iniciar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="650a4-155">Press F5 to start the sample.</span></span>  
  
7.  <span data-ttu-id="650a4-156">Coloque un archivo con la extensión "txt" en el directorio especificado anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="650a4-156">Drop a file with the "txt" extension into the directory specified earlier in this tutorial.</span></span> <span data-ttu-id="650a4-157">Debería ver información similar al siguiente en la ventana de salida del programa:</span><span class="sxs-lookup"><span data-stu-id="650a4-157">You should see information similar to the following in the program output window:</span></span>  
  
     <span data-ttu-id="650a4-158">**El servicio está listo.**</span><span class="sxs-lookup"><span data-stu-id="650a4-158">**The service is ready.**</span></span>  
  
     <span data-ttu-id="650a4-159">**Presione \<ENTRAR > para terminar el servicio.**</span><span class="sxs-lookup"><span data-stu-id="650a4-159">**Press \<ENTER> to terminate service.**</span></span>  
  
     <span data-ttu-id="650a4-160">**ruta de acceso = file:///C:/Tutorial/InboundTest/InboundTest.txt, len = 229179**</span><span class="sxs-lookup"><span data-stu-id="650a4-160">**path = file:///C:/Tutorial/InboundTest/InboundTest.txt, len = 229179**</span></span>  
  
8.  <span data-ttu-id="650a4-161">Presione la tecla ENTRAR para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="650a4-161">Press the Enter key to stop the service.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="650a4-162">¿Simplemente lo que hacía?</span><span class="sxs-lookup"><span data-stu-id="650a4-162">What Did I Just Do?</span></span>  
 <span data-ttu-id="650a4-163">En este paso, ha creado una aplicación de prueba para la operación de entrada expuesta por el adaptador de eco desarrollado en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="650a4-163">In this step, you created a test application for the inbound operation exposed by the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="650a4-164">Para ello, crea un proyecto de Visual Studio, genera un servicio WCF y proporciona código para hospedar el servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="650a4-164">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="650a4-165">Por último, ejecutó la aplicación de prueba.</span><span class="sxs-lookup"><span data-stu-id="650a4-165">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="650a4-166">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="650a4-166">Next Steps</span></span>  
 <span data-ttu-id="650a4-167">Este es el último paso del tutorial.</span><span class="sxs-lookup"><span data-stu-id="650a4-167">This is the last step of the tutorial.</span></span> <span data-ttu-id="650a4-168">Para obtener más información acerca de las operaciones de entrada, consulte `Microsoft.ServiceModel.Channels.Common.IInboundHandler`.</span><span class="sxs-lookup"><span data-stu-id="650a4-168">For more information about Inbound operations, see `Microsoft.ServiceModel.Channels.Common.IInboundHandler`.</span></span> <span data-ttu-id="650a4-169">Para ver un ejemplo SDK que se muestra cómo hospedar un servicio WCF que requiere autenticación, descargar el código de adaptador y prueba de eco en [http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184).</span><span class="sxs-lookup"><span data-stu-id="650a4-169">To see an example SDK that demonstrates how to host a WCF Service that requires authentication, download the echo adapter and test code at [http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650a4-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="650a4-170">See Also</span></span>  
 <span data-ttu-id="650a4-171">[Tutorial 2: Utilizar el adaptador de eco de .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="650a4-171">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="650a4-172">Tutorial 1: Desarrollar el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="650a4-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)