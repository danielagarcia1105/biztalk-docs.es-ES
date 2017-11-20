---
title: "Cómo: implementar el enrutamiento por contenidos mediante propiedades de contexto de mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e47235978960ac89f4ea276c4c4a60c8ddf16e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a><span data-ttu-id="12581-102">Cómo: implementar el enrutamiento por contenidos mediante propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="12581-102">How to: Implement Content-Based Routing Using Message Context Properties</span></span>
## <a name="goal"></a><span data-ttu-id="12581-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="12581-103">Goal</span></span>  
 <span data-ttu-id="12581-104">Esta sección muestra cómo utilizar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Diseñador de itinerario para crear un itinerario que selecciona un destinatario del mensaje en función de la propiedad de contexto de mensaje y, a continuación, enruta un mensaje a dicho destinatario con el agente de itinerario del servicio de mensajería.</span><span class="sxs-lookup"><span data-stu-id="12581-104">This section demonstrates how to use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Itinerary Designer to create an itinerary that selects a message recipient based on the message context property and then routes a message to that recipient using the Itinerary Broker messaging service.</span></span>  
  
 <span data-ttu-id="12581-105">En este tema, se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="12581-105">In this topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="12581-106">Crear un itinerario con un agente itinerario y dos servicios de enrutamiento con resoluciones estáticos.</span><span class="sxs-lookup"><span data-stu-id="12581-106">Create an itinerary with an itinerary broker and two routing services with static resolvers.</span></span>  
  
-   <span data-ttu-id="12581-107">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="12581-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12581-108">Ningún servicio de agente basado en la orquestación se proporciona en la implementación actual.</span><span class="sxs-lookup"><span data-stu-id="12581-108">No orchestration-based broker service is provided in the current implementation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12581-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="12581-109">Prerequisites</span></span>  
 <span data-ttu-id="12581-110">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="12581-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="12581-111">Pasos</span><span class="sxs-lookup"><span data-stu-id="12581-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="12581-112">Para crear un modelo DSL de itinerario de ESB</span><span class="sxs-lookup"><span data-stu-id="12581-112">To create an ESB Itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="12581-113">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="12581-113">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="12581-114">En el Explorador de soluciones, haga clic en **ItineraryLibrary**, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="12581-114">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="12581-115">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **ItineraryDsl** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="12581-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="12581-116">En el **nombre** , escriba **ChoiceRouter**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="12581-116">In the **Name** box, type **ChoiceRouter**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="12581-117">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="12581-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="12581-118">En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario.</span><span class="sxs-lookup"><span data-stu-id="12581-118">In Visual Studio, click the design surface of the **ChoiceRouter** itinerary.</span></span> <span data-ttu-id="12581-119">En el **ChoiceRouter** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-119">In the **ChoiceRouter** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-120">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="12581-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="12581-121">En el **configuración del dispositivo Extender** sección, haga clic en el botón de puntos suspensivos (...) junto a la **archivo XML de itinerario** propiedad.</span><span class="sxs-lookup"><span data-stu-id="12581-121">In the **Extender Settings** section, click the ellipsis button (...) next to the **Itinerary XML file** property.</span></span>  
  
    3.  <span data-ttu-id="12581-122">En el **exportar modo** lista de propiedades de lista desplegable, haga clic en **Strict**.</span><span class="sxs-lookup"><span data-stu-id="12581-122">In the **Export Mode** property drop-down list, click **Strict**.</span></span>  
  
    4.  <span data-ttu-id="12581-123">En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\ChoiceRouter** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="12581-123">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\ChoiceRouter** in the **File name** box, and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12581-124">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="12581-124">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="12581-125">Al exportar un itinerario en una ubicación de archivo local, en lugar de a la base de datos de itinerario, puede probar el itinerario utilizando la aplicación de cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="12581-125">By exporting an itinerary to a local file location, instead of to the itinerary database, you can test the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="12581-126">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="12581-126">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="12581-127">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="12581-127">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="12581-128">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="12581-128">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="12581-129">En la ventana Propiedades de OnRamp1, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-129">In the OnRamp1 Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-130">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="12581-130">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="12581-131">En el **Extender** la lista desplegable, haga clic en **en rampa Extender**.</span><span class="sxs-lookup"><span data-stu-id="12581-131">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-132">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="12581-132">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="12581-133">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="12581-133">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="12581-134">En el cuadro de herramientas, arrastre un **de Service Broker itinerario** elemento a la superficie del diseñador del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-134">From the Toolbox, drag an **Itinerary Broker Service** model element to the designer surface, and then place it to the right side of the **On-Ramp** model element.</span></span> <span data-ttu-id="12581-135">En el **ItineraryBrokerService1**, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-135">In the **ItineraryBrokerService1**, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-136">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteBrokerService**.</span><span class="sxs-lookup"><span data-stu-id="12581-136">Click the **Name** property, and then type **RouteBrokerService**.</span></span>  
  
    2.  <span data-ttu-id="12581-137">En el **Extender** la lista desplegable, haga clic en **extensor de Broker de mensajería**.</span><span class="sxs-lookup"><span data-stu-id="12581-137">In the **Extender** drop-down list, click **Messaging Broker Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-138">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="12581-138">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="12581-139">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**.</span><span class="sxs-lookup"><span data-stu-id="12581-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**.</span></span>  
  
