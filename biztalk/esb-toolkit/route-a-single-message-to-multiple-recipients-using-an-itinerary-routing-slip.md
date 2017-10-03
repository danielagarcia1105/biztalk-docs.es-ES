---
title: "Cómo: enrutar un mensaje único a varios destinatarios mediante una lista de distribución itinerarios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c30493-4fe1-4fd5-8bc7-af091535b091
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fa96603bc93c9d5d19ef102695a1189a50d00ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip"></a><span data-ttu-id="389a9-102">Cómo: enrutar un mensaje único a varios destinatarios mediante una lista de distribución itinerarios</span><span class="sxs-lookup"><span data-stu-id="389a9-102">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="389a9-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="389a9-103">Goal</span></span>  
 <span data-ttu-id="389a9-104">Esta sección muestra cómo utilizar el lenguaje de diseñador específico de dominio (DSL) para crear un itinerario que enruta un mensaje a tres destinatarios distintos con una resolución estática y la [!INCLUDE[prague](../includes/prague-md.md)] adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="389a9-104">This section demonstrates how to use the Designer domain-specific language (DSL) to create an itinerary that routes a message to three distinct recipients using a static resolver and the [!INCLUDE[prague](../includes/prague-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="389a9-105">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="389a9-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="389a9-106">Crear un itinerario con tres resoluciones estáticas para enrutar mensajes a varios destinatarios.</span><span class="sxs-lookup"><span data-stu-id="389a9-106">Create an itinerary with three static resolvers to route messages to multiple recipients.</span></span>  
  
-   <span data-ttu-id="389a9-107">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="389a9-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="389a9-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="389a9-108">Prerequisites</span></span>  
 <span data-ttu-id="389a9-109">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="389a9-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="389a9-110">Pasos</span><span class="sxs-lookup"><span data-stu-id="389a9-110">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="389a9-111">Para crear un modelo DSL itinerario de ESB</span><span class="sxs-lookup"><span data-stu-id="389a9-111">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="389a9-112">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="389a9-112">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="389a9-113">En el Explorador de soluciones, haga clic en **ItineraryLibrary**, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="389a9-113">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="389a9-114">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **ItineraryDsl** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="389a9-114">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="389a9-115">En el **nombre** , escriba **RecipientList**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="389a9-115">In the **Name** box, type **RecipientList**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="389a9-116">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="389a9-116">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="389a9-117">En Visual Studio, haga clic en la superficie de diseño de RecipientList.itinerary.</span><span class="sxs-lookup"><span data-stu-id="389a9-117">In Visual Studio, click the design surface of RecipientList.itinerary.</span></span> <span data-ttu-id="389a9-118">En la ventana Propiedades de RecipientList, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-118">In the RecipientList Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-119">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="389a9-119">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="389a9-120">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="389a9-120">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="389a9-121">En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\RecipientList**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="389a9-121">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RecipientList**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="389a9-122">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="389a9-122">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="389a9-123">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="389a9-123">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="389a9-124">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="389a9-124">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="389a9-125">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="389a9-125">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="389a9-126">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="389a9-126">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="389a9-127">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-127">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-128">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="389a9-128">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="389a9-129">En el **Extender** la lista desplegable, haga clic en **en rampa Extender**.</span><span class="sxs-lookup"><span data-stu-id="389a9-129">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="389a9-130">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="389a9-130">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="389a9-131">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="389a9-131">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="389a9-132">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="389a9-132">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="389a9-133">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-133">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-134">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToThreeRecipients**.</span><span class="sxs-lookup"><span data-stu-id="389a9-134">Click the **Name** property, and then type **RouteToThreeRecipients**.</span></span>  
  
    2.  <span data-ttu-id="389a9-135">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="389a9-135">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="389a9-136">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="389a9-136">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="389a9-137">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="389a9-137">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="389a9-138">En el **contenedor** lista desplegable lista, expanda **ReceiveNaOrderDoc**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="389a9-138">In the **Container** drop-down list, expand **ReceiveNaOrderDoc**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="389a9-139">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="389a9-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="389a9-140">Haga clic en el **resolución** colección de la **RouteToThreeRecipients** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="389a9-140">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="389a9-141">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-141">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-142">Haga clic en el **nombre** propiedad y, a continuación, escriba **FirstResolver**.</span><span class="sxs-lookup"><span data-stu-id="389a9-142">Click the **Name** property, and then type **FirstResolver**.</span></span>  
  
    2.  <span data-ttu-id="389a9-143">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="389a9-143">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="389a9-144">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="389a9-144">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="389a9-145">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\First%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="389a9-145">Click the **Transport Location** property, and then type **C:\HowTos\Out\First%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="389a9-146">Ha agregado el primero de los tres resoluciones para este servicio itinerario.</span><span class="sxs-lookup"><span data-stu-id="389a9-146">You have added the first of three resolvers for this itinerary service.</span></span> <span data-ttu-id="389a9-147">Ahora, agregará dos resoluciones más para enrutar el mensaje a los destinatarios adicionales.</span><span class="sxs-lookup"><span data-stu-id="389a9-147">You will now add two more resolvers to route the message to additional recipients.</span></span>  
  
4.  <span data-ttu-id="389a9-148">Haga clic en el **resolución** colección de la **RouteToThreeRecipients** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="389a9-148">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="389a9-149">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-149">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-150">Haga clic en el **nombre** propiedad y, a continuación, escriba **SecondResolver**.</span><span class="sxs-lookup"><span data-stu-id="389a9-150">Click the **Name** property, and then type **SecondResolver**.</span></span>  
  
    2.  <span data-ttu-id="389a9-151">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="389a9-151">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="389a9-152">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="389a9-152">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="389a9-153">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\Second%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="389a9-153">Click the **Transport Location** property, and then type **C:\HowTos\Out\Second%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="389a9-154">Haga clic en el **resolución** colección de la **RouteToThreeRecipients** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="389a9-154">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="389a9-155">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-155">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-156">Haga clic en el **nombre** propiedad y, a continuación, escriba **ThirdResolver**.</span><span class="sxs-lookup"><span data-stu-id="389a9-156">Click the **Name** property, and then type **ThirdResolver**.</span></span>  
  
    2.  <span data-ttu-id="389a9-157">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="389a9-157">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="389a9-158">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="389a9-158">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="389a9-159">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\Third%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="389a9-159">Click the **Transport Location** property, and then type **C:\HowTos\Out\Third%MessageID%.xml**.</span></span>  
  
6.  <span data-ttu-id="389a9-160">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="389a9-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="389a9-161">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteToThreeRecipients** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="389a9-161">Drag a connection from the **ReceiveNAOrder** model element to the **RouteToThreeRecipients** model element.</span></span>  
  
7.  <span data-ttu-id="389a9-162">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToThreeRecipients** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="389a9-162">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToThreeRecipients** model element.</span></span> <span data-ttu-id="389a9-163">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-163">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-164">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendThreeMessages**.</span><span class="sxs-lookup"><span data-stu-id="389a9-164">Click the **Name** property, and then type **SendThreeMessages**.</span></span>  
  
    2.  <span data-ttu-id="389a9-165">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="389a9-165">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="389a9-166">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="389a9-166">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="389a9-167">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="389a9-167">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
8.  <span data-ttu-id="389a9-168">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToThreeRecipients** elemento del modelo y la **SendThreeMessages** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="389a9-168">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToThreeRecipients** model element and the **SendThreeMessages** model element.</span></span> <span data-ttu-id="389a9-169">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="389a9-169">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="389a9-170">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="389a9-170">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="389a9-171">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="389a9-171">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="389a9-172">En el **fuera de rampa** lista desplegable lista, expanda **SendThreeMessages**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="389a9-172">In the **Off-Ramp** drop-down list, expand **SendThreeMessages**, and then click **Send Handlers**.</span></span>  
  
9. <span data-ttu-id="389a9-173">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="389a9-173">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="389a9-174">Arrastre una conexión desde el **RouteToThreeRecipients** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="389a9-174">Drag a connection from the **RouteToThreeRecipients** model element to the **SendPortFilter** model element.</span></span>  
  
10. <span data-ttu-id="389a9-175">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="389a9-175">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="389a9-176">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendThreeMessages** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="389a9-176">Drag a connection from the **SendPortFilter** model element to the **SendThreeMessages** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="389a9-177">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="389a9-177">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="389a9-178">En Visual Studio, haga clic en la superficie de diseño de la **RecipientList** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="389a9-178">In Visual Studio, right-click the design surface of the **RecipientList** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="389a9-179">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="389a9-179">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="389a9-180">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="389a9-180">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="389a9-181">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y, a continuación, observe la creación de su itinerario XML (RecipientList.xml).</span><span class="sxs-lookup"><span data-stu-id="389a9-181">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (RecipientList.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="389a9-182">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="389a9-182">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="389a9-183">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="389a9-183">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="389a9-184">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="389a9-184">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="389a9-185">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="389a9-185">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="389a9-186">Seleccione **RecipientList.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="389a9-186">Select **RecipientList.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="389a9-187">Haga clic en **Aceptar** para borrar la "itinerario se cargó correctamente: mensaje.</span><span class="sxs-lookup"><span data-stu-id="389a9-187">Click **OK** to clear the "Itinerary Loaded Successfully: message.</span></span>  
  
5.  <span data-ttu-id="389a9-188">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="389a9-188">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="389a9-189">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\Patterns.</span><span class="sxs-lookup"><span data-stu-id="389a9-189">In the **Select XML Document to load** dialog box, browse to C:\Patterns.</span></span> <span data-ttu-id="389a9-190">Seleccione NAOrderDoc.xml y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="389a9-190">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="389a9-191">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="389a9-191">Click the **Submit Request** button.</span></span> <span data-ttu-id="389a9-192">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="389a9-192">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="389a9-193">En el Explorador de Windows, vaya a C:\HowTos\Out\\.</span><span class="sxs-lookup"><span data-stu-id="389a9-193">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="389a9-194">Compruebe que los mensajes siguientes se han escrito en el directorio:</span><span class="sxs-lookup"><span data-stu-id="389a9-194">Verify that the following messages have been written to the directory:</span></span>  
  
    -   <span data-ttu-id="389a9-195">First%MessageID%.Xml</span><span class="sxs-lookup"><span data-stu-id="389a9-195">First%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="389a9-196">Second%MessageID%.Xml</span><span class="sxs-lookup"><span data-stu-id="389a9-196">Second%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="389a9-197">Third%MessageID%.Xml</span><span class="sxs-lookup"><span data-stu-id="389a9-197">Third%MessageID%.xml</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="389a9-198">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="389a9-198">Additional Resources</span></span>  
 <span data-ttu-id="389a9-199">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="389a9-199">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="389a9-200">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="389a9-200">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="389a9-201">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="389a9-201">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="389a9-202">Uso de resolución dinámica y enrutamiento</span><span class="sxs-lookup"><span data-stu-id="389a9-202">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)