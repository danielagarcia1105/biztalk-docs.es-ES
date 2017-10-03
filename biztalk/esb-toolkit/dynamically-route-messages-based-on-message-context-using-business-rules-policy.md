---
title: "Cómo: dinámicamente enrutar un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717e0180ba92d49751342e00a4d0367832084135
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a><span data-ttu-id="87348-102">Cómo: dinámicamente enrutar un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="87348-102">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="87348-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="87348-103">Goal</span></span>  
 <span data-ttu-id="87348-104">En esta sección se muestra cómo crear un itinerario que determina los puntos de conexión de mensaje, en función de propiedades de contexto de mensaje con un [!INCLUDE[prague](../includes/prague-md.md)] directiva del motor de reglas de negocios (BRE) y, a continuación, las rutas el mensaje mediante la [!INCLUDE[prague](../includes/prague-md.md)] adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="87348-104">This section demonstrates how to create an itinerary that determines message endpoints, based on message context properties, using a [!INCLUDE[prague](../includes/prague-md.md)] Business Rules Engine (BRE) policy, and then routes the message using the [!INCLUDE[prague](../includes/prague-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="87348-105">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="87348-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="87348-106">Crear una directiva de reglas de negocios para evaluar el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="87348-106">Create a business rules policy to evaluate message type.</span></span>  
  
-   <span data-ttu-id="87348-107">Crear una lista de distribución itinerario para dirigir de manera dinámica mediante una directiva de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="87348-107">Create an itinerary routing slip to dynamically route using a business rules policy.</span></span>  
  
-   <span data-ttu-id="87348-108">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="87348-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87348-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="87348-109">Prerequisites</span></span>  
 <span data-ttu-id="87348-110">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="87348-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="87348-111">Pasos</span><span class="sxs-lookup"><span data-stu-id="87348-111">Steps</span></span>  
 <span data-ttu-id="87348-112">**Para crear una directiva del BRE para enrutar un mensaje con propiedades de contexto de mensaje**</span><span class="sxs-lookup"><span data-stu-id="87348-112">**To create a BRE policy to route a message using message context properties**</span></span>  
  
1.  <span data-ttu-id="87348-113">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione  **[!INCLUDE[prague](../includes/prague-md.md)]** y, a continuación, haga clic en **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="87348-113">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="87348-114">En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="87348-114">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="87348-115">Nombre de la directiva **RouteBasedOnMessageType**.</span><span class="sxs-lookup"><span data-stu-id="87348-115">Name the policy **RouteBasedOnMessageType**.</span></span>  
  
 <span data-ttu-id="87348-116">**Para agregar una regla de enrutamiento para los pedidos de América del Norte**</span><span class="sxs-lookup"><span data-stu-id="87348-116">**To add a routing rule for North American orders**</span></span>  
  
1.  <span data-ttu-id="87348-117">En el **RouteBasedOnMessageType** directiva, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="87348-117">In the **RouteBasedOnMessageType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="87348-118">Nombre de la regla **SetNAOrderEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="87348-118">Name the rule **SetNAOrderEndpoint**.</span></span>  
  
2.  <span data-ttu-id="87348-119">En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.</span><span class="sxs-lookup"><span data-stu-id="87348-119">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
3.  <span data-ttu-id="87348-120">En el Explorador de hechos, expanda el **ESB. ContextInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **tipo de mensaje de contexto** hecho a la **argumento1** nodo bajo  **Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="87348-120">In Facts Explorer, expand the **ESB.ContextInfo** vocabulary, expand **Version 1.0**, and then drag the **Context Message Type** fact to the **argument1** node under **Conditions**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87348-121">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varios vocabularios que pueden usarse para crear reglas.</span><span class="sxs-lookup"><span data-stu-id="87348-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules.</span></span> <span data-ttu-id="87348-122">Algunos de ellos deben reemplazarse o ampliada con sus propios vocabularios.</span><span class="sxs-lookup"><span data-stu-id="87348-122">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="87348-123">Por ejemplo, el **DynamicRunTimeMaptypes** directiva tiene definiciones de las asignaciones proporcionadas en el **GlobalBank** ejemplos.</span><span class="sxs-lookup"><span data-stu-id="87348-123">For example, the **DynamicRunTimeMaptypes** policy has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
4.  <span data-ttu-id="87348-124">Haga clic en el **argumento2** nodo y, a continuación, escriba **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span><span class="sxs-lookup"><span data-stu-id="87348-124">Click the **argument2** node, and then type **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span></span>  
  
5.  <span data-ttu-id="87348-125">En el Explorador de hechos, expanda el **ESB. EndPointInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **establecer ubicación de transporte saliente de punto final** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="87348-125">In Facts Explorer, expand the **ESB.EndPointInfo** vocabulary, expand **Version 1.0**, and then drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
6.  <span data-ttu-id="87348-126">Haga clic en  **\<una cadena vacía >**y, a continuación, escriba **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="87348-126">Click **\<empty string>**, and then type **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span></span>  
  
7.  <span data-ttu-id="87348-127">En el Explorador de hechos, arrastre el **establecer tipo de transporte saliente de punto final** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="87348-127">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
8.  <span data-ttu-id="87348-128">En el Explorador de hechos, expanda el **ESB. TansportTypes** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **proveedores de adaptador** definición a  **\<una cadena vacía >**.</span><span class="sxs-lookup"><span data-stu-id="87348-128">In Facts Explorer, expand the **ESB.TansportTypes** vocabulary, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string>**.</span></span>  
  
9. <span data-ttu-id="87348-129">En el panel Acciones, expanda la **proveedores de adaptador** lista desplegable y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="87348-129">In the Actions pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
 <span data-ttu-id="87348-130">**Para publicar e implementar la directiva**</span><span class="sxs-lookup"><span data-stu-id="87348-130">**To publish and deploy the policy**</span></span>  
  
1.  <span data-ttu-id="87348-131">En el Explorador de directivas, en la **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 (sin guardar)**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="87348-131">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="87348-132">En el Explorador de directivas, en la **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="87348-132">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
 <span data-ttu-id="87348-133">**Para crear un modelo de lenguaje de específico de dominio (DSL) itinerarios de ESB**</span><span class="sxs-lookup"><span data-stu-id="87348-133">**To create an ESB itinerary domain-specific language (DSL) model**</span></span>  
  
1.  <span data-ttu-id="87348-134">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="87348-134">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="87348-135">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="87348-135">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="87348-136">En el **nombre** , escriba **MessageType**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="87348-136">In the **Name** box, type **MessageType**, and then click **Add**.</span></span>  
  
 <span data-ttu-id="87348-137">**Para configurar las propiedades de la itinerario**</span><span class="sxs-lookup"><span data-stu-id="87348-137">**To configure the properties of the itinerary**</span></span>  
  
1.  <span data-ttu-id="87348-138">En Visual Studio, haga clic en la superficie de diseño de **MessageType.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="87348-138">In Visual Studio, click the design surface of **MessageType.itinerary**.</span></span> <span data-ttu-id="87348-139">En el **MessageType** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="87348-139">In the **MessageType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="87348-140">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="87348-140">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="87348-141">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="87348-141">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="87348-142">En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\MessageType**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="87348-142">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\MessageType**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="87348-143">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="87348-143">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="87348-144">Exportar un itinerario en una ubicación de archivo local, en lugar de a la base de datos de itinerario, habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="87348-144">Exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="87348-145">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="87348-145">You will complete this process later in this How-to topic.</span></span>  
  
 <span data-ttu-id="87348-146">**Para definir la estructura de la itinerario**</span><span class="sxs-lookup"><span data-stu-id="87348-146">**To define the structure of the itinerary**</span></span>  
  
1.  <span data-ttu-id="87348-147">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="87348-147">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="87348-148">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="87348-148">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="87348-149">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveOrders**.</span><span class="sxs-lookup"><span data-stu-id="87348-149">Click the **Name** property, and then type **ReceiveOrders**.</span></span>  
  
    2.  <span data-ttu-id="87348-150">En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="87348-150">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="87348-151">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="87348-151">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="87348-152">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="87348-152">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="87348-153">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="87348-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="87348-154">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="87348-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="87348-155">Haga clic en el **nombre** propiedad y, a continuación, escriba **BreRoute**.</span><span class="sxs-lookup"><span data-stu-id="87348-155">Click the **Name** property, and then type **BreRoute**.</span></span>  
  
    2.  <span data-ttu-id="87348-156">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="87348-156">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="87348-157">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="87348-157">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="87348-158">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="87348-158">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="87348-159">En el **contenedor** lista desplegable lista, expanda **ReceiveOrders**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="87348-159">In the **Container** drop-down list, expand **ReceiveOrders**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="87348-160">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="87348-160">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="87348-161">Haga clic en el **resolución** colección de la **BreRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="87348-161">Right-click the **Resolver** collection of the **BreRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="87348-162">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="87348-162">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="87348-163">Haga clic en el **nombre** propiedad y, a continuación, escriba **ByMessageType**.</span><span class="sxs-lookup"><span data-stu-id="87348-163">Click the **Name** property, and then type **ByMessageType**.</span></span>  
  
    2.  <span data-ttu-id="87348-164">En el **implementación de la resolución** la lista desplegable, haga clic en **Bre resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="87348-164">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="87348-165">En el **directiva** la lista desplegable, haga clic en **RouteBasedOnMessageType v1.0**.</span><span class="sxs-lookup"><span data-stu-id="87348-165">In the **Policy** drop-down list, click **RouteBasedOnMessageType v 1.0**.</span></span>  
  
4.  <span data-ttu-id="87348-166">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="87348-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="87348-167">Arrastre una conexión desde el **ReceiveOrders** elemento de modelo para el **BreRoute** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="87348-167">Drag a connection from the **ReceiveOrders** model element to the **BreRoute** model element.</span></span>  
  
5.  <span data-ttu-id="87348-168">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BreRoute** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="87348-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BreRoute** model element.</span></span> <span data-ttu-id="87348-169">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="87348-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="87348-170">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendBasedOnType**.</span><span class="sxs-lookup"><span data-stu-id="87348-170">Click the **Name** property, and then type **SendBasedOnType**.</span></span>  
  
    2.  <span data-ttu-id="87348-171">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="87348-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="87348-172">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="87348-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="87348-173">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="87348-173">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="87348-174">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BreRoute** elemento del modelo y la **SendBasedOnType** modelo elemento.</span><span class="sxs-lookup"><span data-stu-id="87348-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BreRoute** model element and the **SendBasedOnType** model element.</span></span> <span data-ttu-id="87348-175">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="87348-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="87348-176">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="87348-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="87348-177">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="87348-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="87348-178">En el **fuera de rampa** lista desplegable lista, expanda **SendBasedOnType**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="87348-178">In the **Off-Ramp** drop-down list, expand **SendBasedOnType**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="87348-179">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="87348-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="87348-180">Arrastre una conexión desde el **BreRoute** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="87348-180">Drag a connection from the **BreRoute** model element to the **SendPortFilter** model element.</span></span>  
  
8.  <span data-ttu-id="87348-181">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="87348-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="87348-182">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendBasedOnType** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="87348-182">Drag a connection from the **SendPortFilter** model element to the **SendBasedOnType** model element.</span></span>  
  
 <span data-ttu-id="87348-183">**Para exportar el modelo para su uso con el cliente de prueba de itinerario**</span><span class="sxs-lookup"><span data-stu-id="87348-183">**To export the model for use with the Itinerary Test Client**</span></span>  
  
1.  <span data-ttu-id="87348-184">En Visual Studio, haga clic en la superficie de diseño de la **MessageType** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="87348-184">In Visual Studio, right-click the design surface of the **MessageType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87348-185">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="87348-185">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="87348-186">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="87348-186">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="87348-187">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (MessageType.xml).</span><span class="sxs-lookup"><span data-stu-id="87348-187">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (MessageType.xml).</span></span>  
  
 <span data-ttu-id="87348-188">**Para probar el itinerario**</span><span class="sxs-lookup"><span data-stu-id="87348-188">**To test the itinerary**</span></span>  
  
1.  <span data-ttu-id="87348-189">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="87348-189">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="87348-190">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="87348-190">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="87348-191">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="87348-191">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="87348-192">Seleccione **MessageType.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="87348-192">Select **MessageType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="87348-193">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="87348-193">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="87348-194">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="87348-194">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="87348-195">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="87348-195">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="87348-196">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="87348-196">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="87348-197">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="87348-197">Click the **Submit Request** button.</span></span> <span data-ttu-id="87348-198">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="87348-198">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="87348-199">En el Explorador de Windows, vaya a C:\HowTos\Out\\.</span><span class="sxs-lookup"><span data-stu-id="87348-199">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="87348-200">Compruebe que se ha escrito el mensaje NorthAmerica%MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="87348-200">Verify that the NorthAmerica%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="87348-201">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="87348-201">Additional Resources</span></span>  
 <span data-ttu-id="87348-202">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="87348-202">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="87348-203">Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="87348-203">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="87348-204">Cómo: transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución itinerario</span><span class="sxs-lookup"><span data-stu-id="87348-204">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="87348-205">Cómo: implementar enrutamiento por contenidos mediante una empresa de reglas de directiva para un tipo de mensaje conocido</span><span class="sxs-lookup"><span data-stu-id="87348-205">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [<span data-ttu-id="87348-206">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="87348-206">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="87348-207">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="87348-207">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="87348-208">Uso de resolución dinámica y enrutamiento</span><span class="sxs-lookup"><span data-stu-id="87348-208">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)