3.  <span data-ttu-id="12581-140">Haga clic en el **filtro** colección y, a continuación, haga clic en **Agregar nuevo filtro**.</span><span class="sxs-lookup"><span data-stu-id="12581-140">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="12581-141">En el **Filter1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-141">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-142">Haga clic en el **nombre** propiedad y, a continuación, escriba **ASMXFilter**.</span><span class="sxs-lookup"><span data-stu-id="12581-142">Click the **Name** property, and then type **ASMXFilter**.</span></span>  
  
    2.  <span data-ttu-id="12581-143">Haga clic en el **filtro** la lista desplegable de implementación y, a continuación, haga clic en **filtro XPath**.</span><span class="sxs-lookup"><span data-stu-id="12581-143">Click the **Filter** Implementation drop-down list, and then click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="12581-144">Haga clic en el **expresión** propiedad y, a continuación, escriba **recuento (/ ContextProperties/propiedad [@name= 'InboundTransportLocation'] [contiene (., 'ProcessItinerary.asmx')]) > 0**.</span><span class="sxs-lookup"><span data-stu-id="12581-144">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ProcessItinerary.asmx')]) > 0**.</span></span>  
  
4.  <span data-ttu-id="12581-145">Haga clic en el **filtro** colección y, a continuación, haga clic en **Agregar nuevo filtro**.</span><span class="sxs-lookup"><span data-stu-id="12581-145">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="12581-146">En el **Filter1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-146">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-147">Haga clic en el **nombre** propiedad y, a continuación, escriba **WCFFilter**.</span><span class="sxs-lookup"><span data-stu-id="12581-147">Click the **Name** property, and then type **WCFFilter**.</span></span>  
  
    2.  <span data-ttu-id="12581-148">Haga clic en el **filtro implementación** lista desplegable y haga clic en **filtro XPath**.</span><span class="sxs-lookup"><span data-stu-id="12581-148">Click the **Filter Implementation** drop-down list, and click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="12581-149">Haga clic en el **expresión** propiedad y, a continuación, escriba **recuento (/ ContextProperties/propiedad [@name= 'InboundTransportLocation'] [contiene (., ' ESB. ItineraryServices.WCF')]) > 0**.</span><span class="sxs-lookup"><span data-stu-id="12581-149">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ESB.ItineraryServices.WCF')]) > 0**.</span></span>  
  
5.  <span data-ttu-id="12581-150">Haga clic en el **resolución** colección de la **RouteBrokerService** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="12581-150">Right-click the **Resolver** collection of the **RouteBrokerService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="12581-151">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-151">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-152">Haga clic en el **nombre** propiedad y, a continuación, escriba **ResolverBrokerRoute**.</span><span class="sxs-lookup"><span data-stu-id="12581-152">Click the **Name** property, and then type **ResolverBrokerRoute**.</span></span>  
  
    2.  <span data-ttu-id="12581-153">En el **implementación de la resolución** la lista desplegable, haga clic en **MessageContext resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="12581-153">In the **Resolver Implementation** drop-down list, click **MessageContext Resolver Extension**.</span></span>  
  
6.  <span data-ttu-id="12581-154">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="12581-154">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="12581-155">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteBrokerService** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-155">Drag a connection from the **ReceiveNAOrder** model element to the **RouteBrokerService** model element.</span></span>  
  
7.  <span data-ttu-id="12581-156">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquela bajo la **RouteBrokerService** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-156">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it under the **RouteBrokerService** model element.</span></span> <span data-ttu-id="12581-157">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-157">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-158">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToFileFromASMX**.</span><span class="sxs-lookup"><span data-stu-id="12581-158">Click the **Name** property, and then type **RouteToFileFromASMX**.</span></span>  
  
    2.  <span data-ttu-id="12581-159">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="12581-159">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="12581-160">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="12581-160">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="12581-161">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="12581-161">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-162">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="12581-162">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="12581-163">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="12581-163">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
