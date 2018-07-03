---
title: 'Cómo: enrutar dinámicamente un mensaje en función del contexto de mensaje mediante una directiva de reglas de negocio | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7406b0daed4374241bb92fdcb4afcdcd5acd77b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973893"
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a><span data-ttu-id="42efb-102">Cómo: enrutar dinámicamente un mensaje en función del contexto de mensaje mediante una directiva de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="42efb-102">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="42efb-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="42efb-103">Goal</span></span>  
 <span data-ttu-id="42efb-104">Esta sección muestra cómo crear un itinerario que determina los puntos de conexión de mensaje, según las propiedades de contexto de mensaje, mediante una directiva de motor de reglas de negocios (BRE) de BizTalk Server y, a continuación, enruta el mensaje mediante el adaptador de archivo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="42efb-104">This section demonstrates how to create an itinerary that determines message endpoints, based on message context properties, using a BizTalk Server Business Rules Engine (BRE) policy, and then routes the message using the BizTalk Server FILE adapter.</span></span>  
  
 <span data-ttu-id="42efb-105">En este tema de procedimientos, se completará los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="42efb-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="42efb-106">Crear una directiva de reglas de negocios para evaluar el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="42efb-106">Create a business rules policy to evaluate message type.</span></span>  
  
-   <span data-ttu-id="42efb-107">Crear una lista de distribución de itinerarios para enrutar dinámicamente mediante una directiva de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="42efb-107">Create an itinerary routing slip to dynamically route using a business rules policy.</span></span>  
  
-   <span data-ttu-id="42efb-108">Pruebe el itinerario mediante la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="42efb-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42efb-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="42efb-109">Prerequisites</span></span>  
 <span data-ttu-id="42efb-110">Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="42efb-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="42efb-111">Pasos</span><span class="sxs-lookup"><span data-stu-id="42efb-111">Steps</span></span>  
 <span data-ttu-id="42efb-112">**Para crear una directiva BRE para enrutar un mensaje mediante las propiedades de contexto de mensaje**</span><span class="sxs-lookup"><span data-stu-id="42efb-112">**To create a BRE policy to route a message using message context properties**</span></span>  
  
1. <span data-ttu-id="42efb-113">Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a **BizTalk Server**y, a continuación, haga clic en **compositor**.</span><span class="sxs-lookup"><span data-stu-id="42efb-113">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2. <span data-ttu-id="42efb-114">En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="42efb-114">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="42efb-115">Nombre de la directiva **RouteBasedOnMessageType**.</span><span class="sxs-lookup"><span data-stu-id="42efb-115">Name the policy **RouteBasedOnMessageType**.</span></span>  
  
   <span data-ttu-id="42efb-116">**Para agregar una regla de enrutamiento para los pedidos de América del Norte**</span><span class="sxs-lookup"><span data-stu-id="42efb-116">**To add a routing rule for North American orders**</span></span>  
  
3. <span data-ttu-id="42efb-117">En el **RouteBasedOnMessageType** directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="42efb-117">In the **RouteBasedOnMessageType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="42efb-118">Nombre de la regla **SetNAOrderEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="42efb-118">Name the rule **SetNAOrderEndpoint**.</span></span>  
  
4. <span data-ttu-id="42efb-119">En la ventana de la regla, haga clic en **condiciones**, apunte a **predicados**y, a continuación, haga clic en **igual**.</span><span class="sxs-lookup"><span data-stu-id="42efb-119">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
5. <span data-ttu-id="42efb-120">En el Explorador de hechos, expanda el **ESB. ContextInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **tipo de contexto de mensaje** hecho a la **argumento1** nodo bajo  **Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="42efb-120">In Facts Explorer, expand the **ESB.ContextInfo** vocabulary, expand **Version 1.0**, and then drag the **Context Message Type** fact to the **argument1** node under **Conditions**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="42efb-121">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varios vocabularios que pueden usarse para crear reglas.</span><span class="sxs-lookup"><span data-stu-id="42efb-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules.</span></span> <span data-ttu-id="42efb-122">Algunas de estas deben reemplazar o ampliada con sus propios vocabularios.</span><span class="sxs-lookup"><span data-stu-id="42efb-122">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="42efb-123">Por ejemplo, el **DynamicRunTimeMaptypes** directiva tiene definiciones para las asignaciones proporcionadas en el **GlobalBank** ejemplos.</span><span class="sxs-lookup"><span data-stu-id="42efb-123">For example, the **DynamicRunTimeMaptypes** policy has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
6. <span data-ttu-id="42efb-124">Haga clic en el **argumento2** nodo y, a continuación, escriba **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span><span class="sxs-lookup"><span data-stu-id="42efb-124">Click the **argument2** node, and then type **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span></span>  
  
