---
title: 'Cómo: publicar un servicio en la especificación UDDI 3.0 registro | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c3bd0ed-e5f1-43eb-98d1-e3247a565ba2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5ab38da9c78831b319d8c64e789b442fb6eef5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008021"
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a><span data-ttu-id="9b074-102">Cómo: publicar un servicio en la especificación UDDI 3.0 registro</span><span class="sxs-lookup"><span data-stu-id="9b074-102">How to: Publish a Service to the UDDI 3.0 Registry</span></span>
## <a name="goal"></a><span data-ttu-id="9b074-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="9b074-103">Goal</span></span>  
 <span data-ttu-id="9b074-104">Esta sección muestra cómo usar el sitio de servicios UDDI para publicar un punto de conexión de servicio Web que se pueda resolver desde dentro de un itinerario para el enrutamiento de un mensaje de ESB.</span><span class="sxs-lookup"><span data-stu-id="9b074-104">This section demonstrates how to use the UDDI Service site to publish a Web service endpoint that can be resolved from within an itinerary for the purpose of routing an ESB message.</span></span> <span data-ttu-id="9b074-105">Duplicará el servicio PurchaseOrderSubmitOrderService existente publicado actualmente en el registro.</span><span class="sxs-lookup"><span data-stu-id="9b074-105">You will duplicate the existing PurchaseOrderSubmitOrderService service presently published to the registry.</span></span>  

 <span data-ttu-id="9b074-106">En este tema de procedimientos, se completará los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b074-106">In this How-to topic, you will complete the following steps:</span></span>  

-   <span data-ttu-id="9b074-107">Publicar un servicio en la Universal Description, Discovery and Integration (UDDI) 3 registro mediante la herramienta de editor UDDI.</span><span class="sxs-lookup"><span data-stu-id="9b074-107">Publish a service to the Universal Description, Discovery, and Integration (UDDI) 3 registry using the UDDI Publisher tool.</span></span>  

-   <span data-ttu-id="9b074-108">Probar la publicación de servicio mediante una lista de distribución de itinerarios que resuelve el punto de conexión de servicio con una resolución de UDDI3.</span><span class="sxs-lookup"><span data-stu-id="9b074-108">Test the service publication using an itinerary routing slip that resolves the service endpoint using a UDDI3 resolver.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9b074-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9b074-109">Prerequisites</span></span>  
 <span data-ttu-id="9b074-110">Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) y la ejecución de la herramienta de editor UDDI (puede instalarlo en % ESB instalar Folder%\Bin\ Microsoft.Practices.ESB.UDDIPublisher.exe).</span><span class="sxs-lookup"><span data-stu-id="9b074-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) and the execution of the UDDI Publisher tool (you can install it at %ESB Install Folder%\Bin\Microsoft.Practices.ESB.UDDIPublisher.exe).</span></span>  

## <a name="steps"></a><span data-ttu-id="9b074-111">Pasos</span><span class="sxs-lookup"><span data-stu-id="9b074-111">Steps</span></span>  

#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a><span data-ttu-id="9b074-112">Para crear el NewPOService en el registro UDDI</span><span class="sxs-lookup"><span data-stu-id="9b074-112">To create the NewPOService in the UDDI registry</span></span>  