8.  <span data-ttu-id="12581-164">Haga clic en el **resolución** colección de la **RouteToFileFromASMX** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="12581-164">Right-click the **Resolver** collection of the **RouteToFileFromASMX** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="12581-165">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-165">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-166">Haga clic en el **nombre** propiedad y, a continuación, escriba **ResolverFromAsmx**.</span><span class="sxs-lookup"><span data-stu-id="12581-166">Click the **Name** property, and then type **ResolverFromAsmx**.</span></span>  
  
    2.  <span data-ttu-id="12581-167">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="12581-167">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="12581-168">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="12581-168">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="12581-169">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **c:\howtos\out\asmx%MessageId%.xml**.</span><span class="sxs-lookup"><span data-stu-id="12581-169">Click the **Transport Location** property, and then type **c:\howtos\out\asmx%MessageId%.xml**.</span></span>  
  
9. <span data-ttu-id="12581-170">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToFileFromASMX** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-170">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromASMX** model element.</span></span> <span data-ttu-id="12581-171">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-171">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-172">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendASMXOrder**.</span><span class="sxs-lookup"><span data-stu-id="12581-172">Click the **Name** property, and then type **SendASMXOrder**.</span></span>  
  
    2.  <span data-ttu-id="12581-173">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="12581-173">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-174">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="12581-174">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="12581-175">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="12581-175">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
10. <span data-ttu-id="12581-176">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToFileFromASMX** elemento del modelo y la **SendASMXOrder**elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-176">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromASMX** model element and the **SendASMXOrder** model element.</span></span> <span data-ttu-id="12581-177">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-177">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-178">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilterASMX**.</span><span class="sxs-lookup"><span data-stu-id="12581-178">Click the **Name** property, and then type **SendPortFilterASMX**.</span></span>  
  
    2.  <span data-ttu-id="12581-179">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="12581-179">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-180">En el **fuera de rampa** lista desplegable lista, expanda **SendASMXOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="12581-180">In the **Off-Ramp** drop-down list, expand **SendASMXOrder**, and then click **Send Handlers**.</span></span>  
  
11. <span data-ttu-id="12581-181">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="12581-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="12581-182">Arrastre una conexión desde el **RouteToFileFromASMX** elemento de modelo para el **SendPortFilterASMX** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-182">Drag a connection from the **RouteToFileFromASMX** model element to the **SendPortFilterASMX** model element.</span></span>  
  
12. <span data-ttu-id="12581-183">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="12581-183">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="12581-184">Arrastre una conexión desde el **SendPortFilterASMX** elemento de modelo para el **SendASMXOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-184">Drag a connection from the **SendPortFilterASMX** model element to the **SendASMXOrder** model element.</span></span>  
  
13. <span data-ttu-id="12581-185">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha del **RouteBrokerService** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-185">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of **RouteBrokerService** model element.</span></span> <span data-ttu-id="12581-186">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-186">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-187">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToFileFromWCF**.</span><span class="sxs-lookup"><span data-stu-id="12581-187">Click the **Name** property, and then type **RouteToFileFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="12581-188">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="12581-188">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="12581-189">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="12581-189">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="12581-190">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="12581-190">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-191">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="12581-191">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="12581-192">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="12581-192">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
14. <span data-ttu-id="12581-193">Haga clic en el **resolución** colección de la **RouteToFileFromWCF** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="12581-193">Right-click the **Resolver** collection of the **RouteToFileFromWCF** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="12581-194">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-194">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-195">Haga clic en el **nombre** propiedad y, a continuación, escriba **ResolverFromWCF**.</span><span class="sxs-lookup"><span data-stu-id="12581-195">Click the **Name** property, and then type **ResolverFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="12581-196">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="12581-196">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="12581-197">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="12581-197">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="12581-198">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **c:\howtos\out\wcf%MessageId%.xml**.</span><span class="sxs-lookup"><span data-stu-id="12581-198">Click the **Transport Location** property, and then type **c:\howtos\out\wcf%MessageId%.xml**.</span></span>  
  
