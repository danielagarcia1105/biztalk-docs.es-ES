---
title: 'Paso 1: Utilizar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a63953b0928915a8fea5b357722cd4e34f1b900c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a><span data-ttu-id="870ac-102">Paso 1: Utilizar al Asistente para desarrollo de servicio de adaptador para crear el proyecto Web</span><span class="sxs-lookup"><span data-stu-id="870ac-102">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>
<span data-ttu-id="870ac-103">![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="870ac-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="870ac-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="870ac-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="870ac-105">En este paso, creará un proyecto con Visual Studio y la [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="870ac-105">In this step, you create a project using Visual Studio and the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="870ac-106">El [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] recopila información sobre el adaptador, las operaciones y las configuraciones de punto de conexión y genera un proyecto Web que, a continuación, se puede implementar en IIS.</span><span class="sxs-lookup"><span data-stu-id="870ac-106">The [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] collects information about the adapter, operations, and endpoint configurations, and generates a Web project that can then be deployed to IIS.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="870ac-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="870ac-107">Prerequisites</span></span>  
 <span data-ttu-id="870ac-108">Debe compilar e implementar el ejemplo de eco que se describe en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) antes de comenzar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="870ac-108">You must build and deploy the Echo sample described in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) before beginning this tutorial.</span></span>  
  
### <a name="to-start-the-adapter-service-development-wizard"></a><span data-ttu-id="870ac-109">Para iniciar al Asistente de desarrollo del servicio de adaptador</span><span class="sxs-lookup"><span data-stu-id="870ac-109">To start the Adapter Service Development Wizard</span></span>  
  
1.  <span data-ttu-id="870ac-110">Inicie Visual Studio y, a continuación, en la **archivo** menú, elija **New**y, a continuación, haga clic en **sitio Web**.</span><span class="sxs-lookup"><span data-stu-id="870ac-110">Start Visual Studio and then on the **File** menu, point to **New**, and then click **Web Site**.</span></span>  
  
2.  <span data-ttu-id="870ac-111">En el **nuevo sitio Web** diálogo cuadro, lleve a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="870ac-111">In the **New Web Site** dialog box, perform the following actions:</span></span>  
  
    |<span data-ttu-id="870ac-112">Use</span><span class="sxs-lookup"><span data-stu-id="870ac-112">Use this</span></span>|<span data-ttu-id="870ac-113">Para</span><span class="sxs-lookup"><span data-stu-id="870ac-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="870ac-114">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="870ac-114">**Language**</span></span>|<span data-ttu-id="870ac-115">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="870ac-115">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="870ac-116">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="870ac-116">**Templates**</span></span>|<span data-ttu-id="870ac-117">Haga clic en **servicio de adaptador WCF**.</span><span class="sxs-lookup"><span data-stu-id="870ac-117">Click **WCF Adapter Service**.</span></span>|  
    |<span data-ttu-id="870ac-118">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="870ac-118">**Location**</span></span>|<span data-ttu-id="870ac-119">Seleccione **sistema de archivos**y, a continuación, escriba **C:\Tutorials\EchoWeb** como la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="870ac-119">Select **File System**, and then type **C:\Tutorials\EchoWeb** as the path.</span></span>|  
  
3.  <span data-ttu-id="870ac-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="870ac-120">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="870ac-121">En el **página de bienvenida**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="870ac-121">On the **Welcome page**, click **Next**.</span></span>  
  
### <a name="to-select-the-adapter-and-uri"></a><span data-ttu-id="870ac-122">Para seleccionar el adaptador y el URI</span><span class="sxs-lookup"><span data-stu-id="870ac-122">To select the adapter and URI</span></span>  
  
