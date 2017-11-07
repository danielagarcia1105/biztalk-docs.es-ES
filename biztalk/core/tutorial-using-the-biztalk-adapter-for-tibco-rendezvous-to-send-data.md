---
title: 'Tutorial: Usar el adaptador de TIBCO Rendezvous para enviar | Documentos de Microsoft'
description: "Guía paso a paso para usar el adaptador de BizTalk para TIBCO Rendezvous en BizTalk Server para enviar datos al sistema TIBCO"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a08987e92465358276df7936f39cfa7c449c0503
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="39f7a-103">Tutorial: Uso del adaptador de BizTalk para TIBCO Rendezvous para enviar datos</span><span class="sxs-lookup"><span data-stu-id="39f7a-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="39f7a-104">Puede usar BizTalk Adapter para TIBCO Rendezvous para enviar datos a un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="39f7a-104">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="39f7a-105">En este tutorial se describe un ejemplo de SDK que ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="39f7a-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="39f7a-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="39f7a-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="39f7a-107">Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
-   <span data-ttu-id="39f7a-108">En el ejemplo se utiliza una DLL que contiene las propiedades del contexto del mensaje: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span><span class="sxs-lookup"><span data-stu-id="39f7a-108">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="39f7a-109">Puede necesitar actualizar la referencia de la solución a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="39f7a-109">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="39f7a-110">Para obtener más información, consulte [propiedades de contexto de mensaje de BizTalk Server (controladores de envío)](../core/biztalk-server-message-context-properties-send-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="39f7a-110">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  
  
## <a name="about-the-sample"></a><span data-ttu-id="39f7a-111">Acerca del ejemplo</span><span class="sxs-lookup"><span data-stu-id="39f7a-111">About the sample</span></span> 

- <span data-ttu-id="39f7a-112">Este ejemplo toma un archivo XML de una carpeta de archivos, envía el archivo a una orquestación y, luego, usa BizTalk Adapter para TIBCO Rendezvous para crear un registro en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="39f7a-112">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  
  
- <span data-ttu-id="39f7a-113">Este ejemplo, diseñado en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], ilustra la funcionalidad básica del uso de BizTalk Adapter para TIBCO Rendezvous con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="39f7a-113">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  
  
