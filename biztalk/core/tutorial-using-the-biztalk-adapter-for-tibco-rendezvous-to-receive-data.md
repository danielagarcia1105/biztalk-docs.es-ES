---
title: 'Tutorial: Usar el adaptador de TIBCO Rendezvous para recibir | Documentos de Microsoft'
description: "Guía paso a paso para usar el adaptador de BizTalk para TIBCO Rendezvous en BizTalk Server para recibir datos desde el sistema TIBCO"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75aaba0cc2e455676e78381c04934dda30741a85
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a><span data-ttu-id="447f3-103">Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos</span><span class="sxs-lookup"><span data-stu-id="447f3-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data</span></span>
<span data-ttu-id="447f3-104">Puede usar el Adaptador de BizTalk para TIBCO Rendezvous para recibir datos de un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="447f3-104">You can use the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="447f3-105">En este tutorial se describe un ejemplo de SDK que ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="447f3-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="447f3-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="447f3-106">Prerequisites</span></span>  
  
<span data-ttu-id="447f3-107">Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="447f3-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="about-the-sample"></a><span data-ttu-id="447f3-108">Acerca del ejemplo</span><span class="sxs-lookup"><span data-stu-id="447f3-108">About the sample</span></span> 
- <span data-ttu-id="447f3-109">Este ejemplo usa el Adaptador de BizTalk para TIBCO Rendezvous para recibir datos de un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="447f3-109">This sample uses the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="447f3-110">Una orquestación procesa el mensaje y, mediante el adaptador de archivos, escribe los datos como un archivo XML en una carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="447f3-110">An orchestration processes the message and, using the file adapter, writes the data as an XML file in a specified folder.</span></span>  
  