1.  <span data-ttu-id="9b074-113">En Internet Explorer, vaya al sitio de servicios UDDI (de forma predeterminada, la dirección URL para esto es http://localhost/uddi).</span><span class="sxs-lookup"><span data-stu-id="9b074-113">In Internet Explorer, browse to the UDDI Service site (by default, the URL for this is http://localhost/uddi).</span></span>  

2.  <span data-ttu-id="9b074-114">En el **servicios uddi** página, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-114">On the **uddi Services** page, click **Publish**.</span></span>  

3.  <span data-ttu-id="9b074-115">En el panel publicar, haga clic en **Microsoft.Practices.ESB**y, a continuación, haga clic en **Agregar servicio**.</span><span class="sxs-lookup"><span data-stu-id="9b074-115">In the Publish pane, right-click **Microsoft.Practices.ESB**, and then click **Add Service**.</span></span>  

4.  <span data-ttu-id="9b074-116">En la página siguiente, seleccione **especificar una clave para usar**y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-116">On the following page, select **Specify a key to use**, and then click **Continue**.</span></span>  

5.  <span data-ttu-id="9b074-117">En la siguiente página, haga clic en el **esb** clave de partición.</span><span class="sxs-lookup"><span data-stu-id="9b074-117">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="9b074-118">En el **clave sufijo** , escriba **newposervice**y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-118">In the **Key Suffix** box, type **newposervice**, and then click **Continue**.</span></span>  

6.  <span data-ttu-id="9b074-119">En la página siguiente, junto a (**nuevo nombre de servicio**), haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-119">On the following page, next to (**New Service Name**), click **Edit**.</span></span> <span data-ttu-id="9b074-120">Nombre del servicio **NewPOService**y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="9b074-120">Name the service **NewPOService**, and then click **Update**.</span></span>  

7.  <span data-ttu-id="9b074-121">Haga clic en **Agregar descripción**, escriba una descripción para el servicio (por ejemplo, **servicio de ejemplo**) y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="9b074-121">Click **Add Description**, type a description for the service (for example, **Sample Service**), and then click **Update**.</span></span>  

#### <a name="to-add-a-binding-for-the-newposervice"></a><span data-ttu-id="9b074-122">Para agregar un enlace para el NewPOService</span><span class="sxs-lookup"><span data-stu-id="9b074-122">To add a binding for the NewPOService</span></span>  

1.  <span data-ttu-id="9b074-123">Haga clic en el **enlaces** pestaña y, a continuación, haga clic en **Agregar enlace**.</span><span class="sxs-lookup"><span data-stu-id="9b074-123">Click the **Bindings** tab, and then click **Add Binding**.</span></span>  

2.  <span data-ttu-id="9b074-124">Seleccione **especificar una clave para usar**y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-124">Select **Specify a key to use**, and then click **Continue**.</span></span>  

3.  <span data-ttu-id="9b074-125">En la siguiente página, haga clic en el **esb** clave de partición.</span><span class="sxs-lookup"><span data-stu-id="9b074-125">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="9b074-126">En el **clave sufijo** , escriba **newposervicebinding**y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-126">In the **Key Suffix** box, type **newposervicebinding**, and then click **Continue**.</span></span>  

4.  <span data-ttu-id="9b074-127">En **punto de acceso**, haga clic en **editar**y, a continuación, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b074-127">Under **Access Point**, click **Edit**, and then complete the following:</span></span>  

    1.  <span data-ttu-id="9b074-128">En el **punto de acceso** , escriba **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span><span class="sxs-lookup"><span data-stu-id="9b074-128">In the **Access Point** box, type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  

    2.  <span data-ttu-id="9b074-129">En el **Use Type** la lista desplegable, haga clic en **extremo**y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="9b074-129">In the **Use Type** drop-down list, click **endpoint**, and then click **Update**.</span></span>  

#### <a name="to-configure-the-binding-instance-information"></a><span data-ttu-id="9b074-130">Para configurar la información de la instancia de enlace</span><span class="sxs-lookup"><span data-stu-id="9b074-130">To configure the binding instance information</span></span>  

1. <span data-ttu-id="9b074-131">Haga clic en el **información de instancia** pestaña y, a continuación, haga clic en **agregar información de instancia**.</span><span class="sxs-lookup"><span data-stu-id="9b074-131">Click the **Instance Info** tab, and then click **Add Instance Info**.</span></span>  

2. <span data-ttu-id="9b074-132">En el **buscar nombres de estructuras tModel que contiene** , escriba **esb %** y, a continuación, haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="9b074-132">In the **Search for tModel names containing** box, type **%esb%** and then click **Search**.</span></span>  

3. <span data-ttu-id="9b074-133">Busque y haga clic en el **tModel** para **transporttype**.</span><span class="sxs-lookup"><span data-stu-id="9b074-133">Locate and click the **tModel** for **transporttype**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9b074-134">Para completar los pasos restantes de este procedimiento, es pueden que deba cambiar entre páginas 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="9b074-134">To complete the remaining steps in this procedure, you may be required to change between page 1 and page 2.</span></span>  

4. <span data-ttu-id="9b074-135">En el **descripciones** sección, haga clic en **Agregar descripción**.</span><span class="sxs-lookup"><span data-stu-id="9b074-135">In the **Descriptions** section, click **Add Description**.</span></span>  

5. <span data-ttu-id="9b074-136">En el **descripción** , escriba **tipo de transporte para el uso de itinerarios de ESB**y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="9b074-136">In the **Description** box, type **Transport Type for ESB Itinerary Use**, and then click **Update**.</span></span>  

6. <span data-ttu-id="9b074-137">Haga clic en el **detalles de la instancia** pestaña y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-137">Click the **Instance Details** tab, and then click **Edit**.</span></span>  

7. <span data-ttu-id="9b074-138">En el **parámetros de instancia** , escriba **WCF-BasicHttp**y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="9b074-138">In the **Instance Parameters** box, type **WCF-BasicHttp**, and then click **Update**.</span></span>  

8. <span data-ttu-id="9b074-139">En el **descripciones** sección, haga clic en **Agregar descripción**.</span><span class="sxs-lookup"><span data-stu-id="9b074-139">In the **Descriptions** section, click **Add Description**.</span></span>  

9. <span data-ttu-id="9b074-140">En el **descripción** , escriba **transporte HTTP básica de WCF**y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="9b074-140">In the **Description** box, type **WCF Basic HTTP Transport**, and then click **Update**.</span></span>  

10. <span data-ttu-id="9b074-141">En el panel publicar, bajo **NewPOService**, haga clic en **http://localhost/esb.canadianservices/submitposervice.asmx**.</span><span class="sxs-lookup"><span data-stu-id="9b074-141">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  

11. <span data-ttu-id="9b074-142">En el **información de instancia** , haga clic **agregar información de instancia**.</span><span class="sxs-lookup"><span data-stu-id="9b074-142">On the **Instance Info** tab, click **Add Instance Info**.</span></span>  

12. <span data-ttu-id="9b074-143">Mediante los pasos descritos anteriormente, agregue la siguiente información de instancia, según los valores mostrados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9b074-143">Using the steps described earlier, add the following instance information, according to the values shown in the following table.</span></span>  


    |                           <span data-ttu-id="9b074-144">tModel</span><span class="sxs-lookup"><span data-stu-id="9b074-144">tModel</span></span>                           |       <span data-ttu-id="9b074-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b074-145">Description</span></span>        |                          <span data-ttu-id="9b074-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9b074-146">Parameter</span></span>                           |         <span data-ttu-id="9b074-147">Descripción del parámetro</span><span class="sxs-lookup"><span data-stu-id="9b074-147">Parameter description</span></span>          |
    |------------------------------------------------------------|--------------------------|--------------------------------------------------------------|----------------------------------------|
    | <span data-ttu-id="9b074-148">Microsoft-com:esb:runtimeresolution:messageexchangepattern</span><span class="sxs-lookup"><span data-stu-id="9b074-148">microsoft-com:esb:runtimeresolution:messageexchangepattern</span></span> | <span data-ttu-id="9b074-149">Patrón de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="9b074-149">Message Exchange Pattern</span></span> |                           <span data-ttu-id="9b074-150">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="9b074-150">Two-Way</span></span>                            |           <span data-ttu-id="9b074-151">Operación bidireccional</span><span class="sxs-lookup"><span data-stu-id="9b074-151">Two-way operation</span></span>            |
    |      <span data-ttu-id="9b074-152">Microsoft-com:esb:runtimeresolution:cachetimeout</span><span class="sxs-lookup"><span data-stu-id="9b074-152">microsoft-com:esb:runtimeresolution:cachetimeout</span></span>      |      <span data-ttu-id="9b074-153">Tiempo de espera de caché</span><span class="sxs-lookup"><span data-stu-id="9b074-153">Cache Timeout</span></span>       |                              <span data-ttu-id="9b074-154">-1</span><span class="sxs-lookup"><span data-stu-id="9b074-154">-1</span></span>                              |           <span data-ttu-id="9b074-155">Actualmente deshabilitado</span><span class="sxs-lookup"><span data-stu-id="9b074-155">Currently disabled</span></span>           |
    |     <span data-ttu-id="9b074-156">Microsoft-com:esb:runtimeresolution:jaxrpcresponse</span><span class="sxs-lookup"><span data-stu-id="9b074-156">microsoft-com:esb:runtimeresolution:jaxrpcresponse</span></span>     |      <span data-ttu-id="9b074-157">JaxRpcResponse</span><span class="sxs-lookup"><span data-stu-id="9b074-157">JaxRpcResponse</span></span>      |                            <span data-ttu-id="9b074-158">false</span><span class="sxs-lookup"><span data-stu-id="9b074-158">false</span></span>                             |                                        |
    |         <span data-ttu-id="9b074-159">Microsoft-com:esb:runtimeresolution:action</span><span class="sxs-lookup"><span data-stu-id="9b074-159">microsoft-com:esb:runtimeresolution:action</span></span>         |      <span data-ttu-id="9b074-160">Acción de servicio</span><span class="sxs-lookup"><span data-stu-id="9b074-160">Service Action</span></span>      |                         <span data-ttu-id="9b074-161">submitOrder</span><span class="sxs-lookup"><span data-stu-id="9b074-161">submitOrder</span></span>                          | <span data-ttu-id="9b074-162">Especifica el método de servicio para invocar</span><span class="sxs-lookup"><span data-stu-id="9b074-162">Specifies the service method to invoke</span></span> |
    |    <span data-ttu-id="9b074-163">Microsoft-com:esb:runtimeresolution:targetnamespace</span><span class="sxs-lookup"><span data-stu-id="9b074-163">microsoft-com:esb:runtimeresolution:targetnamespace</span></span>     |    <span data-ttu-id="9b074-164">Namespace de servicio</span><span class="sxs-lookup"><span data-stu-id="9b074-164">Service Namespace</span></span>     | http://globalbank.esb.dynamicresolution.com/canadianservices |            <span data-ttu-id="9b074-165">Espacio de nombres de destino</span><span class="sxs-lookup"><span data-stu-id="9b074-165">Target namespace</span></span>            |

#### <a name="to-configure-the-binding-categorization"></a><span data-ttu-id="9b074-166">Para configurar la categorización de enlace</span><span class="sxs-lookup"><span data-stu-id="9b074-166">To configure the binding categorization</span></span>  

1.  <span data-ttu-id="9b074-167">En el panel publicar, bajo **NewPOService**, haga clic en **http://localhost/esb.canadianservices/submitposervice.asmx**.</span><span class="sxs-lookup"><span data-stu-id="9b074-167">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  

2.  <span data-ttu-id="9b074-168">En el **categorías** , haga clic **Agregar categoría personalizada**.</span><span class="sxs-lookup"><span data-stu-id="9b074-168">On the **Categories** tab, click **Add Custom Category**.</span></span>  

3.  <span data-ttu-id="9b074-169">En el **búsqueda** , escriba **esb %** y, a continuación, haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="9b074-169">In the **Search** box, type **%esb%** and then click **Search**.</span></span>  

4.  <span data-ttu-id="9b074-170">Busque y haga clic en el **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel.</span><span class="sxs-lookup"><span data-stu-id="9b074-170">Locate and click the **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel.</span></span>  

5.  <span data-ttu-id="9b074-171">En el **nombre de clave** , escriba **aplicación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="9b074-171">In the **Key Name** box, type **BizTalk Application**.</span></span>  

6.  <span data-ttu-id="9b074-172">En el **clave valor** , escriba **Microsoft.Practices.ESB**y, a continuación, haga clic en **Agregar categoría**.</span><span class="sxs-lookup"><span data-stu-id="9b074-172">In the **Key Value** box, type **Microsoft.Practices.ESB**, and then click **Add Category**.</span></span>  

7.  <span data-ttu-id="9b074-173">Siguiendo los pasos descritos anteriormente, agregue las siguientes categorías personalizadas, según los valores mostrados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9b074-173">Using the steps described earlier, add the following custom categories, according to the values shown in the following table.</span></span>  

    |<span data-ttu-id="9b074-174">tModel</span><span class="sxs-lookup"><span data-stu-id="9b074-174">tModel</span></span>|<span data-ttu-id="9b074-175">Nombre de clave</span><span class="sxs-lookup"><span data-stu-id="9b074-175">Key name</span></span>|<span data-ttu-id="9b074-176">Valor de clave</span><span class="sxs-lookup"><span data-stu-id="9b074-176">Key value</span></span>|  
    |------------|--------------|---------------|  
    |<span data-ttu-id="9b074-177">Microsoft-com:esb:runtimeresolution:portname</span><span class="sxs-lookup"><span data-stu-id="9b074-177">microsoft-com:esb:runtimeresolution:portname</span></span>|<span data-ttu-id="9b074-178">Nombre de puerto</span><span class="sxs-lookup"><span data-stu-id="9b074-178">Port Name</span></span>|<span data-ttu-id="9b074-179">NewPOService</span><span class="sxs-lookup"><span data-stu-id="9b074-179">NewPOService</span></span>|  
    |<span data-ttu-id="9b074-180">Microsoft-com:esb:runtimeresolution:transporttype</span><span class="sxs-lookup"><span data-stu-id="9b074-180">microsoft-com:esb:runtimeresolution:transporttype</span></span>|<span data-ttu-id="9b074-181">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="9b074-181">Transport Type</span></span>|<span data-ttu-id="9b074-182">WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="9b074-182">WCF-BasicHttp</span></span>|  

#### <a name="to-locate-the-service-in-the-uddi-registry"></a><span data-ttu-id="9b074-183">Para localizar el servicio en el registro UDDI</span><span class="sxs-lookup"><span data-stu-id="9b074-183">To locate the service in the UDDI registry</span></span>  

1.  <span data-ttu-id="9b074-184">En Internet Explorer, en el **servicios uddi** página, haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="9b074-184">In Internet Explorer, on the **uddi Services** page, click **Search**.</span></span>  

2.  <span data-ttu-id="9b074-185">Haga clic en el **servicios** ficha.</span><span class="sxs-lookup"><span data-stu-id="9b074-185">Click the **Services** tab.</span></span>  

3.  <span data-ttu-id="9b074-186">En el **Service Name** , escriba **% PO**y, a continuación, haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="9b074-186">In the **Service Name** box, type **%PO%**, and then click **Search**.</span></span>  

4.  <span data-ttu-id="9b074-187">En el **búsqueda** panel, en el **resultados** , haga clic **NewPOService**.</span><span class="sxs-lookup"><span data-stu-id="9b074-187">In the **Search** pane, on the **Results** tab, click **NewPOService**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="9b074-188">Esto confirma que el servicio se publicó correctamente en el registro.</span><span class="sxs-lookup"><span data-stu-id="9b074-188">This confirms the service was successfully published to the registry.</span></span>  

#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a><span data-ttu-id="9b074-189">Para crear un modelo de itinerarios para probar la publicación de servicios UDDI</span><span class="sxs-lookup"><span data-stu-id="9b074-189">To create an itinerary model to test the UDDI service publication</span></span>  

1.  <span data-ttu-id="9b074-190">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="9b074-190">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  

2.  <span data-ttu-id="9b074-191">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9b074-191">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  

3.  <span data-ttu-id="9b074-192">En el **Agregar nuevo elemento** cuadro de diálogo el **nombre** , escriba **NewBindingKeySearch**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-192">In the **Add New Item** dialog box, in the **Name** box, type **NewBindingKeySearch**, and then click **Add**.</span></span>  

#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="9b074-193">Para configurar las propiedades de los itinerarios</span><span class="sxs-lookup"><span data-stu-id="9b074-193">To configure the properties of the itinerary</span></span>  

1.  <span data-ttu-id="9b074-194">En Visual Studio, haga clic en la superficie de diseño de **NewBindingKeySearch.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="9b074-194">In Visual Studio, click the design surface of **NewBindingKeySearch.itinerary**.</span></span> <span data-ttu-id="9b074-195">En el **NewBindingKeySearch** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-195">In the **NewBindingKeySearch** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-196">En el **es solicitud-respuesta** la lista desplegable, haga clic en **True**.</span><span class="sxs-lookup"><span data-stu-id="9b074-196">In the **Is Request Response** drop-down list, click **True**.</span></span>  

    2.  <span data-ttu-id="9b074-197">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="9b074-197">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  

    3.  <span data-ttu-id="9b074-198">En el **configuración extensor** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="9b074-198">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  

    4.  <span data-ttu-id="9b074-199">En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\NewBindingKeySearch** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="9b074-199">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\NewBindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  

        > [!NOTE]
        >  <span data-ttu-id="9b074-200">Este paso le permite exportar el itinerario como XML en una ubicación de archivos local.</span><span class="sxs-lookup"><span data-stu-id="9b074-200">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="9b074-201">Exportando un itinerario en una ubicación de archivos local, en lugar de a la base de datos de itinerario, permite probar el itinerario mediante la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="9b074-201">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="9b074-202">Complete este proceso más adelante en este tema de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="9b074-202">You will complete this process later in this How-to topic.</span></span>  

#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="9b074-203">Para definir la estructura de los itinerarios</span><span class="sxs-lookup"><span data-stu-id="9b074-203">To define the structure of the itinerary</span></span>  

1.  <span data-ttu-id="9b074-204">En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="9b074-204">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="9b074-205">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-205">In the **OnRamp1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-206">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="9b074-206">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  

    2.  <span data-ttu-id="9b074-207">En el **extensor** la lista desplegable, haga clic en **rampa de ESB extensor**.</span><span class="sxs-lookup"><span data-stu-id="9b074-207">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  

    3.  <span data-ttu-id="9b074-208">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="9b074-208">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  

    4.  <span data-ttu-id="9b074-209">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary.Response**.</span><span class="sxs-lookup"><span data-stu-id="9b074-209">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  

2.  <span data-ttu-id="9b074-210">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento de modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="9b074-210">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="9b074-211">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-211">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-212">Haga clic en el **nombre** propiedad y, a continuación, escriba **TransformNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="9b074-212">Click the **Name** property, and then type **TransformNAOrder**.</span></span>  

    2.  <span data-ttu-id="9b074-213">En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **mensajería extensor**.</span><span class="sxs-lookup"><span data-stu-id="9b074-213">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  

    3.  <span data-ttu-id="9b074-214">En el **contenedor** desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="9b074-214">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  

    4.  <span data-ttu-id="9b074-215">En el **Service Name** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="9b074-215">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  

3.  <span data-ttu-id="9b074-216">Haga clic en el **resolución** colección de la **TransformNAOrder** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="9b074-216">Right-click the **Resolver** collection of the **TransformNAOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9b074-217">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-217">In the **Resolver1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-218">Haga clic en el **nombre** propiedad y, a continuación, escriba **NAOrder_to_CNOrder**.</span><span class="sxs-lookup"><span data-stu-id="9b074-218">Click the **Name** property, and then type **NAOrder_to_CNOrder**.</span></span>  

    2.  <span data-ttu-id="9b074-219">En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estático**.</span><span class="sxs-lookup"><span data-stu-id="9b074-219">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  

    3.  <span data-ttu-id="9b074-220">En el **transformar tipo** la lista desplegable, haga clic en **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span><span class="sxs-lookup"><span data-stu-id="9b074-220">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  

4.  <span data-ttu-id="9b074-221">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="9b074-221">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9b074-222">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **TransformNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="9b074-222">Drag a connection from the **ReceiveNAOrder** model element to the **TransformNAOrder** model element.</span></span>  

5.  <span data-ttu-id="9b074-223">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento de modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="9b074-223">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="9b074-224">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-224">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-225">Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeyRoute**.</span><span class="sxs-lookup"><span data-stu-id="9b074-225">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  

    2.  <span data-ttu-id="9b074-226">En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **mensajería extensor**.</span><span class="sxs-lookup"><span data-stu-id="9b074-226">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  

    3.  <span data-ttu-id="9b074-227">En el **contenedor** desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="9b074-227">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  

    4.  <span data-ttu-id="9b074-228">En el **Service Name** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="9b074-228">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  

6.  <span data-ttu-id="9b074-229">Haga clic en el **resolución** colección de la **BindingKeyRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="9b074-229">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9b074-230">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-230">In the **Resolver1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-231">Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeySearch**.</span><span class="sxs-lookup"><span data-stu-id="9b074-231">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  

    2.  <span data-ttu-id="9b074-232">En el **implementación de la resolución** la lista desplegable, haga clic en **Uddi3 resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="9b074-232">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  

    3.  <span data-ttu-id="9b074-233">En el **resolución de Moniker** la lista desplegable, haga clic en **UDDI3**.</span><span class="sxs-lookup"><span data-stu-id="9b074-233">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  

    4.  <span data-ttu-id="9b074-234">Haga clic en el **clave de enlace** propiedad y, a continuación, escriba **uddi:esb:newposervicebinding**.</span><span class="sxs-lookup"><span data-stu-id="9b074-234">Click the **Binding key** property, and then type **uddi:esb:newposervicebinding**.</span></span> <span data-ttu-id="9b074-235">Para buscar el valor de clave, haga clic en el http://localhost/ESB.CanadianServices/SubmitPOService.asmx de servicios de UDDI y, a continuación, haga clic en más detalles.</span><span class="sxs-lookup"><span data-stu-id="9b074-235">To find the key value, click the http://localhost/ESB.CanadianServices/SubmitPOService.asmx service in UDDI, and then click More Details.</span></span>  

7.  <span data-ttu-id="9b074-236">Haga clic en el **BindingKeySearch** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.</span><span class="sxs-lookup"><span data-stu-id="9b074-236">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="9b074-237">Compruebe el resultado que aparece en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="9b074-237">Verify the output displayed in the Output window.</span></span>  

8.  <span data-ttu-id="9b074-238">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="9b074-238">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9b074-239">Arrastre una conexión desde el **TransformNAOrder** elemento de modelo para el **BindingKeyRoute** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="9b074-239">Drag a connection from the **TransformNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  

9. <span data-ttu-id="9b074-240">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BindingKeyRoute** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="9b074-240">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="9b074-241">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-241">In the **OffRamp1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-242">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendCNOrder**.</span><span class="sxs-lookup"><span data-stu-id="9b074-242">Click the **Name** property, and then type **SendCNOrder**.</span></span>  

    2.  <span data-ttu-id="9b074-243">En el **extensor** la lista desplegable, haga clic en **fuera de rampa ESB extensor**.</span><span class="sxs-lookup"><span data-stu-id="9b074-243">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  

    3.  <span data-ttu-id="9b074-244">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="9b074-244">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  

    4.  <span data-ttu-id="9b074-245">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionSolicitResp**.</span><span class="sxs-lookup"><span data-stu-id="9b074-245">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  

10. <span data-ttu-id="9b074-246">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BindingKeyRoute** elemento de modelo y la **SendCNOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="9b074-246">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="9b074-247">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9b074-247">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="9b074-248">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="9b074-248">Click the **Name** property, and then type **SendPortFilter**.</span></span>  

    2.  <span data-ttu-id="9b074-249">En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **fuera de rampa extensor**.</span><span class="sxs-lookup"><span data-stu-id="9b074-249">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  

    3.  <span data-ttu-id="9b074-250">En el **fuera de rampa** desplegable lista, expanda **SendCNOrder**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="9b074-250">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  

11. <span data-ttu-id="9b074-251">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="9b074-251">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9b074-252">Arrastre una conexión desde el **BindingKeyRoute** elemento de modelo para el **SendPortFilter** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="9b074-252">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  

12. <span data-ttu-id="9b074-253">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="9b074-253">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9b074-254">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="9b074-254">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  

#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="9b074-255">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="9b074-255">To export the model for use with the Itinerary Test Client</span></span>  

1.  <span data-ttu-id="9b074-256">En Visual Studio, haga clic en la superficie de diseño de la **NewBindingKeySearch** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="9b074-256">In Visual Studio, right-click the design surface of the **NewBindingKeySearch** itinerary, and then click **Export Model**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="9b074-257">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9b074-257">The XML version of the itinerary opens in Visual Studio.</span></span>  

2.  <span data-ttu-id="9b074-258">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b074-258">Save all project artifacts.</span></span>  

3.  <span data-ttu-id="9b074-259">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (NewBindingKeySearch.xml).</span><span class="sxs-lookup"><span data-stu-id="9b074-259">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (NewBindingKeySearch.xml).</span></span>  

#### <a name="to-test-the-itinerary"></a><span data-ttu-id="9b074-260">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="9b074-260">To test the itinerary</span></span>  

1.  <span data-ttu-id="9b074-261">Abra la aplicación de ejemplo de cliente de prueba de itinerario mediante el acceso directo que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="9b074-261">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  

2.  <span data-ttu-id="9b074-262">En el cliente de prueba de itinerario, en el **opciones del servicio Web** grupo, desactive la **usar el servicio de WCF** cuadro y, a continuación, seleccione el **servicio bidireccional** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="9b074-262">In the Itinerary Test Client, in the **Web Service Options** group, clear the **Use WCF Service** box and then select the **Two-Way Service** check box.</span></span>  

3.  <span data-ttu-id="9b074-263">Haga clic en el **carga itinerario** botón.</span><span class="sxs-lookup"><span data-stu-id="9b074-263">Click the **Load Itinerary** button.</span></span>  

4.  <span data-ttu-id="9b074-264">En el **abrir archivo itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="9b074-264">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="9b074-265">Seleccione **NewBindingKeySearch.xml**y, a continuación, haga clic en **abierto** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="9b074-265">Select **NewBindingKeySearch.xml**, and then click **Open** to load the itinerary.</span></span>  

5.  <span data-ttu-id="9b074-266">Haga clic en **Aceptar** para borrar el **itinerario se cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b074-266">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  

6.  <span data-ttu-id="9b074-267">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **carga mensaje** cuadro.</span><span class="sxs-lookup"><span data-stu-id="9b074-267">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  

7.  <span data-ttu-id="9b074-268">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="9b074-268">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="9b074-269">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abierto** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="9b074-269">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  

8.  <span data-ttu-id="9b074-270">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="9b074-270">Click the **Submit Request** button.</span></span> <span data-ttu-id="9b074-271">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="9b074-271">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  

9. <span data-ttu-id="9b074-272">Compruebe que aparece el mensaje de respuesta correcta en el **resultado** cuadro de texto de la **cliente de prueba Itineray**.</span><span class="sxs-lookup"><span data-stu-id="9b074-272">Verify that the correct response message appears in the **Result** text box of the **Itineray Test Client**.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="9b074-273">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9b074-273">Additional Resources</span></span>  
 <span data-ttu-id="9b074-274">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="9b074-274">For more information, see the following related topics:</span></span>  

-   [<span data-ttu-id="9b074-275">Cómo: Resolver un punto de conexión de servicio mediante una búsqueda de claves de enlace de UDDI</span><span class="sxs-lookup"><span data-stu-id="9b074-275">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  

-   [<span data-ttu-id="9b074-276">Cómo: Resolver un punto de conexión de servicio mediante una búsqueda de categorías de UDDI</span><span class="sxs-lookup"><span data-stu-id="9b074-276">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  

-   [<span data-ttu-id="9b074-277">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="9b074-277">Development Activities</span></span>](../esb-toolkit/development-activities.md)