15. <span data-ttu-id="12581-199">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToFileFromWCF** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-199">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromWCF** model element.</span></span> <span data-ttu-id="12581-200">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-200">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-201">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendWCFOrder**.</span><span class="sxs-lookup"><span data-stu-id="12581-201">Click the **Name** property, and then type **SendWCFOrder**.</span></span>  
  
    2.  <span data-ttu-id="12581-202">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="12581-202">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-203">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="12581-203">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="12581-204">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="12581-204">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
16. <span data-ttu-id="12581-205">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToFileFromWCF** elemento del modelo y la **SendWCFOrder**elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-205">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromWCF** model element and the **SendWCFOrder** model element.</span></span> <span data-ttu-id="12581-206">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-206">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-207">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilterWCF**.</span><span class="sxs-lookup"><span data-stu-id="12581-207">Click the **Name** property, and then type **SendPortFilterWCF**.</span></span>  
  
    2.  <span data-ttu-id="12581-208">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="12581-208">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="12581-209">En el **fuera de rampa** lista desplegable lista, expanda **SendWCFOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="12581-209">In the **Off-Ramp** drop-down list, expand **SendWCFOrder**, and then click **Send Handlers**.</span></span>  
  
17. <span data-ttu-id="12581-210">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="12581-210">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="12581-211">Arrastre una conexión desde el **RouteToFileFromWCF** elemento de modelo para el **SendPortFilterWCF** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-211">Drag a connection from the **RouteToFileFromWCF** model element to the **SendPortFilterWCF** model element.</span></span>  
  
18. <span data-ttu-id="12581-212">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="12581-212">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="12581-213">Arrastre una conexión desde el **SendPortFilterWCF** elemento de modelo para el **SendWCFOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-213">Drag a connection from the **SendPortFilterWCF** model element to the **SendWCFOrder** model element.</span></span>  
  
19. <span data-ttu-id="12581-214">En el cuadro de herramientas, arrastre un **itinerario Outport** al borde derecho del elemento del modelo **RouteBrokerService**.</span><span class="sxs-lookup"><span data-stu-id="12581-214">From the Toolbox, drag an **Itinerary Outport** model element to right border of **RouteBrokerService**.</span></span> <span data-ttu-id="12581-215">En el **ItineraryBrokerOutPort1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-215">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-216">Haga clic en el **nombre** propiedad y, a continuación, escriba **puerto WCF**.</span><span class="sxs-lookup"><span data-stu-id="12581-216">Click the **Name** property, and then type **WCF Port**.</span></span>  
  
    2.  <span data-ttu-id="12581-217">En el **filtro** la lista desplegable, haga clic en **WCFFilter**.</span><span class="sxs-lookup"><span data-stu-id="12581-217">In the **Filter** drop-down list, click **WCFFilter**.</span></span>  
  
    3.  <span data-ttu-id="12581-218">En el **resolución** la lista desplegable, haga clic en **ResolverBrokerRoute**.</span><span class="sxs-lookup"><span data-stu-id="12581-218">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
20. <span data-ttu-id="12581-219">En el cuadro de herramientas, arrastre un **itinerario Outport** elemento de modelo para el borde inferior del **RouteBrokerService**.</span><span class="sxs-lookup"><span data-stu-id="12581-219">From the Toolbox, drag an **Itinerary Outport** model element to the bottom border of **RouteBrokerService**.</span></span> <span data-ttu-id="12581-220">En el **ItineraryBrokerOutPort1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="12581-220">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="12581-221">Haga clic en el **nombre** propiedad y, a continuación, escriba **ASMX puerto**.</span><span class="sxs-lookup"><span data-stu-id="12581-221">Click the **Name** property, and then type **ASMX Port**.</span></span>  
  
    2.  <span data-ttu-id="12581-222">En el **filtro** la lista desplegable, haga clic en **ASMXFilter**.</span><span class="sxs-lookup"><span data-stu-id="12581-222">In the **Filter** drop-down list, click **ASMXFilter**.</span></span>  
  
    3.  <span data-ttu-id="12581-223">En el **resolución** la lista desplegable, haga clic en **ResolverBrokerRoute**.</span><span class="sxs-lookup"><span data-stu-id="12581-223">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
21. <span data-ttu-id="12581-224">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="12581-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="12581-225">Arrastre una conexión desde el **puerto WCF** elemento de modelo para el **RouteToFileFromWCF** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-225">Drag a connection from the **WCF Port** model element to the **RouteToFileFromWCF** model element.</span></span>  
  
