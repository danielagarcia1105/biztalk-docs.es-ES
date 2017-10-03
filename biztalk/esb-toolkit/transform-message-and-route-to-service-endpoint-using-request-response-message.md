---
title: "Cómo: transformar un mensaje y una ruta a un extremo de servicio mediante un patrón de intercambio de mensajes de solicitud-respuesta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfc7c7d572f3370e87df2f03d392a993116b74d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a><span data-ttu-id="f78e5-102">Cómo: transformar un mensaje y una ruta a un extremo de servicio mediante un patrón de intercambio de mensajes de solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="f78e5-102">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>
## <a name="goal"></a><span data-ttu-id="f78e5-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="f78e5-103">Goal</span></span>  
 <span data-ttu-id="f78e5-104">Esta sección muestra cómo utilizar el lenguaje de ESB diseñador específico de dominio (DSL) para crear un itinerario de solicitudes y respuestas que se puede utilizar con un aumento bidireccional.</span><span class="sxs-lookup"><span data-stu-id="f78e5-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create a request-response itinerary that can be used with a two-way on-ramp.</span></span> <span data-ttu-id="f78e5-105">Se creará una lista de distribución para recibir un mensaje, transformar el mensaje, envía el mensaje a un servicio y devolver el mensaje de respuesta de servicio para el remitente del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="f78e5-105">You will create a routing slip to receive a message, transform the message, submit the message to a service, and return the service response message to the submitter of the original message.</span></span>  
  
 <span data-ttu-id="f78e5-106">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f78e5-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="f78e5-107">Crear una lista de distribución itinerario con un servicio de itinerarios de transformación que implementa una asignación de Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f78e5-107">Create an itinerary routing slip with a transform itinerary service that implements a Microsoft BizTalk Server map.</span></span>  
  
-   <span data-ttu-id="f78e5-108">Configurar el itinerario para enrutar el mensaje transformado a un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="f78e5-108">Configure the itinerary to route the transformed message to a service endpoint.</span></span>  
  
-   <span data-ttu-id="f78e5-109">Configurar el itinerario para devolver el mensaje de respuesta de servicio a la entidad remitente original.</span><span class="sxs-lookup"><span data-stu-id="f78e5-109">Configure the itinerary to return the service response message to the original sending party.</span></span>  
  
-   <span data-ttu-id="f78e5-110">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="f78e5-110">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f78e5-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f78e5-111">Prerequisites</span></span>  
 <span data-ttu-id="f78e5-112">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="f78e5-112">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="f78e5-113">Pasos</span><span class="sxs-lookup"><span data-stu-id="f78e5-113">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="f78e5-114">Para crear un modelo DSL itinerario de ESB</span><span class="sxs-lookup"><span data-stu-id="f78e5-114">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="f78e5-115">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="f78e5-115">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="f78e5-116">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-116">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="f78e5-117">En el **Agregar nuevo elemento** cuadro de diálogo, en la **nombre** , escriba **RequestResponse**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-117">In the **Add New Item** dialog box, in the **Name** box, type **RequestResponse**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="f78e5-118">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="f78e5-118">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="f78e5-119">En Visual Studio, haga clic en la superficie de diseño de **RequestResponse.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-119">In Visual Studio, click the design surface of **RequestResponse.itinerary**.</span></span> <span data-ttu-id="f78e5-120">En el **RequestResponse** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-120">In the **RequestResponse** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-121">En el **respuesta de solicitud es** la lista desplegable, haga clic en **True**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-121">In the **Is Request Response** drop-down list, click **True**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-122">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-123">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="f78e5-123">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    4.  <span data-ttu-id="f78e5-124">En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\RequestResponse**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-124">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RequestResponse**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f78e5-125">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="f78e5-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="f78e5-126">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="f78e5-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="f78e5-127">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="f78e5-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="f78e5-128">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="f78e5-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="f78e5-129">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="f78e5-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="f78e5-130">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-131">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-132">En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-133">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="f78e5-134">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary.Response**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  
  
