---
title: "Cómo: validar un mensaje mediante un ESB rampa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43dfc791-7cb6-45a4-898f-f53def199c08
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e14fd3f433609da7748197a8b67112d815da153
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a><span data-ttu-id="bb47d-102">Cómo: validar un mensaje mediante un ESB rampa</span><span class="sxs-lookup"><span data-stu-id="bb47d-102">How to: Validate a Message Using an ESB On-Ramp</span></span>
## <a name="goal"></a><span data-ttu-id="bb47d-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="bb47d-103">Goal</span></span>  
 <span data-ttu-id="bb47d-104">Esta sección muestra cómo configurar el componente de canalización de desensamblado de distribuidor de ESB para realizar la validación del mensaje para los mensajes XML enviados a ESB en rampa.</span><span class="sxs-lookup"><span data-stu-id="bb47d-104">This section demonstrates how to configure the ESB Dispatcher Disassemble pipeline component to perform message validation for XML messages submitted to an ESB on-ramp.</span></span>  
  
 <span data-ttu-id="bb47d-105">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb47d-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="bb47d-106">Crear un ESB en rampa que usa el **ItinerarySelectReceiveXml** canalización.</span><span class="sxs-lookup"><span data-stu-id="bb47d-106">Create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline.</span></span>  
  
-   <span data-ttu-id="bb47d-107">Configurar el componente de canalización de desensamblado de distribuidor de ESB para validar el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="bb47d-107">Configure the ESB Dispatcher Disassemble pipeline component to validate message content.</span></span>  
  
-   <span data-ttu-id="bb47d-108">Configurar el componente de canalización de Selector de itinerario para resolver el itinerario adecuado.</span><span class="sxs-lookup"><span data-stu-id="bb47d-108">Configure the Itinerary Selector pipeline component to resolve the appropriate itinerary.</span></span>  
  
-   <span data-ttu-id="bb47d-109">Validación del mensaje de prueba con un mensaje válido y un mensaje no válido.</span><span class="sxs-lookup"><span data-stu-id="bb47d-109">Test message validation using a valid message and an invalid message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bb47d-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bb47d-110">Prerequisites</span></span>  
 <span data-ttu-id="bb47d-111">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="bb47d-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="bb47d-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="bb47d-112">Before You Begin</span></span>  
 <span data-ttu-id="bb47d-113">Complete las tareas siguientes antes de realizar los pasos más adelante en este tema "Cómo...":</span><span class="sxs-lookup"><span data-stu-id="bb47d-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="bb47d-114">Crear un mensaje de prueba no válido.</span><span class="sxs-lookup"><span data-stu-id="bb47d-114">Create an invalid test message.</span></span>  
  
-   <span data-ttu-id="bb47d-115">Crear un modelo de lenguaje de específico de dominio (DSL) itinerarios de ESB.</span><span class="sxs-lookup"><span data-stu-id="bb47d-115">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
-   <span data-ttu-id="bb47d-116">Configurar las propiedades de la itinerario.</span><span class="sxs-lookup"><span data-stu-id="bb47d-116">Configure the properties of the itinerary.</span></span>  
  
-   <span data-ttu-id="bb47d-117">Definir la estructura de la itinerario.</span><span class="sxs-lookup"><span data-stu-id="bb47d-117">Define the structure of the itinerary.</span></span>  
  
-   <span data-ttu-id="bb47d-118">Exportar el modelo a la base de datos de itinerario.</span><span class="sxs-lookup"><span data-stu-id="bb47d-118">Export the model to the Itinerary database.</span></span>  
  
 <span data-ttu-id="bb47d-119">Los procedimientos siguientes describen cómo realizar cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="bb47d-119">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-invalid-test-message"></a><span data-ttu-id="bb47d-120">Para crear un mensaje de prueba no válido.</span><span class="sxs-lookup"><span data-stu-id="bb47d-120">To create an invalid test message</span></span>  
  
1.  <span data-ttu-id="bb47d-121">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="bb47d-121">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="bb47d-122">Crear una copia de NAOrderDoc.xml y, a continuación, cambiar el nombre de la copia Invalid.xml.</span><span class="sxs-lookup"><span data-stu-id="bb47d-122">Create a copy of NAOrderDoc.xml, and then rename the copy Invalid.xml.</span></span>  
  
3.  <span data-ttu-id="bb47d-123">En el Bloc de notas, abra Invalid.xml.</span><span class="sxs-lookup"><span data-stu-id="bb47d-123">In Notepad, open Invalid.xml.</span></span>  
  
