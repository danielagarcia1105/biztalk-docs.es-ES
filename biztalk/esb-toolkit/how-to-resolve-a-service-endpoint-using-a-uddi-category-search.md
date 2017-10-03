---
title: "Cómo: resolver un extremo de servicio mediante una búsqueda de la categoría UDDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ac5d37-5529-4509-a948-415453944e01
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3953baf4a60e2863f986ec54fe9c12663b2b587d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-category-search"></a><span data-ttu-id="01d17-102">Cómo: resolver un extremo de servicio mediante una búsqueda de la categoría UDDI</span><span class="sxs-lookup"><span data-stu-id="01d17-102">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>
## <a name="goal"></a><span data-ttu-id="01d17-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="01d17-103">Goal</span></span>  
 <span data-ttu-id="01d17-104">Esta sección muestra cómo utilizar el lenguaje de ESB diseñador específico de dominio (DSL) para crear una lista de distribución itinerario que usa el Universal Description, Discovery, y solucionador Integration (UDDI) 3 para localizar un punto de conexión de servicio con una categoría de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="01d17-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a category search.</span></span> <span data-ttu-id="01d17-105">En este escenario, el extremo de servicio será un punto de conexión de archivo publicado en UDDI.</span><span class="sxs-lookup"><span data-stu-id="01d17-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="01d17-106">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="01d17-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="01d17-107">Crear una lista de distribución itinerario para resolver un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="01d17-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="01d17-108">Configurar el itinerario para enrutar el mensaje a un extremo de servicio con una resolución de 3 de UDDI.</span><span class="sxs-lookup"><span data-stu-id="01d17-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="01d17-109">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="01d17-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01d17-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="01d17-110">Prerequisites</span></span>  
 <span data-ttu-id="01d17-111">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="01d17-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="01d17-112">Pasos</span><span class="sxs-lookup"><span data-stu-id="01d17-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="01d17-113">Para crear un modelo itinerario</span><span class="sxs-lookup"><span data-stu-id="01d17-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="01d17-114">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="01d17-114">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="01d17-115">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="01d17-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="01d17-116">En el **Agregar nuevo elemento** cuadro de diálogo, escriba **UDDI3CategorySearch** en el **nombre** cuadro y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="01d17-116">In the **Add New Item** dialog box, type **UDDI3CategorySearch** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="01d17-117">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="01d17-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="01d17-118">En Visual Studio, haga clic en la superficie de diseño de **UDDI3CategorySearch.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="01d17-118">In Visual Studio, click the design surface of **UDDI3CategorySearch.itinerary**.</span></span> <span data-ttu-id="01d17-119">En el **UDDI3CategorySearch** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="01d17-119">In the **UDDI3CategorySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="01d17-120">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="01d17-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="01d17-121">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="01d17-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="01d17-122">En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\UDDI3CategorySearch** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="01d17-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3CategorySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="01d17-123">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="01d17-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="01d17-124">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="01d17-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="01d17-125">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="01d17-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="01d17-126">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="01d17-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="01d17-127">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="01d17-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="01d17-128">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="01d17-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="01d17-129">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="01d17-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="01d17-130">En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="01d17-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="01d17-131">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="01d17-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="01d17-132">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="01d17-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="01d17-133">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="01d17-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="01d17-134">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="01d17-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="01d17-135">Haga clic en el **nombre** propiedad y, a continuación, escriba **CategoryRoute**.</span><span class="sxs-lookup"><span data-stu-id="01d17-135">Click the **Name** property, and then type **CategoryRoute**.</span></span>  
  
    2.  <span data-ttu-id="01d17-136">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="01d17-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="01d17-137">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="01d17-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="01d17-138">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**</span><span class="sxs-lookup"><span data-stu-id="01d17-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**</span></span>  
  
