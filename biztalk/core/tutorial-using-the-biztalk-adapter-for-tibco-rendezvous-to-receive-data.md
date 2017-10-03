---
title: 'Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos | Documentos de Microsoft'
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
ms.openlocfilehash: de436413f10cf4882b5c4e4b21af7bac6a3234c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a><span data-ttu-id="322c5-102">Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos</span><span class="sxs-lookup"><span data-stu-id="322c5-102">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data</span></span>
<span data-ttu-id="322c5-103">Puede usar el Adaptador de BizTalk para TIBCO Rendezvous para recibir datos de un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="322c5-103">You can use the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="322c5-104">En este tutorial se describe un ejemplo de SDK que ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="322c5-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="322c5-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="322c5-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="322c5-106">Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="322c5-106">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="322c5-107">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="322c5-107">What This Sample Does</span></span>  
 <span data-ttu-id="322c5-108">Este ejemplo usa el Adaptador de BizTalk para TIBCO Rendezvous para recibir datos de un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="322c5-108">This sample uses the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="322c5-109">Una orquestación procesa el mensaje y, mediante el adaptador de archivos, escribe los datos como un archivo XML en una carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="322c5-109">An orchestration processes the message and, using the file adapter, writes the data as an XML file in a specified folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="322c5-110">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="322c5-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="322c5-111">Este ejemplo, diseñado en [!INCLUDE[vs2010](../includes/vs2010-md.md)], ilustra funciones básicas mediante el uso del adaptador de BizTalk para TIBCO Enterprise Message Service con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="322c5-111">This sample, designed in [!INCLUDE[vs2010](../includes/vs2010-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="322c5-112">Este ejemplo supone que sabe cómo enviar un mensaje desde TIBCO para que la aplicación lo procese.</span><span class="sxs-lookup"><span data-stu-id="322c5-112">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="322c5-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="322c5-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="322c5-114">La ubicación predeterminada para el ejemplo es</span><span class="sxs-lookup"><span data-stu-id="322c5-114">The default location for the sample is</span></span>  
  
 <span data-ttu-id="322c5-115">C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive</span><span class="sxs-lookup"><span data-stu-id="322c5-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive</span></span>  
  
 <span data-ttu-id="322c5-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="322c5-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="322c5-117">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="322c5-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="322c5-118">**Descripción del archivo del proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="322c5-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="322c5-119">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="322c5-119">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="322c5-120">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="322c5-120">OneWayReceive.sln</span></span>|<span data-ttu-id="322c5-121">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="322c5-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="322c5-122">PureMessage.xsd,</span><span class="sxs-lookup"><span data-stu-id="322c5-122">PureMessage.xsd,</span></span>|<span data-ttu-id="322c5-123">Archivo de esquema de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="322c5-123">Schema file for the application.</span></span>|  
|<span data-ttu-id="322c5-124">TIBCORvOWR.odx</span><span class="sxs-lookup"><span data-stu-id="322c5-124">TIBCORvOWR.odx</span></span>|<span data-ttu-id="322c5-125">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="322c5-125">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="322c5-126">TIBCORv.snk</span><span class="sxs-lookup"><span data-stu-id="322c5-126">TIBCORv.snk</span></span>|<span data-ttu-id="322c5-127">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="322c5-127">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="322c5-128">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="322c5-128">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="322c5-129">Crear una nueva instancia del Adaptador de BizTalk para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="322c5-129">Create a new instance of the BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
1.  <span data-ttu-id="322c5-130">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="322c5-130">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="322c5-131">Haga clic en **iniciar**, **todos los programas**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="322c5-131">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="322c5-132">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="322c5-132">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="322c5-133">Haga clic en **adaptadores** y seleccione **New**, **adaptador...**</span><span class="sxs-lookup"><span data-stu-id="322c5-133">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="322c5-134">para mostrar la **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="322c5-134">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="322c5-135">Escriba un valor para el **nombre** campo, por ejemplo **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="322c5-135">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="322c5-136">Seleccione **TIBCO Rendezvous(r)** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-136">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-port"></a><span data-ttu-id="322c5-137">Crear un puerto de recepción de BizTalk</span><span class="sxs-lookup"><span data-stu-id="322c5-137">Create a BizTalk Receive Port</span></span>  
  
1.  <span data-ttu-id="322c5-138">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="322c5-138">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="322c5-139">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional...**  para mostrar la **propiedades de puerto de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="322c5-139">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the **Receive Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="322c5-140">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-140">Enter a value for the **Name** field, for example **TIBCORvOneWayRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-location"></a><span data-ttu-id="322c5-141">Crear una ubicación de recepción de BizTalk</span><span class="sxs-lookup"><span data-stu-id="322c5-141">Create a BizTalk Receive Location</span></span>  
  
