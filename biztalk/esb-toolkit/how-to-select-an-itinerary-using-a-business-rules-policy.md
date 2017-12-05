---
title: "Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 521b3768251cfcd31defe271a21d4b2d0bc771e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a><span data-ttu-id="b350e-102">Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="b350e-102">How to: Select an Itinerary Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="b350e-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="b350e-103">Goal</span></span>  
 <span data-ttu-id="b350e-104">Esta sección muestra cómo crear reglas de negocios que pueden usarse para seleccionar un itinerario en función del contenido de un mensaje recibido y cómo configurar el componente de canalización de Selector de itinerario dentro de un genérico itinerario en rampa para llamar a estas reglas.</span><span class="sxs-lookup"><span data-stu-id="b350e-104">This section demonstrates how to create business rules that can be used to select an itinerary based on the content of a received message and how to configure the Itinerary Selector pipeline component within a generic itinerary on-ramp to call these rules.</span></span> <span data-ttu-id="b350e-105">Esta sección describe un escenario empresarial en el que el mensajes se enrutan de manera diferente, en función de la región donde reside el cliente.</span><span class="sxs-lookup"><span data-stu-id="b350e-105">This section describes a business scenario in which messages are routed differently, based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="b350e-106">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b350e-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="b350e-107">Modelos itinerarios para las divisiones del este y de cliente Global Bank.</span><span class="sxs-lookup"><span data-stu-id="b350e-107">Model itineraries for the Western and Eastern divisions of customer Global Bank.</span></span>  
  
-   <span data-ttu-id="b350e-108">Crear directivas de reglas de negocios que se usará para seleccionar un itinerario para procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b350e-108">Create business rules policies that will be used to select an itinerary for processing request.</span></span>  
  
-   <span data-ttu-id="b350e-109">Configurar el componente de canalización de Selector de itinerario para usar una directiva de reglas de negocios para seleccionar el itinerario adecuado.</span><span class="sxs-lookup"><span data-stu-id="b350e-109">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b350e-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b350e-110">Prerequisites</span></span>  
 <span data-ttu-id="b350e-111">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="b350e-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="b350e-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b350e-112">Before You Begin</span></span>  
 <span data-ttu-id="b350e-113">Complete las tareas siguientes antes de realizar los pasos más adelante en este tema "Cómo...":</span><span class="sxs-lookup"><span data-stu-id="b350e-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="b350e-114">Crear el mensaje de prueba GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="b350e-114">Create the GlobalBank West test message.</span></span>  
  
