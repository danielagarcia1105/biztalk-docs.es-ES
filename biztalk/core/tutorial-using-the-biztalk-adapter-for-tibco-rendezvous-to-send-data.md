---
title: 'Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para enviar datos | Documentos de Microsoft'
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
ms.openlocfilehash: 63540402ca8e060d26c8398af010a81eaad0a6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="fec30-102">Tutorial: Uso del adaptador de BizTalk para TIBCO Rendezvous para enviar datos</span><span class="sxs-lookup"><span data-stu-id="fec30-102">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="fec30-103">Puede usar BizTalk Adapter para TIBCO Rendezvous para enviar datos a un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="fec30-103">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="fec30-104">En este tutorial se describe un ejemplo de SDK que ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="fec30-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fec30-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fec30-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="fec30-106">Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fec30-106">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
-   <span data-ttu-id="fec30-107">En el ejemplo se utiliza una DLL que contiene las propiedades del contexto del mensaje: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span><span class="sxs-lookup"><span data-stu-id="fec30-107">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="fec30-108">Puede necesitar actualizar la referencia de la solución a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="fec30-108">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="fec30-109">Para obtener más información, consulte [propiedades de contexto de mensaje de BizTalk Server (controladores de envío)](../core/biztalk-server-message-context-properties-send-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="fec30-109">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="fec30-110">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="fec30-110">What This Sample Does</span></span>  
 <span data-ttu-id="fec30-111">Este ejemplo toma un archivo XML de una carpeta de archivos, envía el archivo a una orquestación y, luego, usa BizTalk Adapter para TIBCO Rendezvous para crear un registro en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="fec30-111">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="fec30-112">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="fec30-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="fec30-113">Este ejemplo, diseñado en [!INCLUDE[vs2010](../includes/vs2010-md.md)], ilustra la funcionalidad básica del uso de BizTalk Adapter para TIBCO Rendezvous con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fec30-113">This sample, designed in [!INCLUDE[vs2010](../includes/vs2010-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="fec30-114">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="fec30-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="fec30-115">La ubicación predeterminada para el ejemplo es</span><span class="sxs-lookup"><span data-stu-id="fec30-115">The default location for the sample is</span></span>  
  
 <span data-ttu-id="fec30-116">C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend</span><span class="sxs-lookup"><span data-stu-id="fec30-116">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend</span></span>  
  
 <span data-ttu-id="fec30-117">En la tabla siguiente se enumeran y describen los archivos del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fec30-117">The following table lists and describes the files in the sample.</span></span>  
  
|<span data-ttu-id="fec30-118">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="fec30-118">**Runtime Project Filename**</span></span>|<span data-ttu-id="fec30-119">**Descripción del archivo del proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="fec30-119">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="fec30-120">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="fec30-120">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="fec30-121">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="fec30-121">OneWaySend.sln</span></span>|<span data-ttu-id="fec30-122">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fec30-122">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="fec30-123">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="fec30-123">Schema.xsd</span></span><br /><br /> <span data-ttu-id="fec30-124">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="fec30-124">PropertySchema.xsd</span></span>|<span data-ttu-id="fec30-125">Esquema y archivos de esquema de propiedades para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fec30-125">Schema and property schema files for the application.</span></span>|  
|<span data-ttu-id="fec30-126">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="fec30-126">Orchestration.odx</span></span>|<span data-ttu-id="fec30-127">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fec30-127">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="fec30-128">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="fec30-128">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="fec30-129">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="fec30-129">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="fec30-130">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="fec30-130">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="fec30-131">Crear una nueva instancia del Adaptador de BizTalk para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="fec30-131">Create a new instance of the BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
1.  <span data-ttu-id="fec30-132">Inicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fec30-132">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="fec30-133">Haga clic en **iniciar**, **programas**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fec30-133">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fec30-134">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="fec30-134">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="fec30-135">Haga clic en **adaptadores** y seleccione **New**, **adaptador...**</span><span class="sxs-lookup"><span data-stu-id="fec30-135">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="fec30-136">para mostrar la **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fec30-136">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="fec30-137">Escriba un valor para el **nombre** campo, por ejemplo **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="fec30-137">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="fec30-138">Seleccione **TIBCO Rendezvous(r)** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-138">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="fec30-139">Crear un puerto de envío de BizTalk</span><span class="sxs-lookup"><span data-stu-id="fec30-139">Create a BizTalk Send Port</span></span>  
  
1.  <span data-ttu-id="fec30-140">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="fec30-140">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="fec30-141">Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático...**</span><span class="sxs-lookup"><span data-stu-id="fec30-141">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="fec30-142">para mostrar la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fec30-142">to display the **Send Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="fec30-143">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWaySP**.</span><span class="sxs-lookup"><span data-stu-id="fec30-143">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  
  
4.  <span data-ttu-id="fec30-144">Seleccione el adaptador de TIBCO Rendezvous en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fec30-144">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fec30-145">Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO Enterprise Message System en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="fec30-145">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5.  <span data-ttu-id="fec30-146">Escriba valores para la **propiedades de remitente certificado**:</span><span class="sxs-lookup"><span data-stu-id="fec30-146">Enter values for the **Certified Sender Properties**:</span></span>  
  
    |<span data-ttu-id="fec30-147">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="fec30-147">**Property**</span></span>|<span data-ttu-id="fec30-148">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fec30-148">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="fec30-149">Nombre de archivo de contabilidad</span><span class="sxs-lookup"><span data-stu-id="fec30-149">Ledger file name</span></span>|<span data-ttu-id="fec30-150">Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.</span><span class="sxs-lookup"><span data-stu-id="fec30-150">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="fec30-151">Nombre reutilizable</span><span class="sxs-lookup"><span data-stu-id="fec30-151">Reusable name</span></span>|<span data-ttu-id="fec30-152">Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados.</span><span class="sxs-lookup"><span data-stu-id="fec30-152">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="fec30-153">El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.</span><span class="sxs-lookup"><span data-stu-id="fec30-153">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="fec30-154">Escriba valores para la **credenciales**:</span><span class="sxs-lookup"><span data-stu-id="fec30-154">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="fec30-155">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="fec30-155">**Property**</span></span>|<span data-ttu-id="fec30-156">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fec30-156">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="fec30-157">Contraseña</span><span class="sxs-lookup"><span data-stu-id="fec30-157">Password</span></span>|<span data-ttu-id="fec30-158">La contraseña para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="fec30-158">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="fec30-159">Nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="fec30-159">User name</span></span>|<span data-ttu-id="fec30-160">El nombre de usuario para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="fec30-160">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="fec30-161">Escriba valores para la **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="fec30-161">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="fec30-162">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="fec30-162">**Property**</span></span>|<span data-ttu-id="fec30-163">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fec30-163">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="fec30-164">Demonio</span><span class="sxs-lookup"><span data-stu-id="fec30-164">Daemon</span></span>|<span data-ttu-id="fec30-165">Parámetro del demonio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="fec30-165">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="fec30-166">Red</span><span class="sxs-lookup"><span data-stu-id="fec30-166">Network</span></span>|<span data-ttu-id="fec30-167">Parámetro de red del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="fec30-167">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="fec30-168">ssNoVersion</span><span class="sxs-lookup"><span data-stu-id="fec30-168">Service</span></span>|<span data-ttu-id="fec30-169">Parámetro de servicio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="fec30-169">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="fec30-170">Para obtener más información acerca de las propiedades, vea [cómo establecer propiedades de transporte de TIBCO Rendezvous](../core/how-to-set-tibco-rendezvous-transport-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fec30-170">For more information about the properties, see [How to Set TIBCO Rendezvous Transport Properties](../core/how-to-set-tibco-rendezvous-transport-properties.md).</span></span>  
  
8.  <span data-ttu-id="fec30-171">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-171">Click **OK**.</span></span>  
  
9. <span data-ttu-id="fec30-172">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-172">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
10. <span data-ttu-id="fec30-173">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fec30-173">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="create-a-file-receive-port"></a><span data-ttu-id="fec30-174">Crear un puerto de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="fec30-174">Create a file receive port</span></span>  
  
1.  <span data-ttu-id="fec30-175">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="fec30-175">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="fec30-176">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional...**  para mostrar el cuadro de diálogo Propiedades de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="fec30-176">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="fec30-177">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-file-receive-location"></a><span data-ttu-id="fec30-178">Crear una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="fec30-178">Create a file receive location</span></span>  
  
1.  <span data-ttu-id="fec30-179">Cree una carpeta para la ubicación de recepción de archivos que se debe supervisar, por ejemplo, C:\Filesource.</span><span class="sxs-lookup"><span data-stu-id="fec30-179">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  
  
2.  <span data-ttu-id="fec30-180">Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción...**</span><span class="sxs-lookup"><span data-stu-id="fec30-180">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="fec30-181">para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fec30-181">to display the **Receive Location Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="fec30-182">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRL**.</span><span class="sxs-lookup"><span data-stu-id="fec30-182">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  
  
4.  <span data-ttu-id="fec30-183">Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fec30-183">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="fec30-184">Escriba la ubicación de la carpeta que creó anteriormente para la **carpeta recepción** propiedad y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-184">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  
  
6.  <span data-ttu-id="fec30-185">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-185">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="fec30-186">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-186">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="generate-a-document-instance-from-the-schema"></a><span data-ttu-id="fec30-187">Generar una instancia de documento a partir del esquema</span><span class="sxs-lookup"><span data-stu-id="fec30-187">Generate a document instance from the schema</span></span>  
  
1.  <span data-ttu-id="fec30-188">Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fec30-188">Right-click Schema.xsd in Solution Explorer and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fec30-189">En la ventana Propiedades, haga clic en el **nombre de archivo de instancia de salida** opción bajo el **General** sección.</span><span class="sxs-lookup"><span data-stu-id="fec30-189">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  
  
3.  <span data-ttu-id="fec30-190">Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fec30-190">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  
  
4.  <span data-ttu-id="fec30-191">Especifique una carpeta y el nombre de la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="fec30-191">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fec30-192">No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="fec30-192">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  
  
5.  <span data-ttu-id="fec30-193">Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="fec30-193">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  
  
#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="fec30-194">Modificar la instancia de documento generada</span><span class="sxs-lookup"><span data-stu-id="fec30-194">Modify the generated document instance</span></span>  
  
1.  <span data-ttu-id="fec30-195">Abra la instancia de documento generada en un editor de texto, tal como el Bloc de notas, y edite el contenido de la instancia de documento para garantizar que los datos van a generar un registro único en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="fec30-195">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="fec30-196">Por ejemplo, el código siguiente muestra la primera parte del archivo de datos:</span><span class="sxs-lookup"><span data-stu-id="fec30-196">For example the code below shows the first part of the data file:</span></span>  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  <span data-ttu-id="fec30-197">Guarde la instancia de documento modificada.</span><span class="sxs-lookup"><span data-stu-id="fec30-197">Save the modified document instance.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="fec30-198">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="fec30-198">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="fec30-199">Haga clic en el **OneWaySend** del proyecto en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fec30-199">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="fec30-200">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="fec30-200">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="fec30-201">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="fec30-201">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="fec30-202">Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="fec30-202">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="fec30-203">Enlazar y dar de alta la orquestación</span><span class="sxs-lookup"><span data-stu-id="fec30-203">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="fec30-204">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="fec30-204">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="fec30-205">Haga clic en el **actualizar** botón en la barra de herramientas MMC o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="fec30-205">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="fec30-206">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fec30-206">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="fec30-207">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="fec30-207">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="fec30-208">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fec30-208">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="fec30-209">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="fec30-209">**Parameter**</span></span>|<span data-ttu-id="fec30-210">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fec30-210">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="fec30-211">Host</span><span class="sxs-lookup"><span data-stu-id="fec30-211">Host</span></span>|<span data-ttu-id="fec30-212">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="fec30-212">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="fec30-213">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="fec30-213">FileReceivePort</span></span>|<span data-ttu-id="fec30-214">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="fec30-214">TIBCORndOneWayFileRP</span></span>|  
    |<span data-ttu-id="fec30-215">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="fec30-215">TibcoRendezvousSend</span></span>|<span data-ttu-id="fec30-216">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="fec30-216">TIBCORndOneWaySP</span></span>|  
  
6.  <span data-ttu-id="fec30-217">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="fec30-217">Click OK.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="fec30-218">Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="fec30-218">Start the orchestration</span></span>  
  
-   <span data-ttu-id="fec30-219">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="fec30-219">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="fec30-220">Soltar una instancia de documento en la carpeta supervisada por la ubicación del archivo de recepción</span><span class="sxs-lookup"><span data-stu-id="fec30-220">Drop a document instance into the folder monitored by the file receive location</span></span>  
  
-   <span data-ttu-id="fec30-221">Copie la instancia de documento que se creó anteriormente en la carpeta de recepción de archivos que la aplicación supervisa.</span><span class="sxs-lookup"><span data-stu-id="fec30-221">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  
  
#### <a name="verify-that-the-tibco-system-is-updated"></a><span data-ttu-id="fec30-222">Comprobar que el sistema TICBO está actualizado</span><span class="sxs-lookup"><span data-stu-id="fec30-222">Verify that the TIBCO system is updated</span></span>  
  
-   <span data-ttu-id="fec30-223">Use la interfaz web de TIBCO para comprobar que el registro se creó a partir de los datos del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="fec30-223">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  
  
 <span data-ttu-id="fec30-224">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="fec30-224">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="fec30-225">El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fec30-225">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="fec30-226">La orquestación se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk activará una instancia de la orquestación y enviará el mensaje a la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="fec30-226">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="fec30-227">La instancia de la orquestación procesa el mensaje mediante la lógica especificada en la orquestación y vuelve a publicar el mensaje en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="fec30-227">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="fec30-228">El puerto de envío de TIBCO se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de TIBCO.</span><span class="sxs-lookup"><span data-stu-id="fec30-228">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  
  
5.  <span data-ttu-id="fec30-229">El puerto de envío entrega el mensaje a BizTalk Adapter para TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="fec30-229">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
6.  <span data-ttu-id="fec30-230">BizTalk Adapter para TIBCO Rendezvous envía el mensaje al sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="fec30-230">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec30-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="fec30-231">See Also</span></span>  
 <span data-ttu-id="fec30-232">[Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="fec30-232">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="fec30-233">[Tutoriales: Usar el adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="fec30-233">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="fec30-234">Introducción</span><span class="sxs-lookup"><span data-stu-id="fec30-234">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)