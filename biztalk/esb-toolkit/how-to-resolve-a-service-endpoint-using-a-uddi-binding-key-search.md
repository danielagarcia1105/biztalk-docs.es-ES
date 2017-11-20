---
title: "Cómo: resolver un extremo de servicio mediante una búsqueda de la clave de enlace de UDDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a685641-2beb-4153-a9ba-c766679ce48e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e73ecbc5d1ef88fe2b8bdc7f19f56f6f2ae207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a><span data-ttu-id="1e0a0-102">Cómo: resolver un extremo de servicio mediante una búsqueda de la clave de enlace de UDDI</span><span class="sxs-lookup"><span data-stu-id="1e0a0-102">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>
## <a name="goal"></a><span data-ttu-id="1e0a0-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="1e0a0-103">Goal</span></span>  
 <span data-ttu-id="1e0a0-104">Esta sección muestra cómo utilizar el lenguaje de ESB diseñador específico de dominio (DSL) para crear una lista de distribución itinerario que usa el Universal Description, Discovery, y el solucionador Integration (UDDI) 3 para localizar un punto de conexión de servicio con una clave de enlace búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a binding key search.</span></span> <span data-ttu-id="1e0a0-105">En este escenario, el extremo de servicio será un punto de conexión de archivo publicado en UDDI.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="1e0a0-106">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="1e0a0-107">Crear una lista de distribución itinerario para resolver un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="1e0a0-108">Configurar el itinerario para enrutar el mensaje a un extremo de servicio con una resolución de 3 de UDDI.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="1e0a0-109">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1e0a0-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1e0a0-110">Prerequisites</span></span>  
 <span data-ttu-id="1e0a0-111">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="1e0a0-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="1e0a0-112">Pasos</span><span class="sxs-lookup"><span data-stu-id="1e0a0-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="1e0a0-113">Para crear un modelo itinerario</span><span class="sxs-lookup"><span data-stu-id="1e0a0-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="1e0a0-114">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-114">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="1e0a0-115">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1e0a0-116">En el **Agregar nuevo elemento** cuadro de diálogo, en la **nombre** , escriba **UDDI3BindingKeySearch**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-116">In the **Add New Item** dialog box, in the **Name** box, type **UDDI3BindingKeySearch**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="1e0a0-117">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="1e0a0-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="1e0a0-118">En Visual Studio, haga clic en la superficie de diseño de **UDDI3BindingKeySearch.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-118">In Visual Studio, click the design surface of **UDDI3BindingKeySearch.itinerary**.</span></span> <span data-ttu-id="1e0a0-119">En el **UDDI3BindingKeySearch** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-119">In the **UDDI3BindingKeySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1e0a0-120">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="1e0a0-121">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="1e0a0-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="1e0a0-122">En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\UDDI3BindingKeySearch** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3BindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1e0a0-123">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="1e0a0-124">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="1e0a0-125">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="1e0a0-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="1e0a0-126">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="1e0a0-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="1e0a0-127">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="1e0a0-128">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1e0a0-129">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1e0a0-130">En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="1e0a0-131">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1e0a0-132">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="1e0a0-133">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="1e0a0-134">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1e0a0-135">Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeyRoute**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-135">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  
  
    2.  <span data-ttu-id="1e0a0-136">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="1e0a0-137">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="1e0a0-138">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="1e0a0-139">Haga clic en el **resolución** colección de la **BindingKeyRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-139">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="1e0a0-140">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1e0a0-141">Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeySearch**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-141">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  
  
    2.  <span data-ttu-id="1e0a0-142">En el **implementación de la resolución** la lista desplegable, haga clic en **Uddi3 resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="1e0a0-143">En el **Moniker de resolución** la lista desplegable, haga clic en **UDDI3**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="1e0a0-144">Haga clic en el **clave de enlace** propiedad y, a continuación, escriba **uddi:esb:orderfileservicev3.1**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-144">Click the **Binding key** property, and then type **uddi:esb:orderfileservicev3.1**.</span></span>  
  
4.  <span data-ttu-id="1e0a0-145">Haga clic en el **BindingKeySearch** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-145">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1e0a0-146">Compruebe el resultado que aparece en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-146">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="1e0a0-147">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1e0a0-148">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **BindingKeyRoute** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-148">Drag a connection from the **ReceiveNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  
  
6.  <span data-ttu-id="1e0a0-149">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BindingKeyRoute** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="1e0a0-150">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1e0a0-151">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-151">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1e0a0-152">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="1e0a0-153">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1e0a0-154">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="1e0a0-155">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BindingKeyRoute** elemento del modelo y la **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="1e0a0-156">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1e0a0-157">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="1e0a0-158">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="1e0a0-159">En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-159">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="1e0a0-160">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1e0a0-161">Arrastre una conexión desde el **BindingKeyRoute** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-161">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="1e0a0-162">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-162">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1e0a0-163">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-163">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="1e0a0-164">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="1e0a0-164">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="1e0a0-165">En Visual Studio, haga clic en la superficie de diseño de la **UDDI3BindingKeySearch** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-165">In Visual Studio, right-click the design surface of the **UDDI3BindingKeySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1e0a0-166">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-166">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1e0a0-167">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-167">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="1e0a0-168">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (UDDI3BindingKeySearch.xml).</span><span class="sxs-lookup"><span data-stu-id="1e0a0-168">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3BindingKeySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="1e0a0-169">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="1e0a0-169">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="1e0a0-170">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="1e0a0-170">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="1e0a0-171">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-171">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1e0a0-172">En el cuadro de diálogo Abrir archivo de itinerario, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-172">In the Open Itinerary File dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="1e0a0-173">Seleccione UDDI3BindingKeySearch.xml y, a continuación, haga clic en Abrir para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-173">Select UDDI3BindingKeySearch.xml, and then click Open to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="1e0a0-174">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-174">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="1e0a0-175">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-175">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="1e0a0-176">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-176">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="1e0a0-177">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-177">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="1e0a0-178">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-178">Click the **Submit Request** button.</span></span> <span data-ttu-id="1e0a0-179">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-179">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="1e0a0-180">En el Explorador de Windows, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out. Compruebe que se ha escrito el mensaje %MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="1e0a0-180">In Windows Explorer, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out. Verify that the %MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="1e0a0-181">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1e0a0-181">Additional Resources</span></span>  
 <span data-ttu-id="1e0a0-182">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="1e0a0-182">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="1e0a0-183">Cómo: resolver un extremo de servicio mediante una búsqueda de la categoría UDDI</span><span class="sxs-lookup"><span data-stu-id="1e0a0-183">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [<span data-ttu-id="1e0a0-184">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="1e0a0-184">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="1e0a0-185">Uso de resolución dinámica y enrutamiento</span><span class="sxs-lookup"><span data-stu-id="1e0a0-185">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)