4.  <span data-ttu-id="bb47d-124">Cambio  **\<ns0:requestType\>10\</ns0:requestType\> a \<ns0:requestType\>diez\</ns0:requestType\>** .</span><span class="sxs-lookup"><span data-stu-id="bb47d-124">Change **\<ns0:requestType\>10\</ns0:requestType\> to \<ns0:requestType\>TEN\</ns0:requestType\>**.</span></span>  
  
5.  <span data-ttu-id="bb47d-125">Guardar Invalid.xml como UTF-8 y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="bb47d-125">Save Invalid.xml as UTF-8, and then close Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb47d-126">Al cambiar el valor numérico de este elemento de texto, el mensaje ya no será válido de acuerdo con el esquema.</span><span class="sxs-lookup"><span data-stu-id="bb47d-126">By changing the numerical value of this element to text, the message will no longer be valid according to the schema.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="bb47d-127">Para crear un modelo DSL itinerario de ESB</span><span class="sxs-lookup"><span data-stu-id="bb47d-127">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="bb47d-128">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="bb47d-128">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="bb47d-129">En el Explorador de soluciones, haga clic en **ItineraryLibrary**, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-129">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="bb47d-130">En el **Agregar nuevo elemento** cuadro de diálogo, escriba **validación** en el **nombre** cuadro y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-130">In the **Add New Item** dialog box, type **Validation** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="bb47d-131">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="bb47d-131">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="bb47d-132">En Visual Studio, haga clic en la superficie de diseño de **Validation.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-132">In Visual Studio, click the design surface of **Validation.itinerary**.</span></span> <span data-ttu-id="bb47d-133">En el **validación** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bb47d-133">In the **Validation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bb47d-134">En el **modelo exportador** la lista desplegable, haga clic en **base de datos de itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-134">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="bb47d-135">Haga clic en el botón de puntos suspensivos (...) junto a la **base de datos de itinerario** propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb47d-135">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="bb47d-136">En el **propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de repositorio itinerarios y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).</span><span class="sxs-lookup"><span data-stu-id="bb47d-136">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="bb47d-137">En el **estado de itinerario** la lista desplegable, haga clic en **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-137">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb47d-138">Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio cuando se recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="bb47d-138">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when the message is received.</span></span> <span data-ttu-id="bb47d-139">Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar a un solucionador estático para seleccionar el itinerario adecuado en este repositorio.</span><span class="sxs-lookup"><span data-stu-id="bb47d-139">You will later configure the Itinerary Selector pipeline component to use a static resolver to select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="bb47d-140">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="bb47d-140">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="bb47d-141">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb47d-141">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="bb47d-142">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bb47d-142">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bb47d-143">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-143">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="bb47d-144">En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-144">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="bb47d-145">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-145">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="bb47d-146">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-146">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="bb47d-147">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha del elemento del modelo existente.</span><span class="sxs-lookup"><span data-stu-id="bb47d-147">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the existing model element.</span></span> <span data-ttu-id="bb47d-148">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bb47d-148">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bb47d-149">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-149">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="bb47d-150">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-150">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="bb47d-151">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-151">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="bb47d-152">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-152">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="bb47d-153">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="bb47d-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="bb47d-154">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bb47d-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bb47d-155">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-155">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="bb47d-156">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-156">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="bb47d-157">En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-157">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="bb47d-158">Haga clic en el **resolución** colección de la **SendPortFilter** elemento y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-158">Right-click the **Resolver** collection of the **SendPortFilter** element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="bb47d-159">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bb47d-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bb47d-160">Haga clic en el **nombre** propiedad y, a continuación, escriba **ConfigureOffRamp**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-160">Click the **Name** property, and then type **ConfigureOffRamp**.</span></span>  
  
    2.  <span data-ttu-id="bb47d-161">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="bb47d-162">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-162">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="bb47d-163">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\Validated%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-163">Click the **Transport Location** property, and then type **C:\HowTos\Out\Validated%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="bb47d-164">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-164">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="bb47d-165">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="bb47d-165">Drag a connection from the **ReceiveNAOrder** model element to the **SendPortFilter** model element.</span></span>  
  
6.  <span data-ttu-id="bb47d-166">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="bb47d-167">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="bb47d-167">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="bb47d-168">Para exportar el modelo a la base de datos de itinerario</span><span class="sxs-lookup"><span data-stu-id="bb47d-168">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="bb47d-169">En Visual Studio, haga clic en la superficie de diseño de la **validación** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-169">In Visual Studio, right-click the design surface of the **Validation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb47d-170">El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de canalización de Selector de itinerario.</span><span class="sxs-lookup"><span data-stu-id="bb47d-170">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector pipeline component.</span></span>  
  