1.  <span data-ttu-id="870ac-123">En el **elegir las operaciones para generar un contrato de servicio** página, seleccione **echoAdapterBindingV2** desde el **selecciona un enlace** lista desplegable lista y, a continuación, haga clic en  **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="870ac-123">On the **Choose the operations to generate a service contract** page, select **echoAdapterBindingV2** from the **Select a binding** drop-down list, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="870ac-124">En el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo, establezca **tipo de credencial de cliente** a **nombre de usuario**y, a continuación, establezca el  **Las credenciales de nombre de usuario** como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="870ac-124">On the **Security** tab of the **Configure Adapter** dialog box, set **Client Credential type** to **Username**, and then set the **User name credentials** as follows:</span></span>  
  
    |<span data-ttu-id="870ac-125">Propiedad</span><span class="sxs-lookup"><span data-stu-id="870ac-125">Property</span></span>|<span data-ttu-id="870ac-126">Valor</span><span class="sxs-lookup"><span data-stu-id="870ac-126">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="870ac-127">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="870ac-127">**User name**</span></span>|<span data-ttu-id="870ac-128">username</span><span class="sxs-lookup"><span data-stu-id="870ac-128">username</span></span>|  
    |<span data-ttu-id="870ac-129">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="870ac-129">**Password**</span></span>|<span data-ttu-id="870ac-130">password</span><span class="sxs-lookup"><span data-stu-id="870ac-130">password</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="870ac-131">El nombre de usuario y una contraseña escritos aquí sólo se utilizan para conectar con el adaptador al realizar los pasos del asistente y no se conservan cuando se complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="870ac-131">The user name and password entered here are only used to connect to the adapter while performing the steps in the wizard, and are not preserved after the wizard completes.</span></span>  
  
3.  <span data-ttu-id="870ac-132">Haga clic en el **propiedades de URI** ficha y, a continuación, establezca las propiedades como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="870ac-132">Click the **URI Properties** tab, and then set the properties as follows:</span></span>  
  
    |<span data-ttu-id="870ac-133">Propiedad</span><span class="sxs-lookup"><span data-stu-id="870ac-133">Property</span></span>|<span data-ttu-id="870ac-134">Valor</span><span class="sxs-lookup"><span data-stu-id="870ac-134">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="870ac-135">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="870ac-135">**Application**</span></span>|<span data-ttu-id="870ac-136">LobApplication</span><span class="sxs-lookup"><span data-stu-id="870ac-136">LobApplication</span></span>|  
    |<span data-ttu-id="870ac-137">**EnableAuthentication**</span><span class="sxs-lookup"><span data-stu-id="870ac-137">**EnableAuthentication**</span></span>|<span data-ttu-id="870ac-138">True</span><span class="sxs-lookup"><span data-stu-id="870ac-138">True</span></span>|  
    |<span data-ttu-id="870ac-139">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="870ac-139">**Hostname**</span></span>|<span data-ttu-id="870ac-140">lobhostname</span><span class="sxs-lookup"><span data-stu-id="870ac-140">lobhostname</span></span>|  
    |<span data-ttu-id="870ac-141">**EchoInUpperCase**</span><span class="sxs-lookup"><span data-stu-id="870ac-141">**EchoInUpperCase**</span></span>|<span data-ttu-id="870ac-142">False</span><span class="sxs-lookup"><span data-stu-id="870ac-142">False</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="870ac-143">Las propiedades URI que seleccione aquí se usará para crear el \< **cliente**>\<**extremo**> elementos en el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="870ac-143">The URI properties selected here will be used to create the \<**client**>\<**endpoint**> elements in the web.config file.</span></span>  
  
4.  <span data-ttu-id="870ac-144">Haga clic en el **propiedades de enlace** ficha. Tenga en cuenta los valores predeterminados y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="870ac-144">Click the **Binding Properties** tab. Note the default values, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="870ac-145">Los valores de enlace que se usará para generar el \< **enlaces**>\<**echoAdapterBindingV2**> elementos en el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="870ac-145">The binding values will be used to generate the \<**bindings**>\<**echoAdapterBindingV2**> elements in the web.config file.</span></span>  
  
### <a name="to-select-the-contract-and-operations"></a><span data-ttu-id="870ac-146">Para seleccionar el contrato y operaciones</span><span class="sxs-lookup"><span data-stu-id="870ac-146">To select the contract and operations</span></span>  
  
1.  <span data-ttu-id="870ac-147">En el **elegir las operaciones para generar un contrato de servicio** página, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="870ac-147">On the **Choose the operations to generate a service contract** page, click **Connect**.</span></span>  
  
2.  <span data-ttu-id="870ac-148">En el **seleccione una categoría de** de árbol, seleccione **categoría principal**.</span><span class="sxs-lookup"><span data-stu-id="870ac-148">In the **Select a category** tree, select **Main Category**.</span></span> <span data-ttu-id="870ac-149">Este modo se rellenará el **categorías y operaciones disponibles** lista.</span><span class="sxs-lookup"><span data-stu-id="870ac-149">This populates the **Available categories and operations** list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="870ac-150">También puede escribir un término de búsqueda en el **búsqueda en la categoría** campo para buscar cualquier operación que contienen el término de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="870ac-150">You can also enter a search term in the **Search in category** field to find any operations that contain the search term.</span></span>  
  