1.  <span data-ttu-id="322c5-142">Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción...**</span><span class="sxs-lookup"><span data-stu-id="322c5-142">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="322c5-143">para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="322c5-143">to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="322c5-144">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayRL**.</span><span class="sxs-lookup"><span data-stu-id="322c5-144">Enter a value for the **Name** field, for example **TIBCORvOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="322c5-145">Seleccione el adaptador de TIBCO Rendezvous en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="322c5-145">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="322c5-146">Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="322c5-146">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="322c5-147">Escriba un valor para el **RendezvousSubjectName** en el **AdapterRequiredProperties**.</span><span class="sxs-lookup"><span data-stu-id="322c5-147">Enter a value for the **RendezvousSubjectName** under the **AdapterRequiredProperties**.</span></span>  
  
5.  <span data-ttu-id="322c5-148">Escriba valores para la **propiedades de escucha certificadas**:</span><span class="sxs-lookup"><span data-stu-id="322c5-148">Enter values for the **Certified Listener Properties**:</span></span>  
  
    |<span data-ttu-id="322c5-149">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="322c5-149">**Property**</span></span>|<span data-ttu-id="322c5-150">**Valor**</span><span class="sxs-lookup"><span data-stu-id="322c5-150">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="322c5-151">Nombre de archivo de contabilidad</span><span class="sxs-lookup"><span data-stu-id="322c5-151">Ledger file name</span></span>|<span data-ttu-id="322c5-152">Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.</span><span class="sxs-lookup"><span data-stu-id="322c5-152">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="322c5-153">Nombre reutilizable</span><span class="sxs-lookup"><span data-stu-id="322c5-153">Reusable name</span></span>|<span data-ttu-id="322c5-154">Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados.</span><span class="sxs-lookup"><span data-stu-id="322c5-154">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="322c5-155">El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.</span><span class="sxs-lookup"><span data-stu-id="322c5-155">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="322c5-156">Escriba valores para la **credenciales**:</span><span class="sxs-lookup"><span data-stu-id="322c5-156">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="322c5-157">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="322c5-157">**Property**</span></span>|<span data-ttu-id="322c5-158">**Valor**</span><span class="sxs-lookup"><span data-stu-id="322c5-158">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="322c5-159">Contraseña</span><span class="sxs-lookup"><span data-stu-id="322c5-159">Password</span></span>|<span data-ttu-id="322c5-160">La contraseña para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="322c5-160">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="322c5-161">Nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="322c5-161">User name</span></span>|<span data-ttu-id="322c5-162">El nombre de usuario para el servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="322c5-162">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="322c5-163">Escriba valores para la **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="322c5-163">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="322c5-164">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="322c5-164">**Property**</span></span>|<span data-ttu-id="322c5-165">**Valor**</span><span class="sxs-lookup"><span data-stu-id="322c5-165">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="322c5-166">Demonio</span><span class="sxs-lookup"><span data-stu-id="322c5-166">Daemon</span></span>|<span data-ttu-id="322c5-167">Parámetro del demonio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="322c5-167">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="322c5-168">Red</span><span class="sxs-lookup"><span data-stu-id="322c5-168">Network</span></span>|<span data-ttu-id="322c5-169">Parámetro de red del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="322c5-169">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="322c5-170">ssNoVersion</span><span class="sxs-lookup"><span data-stu-id="322c5-170">Service</span></span>|<span data-ttu-id="322c5-171">Parámetro de servicio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="322c5-171">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="322c5-172">Para obtener más información acerca de las propiedades, vea [propiedades de transporte de recepción de configuración de TIBCO Rendezvous](../core/setting-tibco-rendezvous-receive-transport-properties.md).</span><span class="sxs-lookup"><span data-stu-id="322c5-172">For more information about the properties, see [Setting TIBCO Rendezvous Receive Transport Properties](../core/setting-tibco-rendezvous-receive-transport-properties.md).</span></span>  
  
8.  <span data-ttu-id="322c5-173">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="322c5-174">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-174">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
10. <span data-ttu-id="322c5-175">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-175">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="create-a-one-way-file-send-port"></a><span data-ttu-id="322c5-176">Crear un puerto de envío de archivo unidireccional</span><span class="sxs-lookup"><span data-stu-id="322c5-176">Create a one-way file send port</span></span>  
  
