---
title: 'Paso 1: Usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fb8737f51f9e0b6afe3d61218f69015c1cd5d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984037"
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a><span data-ttu-id="d2b5b-102">Paso 1: Usar al Asistente para desarrollo de servicio de adaptador para crear el proyecto Web</span><span class="sxs-lookup"><span data-stu-id="d2b5b-102">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>
<span data-ttu-id="d2b5b-103">![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="d2b5b-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="d2b5b-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="d2b5b-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="d2b5b-105">En este paso, creará un proyecto mediante Visual Studio y el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2b5b-105">In this step, you create a project using Visual Studio and the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="d2b5b-106">El [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] recopila información sobre el adaptador, operaciones y las configuraciones de punto de conexión y genera un proyecto Web que, a continuación, se puede implementar en IIS.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-106">The [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] collects information about the adapter, operations, and endpoint configurations, and generates a Web project that can then be deployed to IIS.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d2b5b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d2b5b-107">Prerequisites</span></span>  
 <span data-ttu-id="d2b5b-108">Debe compilar e implementar el eco de ejemplo se describe en [Tutorial 1: desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) antes de comenzar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-108">You must build and deploy the Echo sample described in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) before beginning this tutorial.</span></span>  
  
### <a name="to-start-the-adapter-service-development-wizard"></a><span data-ttu-id="d2b5b-109">Para iniciar al Asistente para desarrollo de servicio de adaptador</span><span class="sxs-lookup"><span data-stu-id="d2b5b-109">To start the Adapter Service Development Wizard</span></span>  
  
1.  <span data-ttu-id="d2b5b-110">Inicie Visual Studio y, a continuación, en el **archivo** menú, elija **New**y, a continuación, haga clic en **sitio Web**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-110">Start Visual Studio and then on the **File** menu, point to **New**, and then click **Web Site**.</span></span>  
  
2.  <span data-ttu-id="d2b5b-111">En el **nuevo sitio Web** diálogo cuadro, lleve a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d2b5b-111">In the **New Web Site** dialog box, perform the following actions:</span></span>  
  
    |<span data-ttu-id="d2b5b-112">Use</span><span class="sxs-lookup"><span data-stu-id="d2b5b-112">Use this</span></span>|<span data-ttu-id="d2b5b-113">Para</span><span class="sxs-lookup"><span data-stu-id="d2b5b-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d2b5b-114">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-114">**Language**</span></span>|<span data-ttu-id="d2b5b-115">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-115">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="d2b5b-116">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="d2b5b-116">**Templates**</span></span>|<span data-ttu-id="d2b5b-117">Haga clic en **servicio de adaptador WCF**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-117">Click **WCF Adapter Service**.</span></span>|  
    |<span data-ttu-id="d2b5b-118">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-118">**Location**</span></span>|<span data-ttu-id="d2b5b-119">Seleccione **sistema de archivos**y, a continuación, escriba **C:\Tutorials\EchoWeb** como la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-119">Select **File System**, and then type **C:\Tutorials\EchoWeb** as the path.</span></span>|  
  
3.  <span data-ttu-id="d2b5b-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-120">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="d2b5b-121">En el **página de bienvenida**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-121">On the **Welcome page**, click **Next**.</span></span>  
  
### <a name="to-select-the-adapter-and-uri"></a><span data-ttu-id="d2b5b-122">Para seleccionar el adaptador y el URI</span><span class="sxs-lookup"><span data-stu-id="d2b5b-122">To select the adapter and URI</span></span>  
  
1.  <span data-ttu-id="d2b5b-123">En el **elegir las operaciones para generar un contrato de servicio** página, seleccione **echoAdapterBindingV2** desde el **selecciona un enlace** desplegable lista y, a continuación, haga clic en  **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-123">On the **Choose the operations to generate a service contract** page, select **echoAdapterBindingV2** from the **Select a binding** drop-down list, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="d2b5b-124">En el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo, establezca **tipo de credencial de cliente** a **nombre de usuario**y, a continuación, establezca el  **Las credenciales de nombre de usuario** como sigue:</span><span class="sxs-lookup"><span data-stu-id="d2b5b-124">On the **Security** tab of the **Configure Adapter** dialog box, set **Client Credential type** to **Username**, and then set the **User name credentials** as follows:</span></span>  
  
    |<span data-ttu-id="d2b5b-125">Property</span><span class="sxs-lookup"><span data-stu-id="d2b5b-125">Property</span></span>|<span data-ttu-id="d2b5b-126">Valor</span><span class="sxs-lookup"><span data-stu-id="d2b5b-126">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d2b5b-127">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-127">**User name**</span></span>|<span data-ttu-id="d2b5b-128">username</span><span class="sxs-lookup"><span data-stu-id="d2b5b-128">username</span></span>|  
    |<span data-ttu-id="d2b5b-129">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-129">**Password**</span></span>|<span data-ttu-id="d2b5b-130">password</span><span class="sxs-lookup"><span data-stu-id="d2b5b-130">password</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d2b5b-131">El nombre de usuario y contraseña que especifique aquí solo se usan para conectarse al adaptador mientras realiza los pasos del asistente y no se conservan cuando se complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-131">The user name and password entered here are only used to connect to the adapter while performing the steps in the wizard, and are not preserved after the wizard completes.</span></span>  
  
3.  <span data-ttu-id="d2b5b-132">Haga clic en el **propiedades de URI** pestaña y, a continuación, establezca las propiedades como sigue:</span><span class="sxs-lookup"><span data-stu-id="d2b5b-132">Click the **URI Properties** tab, and then set the properties as follows:</span></span>  
  
    |<span data-ttu-id="d2b5b-133">Property</span><span class="sxs-lookup"><span data-stu-id="d2b5b-133">Property</span></span>|<span data-ttu-id="d2b5b-134">Valor</span><span class="sxs-lookup"><span data-stu-id="d2b5b-134">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d2b5b-135">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-135">**Application**</span></span>|<span data-ttu-id="d2b5b-136">LobApplication</span><span class="sxs-lookup"><span data-stu-id="d2b5b-136">LobApplication</span></span>|  
    |<span data-ttu-id="d2b5b-137">**EnableAuthentication**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-137">**EnableAuthentication**</span></span>|<span data-ttu-id="d2b5b-138">True</span><span class="sxs-lookup"><span data-stu-id="d2b5b-138">True</span></span>|  
    |<span data-ttu-id="d2b5b-139">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-139">**Hostname**</span></span>|<span data-ttu-id="d2b5b-140">lobhostname</span><span class="sxs-lookup"><span data-stu-id="d2b5b-140">lobhostname</span></span>|  
    |<span data-ttu-id="d2b5b-141">**EchoInUpperCase**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-141">**EchoInUpperCase**</span></span>|<span data-ttu-id="d2b5b-142">False</span><span class="sxs-lookup"><span data-stu-id="d2b5b-142">False</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d2b5b-143">Las propiedades URI seleccionadas aquí se usará para crear el \< **cliente**\>\<**extremo** \> elementos en el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-143">The URI properties selected here will be used to create the \<**client**\>\<**endpoint**\> elements in the web.config file.</span></span>  
  
4.  <span data-ttu-id="d2b5b-144">Haga clic en el **las propiedades de enlace** ficha. Tenga en cuenta los valores predeterminados y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-144">Click the **Binding Properties** tab. Note the default values, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2b5b-145">Los valores de enlace que se usará para generar el \< **enlaces**\>\<**echoAdapterBindingV2** \> elementos en el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-145">The binding values will be used to generate the \<**bindings**\>\<**echoAdapterBindingV2**\> elements in the web.config file.</span></span>  
  
### <a name="to-select-the-contract-and-operations"></a><span data-ttu-id="d2b5b-146">Para seleccionar el contrato y operaciones</span><span class="sxs-lookup"><span data-stu-id="d2b5b-146">To select the contract and operations</span></span>  
  
1.  <span data-ttu-id="d2b5b-147">En el **elegir las operaciones para generar un contrato de servicio** página, haga clic en **Connect**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-147">On the **Choose the operations to generate a service contract** page, click **Connect**.</span></span>  
  
2.  <span data-ttu-id="d2b5b-148">En el **seleccionar una categoría** de árbol, seleccione **categoría principal**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-148">In the **Select a category** tree, select **Main Category**.</span></span> <span data-ttu-id="d2b5b-149">Esto rellena el **operaciones y categorías disponibles** lista.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-149">This populates the **Available categories and operations** list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2b5b-150">También puede escribir un término de búsqueda en el **búsqueda en la categoría** campo para buscar cualquier operación que contienen el término de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-150">You can also enter a search term in the **Search in category** field to find any operations that contain the search term.</span></span>  
  
3.  <span data-ttu-id="d2b5b-151">En el **operaciones y categorías disponibles** lista, seleccione **EchoGreetings** y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-151">In the **Available categories and operations** list, select **EchoGreetings** and click **Add**.</span></span> <span data-ttu-id="d2b5b-152">Esto mueve a la operación EchoGreetings el **agregar categorías y operaciones** lista.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-152">This moves the EchoGreetings operation to the **Added categories and operations** list.</span></span> <span data-ttu-id="d2b5b-153">Las operaciones seleccionadas aquí se verá expuestas a las aplicaciones cliente a través del código de proxy de cliente generado por el asistente.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-153">The operations selected here will be exposed to client applications through the client proxy code generated by the wizard.</span></span>  
  
     <span data-ttu-id="d2b5b-154">![Seleccionar contrato y operaciones](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span><span class="sxs-lookup"><span data-stu-id="d2b5b-154">![Select Contract and Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span></span>  
  
4.  <span data-ttu-id="d2b5b-155">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-155">Click **Next**.</span></span>  
  
### <a name="to-configure-service-and-endpoint-behavior"></a><span data-ttu-id="d2b5b-156">Para configurar el comportamiento de servicio y extremo</span><span class="sxs-lookup"><span data-stu-id="d2b5b-156">To configure service and endpoint behavior</span></span>  
  
1.  <span data-ttu-id="d2b5b-157">En el **configurar comportamientos del servicio y extremo** , escriba los siguientes valores para **configuración del comportamiento de servicio**:</span><span class="sxs-lookup"><span data-stu-id="d2b5b-157">On the **Configure service and endpoint behaviors** page, enter the following values for **Service Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="d2b5b-158">Property</span><span class="sxs-lookup"><span data-stu-id="d2b5b-158">Property</span></span>|<span data-ttu-id="d2b5b-159">Valor</span><span class="sxs-lookup"><span data-stu-id="d2b5b-159">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d2b5b-160">**EnableMetadataExchange**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-160">**EnableMetadataExchange**</span></span>|<span data-ttu-id="d2b5b-161">True</span><span class="sxs-lookup"><span data-stu-id="d2b5b-161">True</span></span>|  
    |<span data-ttu-id="d2b5b-162">**IncludeExceptionDetailsinFault**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-162">**IncludeExceptionDetailsinFault**</span></span>|<span data-ttu-id="d2b5b-163">True</span><span class="sxs-lookup"><span data-stu-id="d2b5b-163">True</span></span>|  
    |<span data-ttu-id="d2b5b-164">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-164">**Name**</span></span>|<span data-ttu-id="d2b5b-165">customServiceBehavior</span><span class="sxs-lookup"><span data-stu-id="d2b5b-165">customServiceBehavior</span></span>|  
    |<span data-ttu-id="d2b5b-166">**UseServiceCertificate**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-166">**UseServiceCertificate**</span></span>|<span data-ttu-id="d2b5b-167">False</span><span class="sxs-lookup"><span data-stu-id="d2b5b-167">False</span></span>|  
  
     <span data-ttu-id="d2b5b-168">Estos valores se usan para rellenar el \< **serviceBehaviors**\>.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-168">These values are used to populate the \<**serviceBehaviors**\>.</span></span>  
  
2.  <span data-ttu-id="d2b5b-169">Escriba los siguientes valores para **configuración del comportamiento de punto de conexión**:</span><span class="sxs-lookup"><span data-stu-id="d2b5b-169">Enter the following values for **Endpoint Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="d2b5b-170">Property</span><span class="sxs-lookup"><span data-stu-id="d2b5b-170">Property</span></span>|<span data-ttu-id="d2b5b-171">Valor</span><span class="sxs-lookup"><span data-stu-id="d2b5b-171">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d2b5b-172">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-172">**Name**</span></span>|<span data-ttu-id="d2b5b-173">customEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="d2b5b-173">customEndpointBehavior</span></span>|  
    |<span data-ttu-id="d2b5b-174">**AuthenticationType**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-174">**AuthenticationType**</span></span>|<span data-ttu-id="d2b5b-175">**HTTPUsernamePassword**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-175">**HTTPUsernamePassword**</span></span>|  
    |<span data-ttu-id="d2b5b-176">**UsernameHeader**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-176">**UsernameHeader**</span></span>|<span data-ttu-id="d2b5b-177">MyUserHeader</span><span class="sxs-lookup"><span data-stu-id="d2b5b-177">MyUserHeader</span></span>|  
    |<span data-ttu-id="d2b5b-178">**PasswordHeader**</span><span class="sxs-lookup"><span data-stu-id="d2b5b-178">**PasswordHeader**</span></span>|<span data-ttu-id="d2b5b-179">MyPassHeader</span><span class="sxs-lookup"><span data-stu-id="d2b5b-179">MyPassHeader</span></span>|  
  
     <span data-ttu-id="d2b5b-180">Estos valores se usarán para especificar el **adapterSecurityBridgeType** en el <**endpointBehaviors** elemento web.confg.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-180">These values will be used to specify the **adapterSecurityBridgeType** in the <**endpointBehaviors** element in web.confg.</span></span>  
  
     <span data-ttu-id="d2b5b-181">![Configuración de extremo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span><span class="sxs-lookup"><span data-stu-id="d2b5b-181">![Endpoint Configuration](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span></span>  
  
3.  <span data-ttu-id="d2b5b-182">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-182">Click **Next**</span></span>  
  
### <a name="to-configure-the-binding"></a><span data-ttu-id="d2b5b-183">Para configurar el enlace</span><span class="sxs-lookup"><span data-stu-id="d2b5b-183">To configure the binding</span></span>  
  
1. <span data-ttu-id="d2b5b-184">En el **configurar el enlace del punto de conexión de servicio y la dirección** página, seleccione el **BindingConfiguration** entrada en **configurar el enlace para el contrato y dirección**, y a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-184">On the **Configure the service endpoint binding and address** page, select the **BindingConfiguration** entry in **Configure the address and binding for the contract**, and then click the ellipsis (**…**) button.</span></span>  
  
2. <span data-ttu-id="d2b5b-185">En el **Personalizar enlace** cuadro de diálogo, establezca **modo** a **TransportWithMessageCredential**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-185">In the **Customize Binding** dialog box, set **Mode** to **TransportWithMessageCredential**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="d2b5b-186">Haga clic en **aplicar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-186">Click **Apply**, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="d2b5b-187">En el **resumen** , revise los contratos y operaciones seleccionadas para este proyecto y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-187">On the **Summary** page, review the contracts and operations selected for this project, and then click **Finish**.</span></span> <span data-ttu-id="d2b5b-188">Se mostrará con la solución EchoWeb, que contiene los archivos de proyecto creados por el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b5b-188">You will be presented with the EchoWeb solution, which contains the project files created by the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d2b5b-189">Síntesis</span><span class="sxs-lookup"><span data-stu-id="d2b5b-189">What did I just do?</span></span>  
 <span data-ttu-id="d2b5b-190">En este paso, ha utilizado el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] para generar un sitio Web del proyecto que, cuando se publica en IIS, va a hospedar el adaptador de Echo desarrollado en [Tutorial 1: desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) en IIS el proceso.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-190">In this step, you used the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] to generate a Web project that, when published to IIS, will host the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) in the IIS process.</span></span> <span data-ttu-id="d2b5b-191">El proyecto resultante de la Web permite a los clientes WCF y servicios Web tener acceso a las operaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="d2b5b-191">The resulting Web project allows Web Services and WCF clients to access the selected operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d2b5b-192">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d2b5b-192">Next Steps</span></span>  
 <span data-ttu-id="d2b5b-193">Para compilar e implementar el proyecto Web, continúe con [paso 2: implementar el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span><span class="sxs-lookup"><span data-stu-id="d2b5b-193">To build and deploy the Web project, proceed to [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b5b-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2b5b-194">See Also</span></span>  
 [<span data-ttu-id="d2b5b-195">Tutorial 1: Desarrollar el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="d2b5b-195">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)