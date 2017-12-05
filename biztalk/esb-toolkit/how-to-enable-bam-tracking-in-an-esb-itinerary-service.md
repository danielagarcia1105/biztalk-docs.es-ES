---
title: "Cómo: habilitar el seguimiento de BAM en un servicio de itinerarios de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 011de667e06f4275fe75a28b6566a6bc393cf841
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a><span data-ttu-id="26fac-102">Cómo: habilitar el seguimiento de BAM en un servicio de itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="26fac-102">How to: Enable BAM Tracking in an ESB Itinerary Service</span></span>
## <a name="goal"></a><span data-ttu-id="26fac-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="26fac-103">Goal</span></span>  
 <span data-ttu-id="26fac-104">Esta sección muestra cómo habilitar el seguimiento para un itinerario existente Business Activity Monitor (BAM).</span><span class="sxs-lookup"><span data-stu-id="26fac-104">This section demonstrates how to enable Business Activity Monitor (BAM) tracking for an existing itinerary.</span></span>  
  
 <span data-ttu-id="26fac-105">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="26fac-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="26fac-106">Habilitar la propiedad que se utiliza para realizar el seguimiento de los servicios de itinerario mediante el Monitor de actividad de negocio.</span><span class="sxs-lookup"><span data-stu-id="26fac-106">Enable the property used for tracking Itinerary Services using Business Activity Monitor.</span></span>  
  
-   <span data-ttu-id="26fac-107">Seguimiento de BAM de prueba mediante la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="26fac-107">Test BAM tracking using the Itinerary Test Client sample application.</span></span>  
  
-   <span data-ttu-id="26fac-108">Comprobar los resultados BAM usando una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="26fac-108">Verify the BAM results using a SQL query.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26fac-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="26fac-109">Prerequisites</span></span>  
 <span data-ttu-id="26fac-110">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="26fac-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="26fac-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="26fac-111">Before You Begin</span></span>  
 <span data-ttu-id="26fac-112">Complete las tareas siguientes antes de realizar los pasos más adelante en este tema "Cómo...":</span><span class="sxs-lookup"><span data-stu-id="26fac-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="26fac-113">Crear un modelo de lenguaje de específico de dominio (DSL) itinerarios de ESB.</span><span class="sxs-lookup"><span data-stu-id="26fac-113">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
-   <span data-ttu-id="26fac-114">Configurar las propiedades de la itinerario.</span><span class="sxs-lookup"><span data-stu-id="26fac-114">Configure the properties of the itinerary.</span></span>  
  