2.  <span data-ttu-id="f78e5-135">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="f78e5-136">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-137">Haga clic en el **nombre** propiedad y, a continuación, escriba **MapNAOrderToCNOrder**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-137">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-138">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f78e5-139">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="f78e5-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="f78e5-140">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-141">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="f78e5-142">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="f78e5-143">Haga clic en el **resolución** colección de la **MapNAOrderToCNOrder** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-143">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="f78e5-144">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-145">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticallySpecifyTheMap**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-145">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-146">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-146">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-147">En el **transformar tipo** la lista desplegable, haga clic en **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-147">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
4.  <span data-ttu-id="f78e5-148">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-148">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f78e5-149">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **MapNAOrderToCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-149">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="f78e5-150">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **MapNAOrderToCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-150">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="f78e5-151">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-151">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-152">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToCNService**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-152">Click the **Name** property, and then type **RouteToCNService**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-153">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-153">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f78e5-154">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="f78e5-154">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="f78e5-155">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-155">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-156">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-156">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="f78e5-157">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-157">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
6.  <span data-ttu-id="f78e5-158">Haga clic en el **resolución** colección de la **RouteToCNService** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-158">Right-click the **Resolver** collection of the **RouteToCNService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="f78e5-159">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-160">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticallySpecifyTheService**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-160">Click the **Name** property, and then type **StaticallySpecifyTheService**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-161">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-162">En el **nombre del transporte** la lista desplegable, haga clic en **WCF-BasicHttp**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-162">In the **Transport Name** drop-down list, click **WCF-BasicHttp**.</span></span>  
  
    4.  <span data-ttu-id="f78e5-163">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-163">Click the **Transport Location** property, and then type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  
  
    5.  <span data-ttu-id="f78e5-164">Haga clic en el **Target Namespace** propiedad y, a continuación, escriba **http://globalbank.esb.dynamicresolution.com/canadianservices**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-164">Click the **Target Namespace** property, and then type **http://globalbank.esb.dynamicresolution.com/canadianservices**.</span></span>  
  
    6.  <span data-ttu-id="f78e5-165">Haga clic en el **acción** propiedad y, a continuación, escriba **submitOrder**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-165">Click the **Action** property, and then type **submitOrder**.</span></span>  
  
7.  <span data-ttu-id="f78e5-166">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f78e5-167">Arrastre una conexión desde el **MapNAOrderToCNOrder** elemento de modelo para el **RouteToCNService** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **RouteToCNService** model element.</span></span>  
  
8.  <span data-ttu-id="f78e5-168">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToCNService** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToCNService** model element.</span></span> <span data-ttu-id="f78e5-169">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-170">Haga clic en el **nombre** propiedad y, a continuación, escriba **InvokeCNService**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-170">Click the **Name** property, and then type **InvokeCNService**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-171">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-172">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="f78e5-173">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionSolicitResp**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-173">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  
  
9. <span data-ttu-id="f78e5-174">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToCNService** elemento del modelo y la **InvokeCNService**elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToCNService** model element and the **InvokeCNService** model element.</span></span> <span data-ttu-id="f78e5-175">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f78e5-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f78e5-176">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="f78e5-177">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="f78e5-178">En el **fuera de rampa** lista desplegable lista, expanda **InvokeCNService**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-178">In the **Off-Ramp** drop-down list, expand **InvokeCNService**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="f78e5-179">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f78e5-180">Arrastre una conexión desde el **RouteToCNService** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-180">Drag a connection from the **RouteToCNService** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="f78e5-181">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f78e5-182">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **InvokeCNService** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="f78e5-182">Drag a connection from the **SendPortFilter** model element to the **InvokeCNService** model element.</span></span>  
  