- <span data-ttu-id="39f7a-114">La ubicación predeterminada para el ejemplo es `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`e incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="39f7a-114">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`, and includes the following files:</span></span> 
    
    |<span data-ttu-id="39f7a-115">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="39f7a-115">**Runtime Project Filename**</span></span>|<span data-ttu-id="39f7a-116">**Descripción del archivo del proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="39f7a-116">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="39f7a-117">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="39f7a-117">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="39f7a-118">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="39f7a-118">OneWaySend.sln</span></span>|<span data-ttu-id="39f7a-119">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="39f7a-119">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="39f7a-120">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="39f7a-120">Schema.xsd</span></span><br /><br /> <span data-ttu-id="39f7a-121">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="39f7a-121">PropertySchema.xsd</span></span>|<span data-ttu-id="39f7a-122">Esquema y archivos de esquema de propiedades para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="39f7a-122">Schema and property schema files for the application.</span></span>|  
    |<span data-ttu-id="39f7a-123">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="39f7a-123">Orchestration.odx</span></span>|<span data-ttu-id="39f7a-124">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="39f7a-124">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="39f7a-125">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="39f7a-125">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="39f7a-126">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="39f7a-126">The strong naming key file.</span></span>|  
  
## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="39f7a-127">Paso 1: Agregar el adaptador de administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="39f7a-127">Step 1: Add the adapter to BizTalk Administration</span></span>
  
1.  <span data-ttu-id="39f7a-128">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-128">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="39f7a-129">Haga clic en **adaptadores** y seleccione **New**, **adaptador...**</span><span class="sxs-lookup"><span data-stu-id="39f7a-129">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="39f7a-130">para mostrar la **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-130">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="39f7a-131">Escriba un valor para el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-131">Enter a value for the **Name** field.</span></span> <span data-ttu-id="39f7a-132">Por ejemplo, escriba **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-132">For example, enter **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="39f7a-133">Seleccione **TIBCO Rendezvous(r)** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-133">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
## <a name="step-2-create-a-send-port"></a><span data-ttu-id="39f7a-134">Paso 2: Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="39f7a-134">Step 2: Create a Send Port</span></span>  
  
1.  <span data-ttu-id="39f7a-135">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **Puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-135">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="39f7a-136">Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático...**</span><span class="sxs-lookup"><span data-stu-id="39f7a-136">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="39f7a-137">para mostrar la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-137">to display the **Send Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="39f7a-138">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWaySP**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-138">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  
  
4.  <span data-ttu-id="39f7a-139">Seleccione el adaptador de TIBCO Rendezvous en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-139">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39f7a-140">Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO Enterprise Message System en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="39f7a-140">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5.  <span data-ttu-id="39f7a-141">Escriba valores para la **propiedades de remitente certificado**:</span><span class="sxs-lookup"><span data-stu-id="39f7a-141">Enter values for the **Certified Sender Properties**:</span></span>  
  
    |<span data-ttu-id="39f7a-142">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="39f7a-142">**Property**</span></span>|<span data-ttu-id="39f7a-143">**Valor**</span><span class="sxs-lookup"><span data-stu-id="39f7a-143">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="39f7a-144">Nombre de archivo de contabilidad</span><span class="sxs-lookup"><span data-stu-id="39f7a-144">Ledger file name</span></span>|<span data-ttu-id="39f7a-145">Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.</span><span class="sxs-lookup"><span data-stu-id="39f7a-145">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="39f7a-146">Nombre reutilizable</span><span class="sxs-lookup"><span data-stu-id="39f7a-146">Reusable name</span></span>|<span data-ttu-id="39f7a-147">Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados.</span><span class="sxs-lookup"><span data-stu-id="39f7a-147">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="39f7a-148">El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.</span><span class="sxs-lookup"><span data-stu-id="39f7a-148">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="39f7a-149">Escriba valores para la **credenciales**:</span><span class="sxs-lookup"><span data-stu-id="39f7a-149">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="39f7a-150">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="39f7a-150">**Property**</span></span>|<span data-ttu-id="39f7a-151">**Valor**</span><span class="sxs-lookup"><span data-stu-id="39f7a-151">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="39f7a-152">Contraseña</span><span class="sxs-lookup"><span data-stu-id="39f7a-152">Password</span></span>|<span data-ttu-id="39f7a-153">La contraseña para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="39f7a-153">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="39f7a-154">Nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="39f7a-154">User name</span></span>|<span data-ttu-id="39f7a-155">El nombre de usuario para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="39f7a-155">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="39f7a-156">Escriba valores para la **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="39f7a-156">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="39f7a-157">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="39f7a-157">**Property**</span></span>|<span data-ttu-id="39f7a-158">**Valor**</span><span class="sxs-lookup"><span data-stu-id="39f7a-158">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="39f7a-159">Demonio</span><span class="sxs-lookup"><span data-stu-id="39f7a-159">Daemon</span></span>|<span data-ttu-id="39f7a-160">Parámetro del demonio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="39f7a-160">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="39f7a-161">Red</span><span class="sxs-lookup"><span data-stu-id="39f7a-161">Network</span></span>|<span data-ttu-id="39f7a-162">Parámetro de red del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="39f7a-162">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="39f7a-163">ssNoVersion</span><span class="sxs-lookup"><span data-stu-id="39f7a-163">Service</span></span>|<span data-ttu-id="39f7a-164">Parámetro de servicio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="39f7a-164">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="39f7a-165">Para obtener más información acerca de las propiedades, vea [crear los artefactos de envío](../core/creating-tibco-rendezvous-send-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="39f7a-165">For more information about the properties, see [Create the send artifacts](../core/creating-tibco-rendezvous-send-handlers.md).</span></span>  
  
8.  <span data-ttu-id="39f7a-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-166">Click **OK**.</span></span>  
  
9. <span data-ttu-id="39f7a-167">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-167">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
10. <span data-ttu-id="39f7a-168">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="39f7a-168">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
## <a name="step-3-create-a-receive-port"></a><span data-ttu-id="39f7a-169">Paso 3: Crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="39f7a-169">Step 3: Create a receive port</span></span>  
  
1.  <span data-ttu-id="39f7a-170">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-170">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="39f7a-171">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional...**  para mostrar el cuadro de diálogo Propiedades de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="39f7a-171">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="39f7a-172">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-172">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  
  
## <a name="step-4-create-a-receive-location"></a><span data-ttu-id="39f7a-173">Paso 4: Crear una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="39f7a-173">Step 4: Create a receive location</span></span>  
  
1.  <span data-ttu-id="39f7a-174">Cree una carpeta para la ubicación de recepción de archivos que se debe supervisar, por ejemplo, C:\Filesource.</span><span class="sxs-lookup"><span data-stu-id="39f7a-174">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  
  
2.  <span data-ttu-id="39f7a-175">Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción...**</span><span class="sxs-lookup"><span data-stu-id="39f7a-175">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="39f7a-176">para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-176">to display the **Receive Location Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="39f7a-177">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRL**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  
  
4.  <span data-ttu-id="39f7a-178">Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-178">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="39f7a-179">Escriba la ubicación de la carpeta que creó anteriormente para la **carpeta recepción** propiedad y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-179">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  
  
6.  <span data-ttu-id="39f7a-180">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-180">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="39f7a-181">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-181">Right-click the receive location and click **Enable**.</span></span>  
  
## <a name="step-5-generate-a-document-instance-from-the-schema"></a><span data-ttu-id="39f7a-182">Paso 5: Generar una instancia de documento del esquema</span><span class="sxs-lookup"><span data-stu-id="39f7a-182">Step 5: Generate a document instance from the schema</span></span>  
  
1.  <span data-ttu-id="39f7a-183">En Visual Studio, haga clic con el Schema.xsd en el Explorador de soluciones y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-183">In Visual Studio,right-click Schema.xsd in Solution Explorer, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="39f7a-184">En la ventana Propiedades, haga clic en el **nombre de archivo de instancia de salida** opción bajo el **General** sección.</span><span class="sxs-lookup"><span data-stu-id="39f7a-184">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  
  
3.  <span data-ttu-id="39f7a-185">Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-185">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  
  
4.  <span data-ttu-id="39f7a-186">Especifique una carpeta y el nombre de la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-186">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39f7a-187">No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="39f7a-187">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  
  
5.  <span data-ttu-id="39f7a-188">Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="39f7a-188">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  
  
## <a name="step-6-update-the-generated-document-instance"></a><span data-ttu-id="39f7a-189">Paso 6: Actualizar la instancia de documento generada</span><span class="sxs-lookup"><span data-stu-id="39f7a-189">Step 6: Update the generated document instance</span></span>  
  
1.  <span data-ttu-id="39f7a-190">Abra la instancia de documento generada en un editor de texto (funciona el Bloc de notas) y edite el contenido de la instancia de documento para asegurarse de que los datos generarán un registro único en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="39f7a-190">Open the generated document instance in a text editor(Notepad works), and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="39f7a-191">Por ejemplo, el código siguiente muestra la primera parte del archivo de datos:</span><span class="sxs-lookup"><span data-stu-id="39f7a-191">For example, the follow code shows the first part of the data file:</span></span>  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  <span data-ttu-id="39f7a-192">Guarde la instancia de documento modificada.</span><span class="sxs-lookup"><span data-stu-id="39f7a-192">Save the modified document instance.</span></span>  
  
## <a name="step-7-build-and-deploy-the-project"></a><span data-ttu-id="39f7a-193">Paso 7: Crear e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="39f7a-193">Step 7: Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="39f7a-194">Haga clic en el **OneWaySend** del proyecto en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="39f7a-194">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="39f7a-195">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="39f7a-195">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="39f7a-196">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-196">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="39f7a-197">Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="39f7a-197">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
## <a name="step-8-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="39f7a-198">Paso 8: Enlazar, dar de alta e iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="39f7a-198">Step 8: Bind, enlist, and start the orchestration</span></span>  
  
1.  <span data-ttu-id="39f7a-199">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **Orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="39f7a-199">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="39f7a-200">Haga clic en el **actualizar** botón en la barra de herramientas MMC o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="39f7a-200">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="39f7a-201">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="39f7a-201">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="39f7a-202">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f7a-202">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="39f7a-203">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39f7a-203">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="39f7a-204">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="39f7a-204">**Parameter**</span></span>|<span data-ttu-id="39f7a-205">**Valor**</span><span class="sxs-lookup"><span data-stu-id="39f7a-205">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="39f7a-206">Host</span><span class="sxs-lookup"><span data-stu-id="39f7a-206">Host</span></span>|<span data-ttu-id="39f7a-207">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="39f7a-207">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="39f7a-208">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="39f7a-208">FileReceivePort</span></span>|<span data-ttu-id="39f7a-209">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="39f7a-209">TIBCORndOneWayFileRP</span></span>|  
    |<span data-ttu-id="39f7a-210">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="39f7a-210">TibcoRendezvousSend</span></span>|<span data-ttu-id="39f7a-211">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="39f7a-211">TIBCORndOneWaySP</span></span>|  
  
6.  <span data-ttu-id="39f7a-212">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="39f7a-212">Click OK.</span></span>  
  
7. <span data-ttu-id="39f7a-213">Haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f7a-213">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  
  
## <a name="step-9-drop-a-document-and-check-the-tibco-system"></a><span data-ttu-id="39f7a-214">Paso 9: Quitar un documento y compruebe el sistema TIBCO</span><span class="sxs-lookup"><span data-stu-id="39f7a-214">Step 9: Drop a document, and check the TIBCO system</span></span>
  
-   <span data-ttu-id="39f7a-215">Copie la instancia de documento que se creó anteriormente en la carpeta de recepción de archivos que la aplicación supervisa.</span><span class="sxs-lookup"><span data-stu-id="39f7a-215">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  
  
-   <span data-ttu-id="39f7a-216">Use la interfaz web de TIBCO para comprobar que el registro se creó a partir de los datos del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="39f7a-216">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  
  

<span data-ttu-id="39f7a-217">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="39f7a-217">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="39f7a-218">El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="39f7a-218">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="39f7a-219">La orquestación se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk activará una instancia de la orquestación y enviará el mensaje a la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f7a-219">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="39f7a-220">La instancia de la orquestación procesa el mensaje mediante la lógica especificada en la orquestación y vuelve a publicar el mensaje en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="39f7a-220">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="39f7a-221">El puerto de envío de TIBCO se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de TIBCO.</span><span class="sxs-lookup"><span data-stu-id="39f7a-221">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  
  
5.  <span data-ttu-id="39f7a-222">El puerto de envío entrega el mensaje a BizTalk Adapter para TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="39f7a-222">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
6.  <span data-ttu-id="39f7a-223">BizTalk Adapter para TIBCO Rendezvous envía el mensaje al sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="39f7a-223">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f7a-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="39f7a-224">See Also</span></span>  
 <span data-ttu-id="39f7a-225">[Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="39f7a-225">[Tutorial: Use the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="39f7a-226">[Tutoriales: Usar el adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="39f7a-226">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="39f7a-227">Introducción</span><span class="sxs-lookup"><span data-stu-id="39f7a-227">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)