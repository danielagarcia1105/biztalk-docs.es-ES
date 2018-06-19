---
title: 'Cómo: dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos utilizando distintos itinerarios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 538432f548b1403fd9c0cd566b82eb8cb113f737
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010757"
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a><span data-ttu-id="d5be8-102">Cómo: dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos utilizando distintos itinerarios</span><span class="sxs-lookup"><span data-stu-id="d5be8-102">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>
## <a name="goal"></a><span data-ttu-id="d5be8-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="d5be8-103">Goal</span></span>  
 <span data-ttu-id="d5be8-104">En esta sección se muestra cómo crear un ESB en rampa que usa el **ItinerarySelectReceiveXml** canalización y cómo configurar los componentes de la canalización para dividir un intercambio de entrada y seleccione el enrutamiento adecuado para la remisión cada mensaje resultante, basado en contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d5be8-104">This section demonstrates how to create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline and how to configure the pipeline's components to split an inbound interchange and select the appropriate routing slip for each resulting message, based on message context.</span></span> <span data-ttu-id="d5be8-105">Selección de itinerarios se resolverá mediante una directiva de reglas de negocios y los mensajes se enrutarán diferente en función de la región donde reside el cliente.</span><span class="sxs-lookup"><span data-stu-id="d5be8-105">Itinerary selection will be resolved using a business rules policy, and messages will be routed differently based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="d5be8-106">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5be8-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="d5be8-107">Crear un ESB en rampa que divide un intercambio XML.</span><span class="sxs-lookup"><span data-stu-id="d5be8-107">Create an ESB on-ramp that splits an XML interchange.</span></span>  
  
-   <span data-ttu-id="d5be8-108">Configurar el componente de canalización de Selector de itinerario para usar una directiva de reglas de negocios para seleccionar el itinerario adecuado.</span><span class="sxs-lookup"><span data-stu-id="d5be8-108">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5be8-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d5be8-109">Prerequisites</span></span>  
 <span data-ttu-id="d5be8-110">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="d5be8-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="d5be8-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d5be8-111">Before You Begin</span></span>  
 <span data-ttu-id="d5be8-112">Complete las tareas siguientes antes de realizar los pasos más adelante en este tema "Cómo...":</span><span class="sxs-lookup"><span data-stu-id="d5be8-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="d5be8-113">Crear los artefactos necesarios.</span><span class="sxs-lookup"><span data-stu-id="d5be8-113">Create the required artifacts.</span></span>  
  
-   <span data-ttu-id="d5be8-114">Agregue un proyecto de esquemas a la solución de patrones.</span><span class="sxs-lookup"><span data-stu-id="d5be8-114">Add a schemas project to the Patterns solution.</span></span>  
  
-   <span data-ttu-id="d5be8-115">Agregue los artefactos al proyecto de esquemas.</span><span class="sxs-lookup"><span data-stu-id="d5be8-115">Add the artifacts to the Schemas project.</span></span>  
  
-   <span data-ttu-id="d5be8-116">Crear una directiva del BRE para seleccionar un itinerario con propiedades personalizadas de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d5be8-116">Create a BRE policy to select an itinerary using custom message properties.</span></span>  
  
-   <span data-ttu-id="d5be8-117">Agregar una regla de selección de cliente GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="d5be8-117">Add a selection rule for customer GlobalBank West.</span></span>  
  
-   <span data-ttu-id="d5be8-118">Agregar una regla de selección para GlobalBank este cliente.</span><span class="sxs-lookup"><span data-stu-id="d5be8-118">Add a selection rule for customer GlobalBank East.</span></span>  
  
-   <span data-ttu-id="d5be8-119">Publique e implemente la directiva.</span><span class="sxs-lookup"><span data-stu-id="d5be8-119">Publish and deploy the policy.</span></span>  
  
-   <span data-ttu-id="d5be8-120">Crear un modelo de lenguaje de itinerarios específico de dominio (DSL) de ESB para los mensajes de GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="d5be8-120">Create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages.</span></span>  
  
-   <span data-ttu-id="d5be8-121">Configurar las propiedades de la itinerario GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="d5be8-121">Configure the properties of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="d5be8-122">Definir la estructura de la itinerario GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="d5be8-122">Define the structure of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="d5be8-123">Exportar el modelo GlobalBank West a la base de datos de itinerario.</span><span class="sxs-lookup"><span data-stu-id="d5be8-123">Export the GlobalBank West model to the itinerary database.</span></span>  
  