- <span data-ttu-id="447f3-111">Este ejemplo, diseñado en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], ilustra funciones básicas mediante el uso del adaptador de BizTalk para TIBCO Enterprise Message Service con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="447f3-111">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="447f3-112">Este ejemplo supone que sabe cómo enviar un mensaje desde TIBCO para que la aplicación lo procese.</span><span class="sxs-lookup"><span data-stu-id="447f3-112">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
- <span data-ttu-id="447f3-113">La ubicación predeterminada para el ejemplo es `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`e incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="447f3-113">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`, and includes the following files:</span></span> 
  
    |<span data-ttu-id="447f3-114">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="447f3-114">**Runtime Project Filename**</span></span>|<span data-ttu-id="447f3-115">**Descripción del archivo del proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="447f3-115">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="447f3-116">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="447f3-116">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="447f3-117">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="447f3-117">OneWayReceive.sln</span></span>|<span data-ttu-id="447f3-118">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="447f3-118">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="447f3-119">PureMessage.xsd,</span><span class="sxs-lookup"><span data-stu-id="447f3-119">PureMessage.xsd,</span></span>|<span data-ttu-id="447f3-120">Archivo de esquema de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="447f3-120">Schema file for the application.</span></span>|  
    |<span data-ttu-id="447f3-121">TIBCORvOWR.odx</span><span class="sxs-lookup"><span data-stu-id="447f3-121">TIBCORvOWR.odx</span></span>|<span data-ttu-id="447f3-122">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="447f3-122">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="447f3-123">TIBCORv.snk</span><span class="sxs-lookup"><span data-stu-id="447f3-123">TIBCORv.snk</span></span>|<span data-ttu-id="447f3-124">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="447f3-124">The strong naming key file.</span></span>|  
  
  
## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="447f3-125">Paso 1: Agregar el adaptador de administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="447f3-125">Step 1: Add the adapter to BizTalk Administration</span></span>
  
1.  <span data-ttu-id="447f3-126">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="447f3-126">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="447f3-127">Haga clic en **adaptadores** y seleccione **New**, **adaptador...**</span><span class="sxs-lookup"><span data-stu-id="447f3-127">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="447f3-128">para mostrar la **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="447f3-128">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="447f3-129">Escriba un valor para el **nombre** campo, por ejemplo **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="447f3-129">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="447f3-130">Seleccione **TIBCO Rendezvous(r)** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-130">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
## <a name="step-2-create-a-receive-port"></a><span data-ttu-id="447f3-131">Paso 2: Crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="447f3-131">Step 2: Create a Receive Port</span></span>  
  
1.  <span data-ttu-id="447f3-132">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="447f3-132">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="447f3-133">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional...**  para mostrar la **propiedades de puerto de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="447f3-133">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the **Receive Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="447f3-134">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-134">Enter a value for the **Name** field, for example **TIBCORvOneWayRP**, and click **OK**.</span></span>  
  
## <a name="step-3-create-a-receive-location"></a><span data-ttu-id="447f3-135">Paso 3: Crear una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="447f3-135">Step 3: Create a Receive Location</span></span>  
  
1.  <span data-ttu-id="447f3-136">Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción...**</span><span class="sxs-lookup"><span data-stu-id="447f3-136">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="447f3-137">para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="447f3-137">to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="447f3-138">Escriba un valor para el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="447f3-138">Enter a value for the **Name** field.</span></span> <span data-ttu-id="447f3-139">Por ejemplo, escriba **TIBCORvOneWayRL**.</span><span class="sxs-lookup"><span data-stu-id="447f3-139">For example, enter **TIBCORvOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="447f3-140">Seleccione el adaptador de TIBCO Rendezvous en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="447f3-140">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="447f3-141">Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="447f3-141">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="447f3-142">Escriba un valor para el **RendezvousSubjectName** en el **AdapterRequiredProperties**.</span><span class="sxs-lookup"><span data-stu-id="447f3-142">Enter a value for the **RendezvousSubjectName** under the **AdapterRequiredProperties**.</span></span>  
  
5.  <span data-ttu-id="447f3-143">Escriba valores para la **propiedades de escucha certificadas**:</span><span class="sxs-lookup"><span data-stu-id="447f3-143">Enter values for the **Certified Listener Properties**:</span></span>  
  
    |<span data-ttu-id="447f3-144">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="447f3-144">**Property**</span></span>|<span data-ttu-id="447f3-145">**Valor**</span><span class="sxs-lookup"><span data-stu-id="447f3-145">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="447f3-146">Nombre de archivo de contabilidad</span><span class="sxs-lookup"><span data-stu-id="447f3-146">Ledger file name</span></span>|<span data-ttu-id="447f3-147">Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.</span><span class="sxs-lookup"><span data-stu-id="447f3-147">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="447f3-148">Nombre reutilizable</span><span class="sxs-lookup"><span data-stu-id="447f3-148">Reusable name</span></span>|<span data-ttu-id="447f3-149">Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados.</span><span class="sxs-lookup"><span data-stu-id="447f3-149">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="447f3-150">El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.</span><span class="sxs-lookup"><span data-stu-id="447f3-150">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="447f3-151">Escriba valores para la **credenciales**:</span><span class="sxs-lookup"><span data-stu-id="447f3-151">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="447f3-152">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="447f3-152">**Property**</span></span>|<span data-ttu-id="447f3-153">**Valor**</span><span class="sxs-lookup"><span data-stu-id="447f3-153">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="447f3-154">Contraseña</span><span class="sxs-lookup"><span data-stu-id="447f3-154">Password</span></span>|<span data-ttu-id="447f3-155">La contraseña para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="447f3-155">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="447f3-156">Nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="447f3-156">User name</span></span>|<span data-ttu-id="447f3-157">El nombre de usuario para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="447f3-157">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="447f3-158">Escriba valores para la **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="447f3-158">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="447f3-159">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="447f3-159">**Property**</span></span>|<span data-ttu-id="447f3-160">**Valor**</span><span class="sxs-lookup"><span data-stu-id="447f3-160">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="447f3-161">Demonio</span><span class="sxs-lookup"><span data-stu-id="447f3-161">Daemon</span></span>|<span data-ttu-id="447f3-162">Parámetro del demonio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="447f3-162">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="447f3-163">Red</span><span class="sxs-lookup"><span data-stu-id="447f3-163">Network</span></span>|<span data-ttu-id="447f3-164">Parámetro de red del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="447f3-164">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="447f3-165">ssNoVersion</span><span class="sxs-lookup"><span data-stu-id="447f3-165">Service</span></span>|<span data-ttu-id="447f3-166">Parámetro de servicio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="447f3-166">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="447f3-167">Para obtener más información acerca de las propiedades, vea [crear recepción artefactos](../core/creating-tibco-rendezvous-receive-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="447f3-167">For more information about the properties, see [Create Receive artifacts](../core/creating-tibco-rendezvous-receive-handlers.md).</span></span>  
  
8.  <span data-ttu-id="447f3-168">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-168">Click **OK**.</span></span>  
  
9. <span data-ttu-id="447f3-169">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-169">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
10. <span data-ttu-id="447f3-170">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-170">Right-click the receive location and click **Enable**.</span></span>  
  
## <a name="step-4-create-a-one-way-send-port"></a><span data-ttu-id="447f3-171">Paso 4: Crear un puerto de envío unidireccional</span><span class="sxs-lookup"><span data-stu-id="447f3-171">Step 4: Create a one-way send port</span></span>  
  
1.  <span data-ttu-id="447f3-172">Cree una carpeta de destino que va a usar el puerto de envío; por ejemplo C:\FilesOut.</span><span class="sxs-lookup"><span data-stu-id="447f3-172">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="447f3-173">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="447f3-173">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="447f3-174">Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático...**</span><span class="sxs-lookup"><span data-stu-id="447f3-174">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="447f3-175">para mostrar la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="447f3-175">to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="447f3-176">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayFileSP**.</span><span class="sxs-lookup"><span data-stu-id="447f3-176">Enter a value for the **Name** field, for example **TIBCORvOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="447f3-177">Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="447f3-177">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="447f3-178">Para el **carpeta de destino** propiedad, escriba la ubicación de la carpeta que creó anteriormente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-178">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="447f3-179">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-179">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="447f3-180">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="447f3-180">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
## <a name="step-5-build-and-deploy-the-project"></a><span data-ttu-id="447f3-181">Paso 5: Compilar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="447f3-181">Step 5: Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="447f3-182">Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="447f3-182">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="447f3-183">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="447f3-183">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="447f3-184">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk** categoría.</span><span class="sxs-lookup"><span data-stu-id="447f3-184">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="447f3-185">Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="447f3-185">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
## <a name="step-6-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="447f3-186">Paso 6: Enlazar, dar de alta e iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="447f3-186">Step 6: Bind, Enlist, and start the orchestration</span></span>  
  
1.  <span data-ttu-id="447f3-187">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="447f3-187">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="447f3-188">Haga clic en el **actualizar** botón en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] barra de herramientas de consola de administración o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="447f3-188">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="447f3-189">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="447f3-189">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="447f3-190">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="447f3-190">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="447f3-191">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="447f3-191">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="447f3-192">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="447f3-192">**Parameter**</span></span>|<span data-ttu-id="447f3-193">**Valor**</span><span class="sxs-lookup"><span data-stu-id="447f3-193">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="447f3-194">Host</span><span class="sxs-lookup"><span data-stu-id="447f3-194">Host</span></span>|<span data-ttu-id="447f3-195">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="447f3-195">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="447f3-196">SendPort</span><span class="sxs-lookup"><span data-stu-id="447f3-196">SendPort</span></span>|<span data-ttu-id="447f3-197">TIBCORvOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="447f3-197">TIBCORvOneWayFileSP</span></span>|  
    |<span data-ttu-id="447f3-198">ReceivePort</span><span class="sxs-lookup"><span data-stu-id="447f3-198">ReceivePort</span></span>|<span data-ttu-id="447f3-199">TIBCORvOneWayRP</span><span class="sxs-lookup"><span data-stu-id="447f3-199">TIBCORvOneWayRP</span></span>|  
  
6.  <span data-ttu-id="447f3-200">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="447f3-200">Click **OK**.</span></span>  
  
7. <span data-ttu-id="447f3-201">Haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="447f3-201">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  
  
## <a name="step-7-confirm-the-application-receives-a-message"></a><span data-ttu-id="447f3-202">Paso 7: Confirmar que la aplicación recibe un mensaje</span><span class="sxs-lookup"><span data-stu-id="447f3-202">Step 7: Confirm the application receives a message</span></span>  
  
-   <span data-ttu-id="447f3-203">Abra la carpeta que el puerto de envío de archivos está configurado para enviar a y compruebe que se ha generado un documento de salida.</span><span class="sxs-lookup"><span data-stu-id="447f3-203">Open the folder that the file send port is configured to send to, and verify that an output document was generated.</span></span>  
  
 <span data-ttu-id="447f3-204">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="447f3-204">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="447f3-205">El adaptador de TIBCO Rendezvous recibe un mensaje del sistema TIBCO y lo publica en el cuadro de mensajes como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="447f3-205">The TIBCO Rendezvous adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="447f3-206">La orquestación se suscribe a este mensaje publicado para que el motor de mensajería de BizTalk active una instancia de la orquestación y envíe el mensaje a ésta.</span><span class="sxs-lookup"><span data-stu-id="447f3-206">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="447f3-207">La instancia de orquestación publica el mensaje en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="447f3-207">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="447f3-208">El puerto de envío de archivos se suscribe a este mensaje, por lo que BizTalk envía el mensaje al adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="447f3-208">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="447f3-209">El adaptador de archivos escribe un mensaje que contiene el conjunto de resultados en la carpeta de salida designada.</span><span class="sxs-lookup"><span data-stu-id="447f3-209">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447f3-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="447f3-210">See Also</span></span>  
 <span data-ttu-id="447f3-211">[Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para enviar datos](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="447f3-211">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span></span>  
 <span data-ttu-id="447f3-212">[Tutoriales: Usar el adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="447f3-212">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="447f3-213">Introducción</span><span class="sxs-lookup"><span data-stu-id="447f3-213">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)