2.  <span data-ttu-id="bb47d-171">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="bb47d-171">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="bb47d-172">Pasos</span><span class="sxs-lookup"><span data-stu-id="bb47d-172">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="bb47d-173">Para crear y configurar un ESB rampa</span><span class="sxs-lookup"><span data-stu-id="bb47d-173">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="bb47d-174">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-174">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="bb47d-175">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-175">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="bb47d-176">Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-176">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="bb47d-177">En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-177">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="bb47d-178">En el **propiedades de la ubicación de recepción** cuadro de diálogo, escriba **OnRamp.Itinerary.HowTo** en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bb47d-178">In the **Receive Location Properties** dialog box, type **OnRamp.Itinerary.HowTo** in the **Name** box.</span></span>  
  
6.  <span data-ttu-id="bb47d-179">En el **tipo** la lista desplegable, haga clic en **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-179">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="bb47d-180">En el **propiedades de transporte de archivo** cuadro de diálogo, escriba **C:\HowTos\DropFolder** en el **carpeta recepción** cuadro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-180">In the **FILE Transport Properties** dialog box, type **C:\HowTos\DropFolder** in the **Receive folder** box, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a><span data-ttu-id="bb47d-181">Para configurar la en rampa para realizar la validación de mensaje</span><span class="sxs-lookup"><span data-stu-id="bb47d-181">To configure the on-ramp to perform message validation</span></span>  
  
1.  <span data-ttu-id="bb47d-182">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **canalización de recepción** la lista desplegable, haga clic en **ItinerarySelectReceiveXml**y, a continuación, haga clic en el botón de puntos suspensivos (...) ).</span><span class="sxs-lookup"><span data-stu-id="bb47d-182">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, click **ItinerarySelectReceiveXml**, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="bb47d-183">Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **desensamblador XML** propiedades de componente:</span><span class="sxs-lookup"><span data-stu-id="bb47d-183">Use the **Configure Pipeline** dialog box to configure the following **XML disassembler** component properties:</span></span>  
  
    1.  <span data-ttu-id="bb47d-184">Expanda la aplicación GlobalBank.Esb y, a continuación, haga clic en **esquemas**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-184">Expand the GlobalBank.Esb application, and then click **Schemas**.</span></span> <span data-ttu-id="bb47d-185">Haga clic en **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-185">Right-click **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**, and then click **Properties**.</span></span> <span data-ttu-id="bb47d-186">Copia la **nombre** y **ensamblado** propiedades y péguelos en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="bb47d-186">Copy the **Name** and **Assembly** properties and paste them into a text file.</span></span>  
  
    2.  <span data-ttu-id="bb47d-187">En el **desensamblar** componente, haga clic en **True** en el **ValidateDocument** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bb47d-187">In the **Disassemble** component, click **True** in the **ValidateDocument** drop-down list.</span></span>  
  
    3.  <span data-ttu-id="bb47d-188">Haga clic en el **DocumentSpecNames** propiedad y, a continuación, escriba el nombre completo del esquema.</span><span class="sxs-lookup"><span data-stu-id="bb47d-188">Click the **DocumentSpecNames** property, and then type the fully qualified name of the schema.</span></span> <span data-ttu-id="bb47d-189">El nombre completo empieza por el nombre y va seguido por una coma y la información de ensamblado extraída en el paso una.</span><span class="sxs-lookup"><span data-stu-id="bb47d-189">The fully qualified name starts with the name and is followed by a comma and the assembly information extracted in step a.</span></span> <span data-ttu-id="bb47d-190">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bb47d-190">The following is an example:</span></span>  
  
         <span data-ttu-id="bb47d-191">GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc, GlobalBank.ESB.DynamicResolution.Schemas, versión = 2.0.0.0, Culture = neutral, PublicKeyToken = c2c8b2b87f54180a</span><span class="sxs-lookup"><span data-stu-id="bb47d-191">GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc, GlobalBank.ESB.DynamicResolution.Schemas, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bb47d-192">Este es el nombre completo del esquema que se debe validar; está compuesto por el nombre del esquema y las cuatro propiedades de ensamblado: nombre del ensamblado, versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="bb47d-192">This is the fully qualified name of the schema to be validated; it is comprised of the schema name and four assembly properties: assembly name, version, culture, and public key token.</span></span> <span data-ttu-id="bb47d-193">Se permiten varios valores; Separe varios esquemas con una canalización (&#124;) símbolo.</span><span class="sxs-lookup"><span data-stu-id="bb47d-193">Multiple values are allowed; separate multiple schemas with a pipe (&#124;) symbol.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="bb47d-194">Para configurar el componente de canalización de Selector de itinerario</span><span class="sxs-lookup"><span data-stu-id="bb47d-194">To configure the Itinerary Selector Pipeline component</span></span>  
  