22. <span data-ttu-id="12581-226">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="12581-226">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="12581-227">Arrastre una conexión desde el **puerto ASMX** elemento de modelo para el **RouteToFileFromASMX** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="12581-227">Drag a connection from the **ASMX Port** model element to the **RouteToFileFromASMX** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="12581-228">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="12581-228">To export the model for use with the Itinerary Test Client</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12581-229">Debe exportar el itinerario dos veces: una vez en XML y una hora para la base de datos para probar el enrutamiento mediante el agente.</span><span class="sxs-lookup"><span data-stu-id="12581-229">You will need to export the itinerary twice: one time in XML and one time to the database to test the routing through the broker.</span></span>  
  
1.  <span data-ttu-id="12581-230">En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="12581-230">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12581-231">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="12581-231">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="12581-232">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y, a continuación, observe la creación de su itinerario XML (ChoiceRouter.xml).</span><span class="sxs-lookup"><span data-stu-id="12581-232">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (ChoiceRouter.xml).</span></span>  
  
3.  <span data-ttu-id="12581-233">En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="12581-233">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
4.  <span data-ttu-id="12581-234">En la ventana Propiedades, haga clic en **base de datos de itinerario exportador** en el **modelo exportador** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="12581-234">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
5.  <span data-ttu-id="12581-235">En la ventana Propiedades, establezca la **base de datos de itinerario** cadena de conexión de la propiedad para que apunte a la base de datos de itinerario.</span><span class="sxs-lookup"><span data-stu-id="12581-235">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
6.  <span data-ttu-id="12581-236">En el **estado de itinerario** propiedad lista desplegable seleccione **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="12581-236">In the **Itinerary Status** property drop-down list select **Deployed**.</span></span>  
  
7.  <span data-ttu-id="12581-237">En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="12581-237">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="12581-238">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="12581-238">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="12581-239">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="12581-239">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="12581-240">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="12581-240">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="12581-241">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="12581-241">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="12581-242">Seleccione **ChoiceRouter.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="12581-242">Select **ChoiceRouter.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="12581-243">Haga clic en **Aceptar** para cerrar el mensaje "Itinerario cargó correctamente".</span><span class="sxs-lookup"><span data-stu-id="12581-243">Click **OK** to close the "Itinerary Loaded Successfully" message.</span></span>  
  
5.  <span data-ttu-id="12581-244">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="12581-244">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="12581-245">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\Patterns\HowTos.</span><span class="sxs-lookup"><span data-stu-id="12581-245">In the **Select XML Document to load** dialog box, browse to C:\Patterns\HowTos.</span></span> <span data-ttu-id="12581-246">Seleccione NAOrderDoc.xml y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="12581-246">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="12581-247">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="12581-247">Click the **Submit Request** button.</span></span> <span data-ttu-id="12581-248">Cuando se complete la prueba, haga clic en **Aceptar** para cerrar el mensaje de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="12581-248">When the test completes, click **OK** to close the confirmation message that appears.</span></span>  
  
8.  <span data-ttu-id="12581-249">En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se han escrito los mensajes ASMX%MessageID%.xml a este directorio.</span><span class="sxs-lookup"><span data-stu-id="12581-249">In Windows Explorer, browse to C:\HowTos\Out. Verify that the ASMX%MessageID%.xml messages have been written to this directory.</span></span>  
  
9. <span data-ttu-id="12581-250">Haga clic en el cliente de prueba de itinerario **usar el servicio de WCF** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="12581-250">Click the Itinerary Test client **Use WCF Service** check box.</span></span> <span data-ttu-id="12581-251">En el **itinerario nombre** , escriba **ChoiceRouter**y, a continuación, haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="12581-251">In the **Itinerary Name** box, type **ChoiceRouter**, and then click the **Submit Request** button.</span></span> <span data-ttu-id="12581-252">Cuando se complete la prueba, haga clic en **Aceptar** para cerrar el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="12581-252">When the test completes, click **OK** to close the confirmation message.</span></span>  
  
10. <span data-ttu-id="12581-253">En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se han escrito los mensajes WCF%MessageID%.xml a este directorio.</span><span class="sxs-lookup"><span data-stu-id="12581-253">In Windows Explorer, browse to C:\HowTos\Out. Verify that the WCF%MessageID%.xml messages have been written to this directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="12581-254">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="12581-254">Additional Resources</span></span>  
 <span data-ttu-id="12581-255">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="12581-255">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="12581-256">Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="12581-256">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="12581-257">Cómo: dinámicamente enrutar un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="12581-257">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="12581-258">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="12581-258">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="12581-259">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="12581-259">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)