3.  <span data-ttu-id="01d17-139">Haga clic en el **resolución** colección de la **CategoryRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="01d17-139">Right-click the **Resolver** collection of the **CategoryRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="01d17-140">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="01d17-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="01d17-141">Haga clic en el **nombre** propiedad y, a continuación, escriba **CategorySearch**.</span><span class="sxs-lookup"><span data-stu-id="01d17-141">Click the **Name** property, and then type **CategorySearch**.</span></span>  
  
    2.  <span data-ttu-id="01d17-142">En el **implementación de la resolución** la lista desplegable, haga clic en **Uddi3 resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="01d17-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="01d17-143">En el **Moniker de resolución** la lista desplegable, haga clic en **UDDI3**.</span><span class="sxs-lookup"><span data-stu-id="01d17-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="01d17-144">Haga clic en el **categoría búsqueda** propiedad y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="01d17-144">Click the **Category Search** property, and then click the ellipsis button (…).</span></span>  
  
    5.  <span data-ttu-id="01d17-145">En el **Editor de propiedades de nombre de valor** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="01d17-145">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    6.  <span data-ttu-id="01d17-146">Haga clic en el **nombre** propiedad y, a continuación, escriba **uddi:esb:biztalkapplication**.</span><span class="sxs-lookup"><span data-stu-id="01d17-146">Click the **Name** property, and then type **uddi:esb:biztalkapplication**.</span></span>  
  
    7.  <span data-ttu-id="01d17-147">Haga clic en el **valor** propiedad y, a continuación, escriba **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="01d17-147">Click the **Value** property, and then type **GlobalBank.ESB**.</span></span>  
  
    8.  <span data-ttu-id="01d17-148">En el **Editor de propiedades de nombre de valor** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="01d17-148">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    9. <span data-ttu-id="01d17-149">Haga clic en el **nombre** propiedad y, a continuación, escriba **uddi:esb:portname**.</span><span class="sxs-lookup"><span data-stu-id="01d17-149">Click the **Name** property, and then type **uddi:esb:portname**.</span></span>  
  
    10. <span data-ttu-id="01d17-150">Haga clic en el **valor** propiedad y, a continuación, escriba **OrderFileServicev3**.</span><span class="sxs-lookup"><span data-stu-id="01d17-150">Click the **Value** property, and then type **OrderFileServicev3**.</span></span>  
  
    11. <span data-ttu-id="01d17-151">En el **Editor de propiedades de nombre de valor** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="01d17-151">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    12. <span data-ttu-id="01d17-152">Haga clic en el **nombre** propiedad y, a continuación, escriba **uddi:esb:version**.</span><span class="sxs-lookup"><span data-stu-id="01d17-152">Click the **Name** property, and then type **uddi:esb:version**.</span></span>  
  
    13. <span data-ttu-id="01d17-153">Haga clic en el **valor** propiedad y, a continuación, escriba **1**.</span><span class="sxs-lookup"><span data-stu-id="01d17-153">Click the **Value** property, and then type **1**.</span></span>  
  
    14. <span data-ttu-id="01d17-154">Haga clic en **Aceptar** para cerrar el **Editor de propiedades de nombre de valor** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="01d17-154">Click **OK** to close the **Name Value Property Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="01d17-155">Haga clic en el **CategorySearch** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.</span><span class="sxs-lookup"><span data-stu-id="01d17-155">Right-click the **CategorySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01d17-156">Compruebe el resultado que aparece en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="01d17-156">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="01d17-157">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="01d17-157">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="01d17-158">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **CategoryRoute** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="01d17-158">Drag a connection from the **ReceiveNAOrder** model element to the **CategoryRoute** model element.</span></span>  
  
6.  <span data-ttu-id="01d17-159">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **CategoryRoute** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="01d17-159">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **CategoryRoute** model element.</span></span> <span data-ttu-id="01d17-160">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="01d17-160">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="01d17-161">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="01d17-161">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="01d17-162">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="01d17-162">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="01d17-163">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="01d17-163">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="01d17-164">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="01d17-164">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="01d17-165">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **CategoryRoute** elemento del modelo y la **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="01d17-165">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **CategoryRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="01d17-166">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="01d17-166">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="01d17-167">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="01d17-167">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="01d17-168">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="01d17-168">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="01d17-169">En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="01d17-169">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="01d17-170">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="01d17-170">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="01d17-171">Arrastre una conexión desde el **CategoryRoute** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="01d17-171">Drag a connection from the **CategoryRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="01d17-172">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="01d17-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="01d17-173">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="01d17-173">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="01d17-174">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="01d17-174">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="01d17-175">En Visual Studio, haga clic en la superficie de diseño de la **UDDI3CategorySearch** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="01d17-175">In Visual Studio, right-click the design surface of the **UDDI3CategorySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01d17-176">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="01d17-176">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="01d17-177">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="01d17-177">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="01d17-178">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (UDDI3CategorySearch.xml).</span><span class="sxs-lookup"><span data-stu-id="01d17-178">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3CategorySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="01d17-179">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="01d17-179">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="01d17-180">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="01d17-180">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="01d17-181">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="01d17-181">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="01d17-182">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="01d17-182">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="01d17-183">Seleccione **UDDI3CategorySearch.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="01d17-183">Select **UDDI3CategorySearch.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="01d17-184">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="01d17-184">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="01d17-185">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="01d17-185">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="01d17-186">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="01d17-186">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="01d17-187">Seleccione NAOrderDoc.xml y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="01d17-187">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="01d17-188">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="01d17-188">Click the **Submit Request** button.</span></span> <span data-ttu-id="01d17-189">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="01d17-189">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="01d17-190">En el Explorador de Windows, vaya a **C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out** y compruebe que la **%MessageID%.xml** mensaje se ha escrito en el directorio.</span><span class="sxs-lookup"><span data-stu-id="01d17-190">In Windows Explorer, browse to **C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out** and verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="01d17-191">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="01d17-191">Additional Resources</span></span>  
 <span data-ttu-id="01d17-192">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="01d17-192">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="01d17-193">Cómo: resolver un extremo de servicio mediante una búsqueda de la clave de enlace de UDDI</span><span class="sxs-lookup"><span data-stu-id="01d17-193">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [<span data-ttu-id="01d17-194">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="01d17-194">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="01d17-195">Uso de resolución dinámica y enrutamiento</span><span class="sxs-lookup"><span data-stu-id="01d17-195">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)