-   <span data-ttu-id="b350e-115">Crear el mensaje de prueba de este GlobalBank.</span><span class="sxs-lookup"><span data-stu-id="b350e-115">Create the GlobalBank East test message.</span></span>  
  
 <span data-ttu-id="b350e-116">Los procedimientos siguientes describen cómo realizar cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="b350e-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="b350e-117">Para crear el mensaje de prueba GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="b350e-117">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="b350e-118">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="b350e-118">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="b350e-119">Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de West.xml.</span><span class="sxs-lookup"><span data-stu-id="b350e-119">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="b350e-120">En el Bloc de notas, abra West.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankWest**.</span><span class="sxs-lookup"><span data-stu-id="b350e-120">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="b350e-121">Guardar West.xml como UTF-8 y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="b350e-121">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="b350e-122">Para crear el mensaje de prueba de este GlobalBank</span><span class="sxs-lookup"><span data-stu-id="b350e-122">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="b350e-123">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="b350e-123">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="b350e-124">Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de East.xml.</span><span class="sxs-lookup"><span data-stu-id="b350e-124">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="b350e-125">En el Bloc de notas, abra East.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankEast**.</span><span class="sxs-lookup"><span data-stu-id="b350e-125">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="b350e-126">Guardar East.xml como UTF-8 y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="b350e-126">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="b350e-127">Pasos</span><span class="sxs-lookup"><span data-stu-id="b350e-127">Steps</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="b350e-128">Para crear una directiva del motor de reglas de negocios (BRE) para seleccionar un itinerario con propiedades personalizadas de mensajes</span><span class="sxs-lookup"><span data-stu-id="b350e-128">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="b350e-129">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="b350e-129">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="b350e-130">En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="b350e-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="b350e-131">Nombre de la directiva **ResolveItineraryBasedOnCustomer**.</span><span class="sxs-lookup"><span data-stu-id="b350e-131">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-132">Este tema "Cómo..." utiliza la misma directiva de reglas de negocios y los itinerarios como los creados en el tema [Cómo: dividir un intercambio y enrutar los mensajes resultantes a varios archivos ubicaciones utilizando distintos itinerarios](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md).</span><span class="sxs-lookup"><span data-stu-id="b350e-132">This How-to topic uses the same business rules policy and itineraries as those created in the topic [How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md).</span></span> <span data-ttu-id="b350e-133">Si ya ha completado esa sección, puede omitir el procedimiento, "para crear y configurar un ESB en rampa" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b350e-133">If you have already completed that section, you can skip to the procedure, "To create and configure an ESB on-ramp" later in this topic.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="b350e-134">Para agregar una regla de selección de cliente GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="b350e-134">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="b350e-135">En el **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="b350e-135">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="b350e-136">Nombre de la regla **SetGlobalBankWestItinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-136">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="b350e-137">En el Explorador de hechos, haga clic en el **esquemas XML** pestaña, haga clic en **esquemas**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-137">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="b350e-138">En el **archivos de esquema** cuadro de diálogo, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas, seleccione **NAOrderDoc.xsd**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="b350e-138">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-139">Éste es el esquema que define el mensaje NAOrderDoc.xml, que se usó para crear los mensajes de Oeste y este que va a usar para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b350e-139">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="b350e-140">En el Explorador de hechos, haga clic en **NAOrderDoc.xsd**, haga clic en el **tipo de documento** propiedad en el panel de propiedades y, a continuación, escriba **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="b350e-140">In Facts Explorer, click **NAOrderDoc.xsd**, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-141">Este es el nombre completo del esquema.</span><span class="sxs-lookup"><span data-stu-id="b350e-141">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="b350e-142">En el Explorador de hechos, expanda **NAOrderDoc.xsd**y, a continuación, expanda **OrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="b350e-142">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="b350e-143">En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.</span><span class="sxs-lookup"><span data-stu-id="b350e-143">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="b350e-144">En el Explorador de hechos, arrastre el **customerName** elemento a la **argumento1** nodo bajo **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="b350e-144">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="b350e-145">Haga clic en el **argumento2** nodo y, a continuación, escriba **GlobalBankWest**.</span><span class="sxs-lookup"><span data-stu-id="b350e-145">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="b350e-146">En el Explorador de hechos, haga clic en el **vocabularios** ficha. Expanda el **ESB. Itinerario** vocabulario, expanda **versión 1.1**y, a continuación, arrastre el **nombre del conjunto de itinerario** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="b350e-146">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="b350e-147">Haga clic en  **\<una cadena vacía\>**y, a continuación, escriba **GlobalBankWestItinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-147">Click **\<empty string\>**, and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-148">Más adelante en este tema de procedimientos, creará este itinerario para procesar los mensajes de GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="b350e-148">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="b350e-149">Para agregar una regla de selección para este GlobalBank de cliente</span><span class="sxs-lookup"><span data-stu-id="b350e-149">To add a selection rule for Customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="b350e-150">En el Explorador de directivas, haga clic en el **SetGlobalBankWestItinerary** de regla y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="b350e-150">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="b350e-151">Haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-151">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="b350e-152">En el **nombre de nueva regla** cuadro de diálogo, escriba **SetGlobalBankEastItinerary**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-152">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b350e-153">En el Explorador de directivas, haga clic en el **SetGlobalBankEastItinerary** regla.</span><span class="sxs-lookup"><span data-stu-id="b350e-153">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="b350e-154">En el **condiciones** sección, haga clic en **GlobalBankWest**y, a continuación, haga clic en **Restablecer argumento**.</span><span class="sxs-lookup"><span data-stu-id="b350e-154">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="b350e-155">Haga clic en **argumento2**y, a continuación, escriba **GlobalBankEast**.</span><span class="sxs-lookup"><span data-stu-id="b350e-155">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="b350e-156">En el **acciones** sección, haga clic en **GlobalBankWestItinerary**y, a continuación, haga clic en **Restablecer argumento**.</span><span class="sxs-lookup"><span data-stu-id="b350e-156">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="b350e-157">Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **GlobalBankEastItinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-157">Click **\<empty string\>** and then type **GlobalBankEastItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-158">Más adelante en el tema "Cómo...", creará este itinerario para procesar los mensajes de este GlobalBank.</span><span class="sxs-lookup"><span data-stu-id="b350e-158">Later in the How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="b350e-159">Para publicar e implementar la directiva</span><span class="sxs-lookup"><span data-stu-id="b350e-159">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="b350e-160">En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic derecho **versión 1.0 (sin guardar)**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-160">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="b350e-161">En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-161">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="b350e-162">Para crear un modelo de lenguaje de itinerarios específico de dominio (DSL) ESB para los mensajes de GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="b350e-162">To create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="b350e-163">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="b350e-163">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="b350e-164">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="b350e-164">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="b350e-165">En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.</span><span class="sxs-lookup"><span data-stu-id="b350e-165">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="b350e-166">En el **nombre** , escriba **GlobalBankWestItinerary**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-166">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="b350e-167">Para configurar las propiedades de la itinerario GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="b350e-167">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="b350e-168">En Visual Studio, haga clic en la superficie de diseño de **GlobalBankWestItinerary.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-168">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="b350e-169">En el **GlobalBankWestItinerary** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-169">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-170">En el **modelo exportador** la lista desplegable, haga clic en **base de datos de itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="b350e-170">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="b350e-171">Haga clic en el botón de puntos suspensivos (...) junto a la **base de datos de itinerario** propiedad.</span><span class="sxs-lookup"><span data-stu-id="b350e-171">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="b350e-172">En el **propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de repositorio itinerarios y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).</span><span class="sxs-lookup"><span data-stu-id="b350e-172">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="b350e-173">En el **estado de itinerario** la lista desplegable, haga clic en **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="b350e-173">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-174">Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio tras la recepción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b350e-174">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository upon message reception.</span></span> <span data-ttu-id="b350e-175">Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar a la resolución de motor de reglas de negocios (BRI) para evaluar los mensajes entrantes y seleccionar el itinerario adecuado de este repositorio.</span><span class="sxs-lookup"><span data-stu-id="b350e-175">You will later configure the Itinerary Selector pipeline component to use the Business Rules Engine resolver (BRI) to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="b350e-176">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="b350e-176">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="b350e-177">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="b350e-177">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="b350e-178">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-178">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-179">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="b350e-179">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="b350e-180">En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.</span><span class="sxs-lookup"><span data-stu-id="b350e-180">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-181">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="b350e-181">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b350e-182">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-182">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="b350e-183">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-183">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="b350e-184">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-184">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-185">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="b350e-185">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="b350e-186">En el **Extender** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.</span><span class="sxs-lookup"><span data-stu-id="b350e-186">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-187">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="b350e-187">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b350e-188">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="b350e-188">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="b350e-189">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-189">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="b350e-190">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-190">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-191">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.</span><span class="sxs-lookup"><span data-stu-id="b350e-191">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="b350e-192">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.</span><span class="sxs-lookup"><span data-stu-id="b350e-192">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-193">En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="b350e-193">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="b350e-194">Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="b350e-194">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="b350e-195">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-195">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-196">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.</span><span class="sxs-lookup"><span data-stu-id="b350e-196">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="b350e-197">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="b350e-197">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-198">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="b350e-198">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="b350e-199">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\West%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="b350e-199">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="b350e-200">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="b350e-200">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b350e-201">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-201">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="b350e-202">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="b350e-202">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b350e-203">Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-203">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="b350e-204">Para exportar el modelo a la base de datos de itinerario</span><span class="sxs-lookup"><span data-stu-id="b350e-204">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="b350e-205">En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankWestItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="b350e-205">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-206">El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.</span><span class="sxs-lookup"><span data-stu-id="b350e-206">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="b350e-207">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b350e-207">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="b350e-208">Para crear un modelo DSL itinerario de ESB para mensaje de este GlobalBank</span><span class="sxs-lookup"><span data-stu-id="b350e-208">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="b350e-209">En Visual Studio, abra C:\HowTos\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="b350e-209">In Visual Studio, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="b350e-210">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="b350e-210">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="b350e-211">En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.</span><span class="sxs-lookup"><span data-stu-id="b350e-211">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="b350e-212">En el **nombre** , escriba **GlobalBankEastItinerary**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-212">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="b350e-213">Para configurar las propiedades de la itinerario este GlobalBank</span><span class="sxs-lookup"><span data-stu-id="b350e-213">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="b350e-214">En Visual Studio, haga clic en la superficie de diseño de **GlobalBankEastItinerary.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-214">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="b350e-215">En el **GlobalBankEastItinerary** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-215">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-216">En el **modelo exportador** la lista desplegable, haga clic en **base de datos de itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="b350e-216">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="b350e-217">Haga clic en el botón de puntos suspensivos (...) junto a la **base de datos de itinerario** propiedad.</span><span class="sxs-lookup"><span data-stu-id="b350e-217">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="b350e-218">En el **propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de repositorio itinerarios y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).</span><span class="sxs-lookup"><span data-stu-id="b350e-218">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="b350e-219">En el **estado de itinerario** la lista desplegable, haga clic en **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="b350e-219">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-220">Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio cuando se reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="b350e-220">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="b350e-221">Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar al Solucionador BRI para evaluar los mensajes entrantes y seleccionar el itinerario adecuado de este repositorio.</span><span class="sxs-lookup"><span data-stu-id="b350e-221">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="b350e-222">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="b350e-222">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="b350e-223">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="b350e-223">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="b350e-224">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-224">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-225">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="b350e-225">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="b350e-226">En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.</span><span class="sxs-lookup"><span data-stu-id="b350e-226">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-227">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="b350e-227">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b350e-228">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-228">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="b350e-229">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-229">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="b350e-230">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-230">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-231">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="b350e-231">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="b350e-232">En el **Extender** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.</span><span class="sxs-lookup"><span data-stu-id="b350e-232">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-233">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="b350e-233">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b350e-234">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="b350e-234">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="b350e-235">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-235">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="b350e-236">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-236">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-237">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.</span><span class="sxs-lookup"><span data-stu-id="b350e-237">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="b350e-238">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.</span><span class="sxs-lookup"><span data-stu-id="b350e-238">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-239">En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="b350e-239">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="b350e-240">Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="b350e-240">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="b350e-241">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b350e-241">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-242">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.</span><span class="sxs-lookup"><span data-stu-id="b350e-242">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="b350e-243">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="b350e-243">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="b350e-244">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="b350e-244">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="b350e-245">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\East%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="b350e-245">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="b350e-246">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="b350e-246">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b350e-247">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-247">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="b350e-248">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="b350e-248">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b350e-249">Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="b350e-249">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="b350e-250">Para exportar el modelo a la base de datos de itinerario</span><span class="sxs-lookup"><span data-stu-id="b350e-250">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="b350e-251">En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankEastItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="b350e-251">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-252">El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.</span><span class="sxs-lookup"><span data-stu-id="b350e-252">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="b350e-253">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b350e-253">Save all project artifacts.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="b350e-254">Para crear y configurar un ESB rampa</span><span class="sxs-lookup"><span data-stu-id="b350e-254">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="b350e-255">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="b350e-255">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b350e-256">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="b350e-256">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="b350e-257">Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="b350e-257">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="b350e-258">En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-258">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b350e-259">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba **OnRamp.Itinerary.HowTo**.</span><span class="sxs-lookup"><span data-stu-id="b350e-259">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="b350e-260">En el **tipo** la lista desplegable, haga clic en **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-260">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="b350e-261">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba **C:\HowTos\DropFolder**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-261">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="b350e-262">Para configurar el componente de canalización de Selector de itinerario</span><span class="sxs-lookup"><span data-stu-id="b350e-262">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="b350e-263">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **canalización de recepción** la lista desplegable, haga clic en **ItinerarySelectReceiveXml**y, a continuación, haga clic en el botón de puntos suspensivos (...) ).</span><span class="sxs-lookup"><span data-stu-id="b350e-263">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, click **ItinerarySelectReceiveXml**, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="b350e-264">Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **Selector de itinerario** propiedades de componente:</span><span class="sxs-lookup"><span data-stu-id="b350e-264">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="b350e-265">Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="b350e-265">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="b350e-266">Haga clic en el **ResolverConnectionString** propiedad y, a continuación, escriba **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span><span class="sxs-lookup"><span data-stu-id="b350e-266">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="b350e-267">Haga clic en **Aceptar** para cerrar el **configurar canalización** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b350e-267">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