12. <span data-ttu-id="f78e5-183">Haga clic en la superficie de diseño y, a continuación, haga clic en **validar**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-183">Right-click the design surface, and then click **Validate**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f78e5-184">Valida el itinerario; no es necesario volver a conectar fuera de rampa con el aumento con el fin de enviar el mensaje de respuesta a la entidad que lo solicita.</span><span class="sxs-lookup"><span data-stu-id="f78e5-184">The itinerary validates; it is not necessary to connect the off-ramp back to the on-ramp in order to send the response message back to the requesting party.</span></span> <span data-ttu-id="f78e5-185">Mediante el uso de un aumento bidireccional, el mensaje final se devuelve automáticamente a la entidad que lo solicita.</span><span class="sxs-lookup"><span data-stu-id="f78e5-185">By using a two-way on-ramp, the final message is automatically returned to the requesting party.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="f78e5-186">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="f78e5-186">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="f78e5-187">En Visual Studio, haga clic en la superficie de diseño de la **RequestResponse** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-187">In Visual Studio, right-click the design surface of the **RequestResponse** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f78e5-188">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f78e5-188">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f78e5-189">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f78e5-189">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="f78e5-190">En el Explorador de Windows, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="f78e5-190">In Windows Explorer, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="f78e5-191">Tenga en cuenta la creación de su itinerario XML (RequestResponse.xml).</span><span class="sxs-lookup"><span data-stu-id="f78e5-191">Notice the creation of your itinerary XML (RequestResponse.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="f78e5-192">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="f78e5-192">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="f78e5-193">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="f78e5-193">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="f78e5-194">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="f78e5-194">In the Itinerary Test Client, clear the **Use WCF Service** check box.</span></span>  
  
3.  <span data-ttu-id="f78e5-195">En el **opciones del servicio Web** sección, seleccione la **dos servicios de manera** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-195">In the **Web Service Options** section, select the **Two Way Service** check box, and then click **Load Itinerary**.</span></span>  
  
4.  <span data-ttu-id="f78e5-196">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="f78e5-196">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="f78e5-197">Seleccione **RequestResponse.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="f78e5-197">Select **RequestResponse.xml**, and then click **Open** to load the itinerary.</span></span>  
  
5.  <span data-ttu-id="f78e5-198">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="f78e5-198">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
6.  <span data-ttu-id="f78e5-199">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="f78e5-199">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
7.  <span data-ttu-id="f78e5-200">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="f78e5-200">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="f78e5-201">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="f78e5-201">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
8.  <span data-ttu-id="f78e5-202">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="f78e5-202">Click the **Submit Request** button.</span></span> <span data-ttu-id="f78e5-203">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="f78e5-203">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
9. <span data-ttu-id="f78e5-204">En el **resultados** cuadro, observe el nodo de raíz del mensaje es **submitOrderResponse** y el espacio de nombres predeterminado es... **canadianservices**.</span><span class="sxs-lookup"><span data-stu-id="f78e5-204">In the **Results** box, notice the message's root node is **submitOrderResponse** and the default namespace is ... **canadianservices**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f78e5-205">Si el mensaje de respuesta requiere transformación adicional antes de que la respuesta se envía a la entidad de solicitud, debe utilizar una canalización que contiene el componente de reenviador de ESB.</span><span class="sxs-lookup"><span data-stu-id="f78e5-205">If the response message requires additional transformation before the response is sent to the requesting party, you must use a pipeline that contains the ESB Forwarder component.</span></span> <span data-ttu-id="f78e5-206">Para obtener un ejemplo de esta funcionalidad, consulte la [instalar y ejecutar el ejemplo de servicios Web varios](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f78e5-206">For an example of this functionality, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="f78e5-207">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f78e5-207">Additional Resources</span></span>  
 <span data-ttu-id="f78e5-208">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="f78e5-208">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="f78e5-209">Cómo: transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución itinerario</span><span class="sxs-lookup"><span data-stu-id="f78e5-209">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="f78e5-210">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="f78e5-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="f78e5-211">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="f78e5-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="f78e5-212">Instalar y ejecutar el ejemplo de servicios Web varios</span><span class="sxs-lookup"><span data-stu-id="f78e5-212">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)