1.  <span data-ttu-id="bb47d-195">En el **configurar canalización** diálogo cuadro, configure lo siguiente **Selector de itinerario** propiedades de componente:</span><span class="sxs-lookup"><span data-stu-id="bb47d-195">In the **Configure Pipeline** dialog box, configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="bb47d-196">Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-196">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="bb47d-197">Haga clic en el **ResolverConnectionString** propiedad y, a continuación, escriba **itinerario:\\\name=Validation;**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-197">Click the **ResolverConnectionString** property, and then type **ITINERARY:\\\name=Validation;**.</span></span>  
  
    3.  <span data-ttu-id="bb47d-198">Haga clic en **Aceptar** para cerrar el **configurar canalización** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb47d-198">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
2.  <span data-ttu-id="bb47d-199">Haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb47d-199">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="bb47d-200">En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-200">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a><span data-ttu-id="bb47d-201">Para probar la selección de itinerario y la validación de mensaje</span><span class="sxs-lookup"><span data-stu-id="bb47d-201">To test the message validation and itinerary selection</span></span>  
  
1.  <span data-ttu-id="bb47d-202">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="bb47d-202">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="bb47d-203">Copia (no se mueven) NAOrderDoc.xml a la carpeta CarpetaDestino.</span><span class="sxs-lookup"><span data-stu-id="bb47d-203">Copy (do not move) NAOrderDoc.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="bb47d-204">Vaya a C:\HowTos\Out. Compruebe que Validated%MessageID%.xml se ha escrito en el directorio.</span><span class="sxs-lookup"><span data-stu-id="bb47d-204">Browse to C:\HowTos\Out. Verify that Validated%MessageID%.xml has been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb47d-205">El mensaje válido completa su enrutamiento basado en itinerario, según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="bb47d-205">The valid message completed its itinerary-based routing, as expected.</span></span>  
  
4.  <span data-ttu-id="bb47d-206">Eliminar Validated%MessageID%.xml desde la carpeta Out.</span><span class="sxs-lookup"><span data-stu-id="bb47d-206">Delete Validated%MessageID%.xml from the Out folder.</span></span>  
  
5.  <span data-ttu-id="bb47d-207">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="bb47d-207">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
6.  <span data-ttu-id="bb47d-208">Copia (no se mueven) Invalid.xml a la carpeta CarpetaDestino.</span><span class="sxs-lookup"><span data-stu-id="bb47d-208">Copy (do not move) Invalid.xml to the DropFolder folder.</span></span>  
  
7.  <span data-ttu-id="bb47d-209">Vaya a C:\HowTos\Out. Compruebe que no se ha entregado ningún mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="bb47d-209">Browse to C:\HowTos\Out. Verify that no new message has been delivered.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb47d-210">No se pudo validar el mensaje; por lo tanto, enrutamiento basado en itinerario no se pudo completar.</span><span class="sxs-lookup"><span data-stu-id="bb47d-210">The message could not be validated; therefore, itinerary-based routing could not be completed.</span></span>  
  
8.  <span data-ttu-id="bb47d-211">Haga clic en **iniciar** en la barra de tareas, seleccione **herramientas administrativas**y, a continuación, haga clic en **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-211">Click **Start** on the taskbar, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
9. <span data-ttu-id="bb47d-212">En el Visor de eventos, expanda **registros de Windows**y, a continuación, haga clic en **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-212">In Event Viewer, expand **Windows Logs**, and then click **Application**.</span></span>  
  
10. <span data-ttu-id="bb47d-213">Busque un evento reciente donde la **origen** es **BizTalk Server**y el **Id. de evento** es **5719**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-213">Locate a recent event where the **Source** is **BizTalk Server**, and the **Event ID** is **5719**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb47d-214">La presentación y el error del mensaje no válido generó una entrada de excepción en el registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb47d-214">The submission and failure of the invalid message resulted in an exception entry to the application event log.</span></span>  
  
11. <span data-ttu-id="bb47d-215">En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-215">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Disable**.</span></span>  
  
12. <span data-ttu-id="bb47d-216">Después de la **OnRamp.Itinerary.HowTo** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-216">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="bb47d-217">En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bb47d-217">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="bb47d-218">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bb47d-218">Additional Resources</span></span>  
 <span data-ttu-id="bb47d-219">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="bb47d-219">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="bb47d-220">Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="bb47d-220">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="bb47d-221">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="bb47d-221">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="bb47d-222">Instalación y ejecución del ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="bb47d-222">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)