7. <span data-ttu-id="42efb-125">En el Explorador de hechos, expanda el **ESB. EndPointInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **establecer ubicación de transporte de salida de punto de conexión** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="42efb-125">In Facts Explorer, expand the **ESB.EndPointInfo** vocabulary, expand **Version 1.0**, and then drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
8. <span data-ttu-id="42efb-126">Haga clic en  **\<una cadena vacía\>** y, a continuación, escriba **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="42efb-126">Click **\<empty string\>**, and then type **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span></span>  
  
9. <span data-ttu-id="42efb-127">En el Explorador de hechos, arrastre el **establecer tipo de transporte saliente de punto de conexión** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="42efb-127">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="42efb-128">En el Explorador de hechos, expanda el **ESB. TansportTypes** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **adaptador proveedores** definición a **\<una cadena vacía\>**.</span><span class="sxs-lookup"><span data-stu-id="42efb-128">In Facts Explorer, expand the **ESB.TansportTypes** vocabulary, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
11. <span data-ttu-id="42efb-129">En el panel Acciones, expanda el **adaptador proveedores** lista desplegable y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="42efb-129">In the Actions pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
    <span data-ttu-id="42efb-130">**Para publicar e implementar la directiva**</span><span class="sxs-lookup"><span data-stu-id="42efb-130">**To publish and deploy the policy**</span></span>  
  
12. <span data-ttu-id="42efb-131">En el Explorador de directivas, bajo el **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 (sin guardar)** y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="42efb-131">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
13. <span data-ttu-id="42efb-132">En el Explorador de directivas, bajo el **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="42efb-132">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
    <span data-ttu-id="42efb-133">**Para crear un modelo de lenguaje de específicos de dominio (DSL) itinerarios de ESB**</span><span class="sxs-lookup"><span data-stu-id="42efb-133">**To create an ESB itinerary domain-specific language (DSL) model**</span></span>  
  
14. <span data-ttu-id="42efb-134">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="42efb-134">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
15. <span data-ttu-id="42efb-135">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nuevo**.</span><span class="sxs-lookup"><span data-stu-id="42efb-135">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
16. <span data-ttu-id="42efb-136">En el **nombre** , escriba **MessageType**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="42efb-136">In the **Name** box, type **MessageType**, and then click **Add**.</span></span>  
  
    <span data-ttu-id="42efb-137">**Para configurar las propiedades de los itinerarios**</span><span class="sxs-lookup"><span data-stu-id="42efb-137">**To configure the properties of the itinerary**</span></span>  
  
17. <span data-ttu-id="42efb-138">En Visual Studio, haga clic en la superficie de diseño de **MessageType.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="42efb-138">In Visual Studio, click the design surface of **MessageType.itinerary**.</span></span> <span data-ttu-id="42efb-139">En el **MessageType** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="42efb-139">In the **MessageType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="42efb-140">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="42efb-140">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="42efb-141">En el **configuración extensor** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="42efb-141">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="42efb-142">En el **Seleccionar archivo XML** cuadro de diálogo el **nombre de archivo** , escriba **C:\HowTos\Itineraries\MessageType**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="42efb-142">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\MessageType**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="42efb-143">Este paso le permite exportar el itinerario como XML en una ubicación de archivos local.</span><span class="sxs-lookup"><span data-stu-id="42efb-143">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="42efb-144">Exportar un itinerario en una ubicación de archivos local, en lugar de a la base de datos de itinerario, permite probar el itinerario mediante la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="42efb-144">Exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="42efb-145">Complete este proceso más adelante en este tema de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="42efb-145">You will complete this process later in this How-to topic.</span></span>  
  
    <span data-ttu-id="42efb-146">**Para definir la estructura de los itinerarios**</span><span class="sxs-lookup"><span data-stu-id="42efb-146">**To define the structure of the itinerary**</span></span>  
  