-   <span data-ttu-id="26fac-115">Definir la estructura de la itinerario.</span><span class="sxs-lookup"><span data-stu-id="26fac-115">Define the structure of the itinerary.</span></span>  
  
 <span data-ttu-id="26fac-116">Los procedimientos siguientes describen cómo realizar cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="26fac-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="26fac-117">Para crear un modelo DSL itinerario de ESB</span><span class="sxs-lookup"><span data-stu-id="26fac-117">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="26fac-118">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="26fac-118">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="26fac-119">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="26fac-119">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="26fac-120">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **ItineraryDsl** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="26fac-120">In the **Add New Item** dialog box, click  **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="26fac-121">En el **nombre** , escriba **BamTracking**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="26fac-121">In the **Name** box, type **BamTracking**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="26fac-122">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="26fac-122">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="26fac-123">En Visual Studio, haga clic en la superficie de diseño de **BamTracking.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="26fac-123">In Visual Studio, click the design surface of **BamTracking.itinerary**.</span></span> <span data-ttu-id="26fac-124">En el **BamTracking** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26fac-124">In the **BamTracking** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="26fac-125">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="26fac-125">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="26fac-126">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="26fac-126">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="26fac-127">En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\BamTracking** y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="26fac-127">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\BamTracking** and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="26fac-128">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="26fac-128">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="26fac-129">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="26fac-129">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="26fac-130">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="26fac-130">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="26fac-131">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="26fac-131">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="26fac-132">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="26fac-132">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="26fac-133">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26fac-133">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="26fac-134">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="26fac-134">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="26fac-135">En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.</span><span class="sxs-lookup"><span data-stu-id="26fac-135">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="26fac-136">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="26fac-136">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="26fac-137">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="26fac-137">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="26fac-138">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="26fac-138">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="26fac-139">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26fac-139">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="26fac-140">Haga clic en el **nombre** propiedad y, a continuación, escriba **MapNAOrderToCNOrder**.</span><span class="sxs-lookup"><span data-stu-id="26fac-140">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="26fac-141">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de los servicios de mensajería itinerario**.</span><span class="sxs-lookup"><span data-stu-id="26fac-141">In the **Itinerary Service Extender** drop-down list, click **Messaging Itinerary Service Extension**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="26fac-142">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="26fac-142">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="26fac-143">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensión de servicio de orquestación itinerario**.</span><span class="sxs-lookup"><span data-stu-id="26fac-143">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="26fac-144">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="26fac-144">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="26fac-145">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="26fac-145">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="26fac-146">Haga clic en el **resolución** colección de la **MapNAOrderToCNOrder** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="26fac-146">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="26fac-147">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26fac-147">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="26fac-148">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticallySpecifyTheMap**.</span><span class="sxs-lookup"><span data-stu-id="26fac-148">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="26fac-149">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="26fac-149">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="26fac-150">En el **transformar tipo** la lista desplegable, haga clic en **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span><span class="sxs-lookup"><span data-stu-id="26fac-150">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="26fac-151">En el **TransportName** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="26fac-151">In the **TransportName** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="26fac-152">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="26fac-152">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="26fac-153">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **MapNAOrderToCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="26fac-153">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="26fac-154">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **MapNAOrderToCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="26fac-154">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="26fac-155">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26fac-155">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="26fac-156">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendCNOrder**.</span><span class="sxs-lookup"><span data-stu-id="26fac-156">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="26fac-157">En el **Extender** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.</span><span class="sxs-lookup"><span data-stu-id="26fac-157">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="26fac-158">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="26fac-158">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="26fac-159">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="26fac-159">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="26fac-160">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **MapNAOrderToCNOrder** elemento del modelo y la **SendCNOrder**elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="26fac-160">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="26fac-161">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26fac-161">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="26fac-162">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="26fac-162">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="26fac-163">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.</span><span class="sxs-lookup"><span data-stu-id="26fac-163">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="26fac-164">En el **fuera de rampa** lista desplegable lista, expanda **SendCNOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="26fac-164">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="26fac-165">Haga clic en el **resolución** colección de la **SendPortFilter** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="26fac-165">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="26fac-166">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="26fac-166">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="26fac-167">Haga clic en el **nombre** propiedad y, a continuación, escriba **ConfigureFolderSettings**.</span><span class="sxs-lookup"><span data-stu-id="26fac-167">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="26fac-168">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="26fac-168">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="26fac-169">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="26fac-169">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="26fac-170">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\BAM%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="26fac-170">Click the **Transport Location** property, and then type **C:\HowTos\Out\BAM%MessageID%.xml**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="26fac-171">Cada fuera de rampa tendrá un servicio itinerario asociado a él; la combinación de las propiedades del servicio itinerarios y las propiedades de fuera de rampa definir la suscripción del puerto de envío dinámico.</span><span class="sxs-lookup"><span data-stu-id="26fac-171">Each off-ramp will have an itinerary service associated with it; the combination of the itinerary service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="26fac-172">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="26fac-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="26fac-173">Arrastre una conexión desde el **MapNAOrderToCNOrder** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="26fac-173">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="26fac-174">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="26fac-174">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="26fac-175">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendCNOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="26fac-175">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
10. <span data-ttu-id="26fac-176">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="26fac-176">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="26fac-177">Pasos</span><span class="sxs-lookup"><span data-stu-id="26fac-177">Steps</span></span>  
  