-   <span data-ttu-id="d5be8-124">Crear un modelo DSL itinerario de ESB para los mensajes de este GlobalBank.</span><span class="sxs-lookup"><span data-stu-id="d5be8-124">Create an ESB itinerary DSL model for GlobalBank East messages.</span></span>  
  
-   <span data-ttu-id="d5be8-125">Configurar las propiedades de la itinerario GlobalBank este.</span><span class="sxs-lookup"><span data-stu-id="d5be8-125">Configure the properties of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="d5be8-126">Definir la estructura de la itinerario GlobalBank este.</span><span class="sxs-lookup"><span data-stu-id="d5be8-126">Define the structure of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="d5be8-127">Exportar el modelo de este GlobalBank a la base de datos de itinerario.</span><span class="sxs-lookup"><span data-stu-id="d5be8-127">Export the GlobalBank East model to the itinerary database.</span></span>  
  
     <span data-ttu-id="d5be8-128">Los procedimientos siguientes describen cómo realizar cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="d5be8-128">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-required-artifacts"></a><span data-ttu-id="d5be8-129">Para crear los artefactos necesarios</span><span class="sxs-lookup"><span data-stu-id="d5be8-129">To create the required artifacts</span></span>  
  
1.  <span data-ttu-id="d5be8-130">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="d5be8-130">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="d5be8-131">Crear un nuevo documento de texto denominado OrderDocEnvelope.xsd.</span><span class="sxs-lookup"><span data-stu-id="d5be8-131">Create a new text document named OrderDocEnvelope.xsd.</span></span>  
  
3.  <span data-ttu-id="d5be8-132">Abra el esquema de OrderDocEnvelope.xsd en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="d5be8-132">Open the OrderDocEnvelope.xsd schema in Notepad.</span></span>  
  
4.  <span data-ttu-id="d5be8-133">Editar el documento utilizando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5be8-133">Edit the document using the following code.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <xs:schema xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://ESB.BizUnit.Map.Test" targetNamespace="http://ESB.BizUnit.Map.Test" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
      <xs:import schemaLocation="GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc" namespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
      <xs:annotation>  
        <xs:appinfo>  
          <b:schemaInfo is_envelope="yes" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
          <b:references>  
            <b:reference targetNamespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
          </b:references>  
        </xs:appinfo>  
      </xs:annotation>  
      <xs:element name="OrderEnvelope">  
        <xs:annotation>  
          <xs:appinfo>  
            <b:recordInfo body_xpath="/*[local-name()='OrderEnvelope' and namespace-uri()='http://ESB.BizUnit.Map.Test']" />  
          </xs:appinfo>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element ref="ns0:OrderDoc" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
5.  <span data-ttu-id="d5be8-134">Guardar OrderDocEnvelope.xsd como UTF-8 y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="d5be8-134">Save OrderDocEnvelope.xsd as UTF-8, and then close Notepad.</span></span>  
  
6.  <span data-ttu-id="d5be8-135">En la carpeta C:\HowTos, cree un nuevo documento de texto denominado Batch.xml.</span><span class="sxs-lookup"><span data-stu-id="d5be8-135">In the C:\HowTos folder, create a new text document named Batch.xml.</span></span>  
  
7.  <span data-ttu-id="d5be8-136">En el Bloc de notas, abra Batch.xml.</span><span class="sxs-lookup"><span data-stu-id="d5be8-136">In Notepad, open Batch.xml.</span></span>  
  