18. <span data-ttu-id="42efb-147">En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="42efb-147">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="42efb-148">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="42efb-148">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="42efb-149">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveOrders**.</span><span class="sxs-lookup"><span data-stu-id="42efb-149">Click the **Name** property, and then type **ReceiveOrders**.</span></span>  
  
    2.  <span data-ttu-id="42efb-150">En el **extensor** la lista desplegable, haga clic en **rampa de ESB extensor**.</span><span class="sxs-lookup"><span data-stu-id="42efb-150">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="42efb-151">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="42efb-151">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="42efb-152">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="42efb-152">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
19. <span data-ttu-id="42efb-153">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **vía** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="42efb-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="42efb-154">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="42efb-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="42efb-155">Haga clic en el **nombre** propiedad y, a continuación, escriba **BreRoute**.</span><span class="sxs-lookup"><span data-stu-id="42efb-155">Click the **Name** property, and then type **BreRoute**.</span></span>  
  
    2.  <span data-ttu-id="42efb-156">En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **mensajería extensor**.</span><span class="sxs-lookup"><span data-stu-id="42efb-156">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="42efb-157">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="42efb-157">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="42efb-158">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca el **extensor del servicio de itinerarios** propiedad **orquestación extensor**.</span><span class="sxs-lookup"><span data-stu-id="42efb-158">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="42efb-159">En el **contenedor** desplegable lista, expanda **ReceiveOrders**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="42efb-159">In the **Container** drop-down list, expand **ReceiveOrders**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="42efb-160">En el **Service Name** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="42efb-160">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
20. <span data-ttu-id="42efb-161">Haga clic en el **resolución** colección de la **BreRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="42efb-161">Right-click the **Resolver** collection of the **BreRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="42efb-162">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="42efb-162">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="42efb-163">Haga clic en el **nombre** propiedad y, a continuación, escriba **ByMessageType**.</span><span class="sxs-lookup"><span data-stu-id="42efb-163">Click the **Name** property, and then type **ByMessageType**.</span></span>  
  
    2.  <span data-ttu-id="42efb-164">En el **implementación de la resolución** la lista desplegable, haga clic en **Bre resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="42efb-164">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="42efb-165">En el **directiva** la lista desplegable, haga clic en **RouteBasedOnMessageType v 1.0**.</span><span class="sxs-lookup"><span data-stu-id="42efb-165">In the **Policy** drop-down list, click **RouteBasedOnMessageType v 1.0**.</span></span>  
  
21. <span data-ttu-id="42efb-166">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="42efb-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="42efb-167">Arrastre una conexión desde el **ReceiveOrders** elemento de modelo para el **BreRoute** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="42efb-167">Drag a connection from the **ReceiveOrders** model element to the **BreRoute** model element.</span></span>  
  
22. <span data-ttu-id="42efb-168">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BreRoute** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="42efb-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BreRoute** model element.</span></span> <span data-ttu-id="42efb-169">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="42efb-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="42efb-170">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendBasedOnType**.</span><span class="sxs-lookup"><span data-stu-id="42efb-170">Click the **Name** property, and then type **SendBasedOnType**.</span></span>  
  
    2.  <span data-ttu-id="42efb-171">En el **extensor** la lista desplegable, haga clic en **fuera de rampa ESB extensor**.</span><span class="sxs-lookup"><span data-stu-id="42efb-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="42efb-172">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="42efb-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="42efb-173">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="42efb-173">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
