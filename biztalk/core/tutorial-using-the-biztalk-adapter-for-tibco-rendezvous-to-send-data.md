---
title: 'Tutorial: Uso del adaptador de TIBCO Rendezvous para enviar | Microsoft Docs'
description: Guía paso a paso para usar el adaptador de BizTalk para TIBCO Rendezvous en BizTalk Server para enviar datos al sistema TIBCO
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef842eacf261904173b90728ba2702513973cf53
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966941"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="db874-103">Tutorial: Uso del adaptador de BizTalk para TIBCO Rendezvous para enviar datos</span><span class="sxs-lookup"><span data-stu-id="db874-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="db874-104">Puede usar BizTalk Adapter para TIBCO Rendezvous para enviar datos a un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="db874-104">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="db874-105">En este tutorial se describe un ejemplo de SDK que ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="db874-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="db874-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="db874-106">Prerequisites</span></span>  

- <span data-ttu-id="db874-107">Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="db874-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

- <span data-ttu-id="db874-108">En el ejemplo se utiliza una DLL que contiene las propiedades del contexto del mensaje: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span><span class="sxs-lookup"><span data-stu-id="db874-108">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="db874-109">Puede necesitar actualizar la referencia de la solución a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="db874-109">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="db874-110">Para obtener más información, consulte [propiedades de contexto de mensaje de BizTalk Server (controladores de envío)](../core/biztalk-server-message-context-properties-send-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="db874-110">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  

## <a name="about-the-sample"></a><span data-ttu-id="db874-111">Acerca del ejemplo</span><span class="sxs-lookup"><span data-stu-id="db874-111">About the sample</span></span> 

- <span data-ttu-id="db874-112">Este ejemplo toma un archivo XML de una carpeta de archivos, envía el archivo a una orquestación y, luego, usa BizTalk Adapter para TIBCO Rendezvous para crear un registro en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="db874-112">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  

- <span data-ttu-id="db874-113">Este ejemplo, diseñado en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], ilustra la funcionalidad básica del uso de BizTalk Adapter para TIBCO Rendezvous con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="db874-113">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  