3.  <span data-ttu-id="870ac-151">En el **categorías y operaciones disponibles** lista, seleccione **EchoGreetings** y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="870ac-151">In the **Available categories and operations** list, select **EchoGreetings** and click **Add**.</span></span> <span data-ttu-id="870ac-152">Este paso traslada a la operación de EchoGreetings el **agregar categorías y operaciones** lista.</span><span class="sxs-lookup"><span data-stu-id="870ac-152">This moves the EchoGreetings operation to the **Added categories and operations** list.</span></span> <span data-ttu-id="870ac-153">Las operaciones que seleccione aquí se expondrán a las aplicaciones cliente a través del código de proxy de cliente generado por el asistente.</span><span class="sxs-lookup"><span data-stu-id="870ac-153">The operations selected here will be exposed to client applications through the client proxy code generated by the wizard.</span></span>  
  
     <span data-ttu-id="870ac-154">![Seleccionar contrato y operaciones](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span><span class="sxs-lookup"><span data-stu-id="870ac-154">![Select Contract and Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span></span>  
  
4.  <span data-ttu-id="870ac-155">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="870ac-155">Click **Next**.</span></span>  
  
### <a name="to-configure-service-and-endpoint-behavior"></a><span data-ttu-id="870ac-156">Para configurar el comportamiento de servicio y extremo</span><span class="sxs-lookup"><span data-stu-id="870ac-156">To configure service and endpoint behavior</span></span>  
  
1.  <span data-ttu-id="870ac-157">En el **configurar comportamientos de servicio y extremo** página, escriba los siguientes valores para **configuración de comportamiento de servicio**:</span><span class="sxs-lookup"><span data-stu-id="870ac-157">On the **Configure service and endpoint behaviors** page, enter the following values for **Service Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="870ac-158">Propiedad</span><span class="sxs-lookup"><span data-stu-id="870ac-158">Property</span></span>|<span data-ttu-id="870ac-159">Valor</span><span class="sxs-lookup"><span data-stu-id="870ac-159">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="870ac-160">**EnableMetadataExchange**</span><span class="sxs-lookup"><span data-stu-id="870ac-160">**EnableMetadataExchange**</span></span>|<span data-ttu-id="870ac-161">True</span><span class="sxs-lookup"><span data-stu-id="870ac-161">True</span></span>|  
    |<span data-ttu-id="870ac-162">**IncludeExceptionDetailsinFault**</span><span class="sxs-lookup"><span data-stu-id="870ac-162">**IncludeExceptionDetailsinFault**</span></span>|<span data-ttu-id="870ac-163">True</span><span class="sxs-lookup"><span data-stu-id="870ac-163">True</span></span>|  
    |<span data-ttu-id="870ac-164">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="870ac-164">**Name**</span></span>|<span data-ttu-id="870ac-165">customServiceBehavior</span><span class="sxs-lookup"><span data-stu-id="870ac-165">customServiceBehavior</span></span>|  
    |<span data-ttu-id="870ac-166">**UseServiceCertificate**</span><span class="sxs-lookup"><span data-stu-id="870ac-166">**UseServiceCertificate**</span></span>|<span data-ttu-id="870ac-167">False</span><span class="sxs-lookup"><span data-stu-id="870ac-167">False</span></span>|  
  
     <span data-ttu-id="870ac-168">Estos valores se usan para rellenar el \< **serviceBehaviors**>.</span><span class="sxs-lookup"><span data-stu-id="870ac-168">These values are used to populate the \<**serviceBehaviors**>.</span></span>  
  
2.  <span data-ttu-id="870ac-169">Escriba los siguientes valores para **configuración de comportamiento de extremo**:</span><span class="sxs-lookup"><span data-stu-id="870ac-169">Enter the following values for **Endpoint Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="870ac-170">Propiedad</span><span class="sxs-lookup"><span data-stu-id="870ac-170">Property</span></span>|<span data-ttu-id="870ac-171">Valor</span><span class="sxs-lookup"><span data-stu-id="870ac-171">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="870ac-172">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="870ac-172">**Name**</span></span>|<span data-ttu-id="870ac-173">customEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="870ac-173">customEndpointBehavior</span></span>|  
    |<span data-ttu-id="870ac-174">**AuthenticationType**</span><span class="sxs-lookup"><span data-stu-id="870ac-174">**AuthenticationType**</span></span>|<span data-ttu-id="870ac-175">**HTTPUsernamePassword**</span><span class="sxs-lookup"><span data-stu-id="870ac-175">**HTTPUsernamePassword**</span></span>|  
    |<span data-ttu-id="870ac-176">**UsernameHeader**</span><span class="sxs-lookup"><span data-stu-id="870ac-176">**UsernameHeader**</span></span>|<span data-ttu-id="870ac-177">MyUserHeader</span><span class="sxs-lookup"><span data-stu-id="870ac-177">MyUserHeader</span></span>|  
    |<span data-ttu-id="870ac-178">**PasswordHeader**</span><span class="sxs-lookup"><span data-stu-id="870ac-178">**PasswordHeader**</span></span>|<span data-ttu-id="870ac-179">MyPassHeader</span><span class="sxs-lookup"><span data-stu-id="870ac-179">MyPassHeader</span></span>|  
  
     <span data-ttu-id="870ac-180">Estos valores se utilizarán para especificar el **adapterSecurityBridgeType** en el <**endpointBehaviors** elemento en Web.config.</span><span class="sxs-lookup"><span data-stu-id="870ac-180">These values will be used to specify the **adapterSecurityBridgeType** in the <**endpointBehaviors** element in web.confg.</span></span>  
  
     <span data-ttu-id="870ac-181">![Configuración de extremo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span><span class="sxs-lookup"><span data-stu-id="870ac-181">![Endpoint Configuration](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span></span>  
  
3.  <span data-ttu-id="870ac-182">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="870ac-182">Click **Next**</span></span>  
  
### <a name="to-configure-the-binding"></a><span data-ttu-id="870ac-183">Para configurar el enlace</span><span class="sxs-lookup"><span data-stu-id="870ac-183">To configure the binding</span></span>  
  
1.  <span data-ttu-id="870ac-184">En el **configurar el enlace de punto de conexión de servicio y la dirección** página, seleccione la **BindingConfiguration** entrada en **configurar el enlace para el contrato y dirección**, y a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="870ac-184">On the **Configure the service endpoint binding and address** page, select the **BindingConfiguration** entry in **Configure the address and binding for the contract**, and then click the ellipsis (**…**) button.</span></span>  
  
2.  <span data-ttu-id="870ac-185">En el **Personalizar enlace** cuadro de diálogo, establezca **modo** a **TransportWithMessageCredential**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="870ac-185">In the **Customize Binding** dialog box, set **Mode** to **TransportWithMessageCredential**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="870ac-186">Haga clic en **aplicar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="870ac-186">Click **Apply**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="870ac-187">En el **resumen** página, revise los contratos y operaciones seleccionadas para este proyecto y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="870ac-187">On the **Summary** page, review the contracts and operations selected for this project, and then click **Finish**.</span></span> <span data-ttu-id="870ac-188">Le presentará la solución EchoWeb, que contiene los archivos de proyecto creados por el[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="870ac-188">You will be presented with the EchoWeb solution, which contains the project files created by the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="870ac-189">Síntesis</span><span class="sxs-lookup"><span data-stu-id="870ac-189">What did I just do?</span></span>  
 <span data-ttu-id="870ac-190">En este paso, ha utilizado la [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] para generar un sitio Web del proyecto que, cuando se publica en IIS, va a hospedar el adaptador de eco desarrollado en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) en IIS procesar.</span><span class="sxs-lookup"><span data-stu-id="870ac-190">In this step, you used the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] to generate a Web project that, when published to IIS, will host the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) in the IIS process.</span></span> <span data-ttu-id="870ac-191">El proyecto Web resultante permite a los clientes de servicios Web y WCF tener acceso a las operaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="870ac-191">The resulting Web project allows Web Services and WCF clients to access the selected operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="870ac-192">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="870ac-192">Next Steps</span></span>  
 <span data-ttu-id="870ac-193">Para compilar e implementar el proyecto Web, continúe con [paso 2: implementar el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span><span class="sxs-lookup"><span data-stu-id="870ac-193">To build and deploy the Web project, proceed to [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870ac-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="870ac-194">See Also</span></span>  
 [<span data-ttu-id="870ac-195">Tutorial 1: Desarrollar el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="870ac-195">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)