1.  <span data-ttu-id="322c5-177">Cree una carpeta de destino que va a usar el puerto de envío; por ejemplo C:\FilesOut.</span><span class="sxs-lookup"><span data-stu-id="322c5-177">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="322c5-178">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="322c5-178">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="322c5-179">Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático...**</span><span class="sxs-lookup"><span data-stu-id="322c5-179">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="322c5-180">para mostrar la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="322c5-180">to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="322c5-181">Escriba un valor para el **nombre** campo, por ejemplo **TIBCORvOneWayFileSP**.</span><span class="sxs-lookup"><span data-stu-id="322c5-181">Enter a value for the **Name** field, for example **TIBCORvOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="322c5-182">Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="322c5-182">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="322c5-183">Para el **carpeta de destino** propiedad, escriba la ubicación de la carpeta que creó anteriormente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-183">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="322c5-184">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-184">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="322c5-185">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="322c5-185">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="322c5-186">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="322c5-186">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="322c5-187">Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="322c5-187">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="322c5-188">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="322c5-188">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="322c5-189">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk** categoría.</span><span class="sxs-lookup"><span data-stu-id="322c5-189">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="322c5-190">Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="322c5-190">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="322c5-191">Enlazar y dar de alta la orquestación</span><span class="sxs-lookup"><span data-stu-id="322c5-191">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="322c5-192">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="322c5-192">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="322c5-193">Haga clic en el **actualizar** botón en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] barra de herramientas de consola de administración o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="322c5-193">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="322c5-194">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="322c5-194">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="322c5-195">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="322c5-195">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="322c5-196">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="322c5-196">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="322c5-197">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="322c5-197">**Parameter**</span></span>|<span data-ttu-id="322c5-198">**Valor**</span><span class="sxs-lookup"><span data-stu-id="322c5-198">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="322c5-199">Host</span><span class="sxs-lookup"><span data-stu-id="322c5-199">Host</span></span>|<span data-ttu-id="322c5-200">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="322c5-200">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="322c5-201">SendPort</span><span class="sxs-lookup"><span data-stu-id="322c5-201">SendPort</span></span>|<span data-ttu-id="322c5-202">TIBCORvOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="322c5-202">TIBCORvOneWayFileSP</span></span>|  
    |<span data-ttu-id="322c5-203">ReceivePort</span><span class="sxs-lookup"><span data-stu-id="322c5-203">ReceivePort</span></span>|<span data-ttu-id="322c5-204">TIBCORvOneWayRP</span><span class="sxs-lookup"><span data-stu-id="322c5-204">TIBCORvOneWayRP</span></span>|  
  
6.  <span data-ttu-id="322c5-205">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="322c5-205">Click **OK**.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="322c5-206">Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="322c5-206">Start the orchestration</span></span>  
  
-   <span data-ttu-id="322c5-207">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="322c5-207">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="verify-that-the-application-receives-a-message"></a><span data-ttu-id="322c5-208">Comprobar que la aplicación recibe un mensaje</span><span class="sxs-lookup"><span data-stu-id="322c5-208">Verify that the application receives a message</span></span>  
  
-   <span data-ttu-id="322c5-209">Abra la carpeta a la que el puerto de envío de archivos debe enviar elementos y compruebe que se generó un documento de salida.</span><span class="sxs-lookup"><span data-stu-id="322c5-209">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span>  
  
 <span data-ttu-id="322c5-210">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="322c5-210">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="322c5-211">El adaptador de TIBCO Rendezvous recibe un mensaje del sistema TIBCO y lo publica en el cuadro de mensajes como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="322c5-211">The TIBCO Rendezvous adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="322c5-212">La orquestación se suscribe a este mensaje publicado para que el motor de mensajería de BizTalk active una instancia de la orquestación y envíe el mensaje a ésta.</span><span class="sxs-lookup"><span data-stu-id="322c5-212">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="322c5-213">La instancia de orquestación publica el mensaje en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="322c5-213">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="322c5-214">El puerto de envío de archivos se suscribe a este mensaje, por lo que BizTalk envía el mensaje al adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="322c5-214">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="322c5-215">El adaptador de archivos escribe un mensaje que contiene el conjunto de resultados en la carpeta de salida designada.</span><span class="sxs-lookup"><span data-stu-id="322c5-215">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322c5-216">Vea también</span><span class="sxs-lookup"><span data-stu-id="322c5-216">See Also</span></span>  
 <span data-ttu-id="322c5-217">[Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para enviar datos](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="322c5-217">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span></span>  
 <span data-ttu-id="322c5-218">[Tutoriales: Usar el adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="322c5-218">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="322c5-219">Introducción</span><span class="sxs-lookup"><span data-stu-id="322c5-219">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)