3.  <span data-ttu-id="b350e-268">Haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b350e-268">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="b350e-269">En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-269">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="b350e-270">Para probar el selector itinerario y reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="b350e-270">To test the itinerary selector and business rules</span></span>  
  
1.  <span data-ttu-id="b350e-271">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="b350e-271">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="b350e-272">Copia (no se mueven) los archivos East.xml y West.xml a la carpeta CarpetaDestino.</span><span class="sxs-lookup"><span data-stu-id="b350e-272">Copy (do not move) the files East.xml and West.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="b350e-273">Vaya a C:\HowTos\Out. Compruebe que los mensajes de East%MessageID%.xml y West%MessageID%.xml se han escrito en el directorio.</span><span class="sxs-lookup"><span data-stu-id="b350e-273">Browse to C:\HowTos\Out. Verify that the East%MessageID%.xml and West%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b350e-274">Aunque idénticos salvo por el valor del elemento del cliente, los mensajes se han procesado mediante diferentes itinerarios, basados en la resolución del componente de canalización de Selector de itinerario.</span><span class="sxs-lookup"><span data-stu-id="b350e-274">Though identical except for the value of the customer element, the messages were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="b350e-275">En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-275">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="b350e-276">Después de la **OnRamp.Itinerary.HowTo** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b350e-276">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="b350e-277">En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b350e-277">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="b350e-278">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b350e-278">Additional Resources</span></span>  
 <span data-ttu-id="b350e-279">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="b350e-279">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="b350e-280">Cómo: Dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos mediante distintos itinerarios</span><span class="sxs-lookup"><span data-stu-id="b350e-280">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [<span data-ttu-id="b350e-281">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="b350e-281">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="b350e-282">Instalación y ejecución del ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="b350e-282">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="b350e-283">Uso de resolución y enrutamiento dinámicos</span><span class="sxs-lookup"><span data-stu-id="b350e-283">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="b350e-284">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="b350e-284">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)