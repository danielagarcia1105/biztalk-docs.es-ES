---
title: 'Paso 1: Probar el controlador de salida del adaptador de eco | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba2b1d6586588d17c58c0ca9a74cb11a7a9bd9f2
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a><span data-ttu-id="bf276-102">Paso 1: Probar el controlador de salida del adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="bf276-102">Step 1: Test Outbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="bf276-103">![Paso 1 de 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="bf276-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="bf276-104">**Tiempo para completar:** 15 minutos</span><span class="sxs-lookup"><span data-stu-id="bf276-104">**Time to Complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="bf276-105">En este paso, probará las tres operaciones de salida proporcionadas por el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="bf276-105">In this step, you will test the three outbound operations provided by the Echo Adapter.</span></span> <span data-ttu-id="bf276-106">Se hace esto con Visual Studio, agregar adaptador de servicio de referencia de complemento de Visual Studio y código personalizado.</span><span class="sxs-lookup"><span data-stu-id="bf276-106">You will do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf276-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bf276-107">Prerequisites</span></span>  
 <span data-ttu-id="bf276-108">Para completar este paso, debe haber completado [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="bf276-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="bf276-109">Crear un proyecto de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf276-109">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="bf276-110">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf276-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="bf276-111">En Visual Studio, en el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bf276-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="bf276-112">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf276-112">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="bf276-113">Use</span><span class="sxs-lookup"><span data-stu-id="bf276-113">Use this</span></span>|<span data-ttu-id="bf276-114">Para</span><span class="sxs-lookup"><span data-stu-id="bf276-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="bf276-115">**Tipos de proyecto**</span><span class="sxs-lookup"><span data-stu-id="bf276-115">**Project types**</span></span>|<span data-ttu-id="bf276-116">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="bf276-116">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="bf276-117">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="bf276-117">**Templates**</span></span>|<span data-ttu-id="bf276-118">Haga clic en **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="bf276-118">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="bf276-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="bf276-119">**Name**</span></span>|<span data-ttu-id="bf276-120">Tipo de **ConsumeEchoAdapter_Outbound**.</span><span class="sxs-lookup"><span data-stu-id="bf276-120">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
    |<span data-ttu-id="bf276-121">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="bf276-121">**Location**</span></span>|<span data-ttu-id="bf276-122">Tipo de **C:\Tutorials**.</span><span class="sxs-lookup"><span data-stu-id="bf276-122">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="bf276-123">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="bf276-123">**Solution Name**</span></span>|<span data-ttu-id="bf276-124">Tipo de **ConsumeEchoAdapter_Outbound**.</span><span class="sxs-lookup"><span data-stu-id="bf276-124">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
  
4.  <span data-ttu-id="bf276-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf276-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bf276-126">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="bf276-126">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-client"></a><span data-ttu-id="bf276-127">Examinar, buscar y generar al cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="bf276-127">Browse, search, and generate the WCF client</span></span>  
  
1.  <span data-ttu-id="bf276-128">En el panel de la solución de Visual Studio, haga clic en **ConsumeEchoAdapter_Outbound** del proyecto, y luego elija **Agregar referencia de servicio de adaptador** para iniciar el complemento de agregar Adapter Service Reference.</span><span class="sxs-lookup"><span data-stu-id="bf276-128">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Outbound** project, then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="bf276-129">En el **Agregar referencia de servicio de adaptador** , elija un enlace.</span><span class="sxs-lookup"><span data-stu-id="bf276-129">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="bf276-130">Para ello, elija **echoAdapterBindingV2**.</span><span class="sxs-lookup"><span data-stu-id="bf276-130">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="bf276-131">A continuación, configure las propiedades de conexión y adaptador, haga clic en **configurar...** .</span><span class="sxs-lookup"><span data-stu-id="bf276-131">Next, configure the adapter and connection properties by clicking **Configure…**.</span></span>  <span data-ttu-id="bf276-132">Esto le llevará a la **configurar el adaptador** pantalla.</span><span class="sxs-lookup"><span data-stu-id="bf276-132">This will bring up the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="bf276-133">En el **configurar el adaptador** pantalla, seleccione la **propiedades de URI** ficha para configurar las propiedades de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf276-133">In the **Configure Adapter** screen, select the **URI Properties** tab to configure connection properties.</span></span> <span data-ttu-id="bf276-134">Tenga en cuenta que se muestran las categorías de eco adaptador personalizadas: **conexión** y **formato**.</span><span class="sxs-lookup"><span data-stu-id="bf276-134">Notice that the custom Echo Adapter categories are shown — **Connection** and **Format**.</span></span> <span data-ttu-id="bf276-135">En el **formato** categoría, cambio **EchoInUpperCase** a **True**.</span><span class="sxs-lookup"><span data-stu-id="bf276-135">Under the **Format** category, change **EchoInUpperCase** to **True**.</span></span>  
  
5.  <span data-ttu-id="bf276-136">En el **configurar el adaptador** pantalla, seleccione la **propiedades de enlace** ficha para configurar las propiedades del adaptador.</span><span class="sxs-lookup"><span data-stu-id="bf276-136">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="bf276-137">Tenga en cuenta que las categorías de eco adaptador personalizadas **entrada** y **varios** se muestran.</span><span class="sxs-lookup"><span data-stu-id="bf276-137">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="bf276-138">En el **varios** categoría, cambio **recuento** a **3**.</span><span class="sxs-lookup"><span data-stu-id="bf276-138">Under the **Misc** category, change **Count** to **3**.</span></span>  
  
6.  <span data-ttu-id="bf276-139">Haga clic en **Aceptar** para cerrar el **configurar el adaptador** pantalla y volver a la **Agregar referencia de servicio de adaptador** pantalla.</span><span class="sxs-lookup"><span data-stu-id="bf276-139">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
7.  <span data-ttu-id="bf276-140">A continuación, haga clic en **conectar** para conectar con el adaptador de eco (y el sistema de línea de negocio hipotético admite).</span><span class="sxs-lookup"><span data-stu-id="bf276-140">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="bf276-141">Transcurridos unos instantes, debería cambiar el estado de la conexión a **conectado** y el árbol de categorías (en **seleccione una categoría**) se debe rellenar.</span><span class="sxs-lookup"><span data-stu-id="bf276-141">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
8.  <span data-ttu-id="bf276-142">En el árbol de categorías, haga clic en **categoría principal**.</span><span class="sxs-lookup"><span data-stu-id="bf276-142">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="bf276-143">Esto rellenará la lista de categorías disponibles y las operaciones con tres operaciones de salida.</span><span class="sxs-lookup"><span data-stu-id="bf276-143">This will populate the list of available categories and operations with three outbound operations.</span></span> <span data-ttu-id="bf276-144">No habrá ninguna categoría.</span><span class="sxs-lookup"><span data-stu-id="bf276-144">There will be no categories.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf276-145">El tipo de contrato predeterminado es saliente.</span><span class="sxs-lookup"><span data-stu-id="bf276-145">The default contract type is Outbound.</span></span> <span data-ttu-id="bf276-146">Resultados de la categoría coincidirá con este tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="bf276-146">Category results will match this contract type.</span></span>  
  
9. <span data-ttu-id="bf276-147">En el **categorías y operaciones disponibles**, seleccione las tres operaciones.</span><span class="sxs-lookup"><span data-stu-id="bf276-147">In the **Available Categories and Operations**, select all three operations.</span></span> <span data-ttu-id="bf276-148">Cuando hay un gran número de operaciones, podría usar búsqueda para restringir la selección; en este caso, hay sólo tres.</span><span class="sxs-lookup"><span data-stu-id="bf276-148">When there are a large number of operations, you might use search to narrow down the selection; in this case, there are only three.</span></span> <span data-ttu-id="bf276-149">Haga clic en **agregar** para realizar la parte de operaciones seleccionadas de la interfaz WCF generada.</span><span class="sxs-lookup"><span data-stu-id="bf276-149">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="bf276-150">Haga clic en **Aceptar** para generar la interfaz WCF.</span><span class="sxs-lookup"><span data-stu-id="bf276-150">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="bf276-151">Esto agregará un archivo de configuración de aplicación (app.config) y un proxy de cliente WCF (EchoAdapterBindingClient.cs) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="bf276-151">This will add an application configuration file (app.config) and a WCF client proxy (EchoAdapterBindingClient.cs) to the project.</span></span>  
  
11. <span data-ttu-id="bf276-152">Haga clic en **archivo** en el menú de Visual Studio y elija **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="bf276-152">Click **File** on the Visual Studio menu and choose **Save All**.</span></span>  
  
## <a name="configure-adapter-authentication"></a><span data-ttu-id="bf276-153">Configurar la autenticación de adaptador</span><span class="sxs-lookup"><span data-stu-id="bf276-153">Configure adapter authentication</span></span>  
  
1.  <span data-ttu-id="bf276-154">En el panel de la solución de Visual Studio, haga doble clic en **app.config**.</span><span class="sxs-lookup"><span data-stu-id="bf276-154">In Visual Studio Solution pane, double-click **app.config**.</span></span>  
  
2.  <span data-ttu-id="bf276-155">Buscar el `address` de atributo en el `endpoint` elemento.</span><span class="sxs-lookup"><span data-stu-id="bf276-155">Find the `address` attribute in the `endpoint` element.</span></span> <span data-ttu-id="bf276-156">Debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf276-156">It should look similar to the following:</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     <span data-ttu-id="bf276-157">Cambio **enableAuthentication** de **False** a **True** tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="bf276-157">Change **enableAuthentication** from **False** to **True** as shown below.</span></span> <span data-ttu-id="bf276-158">Esto requerirá la aplicación que realiza la llamada para pasar las credenciales para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="bf276-158">This will require the calling application to pass credentials to the adapter.</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  <span data-ttu-id="bf276-159">Guarde la solución haciendo clic en **archivo** en Visual Studio menú y eligiendo **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="bf276-159">Save the solution by clicking **File** on the Visual Studio menu and choosing **Save All**.</span></span>  
  
## <a name="create-a-sample-xml-file"></a><span data-ttu-id="bf276-160">Crear un archivo XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf276-160">Create a sample XML file</span></span>  
  
1.  <span data-ttu-id="bf276-161">Iniciar una instancia del Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="bf276-161">Start an instance of Notepad.</span></span> <span data-ttu-id="bf276-162">Mediante el menú Inicio, haga clic en **todos los programas** &#124; **Accesorios** y, a continuación, elija **el Bloc de notas**.</span><span class="sxs-lookup"><span data-stu-id="bf276-162">Using the Start menu, click **All Programs** &#124; **Accessories** and then choose **Notepad**.</span></span>  
  
2.  <span data-ttu-id="bf276-163">Copie los siguientes datos de ejemplo en el editor en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="bf276-163">Copy the following sample data into the Notepad editor.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <ns0:greeting xmlns:ns0="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes">  
      <ns0:address>  
        <ns0:street1>123 Microsoft Way</ns0:street1>  
        <ns0:street2>Building # 4599</ns0:street2>  
        <ns0:city>Redmond</ns0:city>  
        <ns0:state>WA</ns0:state>  
        <ns0:zip>98052</ns0:zip>  
      </ns0:address>  
      <ns0:greetingText>Welcome to Redmond!</ns0:greetingText>  
    </ns0:greeting>              
    ```  
  
3.  <span data-ttu-id="bf276-164">En el menú el Bloc de notas, haga clic en **archivo** y, a continuación, elija **Guardar como...** .</span><span class="sxs-lookup"><span data-stu-id="bf276-164">On the Notepad menu, click **File** and then choose **Save As…**.</span></span> <span data-ttu-id="bf276-165">Escriba "CustomGreetingInstance.xml" para el nombre de archivo y elija Unicode para la codificación y, a continuación, guardarlo en el directorio del proyecto o en otra ubicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="bf276-165">Type in "CustomGreetingInstance.xml" for the file name and choose Unicode for the encoding and then save it to the project directory or another suitable location.</span></span> <span data-ttu-id="bf276-166">Tenga en cuenta la ruta de acceso completa y nombre de archivo para consultarlos más adelante.</span><span class="sxs-lookup"><span data-stu-id="bf276-166">Note the full path and filename for later reference.</span></span>  
  
4.  <span data-ttu-id="bf276-167">Cierre el editor de texto cuando el archivo se guardó correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf276-167">Close the text editor when the file is successfully saved.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="bf276-168">Probar el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="bf276-168">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="bf276-169">En el Explorador de soluciones, haga doble clic en el **Program.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="bf276-169">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
2.  <span data-ttu-id="bf276-170">En el editor de Visual Studio, dentro de la **Main** método, agregue la siguiente línea de código para crear una instancia del cliente WCF generado.</span><span class="sxs-lookup"><span data-stu-id="bf276-170">In the Visual Studio editor, inside the **Main** method, add the following line of code to create an instance of the generated WCF client.</span></span>  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  <span data-ttu-id="bf276-171">Ahora, agregue código que establece las credenciales para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="bf276-171">Now add code that establishes credentials for the adapter.</span></span> <span data-ttu-id="bf276-172">Cuando se habilita la autenticación en el adaptador de eco, comprobará la existencia de un nombre de usuario pero no comprobará el valor.</span><span class="sxs-lookup"><span data-stu-id="bf276-172">When authentication is enabled in the Echo Adapter, it will check for the existence of a user name but will not check the value.</span></span>  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  <span data-ttu-id="bf276-173">Continúe agregando código para invocar la operación de EchoStrings.</span><span class="sxs-lookup"><span data-stu-id="bf276-173">Continue by adding code to invoke the EchoStrings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  <span data-ttu-id="bf276-174">Continúe agregando código para invocar la operación de EchoGreetings.</span><span class="sxs-lookup"><span data-stu-id="bf276-174">Continue by adding code to invoke the EchoGreetings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoGreetings()  
    Console.WriteLine("\nInvoking EchoGreetings() method against the adapter...");  
    microsoft.adapters.samples.echov2.Types.Greeting greeting = new microsoft.adapters.samples.echov2.Types.Greeting();  
    greeting.id = Guid.NewGuid();  
    greeting.sentDateTime = DateTime.Now;  
    greeting.greetingText = "Hello World!";  
    greeting.name = new microsoft.adapters.samples.echov2.Types.Name();  
    greeting.name.salutation = microsoft.adapters.samples.echov2.Types.Salutation.Miss;  
    greeting.name.firstName = "Jane";  
    greeting.name.middleName = "Z.";  
    greeting.name.lastName = "Smith";  
    microsoft.adapters.samples.echov2.Types.Greeting[] greetingArray = client.EchoGreetings(greeting);  
    foreach (microsoft.adapters.samples.echov2.Types.Greeting data in greetingArray)  
    {  
        Console.WriteLine(data.id + " " + data.sentDateTime + " " + data.greetingText + " " + data.name.firstName );  
    }  
    ```  
  
6.  <span data-ttu-id="bf276-175">Continúe agregando código para invocar la operación de EchoCustomGreetingsFromFile.</span><span class="sxs-lookup"><span data-stu-id="bf276-175">Continue by adding code to invoke the EchoCustomGreetingsFromFile operation.</span></span>  
  
    ```csharp  
    // Invoke EchoCustomGreetingFromFile()  
    Console.WriteLine("\nInvoking EchoCustomGreetingFromFile() method against the adapter ...");  
    // Copy the sample data from CustomGreeting-instance.xml file and place in appropriate folder  
    // as specified in the operation parameter  
    microsoft.adapters.samples.echov2.PreDefinedTypes.CustomGreeting   
    // change the Uri to point to the greeting instance xml file you created  
    customGreeting = client.EchoCustomGreetingFromFile(new Uri(@"c:\CustomGreetingInstance.xml"));  
    Console.WriteLine(customGreeting.greetingText + " " + customGreeting.address.city);  
    client.Close();  
    Console.ReadLine();  
    ```  
  
7.  <span data-ttu-id="bf276-176">En la EchoCustomGreetingsFromFile probar el código, asegúrese de que el saludo personalizado usa el archivo creado en un procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="bf276-176">In the EchoCustomGreetingsFromFile test code, make sure the custom greeting uses the file you created in a previous procedure.</span></span> <span data-ttu-id="bf276-177">Cambie el código para reflejar la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="bf276-177">Change the code to reflect the location of your file.</span></span>  
  
8.  <span data-ttu-id="bf276-178">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="bf276-178">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
9. <span data-ttu-id="bf276-179">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf276-179">Run the application.</span></span> <span data-ttu-id="bf276-180">Debería ver un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf276-180">You should see output similar to the following:</span></span>  
  
     <span data-ttu-id="bf276-181">**Invocar el método de EchoStrings() con el adaptador...**</span><span class="sxs-lookup"><span data-stu-id="bf276-181">**Invoking EchoStrings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="bf276-182">**¡Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="bf276-182">**Bonjour!**</span></span>  
  
     <span data-ttu-id="bf276-183">**¡Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="bf276-183">**Bonjour!**</span></span>  
  
     <span data-ttu-id="bf276-184">**¡Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="bf276-184">**Bonjour!**</span></span>  
  
     <span data-ttu-id="bf276-185">**¡Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="bf276-185">**Bonjour!**</span></span>  
  
     <span data-ttu-id="bf276-186">**¡Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="bf276-186">**Bonjour!**</span></span>  
  
     <span data-ttu-id="bf276-187">**Invocar el método de EchoGreetings() con el adaptador...**</span><span class="sxs-lookup"><span data-stu-id="bf276-187">**Invoking EchoGreetings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="bf276-188">**179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**</span><span class="sxs-lookup"><span data-stu-id="bf276-188">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="bf276-189">**179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**</span><span class="sxs-lookup"><span data-stu-id="bf276-189">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="bf276-190">**179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**</span><span class="sxs-lookup"><span data-stu-id="bf276-190">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="bf276-191">**179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**</span><span class="sxs-lookup"><span data-stu-id="bf276-191">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="bf276-192">**179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**</span><span class="sxs-lookup"><span data-stu-id="bf276-192">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="bf276-193">**Invocar el método de EchoCustomGreetingFromFile() con el adaptador...**</span><span class="sxs-lookup"><span data-stu-id="bf276-193">**Invoking EchoCustomGreetingFromFile() method against the adapter ...**</span></span>  
  
     <span data-ttu-id="bf276-194">**Bienvenido a Redmond. Redmond**</span><span class="sxs-lookup"><span data-stu-id="bf276-194">**Welcome to Redmond! Redmond**</span></span>  
  
10. <span data-ttu-id="bf276-195">Presione la tecla ENTRAR para detener el programa.</span><span class="sxs-lookup"><span data-stu-id="bf276-195">Press the Enter key to stop the program.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="bf276-196">¿Simplemente lo que hacía?</span><span class="sxs-lookup"><span data-stu-id="bf276-196">What Did I Just Do?</span></span>  
 <span data-ttu-id="bf276-197">En este paso, ha creado una aplicación de prueba para las operaciones de salida tres expuestas por el adaptador de eco desarrollado en el Tutorial 1.</span><span class="sxs-lookup"><span data-stu-id="bf276-197">In this step, you created a test application for the three outbound operations exposed by the Echo Adapter developed in Tutorial 1.</span></span> <span data-ttu-id="bf276-198">Para ello, crea un proyecto de Visual Studio, genera un servicio WCF y proporciona código para hospedar el servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="bf276-198">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="bf276-199">Por último, ejecutó la aplicación de prueba.</span><span class="sxs-lookup"><span data-stu-id="bf276-199">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bf276-200">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bf276-200">Next Steps</span></span>  
 <span data-ttu-id="bf276-201">Para probar la operación de entrada, continúe con [paso 2: probar el controlador de entrada del adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="bf276-201">To test the Inbound operation, proceed to [Step 2: Test Inbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf276-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf276-202">See Also</span></span>  
  <span data-ttu-id="bf276-203">[Tutorial 2: Utilizar el adaptador de eco de .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="bf276-203">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="bf276-204">Paso 2: Probar el controlador de entrada del adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="bf276-204">Step 2: Test Inbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)