8.  <span data-ttu-id="d5be8-137">Editar el documento utilizando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5be8-137">Edit the document using the following code.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <ns0:OrderEnvelope xmlns:ns0="http://ESB.BizUnit.Map.Test">  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankWest</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>10</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>11</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>12</ns0:requestType>  
      </ns0:OrderDoc>  
    </ns0:OrderEnvelope>  
    ```  
  
9. <span data-ttu-id="d5be8-138">Guarde y cierre Batch.xml.</span><span class="sxs-lookup"><span data-stu-id="d5be8-138">Save and close Batch.xml.</span></span>  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a><span data-ttu-id="d5be8-139">Para agregar un proyecto de esquemas a la solución de patrones</span><span class="sxs-lookup"><span data-stu-id="d5be8-139">To add a schemas project to the Patterns solution</span></span>  
  
1.  <span data-ttu-id="d5be8-140">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="d5be8-140">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="d5be8-141">En el Explorador de soluciones, haga clic en **solución 'Patrones'**, seleccione **agregar**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-141">In Solution Explorer, right-click **Solution 'Patterns'**, point to **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="d5be8-142">En el **Agregar nuevo proyecto** cuadro de diálogo, en el panel tipos de proyecto, haga clic en **proyectos de BizTalk**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5be8-142">In the **Add New Project** dialog box, in the Project types pane, click **BizTalk Projects**, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="d5be8-143">En el panel Plantillas, haga clic en **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-143">In the Templates pane, click **Empty BizTalk Server Project**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-144">En el **nombre** , escriba **Patterns.Schemas**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-144">In the **Name** box, type **Patterns.Schemas**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d5be8-145">En el Explorador de soluciones, haga clic en **Patterns.Schemas**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-145">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="d5be8-146">En la ventana Propiedades, en la **firma** ficha, seleccione la **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="d5be8-146">In the Properties window, on the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
6.  <span data-ttu-id="d5be8-147">En el **elegir un archivo de clave de nombre seguro** la lista desplegable, haga clic en  **\<nuevo... \>**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-147">In the **Choose a strong name key file** drop-down list, click **\<New...\>**.</span></span>  
  
7.  <span data-ttu-id="d5be8-148">En el **crear clave de nombre seguro** diálogo cuadro, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-148">In the **Create Strong Name Key** dialog box, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-149">En el **nombre de archivo de clave** , escriba **división**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-149">In the **Key file name** box, type **Splitting**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-150">Desactive el **proteger mi archivo de clave con una contraseña** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-150">Clear the **Protect my key file with a password** check box, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="d5be8-151">En la ventana Propiedades, en la **implementación** ficha la **nombre de la aplicación** , escriba **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-151">In the Properties window, on the **Deployment** tab, in the **Application Name** box, type **Microsoft.Practices.ESB**.</span></span>  
  
9. <span data-ttu-id="d5be8-152">Cierre la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="d5be8-152">Close the Properties window.</span></span>  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a><span data-ttu-id="d5be8-153">Para agregar los artefactos al proyecto de esquemas</span><span class="sxs-lookup"><span data-stu-id="d5be8-153">To add the artifacts to the Schemas project</span></span>  
  
1.  <span data-ttu-id="d5be8-154">En el Explorador de soluciones, haga clic en **Patterns.Schemas**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-154">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="d5be8-155">En el **examinar** pestaña de la **Agregar referencia** cuadro de diálogo, localice y seleccione C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-155">On the **Browse** tab of the **Add Reference** dialog box, browse to and select C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d5be8-156">En el Explorador de soluciones, haga clic en **Patterns.Schemas**, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-156">In Solution Explorer, right-click **Patterns.Schemas**, point to **Add**, and then click **Existing Item**.</span></span>  
  
4.  <span data-ttu-id="d5be8-157">En el **Agregar elemento existente** cuadro de diálogo, busque y seleccione C:\HowTos\OrderDocEnvelope.xsd y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-157">In the **Add Existing Item** dialog box, browse to and select C:\HowTos\OrderDocEnvelope.xsd, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="d5be8-158">Guarde todos los artefactos de la solución.</span><span class="sxs-lookup"><span data-stu-id="d5be8-158">Save all solution artifacts.</span></span>  
  
6.  <span data-ttu-id="d5be8-159">En el Explorador de soluciones, haga clic en **Patterns.Schemas**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-159">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-160">Este tema "Cómo..." utiliza la misma directiva de reglas de negocios y los itinerarios como los creados en el [Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md) tema.</span><span class="sxs-lookup"><span data-stu-id="d5be8-160">This How-to topic uses the same business rules policy and itineraries as those created in the [How to: Select an Itinerary Using a Business Rules Policy](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md) topic.</span></span> <span data-ttu-id="d5be8-161">Si aún no has completado esa sección, complete los siguientes pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="d5be8-161">If you have not already completed that section, please complete the following additional steps.</span></span> <span data-ttu-id="d5be8-162">Si ha completado esa sección, continuar directamente en la sección "Pasos".</span><span class="sxs-lookup"><span data-stu-id="d5be8-162">If you have completed that section, continue directly to the "Steps" section.</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="d5be8-163">Para crear una directiva del motor de reglas de negocios (BRE) para seleccionar un itinerario con propiedades personalizadas de mensajes</span><span class="sxs-lookup"><span data-stu-id="d5be8-163">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="d5be8-164">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-164">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="d5be8-165">En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-165">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="d5be8-166">Nombre de la directiva **ResolveItineraryBasedOnCustomer**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-166">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="d5be8-167">Para agregar una regla de selección de cliente GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="d5be8-167">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="d5be8-168">En el **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-168">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="d5be8-169">Nombre de la regla **SetGlobalBankWestItinerary**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-169">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="d5be8-170">En el Explorador de hechos, haga clic en el **esquemas XML** pestaña, haga clic en **esquemas**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-170">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="d5be8-171">En el **archivos de esquema** cuadro de diálogo, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas, seleccione NAOrderDoc.xsd y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-171">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select NAOrderDoc.xsd, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-172">Éste es el esquema que define el mensaje NAOrderDoc.xml, que se usó para crear los mensajes de Oeste y este que va a usar para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="d5be8-172">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="d5be8-173">En el Explorador de hechos, haga clic en NAOrderDoc.xsd, haga clic en el **tipo de documento** propiedad en el panel de propiedades y, a continuación, escriba **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-173">In Facts Explorer, click NAOrderDoc.xsd, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-174">Este es el nombre completo del esquema.</span><span class="sxs-lookup"><span data-stu-id="d5be8-174">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="d5be8-175">En el Explorador de hechos, expanda **NAOrderDoc.xsd**y, a continuación, expanda **OrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-175">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="d5be8-176">En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-176">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="d5be8-177">En el Explorador de hechos, arrastre el **customerName** elemento a la **argumento1** nodo bajo **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-177">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="d5be8-178">Haga clic en el **argumento2** nodo y, a continuación, escriba **GlobalBankWest**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-178">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="d5be8-179">En el Explorador de hechos, haga clic en el **vocabularios** ficha. Expanda el **ESB. Itinerario** vocabulario, expanda **versión 1.1**y, a continuación, arrastre el **nombre del conjunto de itinerario** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-179">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="d5be8-180">Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **GlobalBankWestItinerary**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-180">Click **\<empty string\>** and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-181">Más adelante en este tema de procedimientos, creará este itinerario para procesar los mensajes de GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="d5be8-181">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="d5be8-182">Para agregar una regla de selección para este GlobalBank de cliente</span><span class="sxs-lookup"><span data-stu-id="d5be8-182">To add a selection rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="d5be8-183">En el Explorador de directivas, haga clic en el **SetGlobalBankWestItinerary** de regla y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-183">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="d5be8-184">Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-184">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="d5be8-185">En el **nombre de nueva regla** cuadro de diálogo, escriba **SetGlobalBankEastItinerary**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-185">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d5be8-186">En el Explorador de directivas, haga clic en el **SetGlobalBankEastItinerary** regla.</span><span class="sxs-lookup"><span data-stu-id="d5be8-186">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="d5be8-187">En el **condiciones** sección, haga clic en **GlobalBankWest**y, a continuación, haga clic en **Restablecer argumento**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-187">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="d5be8-188">Haga clic en **argumento2**y, a continuación, escriba **GlobalBankEast**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-188">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="d5be8-189">En el **acciones** sección, haga clic en **GlobalBankWestItinerary**y, a continuación, haga clic en **Restablecer argumento**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-189">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="d5be8-190">Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **GlobalBankEastItinerary.**</span><span class="sxs-lookup"><span data-stu-id="d5be8-190">Click **\<empty string\>** and then type **GlobalBankEastItinerary.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-191">Más adelante en este tema de procedimientos, creará este itinerario para procesar los mensajes de este GlobalBank.</span><span class="sxs-lookup"><span data-stu-id="d5be8-191">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="d5be8-192">Para publicar e implementar la directiva</span><span class="sxs-lookup"><span data-stu-id="d5be8-192">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="d5be8-193">En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-193">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="d5be8-194">En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-194">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="d5be8-195">Para crear un modelo DSL itinerario de ESB para los mensajes de GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="d5be8-195">To create an ESB itinerary DSL model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="d5be8-196">En **Visual Studio**, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="d5be8-196">In **Visual Studio**, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="d5be8-197">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-197">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="d5be8-198">En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-198">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="d5be8-199">En el **nombre** , escriba **GlobalBankWestItinerary**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-199">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="d5be8-200">Para configurar las propiedades de la itinerario GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="d5be8-200">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="d5be8-201">En Visual Studio, haga clic en la superficie de diseño de **GlobalBankWestItinerary.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-201">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="d5be8-202">En el **GlobalBankWestItinerary** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-202">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-203">En el **modelo exportador** la lista desplegable, haga clic en **base de datos de itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-203">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-204">Haga clic en el botón de puntos suspensivos (...) junto a la **base de datos de itinerario** propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5be8-204">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="d5be8-205">En el **propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de repositorio itinerarios y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).</span><span class="sxs-lookup"><span data-stu-id="d5be8-205">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="d5be8-206">En el **estado de itinerario** la lista desplegable, haga clic en **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-206">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-207">Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio cuando se reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d5be8-207">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="d5be8-208">Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar al Solucionador BRI para evaluar los mensajes entrantes y seleccionar el itinerario adecuado de este repositorio.</span><span class="sxs-lookup"><span data-stu-id="d5be8-208">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a><span data-ttu-id="d5be8-209">Para definir la estructura de la itinerario GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="d5be8-209">To define the structure of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="d5be8-210">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="d5be8-210">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="d5be8-211">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-211">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-212">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-212">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-213">En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-213">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-214">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-214">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="d5be8-215">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-215">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="d5be8-216">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-216">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="d5be8-217">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-217">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-218">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-218">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-219">En el **Extender** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-219">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-220">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-220">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="d5be8-221">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-221">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="d5be8-222">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-222">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="d5be8-223">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-223">In the **ItineraryService1** properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-224">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-224">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-225">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-225">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-226">En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-226">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="d5be8-227">Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-227">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="d5be8-228">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-228">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-229">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-229">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-230">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-230">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-231">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-231">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="d5be8-232">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\West%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-232">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="d5be8-233">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-233">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="d5be8-234">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-234">Drag a connection from the **ReceiveNAOrder** model element to the  **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="d5be8-235">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-235">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="d5be8-236">Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-236">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a><span data-ttu-id="d5be8-237">Para exportar el modelo GlobalBank West a la base de datos de itinerario</span><span class="sxs-lookup"><span data-stu-id="d5be8-237">To export the GlobalBank West model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="d5be8-238">En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankWestItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-238">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-239">El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.</span><span class="sxs-lookup"><span data-stu-id="d5be8-239">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="d5be8-240">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5be8-240">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="d5be8-241">Para crear un modelo DSL itinerario de ESB para mensaje de este GlobalBank</span><span class="sxs-lookup"><span data-stu-id="d5be8-241">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="d5be8-242">En **Visual Studio**, abra C:\HowTos\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="d5be8-242">In **Visual Studio**, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="d5be8-243">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-243">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="d5be8-244">En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-244">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="d5be8-245">En el **nombre** , escriba **GlobalBankEastItinerary**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-245">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="d5be8-246">Para configurar las propiedades de la itinerario este GlobalBank</span><span class="sxs-lookup"><span data-stu-id="d5be8-246">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="d5be8-247">En Visual Studio, haga clic en la superficie de diseño de **GlobalBankEastItinerary.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-247">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="d5be8-248">En el **GlobalBankEastItinerary** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-248">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-249">En el **modelo exportador** la lista desplegable, haga clic en **base de datos de itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-249">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-250">Haga clic en el botón de puntos suspensivos (...) junto a la **base de datos de itinerario** propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5be8-250">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="d5be8-251">En el **propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de repositorio itinerarios y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).</span><span class="sxs-lookup"><span data-stu-id="d5be8-251">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="d5be8-252">En el **estado de itinerario** la lista desplegable, haga clic en **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-252">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-253">Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio cuando se reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d5be8-253">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="d5be8-254">Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar al Solucionador BRI para evaluar los mensajes entrantes y seleccionar el itinerario adecuado de este repositorio.</span><span class="sxs-lookup"><span data-stu-id="d5be8-254">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a><span data-ttu-id="d5be8-255">Para definir la estructura de la itinerario este GlobalBank</span><span class="sxs-lookup"><span data-stu-id="d5be8-255">To define the structure of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="d5be8-256">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="d5be8-256">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="d5be8-257">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-257">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-258">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-258">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-259">En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-259">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-260">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-260">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="d5be8-261">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-261">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="d5be8-262">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-262">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="d5be8-263">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-263">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-264">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-264">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-265">En el **Extender** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-265">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-266">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-266">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="d5be8-267">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-267">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="d5be8-268">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-268">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="d5be8-269">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-269">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-270">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-270">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-271">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-271">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-272">En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-272">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="d5be8-273">Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-273">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="d5be8-274">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d5be8-274">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-275">Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-275">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-276">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-276">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="d5be8-277">En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-277">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="d5be8-278">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\East%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-278">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="d5be8-279">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-279">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="d5be8-280">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-280">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="d5be8-281">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-281">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="d5be8-282">Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-282">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a><span data-ttu-id="d5be8-283">Para exportar el modelo de este GlobalBank a la base de datos de itinerario</span><span class="sxs-lookup"><span data-stu-id="d5be8-283">To export the GlobalBank East model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="d5be8-284">En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankEastItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-284">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-285">El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.</span><span class="sxs-lookup"><span data-stu-id="d5be8-285">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="d5be8-286">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5be8-286">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="d5be8-287">Pasos</span><span class="sxs-lookup"><span data-stu-id="d5be8-287">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="d5be8-288">Para crear y configurar un ESB rampa</span><span class="sxs-lookup"><span data-stu-id="d5be8-288">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="d5be8-289">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-289">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d5be8-290">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-290">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="d5be8-291">Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-291">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="d5be8-292">En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-292">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d5be8-293">En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba **OnRamp.Itinerary.HowTo**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-293">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="d5be8-294">En el **tipo** la lista desplegable, haga clic en **archivo** y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-294">In the **Type** drop-down list, click **FILE,** and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="d5be8-295">En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba **C:\HowTos\DropFolder**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-295">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="d5be8-296">Para configurar el componente de canalización de Selector de itinerario</span><span class="sxs-lookup"><span data-stu-id="d5be8-296">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="d5be8-297">En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **ItinerarySelectReceiveXml** en el **canalización de recepción** lista desplegable lista y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="d5be8-297">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveXml** in the **Receive pipeline** drop-down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="d5be8-298">Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **Selector de itinerario** propiedades de componente:</span><span class="sxs-lookup"><span data-stu-id="d5be8-298">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="d5be8-299">Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-299">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="d5be8-300">Haga clic en el **ResolverConnectionString** propiedad y, a continuación, escriba **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span><span class="sxs-lookup"><span data-stu-id="d5be8-300">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="d5be8-301">Haga clic en **Aceptar** para cerrar el **configurar canalización** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-301">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d5be8-302">Dado que esta recepción ubicación es desensamblar un intercambio XML, se requiere ninguna configuración de componente de desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="d5be8-302">Because this receive location is disassembling an XML interchange, no XML Disassembler component configuration is required.</span></span>  
  
3.  <span data-ttu-id="d5be8-303">Haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d5be8-303">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="d5be8-304">En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-304">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="d5be8-305">Para probar el Selector de itinerario y reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="d5be8-305">To test the Itinerary Selector and business rules</span></span>  
  
1.  <span data-ttu-id="d5be8-306">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="d5be8-306">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="d5be8-307">Copia (no se mueven) Batch.xml a la carpeta CarpetaDestino.</span><span class="sxs-lookup"><span data-stu-id="d5be8-307">Copy (do not move) Batch.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="d5be8-308">Vaya a C:\HowTos\Out. Compruebe que un mensaje de West%MessageID%.xml y dos mensajes East%MessageID%.xml se han escrito en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d5be8-308">Browse to C:\HowTos\Out. Verify that one West%MessageID%.xml message and two East%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5be8-309">Aunque los mensajes son idénticos, salvo por el valor del elemento customer, que fueron procesados mediante diferentes itinerarios, basados en la resolución del componente de canalización de Selector de itinerario.</span><span class="sxs-lookup"><span data-stu-id="d5be8-309">Although the messages are identical except for the value of the customer element, they were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="d5be8-310">En la consola de administración de BizTalk Server, haga la OnRamp.Itinerary.HowTo ubicación de recepción y, a continuación, haga clic en deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="d5be8-310">In the BizTalk Server Administration Console, right-click the OnRamp.Itinerary.HowTo receive location, and then click Disable.</span></span>  
  
5.  <span data-ttu-id="d5be8-311">Después de la **OnRamp.Itinerary.HowTo** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-311">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="d5be8-312">En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d5be8-312">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="d5be8-313">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d5be8-313">Additional Resources</span></span>  
 <span data-ttu-id="d5be8-314">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="d5be8-314">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="d5be8-315">Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="d5be8-315">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="d5be8-316">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="d5be8-316">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="d5be8-317">Instalación y ejecución del ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="d5be8-317">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="d5be8-318">Uso de resolución y enrutamiento dinámicos</span><span class="sxs-lookup"><span data-stu-id="d5be8-318">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="d5be8-319">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="d5be8-319">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)