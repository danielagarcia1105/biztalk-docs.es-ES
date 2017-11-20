---
title: "Cómo: transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución itinerario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27749ba-c228-4cd4-827e-e8009a0c999d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18caef7d7c60fa7aa129baa787c746b3b797c808
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="3cc47-102">Cómo: transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución itinerario</span><span class="sxs-lookup"><span data-stu-id="3cc47-102">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="3cc47-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="3cc47-103">Goal</span></span>  
 <span data-ttu-id="3cc47-104">Esta sección muestra cómo utilizar el lenguaje de ESB diseñador específico de dominio (DSL) para crear un itinerario que implementa la transformación del mensaje mediante la invocación de una asignación de BizTalk y, a continuación, enruta los mensajes mediante el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary that implements message transformation by invoking a BizTalk map, and then it routes the messages using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="3cc47-105">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cc47-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="3cc47-106">Crear una lista de distribución itinerario con un servicio de itinerarios de transformación que implementa una asignación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3cc47-106">Create an itinerary routing slip with a transform itinerary service that implements a BizTalk map.</span></span>  
  
-   <span data-ttu-id="3cc47-107">Configurar el itinerario para enrutar el mensaje transformado en una ubicación de archivo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-107">Configure the itinerary to route the transformed message to a file location.</span></span>  
  
-   <span data-ttu-id="3cc47-108">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="3cc47-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3cc47-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3cc47-109">Prerequisites</span></span>  
 <span data-ttu-id="3cc47-110">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="3cc47-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="3cc47-111">Pasos</span><span class="sxs-lookup"><span data-stu-id="3cc47-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="3cc47-112">Para crear un modelo DSL itinerario de ESB</span><span class="sxs-lookup"><span data-stu-id="3cc47-112">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="3cc47-113">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="3cc47-113">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3cc47-114">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-114">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3cc47-115">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **ItineraryDsl** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="3cc47-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="3cc47-116">En el **nombre** , escriba **DataModelTransformation**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-116">In the **Name** box, type **DataModelTransformation**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="3cc47-117">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="3cc47-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="3cc47-118">En Visual Studio, haga clic en la superficie de diseño de **DataModelTransformation.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-118">In Visual Studio, click the design surface of **DataModelTransformation.itinerary**.</span></span> <span data-ttu-id="3cc47-119">En el **DataModelTransformation** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3cc47-119">In the **DataModelTransformation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3cc47-120">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3cc47-121">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="3cc47-121">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="3cc47-122">En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\DataModelTransformation**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-122">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\DataModelTransformation**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3cc47-123">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="3cc47-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="3cc47-124">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="3cc47-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="3cc47-125">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="3cc47-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="3cc47-126">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="3cc47-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="3cc47-127">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="3cc47-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3cc47-128">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3cc47-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3cc47-129">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3cc47-130">En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-130">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3cc47-131">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3cc47-132">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3cc47-133">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="3cc47-134">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3cc47-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3cc47-135">Haga clic en el **nombre** propiedad y, a continuación, escriba **MapNAOrderToCNOrder**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-135">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="3cc47-136">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3cc47-137">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="3cc47-137">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="3cc47-138">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-138">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="3cc47-139">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-139">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="3cc47-140">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-140">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="3cc47-141">Haga clic en el **resolución** colección de la **MapNAOrderToCNOrder** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-141">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3cc47-142">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3cc47-142">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3cc47-143">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticallySpecifyTheMap**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-143">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="3cc47-144">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-144">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3cc47-145">En el **transformar tipo** la lista desplegable, haga clic en **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-145">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="3cc47-146">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-146">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="3cc47-147">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3cc47-148">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **MapNAOrderToCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-148">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="3cc47-149">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **MapNAOrderToCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="3cc47-150">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3cc47-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3cc47-151">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendCNOrder**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-151">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="3cc47-152">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="3cc47-153">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3cc47-154">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="3cc47-155">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **MapNAOrderToCNOrder** elemento del modelo y la **SendCNOrder**elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="3cc47-156">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3cc47-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3cc47-157">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="3cc47-158">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="3cc47-159">En el **fuera de rampa** lista desplegable lista, expanda **SendCNOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-159">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="3cc47-160">Haga clic en el **resolución** colección de la **SendPortFilter** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-160">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3cc47-161">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3cc47-161">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3cc47-162">Haga clic en el **nombre** propiedad y, a continuación, escriba **ConfigureFolderSettings**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-162">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="3cc47-163">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-163">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    3.  <span data-ttu-id="3cc47-164">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\\%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-164">Click the **Transport Location** property, and then type **C:\HowTos\Out\\%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3cc47-165">Cada fuera de rampa tendrá un servicio de itinerario asociados a él; la combinación de las propiedades del servicio de itinerario y las propiedades de fuera de rampa definir la suscripción del puerto de envío dinámico.</span><span class="sxs-lookup"><span data-stu-id="3cc47-165">Each off-ramp will have an Itinerary Service associated with it; the combination of the Itinerary Service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="3cc47-166">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3cc47-167">Arrastre una conexión desde el **MapNAOrderToCNOrder** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="3cc47-168">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-168">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3cc47-169">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="3cc47-169">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="3cc47-170">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="3cc47-170">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="3cc47-171">En Visual Studio, haga clic en la superficie de diseño de la **DataModelTransformation** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-171">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3cc47-172">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3cc47-172">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="3cc47-173">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3cc47-173">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="3cc47-174">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (DataModelTransformation.xml).</span><span class="sxs-lookup"><span data-stu-id="3cc47-174">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (DataModelTransformation.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="3cc47-175">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="3cc47-175">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="3cc47-176">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="3cc47-176">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="3cc47-177">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="3cc47-177">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3cc47-178">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="3cc47-178">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="3cc47-179">Seleccione **DataModelTransformation.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="3cc47-179">Select **DataModelTransformation.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="3cc47-180">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cc47-180">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="3cc47-181">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="3cc47-181">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="3cc47-182">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="3cc47-182">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="3cc47-183">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="3cc47-183">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="3cc47-184">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="3cc47-184">Click the **Submit Request** button.</span></span> <span data-ttu-id="3cc47-185">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="3cc47-185">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="3cc47-186">En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que la **%MessageID%.xml** mensaje se ha escrito en el directorio.</span><span class="sxs-lookup"><span data-stu-id="3cc47-186">In Windows Explorer, browse to C:\HowTos\Out. Verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="3cc47-187">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3cc47-187">Additional Resources</span></span>  
 <span data-ttu-id="3cc47-188">Para obtener más información, vea que estos temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="3cc47-188">For more information, see these related topics:</span></span>  
  
1.  [<span data-ttu-id="3cc47-189">Cómo: dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos utilizando distintos itinerarios</span><span class="sxs-lookup"><span data-stu-id="3cc47-189">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [<span data-ttu-id="3cc47-190">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="3cc47-190">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
3.  [<span data-ttu-id="3cc47-191">Patrones de transformación de mensajes</span><span class="sxs-lookup"><span data-stu-id="3cc47-191">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)