23. <span data-ttu-id="42efb-174">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BreRoute** elemento de modelo y la **SendBasedOnType** modelo elemento.</span><span class="sxs-lookup"><span data-stu-id="42efb-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BreRoute** model element and the **SendBasedOnType** model element.</span></span> <span data-ttu-id="42efb-175">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="42efb-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="42efb-176">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="42efb-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="42efb-177">En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **fuera de rampa extensor**.</span><span class="sxs-lookup"><span data-stu-id="42efb-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="42efb-178">En el **fuera de rampa** desplegable lista, expanda **SendBasedOnType**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="42efb-178">In the **Off-Ramp** drop-down list, expand **SendBasedOnType**, and then click **Send Handlers**.</span></span>  
  
24. <span data-ttu-id="42efb-179">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="42efb-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="42efb-180">Arrastre una conexión desde el **BreRoute** elemento de modelo para el **SendPortFilter** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="42efb-180">Drag a connection from the **BreRoute** model element to the **SendPortFilter** model element.</span></span>  
  
25. <span data-ttu-id="42efb-181">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="42efb-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="42efb-182">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendBasedOnType** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="42efb-182">Drag a connection from the **SendPortFilter** model element to the **SendBasedOnType** model element.</span></span>  
  
    <span data-ttu-id="42efb-183">**Para exportar el modelo para su uso con el cliente de prueba de itinerario**</span><span class="sxs-lookup"><span data-stu-id="42efb-183">**To export the model for use with the Itinerary Test Client**</span></span>  
  
26. <span data-ttu-id="42efb-184">En Visual Studio, haga clic en la superficie de diseño de la **MessageType** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="42efb-184">In Visual Studio, right-click the design surface of the **MessageType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42efb-185">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="42efb-185">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
27. <span data-ttu-id="42efb-186">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="42efb-186">Save all project artifacts.</span></span>  
  
28. <span data-ttu-id="42efb-187">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (MessageType.xml).</span><span class="sxs-lookup"><span data-stu-id="42efb-187">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (MessageType.xml).</span></span>  
  
    <span data-ttu-id="42efb-188">**Para probar el itinerario**</span><span class="sxs-lookup"><span data-stu-id="42efb-188">**To test the itinerary**</span></span>  
  
29. <span data-ttu-id="42efb-189">Abra la aplicación de ejemplo de cliente de prueba de itinerario mediante el acceso directo que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="42efb-189">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
30. <span data-ttu-id="42efb-190">En el cliente de prueba de itinerario, desactive la **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="42efb-190">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
31. <span data-ttu-id="42efb-191">En el **abrir archivo itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="42efb-191">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="42efb-192">Seleccione **MessageType.xml**y, a continuación, haga clic en **abierto** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="42efb-192">Select **MessageType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
32. <span data-ttu-id="42efb-193">Haga clic en **Aceptar** para borrar el **itinerario se cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="42efb-193">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
33. <span data-ttu-id="42efb-194">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **carga mensaje** cuadro.</span><span class="sxs-lookup"><span data-stu-id="42efb-194">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
34. <span data-ttu-id="42efb-195">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="42efb-195">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="42efb-196">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abierto** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="42efb-196">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
35. <span data-ttu-id="42efb-197">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="42efb-197">Click the **Submit Request** button.</span></span> <span data-ttu-id="42efb-198">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="42efb-198">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
36. <span data-ttu-id="42efb-199">En el Explorador de Windows, vaya a C:\HowTos\Out\\.</span><span class="sxs-lookup"><span data-stu-id="42efb-199">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="42efb-200">Compruebe que se ha escrito el mensaje NorthAmerica%MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="42efb-200">Verify that the NorthAmerica%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="42efb-201">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="42efb-201">Additional Resources</span></span>  
 <span data-ttu-id="42efb-202">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="42efb-202">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="42efb-203">Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="42efb-203">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="42efb-204">Cómo: Transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución de itinerarios</span><span class="sxs-lookup"><span data-stu-id="42efb-204">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="42efb-205">Cómo: Implementar el enrutamiento basado en contenido mediante una directiva de reglas de negocio para un tipo de mensaje conocido</span><span class="sxs-lookup"><span data-stu-id="42efb-205">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [<span data-ttu-id="42efb-206">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="42efb-206">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="42efb-207">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="42efb-207">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="42efb-208">Uso de resolución y enrutamiento dinámicos</span><span class="sxs-lookup"><span data-stu-id="42efb-208">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)