#### <a name="to-modify-the-itinerary"></a><span data-ttu-id="26fac-178">Para modificar el itinerario</span><span class="sxs-lookup"><span data-stu-id="26fac-178">To modify the itinerary</span></span>  
  
1.  <span data-ttu-id="26fac-179">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="26fac-179">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="26fac-180">En el Explorador de soluciones, haga doble clic en **BamTracking.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="26fac-180">In Solution Explorer, double-click **BamTracking.itinerary**.</span></span>  
  
3.  <span data-ttu-id="26fac-181">Haga clic en el **MapNAOrderToCNOrder** elemento servicio itinerarios.</span><span class="sxs-lookup"><span data-stu-id="26fac-181">Click the **MapNAOrderToCNOrder** itinerary service element.</span></span>  
  
4.  <span data-ttu-id="26fac-182">En el **MapNAOrderToCNOrder** ventana Propiedades, haga clic en **True** en el **seguimiento habilitado** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="26fac-182">In the **MapNAOrderToCNOrder** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
5.  <span data-ttu-id="26fac-183">Haga clic en el **SendPortFilter** elemento servicio itinerarios.</span><span class="sxs-lookup"><span data-stu-id="26fac-183">Click the **SendPortFilter** itinerary service element.</span></span>  
  
6.  <span data-ttu-id="26fac-184">En el **SendPortFilter** ventana Propiedades, haga clic en **True** en el **seguimiento habilitado** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="26fac-184">In the **SendPortFilter** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="26fac-185">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="26fac-185">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="26fac-186">En Visual Studio, haga clic en la superficie de diseño de la **BamTracking** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="26fac-186">In Visual Studio, right-click the design surface of the **BamTracking** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="26fac-187">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="26fac-187">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="26fac-188">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="26fac-188">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="26fac-189">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (BamTracking.xml).</span><span class="sxs-lookup"><span data-stu-id="26fac-189">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (BamTracking.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="26fac-190">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="26fac-190">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="26fac-191">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="26fac-191">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="26fac-192">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="26fac-192">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="26fac-193">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="26fac-193">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="26fac-194">Seleccione **BamTracking.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="26fac-194">Select **BamTracking.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="26fac-195">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="26fac-195">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="26fac-196">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="26fac-196">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="26fac-197">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="26fac-197">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="26fac-198">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="26fac-198">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="26fac-199">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="26fac-199">Click the **Submit Request** button.</span></span> <span data-ttu-id="26fac-200">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="26fac-200">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="26fac-201">En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje BAM%MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="26fac-201">In Windows Explorer, browse to C:\HowTos\Out. Verify that the BAM%MessageID%.xml message has been written to the directory.</span></span>  
  
#### <a name="to-verify-message-tracking"></a><span data-ttu-id="26fac-202">Para comprobar el seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="26fac-202">To verify message tracking</span></span>  
  
1.  <span data-ttu-id="26fac-203">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="26fac-203">Click **Start** on the taskbar, point to **All Programs**, point to [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="26fac-204">Haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="26fac-204">Click **New Query**.</span></span>  
  
3.  <span data-ttu-id="26fac-205">En el panel de consulta, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="26fac-205">In the query pane, type the following:</span></span>  
  
    ```  
    SELECT *  
    FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
    GO  
    ```  
  
4.  <span data-ttu-id="26fac-206">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="26fac-206">Click **Execute**.</span></span>  
  
5.  <span data-ttu-id="26fac-207">En el panel de resultados, utilice la **TimeStamp** columna para buscar la entrada más reciente.</span><span class="sxs-lookup"><span data-stu-id="26fac-207">In the Results pane, use the **TimeStamp** column to locate the most recent entry.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="26fac-208">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="26fac-208">Additional Resources</span></span>  
 <span data-ttu-id="26fac-209">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="26fac-209">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="26fac-210">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="26fac-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="26fac-211">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="26fac-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="26fac-212">Uso de resolución y enrutamiento dinámicos</span><span class="sxs-lookup"><span data-stu-id="26fac-212">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)