- <span data-ttu-id="db874-114">La ubicación predeterminada del ejemplo es `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`e incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="db874-114">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`, and includes the following files:</span></span> 

    |<span data-ttu-id="db874-115">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="db874-115">**Runtime Project Filename**</span></span>|<span data-ttu-id="db874-116">**Descripción del archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="db874-116">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="db874-117">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="db874-117">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="db874-118">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="db874-118">OneWaySend.sln</span></span>|<span data-ttu-id="db874-119">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db874-119">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="db874-120">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="db874-120">Schema.xsd</span></span><br /><br /> <span data-ttu-id="db874-121">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="db874-121">PropertySchema.xsd</span></span>|<span data-ttu-id="db874-122">Esquema y archivos de esquema de propiedades para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db874-122">Schema and property schema files for the application.</span></span>|  
    |<span data-ttu-id="db874-123">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="db874-123">Orchestration.odx</span></span>|<span data-ttu-id="db874-124">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db874-124">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="db874-125">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="db874-125">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="db874-126">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="db874-126">The strong naming key file.</span></span>|  

## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="db874-127">Paso 1: Agregar el adaptador para la administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="db874-127">Step 1: Add the adapter to BizTalk Administration</span></span>

1.  <span data-ttu-id="db874-128">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="db874-128">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3.  <span data-ttu-id="db874-129">Haga clic en **adaptadores** y apuntar a **New**, **adaptador...**</span><span class="sxs-lookup"><span data-stu-id="db874-129">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="db874-130">para mostrar el **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db874-130">to display the **Adapter Properties** dialog.</span></span>  

4.  <span data-ttu-id="db874-131">Escriba un valor para el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="db874-131">Enter a value for the **Name** field.</span></span> <span data-ttu-id="db874-132">Por ejemplo, escriba **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="db874-132">For example, enter **TIBCO Rendezvous**.</span></span>  

5.  <span data-ttu-id="db874-133">Seleccione **TIBCO Rendezvous(r)** en la lista de adaptadores disponibles en el **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db874-133">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

## <a name="step-2-create-a-send-port"></a><span data-ttu-id="db874-134">Paso 2: Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="db874-134">Step 2: Create a Send Port</span></span>  

1. <span data-ttu-id="db874-135">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **Puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="db874-135">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="db874-136">Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío unidireccional estático...**</span><span class="sxs-lookup"><span data-stu-id="db874-136">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="db874-137">para mostrar el **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db874-137">to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="db874-138">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWaySP**.</span><span class="sxs-lookup"><span data-stu-id="db874-138">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  

4. <span data-ttu-id="db874-139">Seleccione el adaptador de TIBCO Rendezvous en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db874-139">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="db874-140">Este valor es el nombre que especificó cuando creó el adaptador TIBCO Enterprise Message System en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="db874-140">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

5. <span data-ttu-id="db874-141">Escriba valores para el **propiedades de remitente certificado**:</span><span class="sxs-lookup"><span data-stu-id="db874-141">Enter values for the **Certified Sender Properties**:</span></span>  


   |   <span data-ttu-id="db874-142">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="db874-142">**Property**</span></span>   |                                                                         <span data-ttu-id="db874-143">**Value**</span><span class="sxs-lookup"><span data-stu-id="db874-143">**Value**</span></span>                                                                          |
   |------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="db874-144">Nombre de archivo de contabilidad</span><span class="sxs-lookup"><span data-stu-id="db874-144">Ledger file name</span></span> |                                             <span data-ttu-id="db874-145">Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.</span><span class="sxs-lookup"><span data-stu-id="db874-145">Ledger file name to use for persistent certified message delivery.</span></span>                                             |
   |  <span data-ttu-id="db874-146">Nombre reutilizable</span><span class="sxs-lookup"><span data-stu-id="db874-146">Reusable name</span></span>   | <span data-ttu-id="db874-147">Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados.</span><span class="sxs-lookup"><span data-stu-id="db874-147">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="db874-148">El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.</span><span class="sxs-lookup"><span data-stu-id="db874-148">The name must be unique among all certified message correspondent names on the network.</span></span> |


6. <span data-ttu-id="db874-149">Escriba valores para el **credenciales**:</span><span class="sxs-lookup"><span data-stu-id="db874-149">Enter values for the **Credentials**:</span></span>  


   | <span data-ttu-id="db874-150">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="db874-150">**Property**</span></span> |                   <span data-ttu-id="db874-151">**Value**</span><span class="sxs-lookup"><span data-stu-id="db874-151">**Value**</span></span>                    |
   |--------------|------------------------------------------------|
   |   <span data-ttu-id="db874-152">Contraseña</span><span class="sxs-lookup"><span data-stu-id="db874-152">Password</span></span>   | <span data-ttu-id="db874-153">La contraseña para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="db874-153">The password for the TIBCO Rendezvous server.</span></span>  |
   |  <span data-ttu-id="db874-154">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="db874-154">User name</span></span>   | <span data-ttu-id="db874-155">El nombre de usuario para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="db874-155">The user name for the TIBCO Rendezvous server.</span></span> |


7. <span data-ttu-id="db874-156">Escriba valores para el **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="db874-156">Enter values for the **RendezvousTransport**:</span></span>  

   |<span data-ttu-id="db874-157">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="db874-157">**Property**</span></span>|<span data-ttu-id="db874-158">**Value**</span><span class="sxs-lookup"><span data-stu-id="db874-158">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="db874-159">Demonio</span><span class="sxs-lookup"><span data-stu-id="db874-159">Daemon</span></span>|<span data-ttu-id="db874-160">Parámetro del demonio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="db874-160">Rendezvous Transport Daemon parameter.</span></span>|  
   |<span data-ttu-id="db874-161">red</span><span class="sxs-lookup"><span data-stu-id="db874-161">Network</span></span>|<span data-ttu-id="db874-162">Parámetro de red del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="db874-162">Rendezvous Transport Network parameter.</span></span>|  
   |<span data-ttu-id="db874-163">ssNoVersion</span><span class="sxs-lookup"><span data-stu-id="db874-163">Service</span></span>|<span data-ttu-id="db874-164">Parámetro de servicio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="db874-164">Rendezvous Transport Service parameter.</span></span>|  

    <span data-ttu-id="db874-165">Para obtener más información acerca de las propiedades, vea [crear los artefactos de envío](../core/creating-tibco-rendezvous-send-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="db874-165">For more information about the properties, see [Create the send artifacts](../core/creating-tibco-rendezvous-send-handlers.md).</span></span>  

8. <span data-ttu-id="db874-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db874-166">Click **OK**.</span></span>  

9. <span data-ttu-id="db874-167">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db874-167">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

10. <span data-ttu-id="db874-168">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="db874-168">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

## <a name="step-3-create-a-receive-port"></a><span data-ttu-id="db874-169">Paso 3: Crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="db874-169">Step 3: Create a receive port</span></span>  

1.  <span data-ttu-id="db874-170">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="db874-170">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2.  <span data-ttu-id="db874-171">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional...**  para mostrar el cuadro de diálogo Propiedades de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="db874-171">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  

3.  <span data-ttu-id="db874-172">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db874-172">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  

## <a name="step-4-create-a-receive-location"></a><span data-ttu-id="db874-173">Paso 4: Creación de una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="db874-173">Step 4: Create a receive location</span></span>  

1.  <span data-ttu-id="db874-174">Cree una carpeta para la ubicación de recepción de archivos que se debe supervisar, por ejemplo, C:\Filesource.</span><span class="sxs-lookup"><span data-stu-id="db874-174">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="db874-175">Con el botón secundario del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción...**</span><span class="sxs-lookup"><span data-stu-id="db874-175">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="db874-176">para mostrar el **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db874-176">to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="db874-177">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRL**.</span><span class="sxs-lookup"><span data-stu-id="db874-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="db874-178">Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db874-178">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="db874-179">Escriba la ubicación de la carpeta que creó anteriormente para la **carpetas de recepción** propiedad y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db874-179">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="db874-180">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db874-180">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="db874-181">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="db874-181">Right-click the receive location and click **Enable**.</span></span>  

## <a name="step-5-generate-a-document-instance-from-the-schema"></a><span data-ttu-id="db874-182">Paso 5: Generar una instancia de documento del esquema</span><span class="sxs-lookup"><span data-stu-id="db874-182">Step 5: Generate a document instance from the schema</span></span>  

1.  <span data-ttu-id="db874-183">En Visual Studio, haga clic con el Schema.xsd en el Explorador de soluciones y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="db874-183">In Visual Studio,right-click Schema.xsd in Solution Explorer, and click **Properties**.</span></span>  

2.  <span data-ttu-id="db874-184">En la ventana Propiedades, haga clic para seleccionar el **nombre de archivo de instancia de salida** opción bajo el **General** sección.</span><span class="sxs-lookup"><span data-stu-id="db874-184">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  

3.  <span data-ttu-id="db874-185">Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db874-185">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

4.  <span data-ttu-id="db874-186">Especifique una carpeta y un nombre para la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="db874-186">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="db874-187">No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="db874-187">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

5.  <span data-ttu-id="db874-188">Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="db874-188">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

## <a name="step-6-update-the-generated-document-instance"></a><span data-ttu-id="db874-189">Paso 6: Actualización de la instancia de documento generada</span><span class="sxs-lookup"><span data-stu-id="db874-189">Step 6: Update the generated document instance</span></span>  

1.  <span data-ttu-id="db874-190">Abra la instancia de documento generado en un editor de texto (funciona en el Bloc de notas) y edite el contenido de la instancia de documento para asegurarse de que los datos generará un registro único en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="db874-190">Open the generated document instance in a text editor(Notepad works), and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="db874-191">Por ejemplo, el código siguiente muestra la primera parte del archivo de datos:</span><span class="sxs-lookup"><span data-stu-id="db874-191">For example, the follow code shows the first part of the data file:</span></span>  

    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  

2.  <span data-ttu-id="db874-192">Guarde la instancia de documento modificada.</span><span class="sxs-lookup"><span data-stu-id="db874-192">Save the modified document instance.</span></span>  

## <a name="step-7-build-and-deploy-the-project"></a><span data-ttu-id="db874-193">Paso 7: Crear e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="db874-193">Step 7: Build and deploy the project</span></span>  

1. <span data-ttu-id="db874-194">Haga clic en el **OneWaySend** proyecto en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="db874-194">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="db874-195">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="db874-195">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="db874-196">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="db874-196">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="db874-197">Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **implementar** para compilar el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="db874-197">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

## <a name="step-8-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="db874-198">Paso 8: Enlazar, dar de alta e iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="db874-198">Step 8: Bind, enlist, and start the orchestration</span></span>  

1. <span data-ttu-id="db874-199">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **Orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="db874-199">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="db874-200">Haga clic en el **actualizar** botón en la barra de herramientas MMC o presione la **F5** en el teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="db874-200">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="db874-201">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db874-201">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="db874-202">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="db874-202">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="db874-203">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="db874-203">Specify the appropriate values for the binding options, for example:</span></span>  


   |    <span data-ttu-id="db874-204">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="db874-204">**Parameter**</span></span>    |        <span data-ttu-id="db874-205">**Value**</span><span class="sxs-lookup"><span data-stu-id="db874-205">**Value**</span></span>         |
   |---------------------|--------------------------|
   |        <span data-ttu-id="db874-206">Host</span><span class="sxs-lookup"><span data-stu-id="db874-206">Host</span></span>         | <span data-ttu-id="db874-207">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="db874-207">BizTalkServerApplication</span></span> |
   |   <span data-ttu-id="db874-208">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="db874-208">FileReceivePort</span></span>   |   <span data-ttu-id="db874-209">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="db874-209">TIBCORndOneWayFileRP</span></span>   |
   | <span data-ttu-id="db874-210">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="db874-210">TibcoRendezvousSend</span></span> |     <span data-ttu-id="db874-211">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="db874-211">TIBCORndOneWaySP</span></span>     |


6. <span data-ttu-id="db874-212">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="db874-212">Click OK.</span></span>  

7. <span data-ttu-id="db874-213">Haga clic en la orquestación y haga clic en **iniciar** para dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="db874-213">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  

## <a name="step-9-drop-a-document-and-check-the-tibco-system"></a><span data-ttu-id="db874-214">Paso 9: Quitar un documento y compruebe el sistema TIBCO</span><span class="sxs-lookup"><span data-stu-id="db874-214">Step 9: Drop a document, and check the TIBCO system</span></span>

-   <span data-ttu-id="db874-215">Copie la instancia de documento que se creó anteriormente en la carpeta de recepción de archivos que la aplicación supervisa.</span><span class="sxs-lookup"><span data-stu-id="db874-215">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  

-   <span data-ttu-id="db874-216">Use la interfaz web de TIBCO para comprobar que el registro se creó a partir de los datos del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="db874-216">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  


<span data-ttu-id="db874-217">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="db874-217">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="db874-218">El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="db874-218">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="db874-219">La orquestación se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk activará una instancia de la orquestación y enviará el mensaje a la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="db874-219">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="db874-220">La instancia de la orquestación procesa el mensaje mediante la lógica especificada en la orquestación y vuelve a publicar el mensaje en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="db874-220">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="db874-221">El puerto de envío de TIBCO se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de TIBCO.</span><span class="sxs-lookup"><span data-stu-id="db874-221">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  

5.  <span data-ttu-id="db874-222">El puerto de envío entrega el mensaje a BizTalk Adapter para TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="db874-222">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  

6.  <span data-ttu-id="db874-223">BizTalk Adapter para TIBCO Rendezvous envía el mensaje al sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="db874-223">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  

## <a name="see-also"></a><span data-ttu-id="db874-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="db874-224">See Also</span></span>  
 <span data-ttu-id="db874-225">[Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="db874-225">[Tutorial: Use the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="db874-226">[Tutoriales: Uso del adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="db874-226">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="db874-227">Introducción</span><span class="sxs-lookup"><span data-stu-id="db874-227">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)