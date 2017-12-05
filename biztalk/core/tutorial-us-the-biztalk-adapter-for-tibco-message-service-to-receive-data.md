---
title: 'Tutorial: Usar el adaptador de BizTalk para TIBCO Enterprise Message Service para recibir datos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc5a63ec-1897-4c9b-b37f-cdcec151b1c9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ee9994861772be8fabe04a04e9bb30111cc1bc4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a><span data-ttu-id="a08c1-102">Tutorial: Uso del adaptador de BizTalk para TIBCO Enterprise Message Service para recuperar datos</span><span class="sxs-lookup"><span data-stu-id="a08c1-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data</span></span>
<span data-ttu-id="a08c1-103">Puede usar el adaptador de BizTalk para TIBCO Enterprise Message Service (EMS) para recibir datos de un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="a08c1-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to receive data from a TIBCO system.</span></span> <span data-ttu-id="a08c1-104">En este tutorial se describe un ejemplo de SDK que ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="a08c1-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a08c1-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a08c1-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="a08c1-106">Para el adaptador de BizTalk para TIBCO Enterprise Message Service, es necesario agregar la API de C# de TIBCO EMS, TIBCO.EMS.dll, a la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="a08c1-106">BizTalk Adapter for TIBCO Enterprise Message Service requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="a08c1-107">Para obtener más información acerca de cómo instalar el ensamblado, consulte [TIBCO Enterprise Message Service requisitos y limitaciones](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span><span class="sxs-lookup"><span data-stu-id="a08c1-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  
  
-   <span data-ttu-id="a08c1-108">Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="a08c1-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a08c1-109">What This Sample Does</span></span>  
 <span data-ttu-id="a08c1-110">Este ejemplo toma un archivo XML de una carpeta, envía el archivo a una orquestación y luego usa el adaptador de BizTalk para TIBCO Enterprise Message Service para recuperar datos de un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="a08c1-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to retrieve data from a TIBCO system.</span></span> <span data-ttu-id="a08c1-111">El resultado se escribe en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a08c1-111">The result is written to an XML file.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="a08c1-112">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="a08c1-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="a08c1-113">Este ejemplo, diseñado en Visual Studio, ilustra la funcionalidad básica que usa el adaptador de BizTalk para TIBCO Enterprise Message Service con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a08c1-113">This sample, designed in Visual Studio, illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a08c1-114">Este ejemplo supone que sabe cómo enviar un mensaje desde TIBCO para que la aplicación lo procese.</span><span class="sxs-lookup"><span data-stu-id="a08c1-114">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="a08c1-115">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a08c1-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="a08c1-116">La ubicación predeterminada para el ejemplo es</span><span class="sxs-lookup"><span data-stu-id="a08c1-116">The default location for the sample is</span></span>  
  
 <span data-ttu-id="a08c1-117">C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span><span class="sxs-lookup"><span data-stu-id="a08c1-117">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span></span>  
  
 <span data-ttu-id="a08c1-118">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="a08c1-118">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="a08c1-119">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="a08c1-119">**Runtime Project Filename**</span></span>|<span data-ttu-id="a08c1-120">**Descripción del archivo del proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="a08c1-120">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="a08c1-121">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="a08c1-121">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="a08c1-122">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="a08c1-122">OneWayReceive.sln</span></span>|<span data-ttu-id="a08c1-123">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a08c1-123">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="a08c1-124">Schema.xsd,</span><span class="sxs-lookup"><span data-stu-id="a08c1-124">Schema.xsd,</span></span>|<span data-ttu-id="a08c1-125">Archivo de esquema de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a08c1-125">Schema file for the application.</span></span>|  
|<span data-ttu-id="a08c1-126">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="a08c1-126">Orchestration.odx</span></span>|<span data-ttu-id="a08c1-127">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a08c1-127">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="a08c1-128">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="a08c1-128">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="a08c1-129">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a08c1-129">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="a08c1-130">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a08c1-130">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="a08c1-131">Crear una nueva instancia del adaptador de BizTalk para TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="a08c1-131">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  
  
1.  <span data-ttu-id="a08c1-132">Inicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a08c1-132">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a08c1-133">Haga clic en **iniciar**, **programas**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-133">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a08c1-134">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-134">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="a08c1-135">Haga clic en **adaptadores** y seleccione **New**, **adaptador** para mostrar la **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-135">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="a08c1-136">Escriba un valor para el **nombre** campo, por ejemplo **TIBCO EMS**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-136">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  
  
5.  <span data-ttu-id="a08c1-137">Seleccione **TIBCO Enterprise Message System** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-137">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-port"></a><span data-ttu-id="a08c1-138">Crear un puerto de recepción de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a08c1-138">Create a BizTalk Receive Port</span></span>  
  
1.  <span data-ttu-id="a08c1-139">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="a08c1-140">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional** para mostrar el cuadro de diálogo Propiedades de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a08c1-140">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="a08c1-141">Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-141">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-location"></a><span data-ttu-id="a08c1-142">Crear una ubicación de recepción de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a08c1-142">Create a BizTalk Receive Location</span></span>  
  
1.  <span data-ttu-id="a08c1-143">Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción** para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-143">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="a08c1-144">Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayRL**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-144">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="a08c1-145">Seleccione el adaptador TIBCO EMS en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-145">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a08c1-146">Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a08c1-146">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="a08c1-147">Escriba valores para la **definición de conexión de servidor**:</span><span class="sxs-lookup"><span data-stu-id="a08c1-147">Enter values for the **Server Connection definition**:</span></span>  
  
    |<span data-ttu-id="a08c1-148">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="a08c1-148">**Property**</span></span>|<span data-ttu-id="a08c1-149">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a08c1-149">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="a08c1-150">Destino</span><span class="sxs-lookup"><span data-stu-id="a08c1-150">Destination</span></span>|<span data-ttu-id="a08c1-151">Nombre de cola o tema de destino de servidor.</span><span class="sxs-lookup"><span data-stu-id="a08c1-151">The server destination queue or topic name.</span></span>|  
    |<span data-ttu-id="a08c1-152">Número de puerto</span><span class="sxs-lookup"><span data-stu-id="a08c1-152">Port number</span></span>|<span data-ttu-id="a08c1-153">Puerto en el que el servidor TIBCO está escuchando.</span><span class="sxs-lookup"><span data-stu-id="a08c1-153">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="a08c1-154">Valor predeterminado es 7222.</span><span class="sxs-lookup"><span data-stu-id="a08c1-154">Default value is 7222.</span></span>|  
    |<span data-ttu-id="a08c1-155">Nombre de servidor</span><span class="sxs-lookup"><span data-stu-id="a08c1-155">Server Name</span></span>|<span data-ttu-id="a08c1-156">Nombre del servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a08c1-156">The name of the TIBCO EMS server.</span></span>|  
  
5.  <span data-ttu-id="a08c1-157">Escriba valores para la **las credenciales de usuario**:</span><span class="sxs-lookup"><span data-stu-id="a08c1-157">Enter values for the **User Credentials**:</span></span>  
  
    |<span data-ttu-id="a08c1-158">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="a08c1-158">**Property**</span></span>|<span data-ttu-id="a08c1-159">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a08c1-159">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="a08c1-160">Contraseña</span><span class="sxs-lookup"><span data-stu-id="a08c1-160">Password</span></span>|<span data-ttu-id="a08c1-161">Contraseña para el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a08c1-161">The password for the TIBCO EMS server.</span></span>|  
    |<span data-ttu-id="a08c1-162">Nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="a08c1-162">User name</span></span>|<span data-ttu-id="a08c1-163">Nombre de usuario para el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a08c1-163">The user name for the TIBCO EMS server.</span></span>|  
  
     <span data-ttu-id="a08c1-164">Para obtener más información acerca de las propiedades, vea [crear TIBCO Enterprise servicio recibir controladores de mensajes](../core/creating-tibco-enterprise-message-service-receive-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="a08c1-164">For more information about the properties, see [Creating TIBCO Enterprise Message Service Receive Handlers](../core/creating-tibco-enterprise-message-service-receive-handlers.md).</span></span>  
  
6.  <span data-ttu-id="a08c1-165">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-165">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="a08c1-166">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-166">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
8.  <span data-ttu-id="a08c1-167">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-167">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="create-a-one-way-file-send-port"></a><span data-ttu-id="a08c1-168">Crear un puerto de envío de archivo unidireccional</span><span class="sxs-lookup"><span data-stu-id="a08c1-168">Create a one-way file send port</span></span>  
  
1.  <span data-ttu-id="a08c1-169">Cree una carpeta de destino que va a usar el puerto de envío; por ejemplo C:\FilesOut.</span><span class="sxs-lookup"><span data-stu-id="a08c1-169">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="a08c1-170">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-170">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="a08c1-171">Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático** para mostrar la **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-171">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="a08c1-172">Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayFileSP**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-172">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="a08c1-173">Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-173">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="a08c1-174">Para el **carpeta de destino** propiedad, escriba la ubicación de la carpeta que creó anteriormente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-174">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="a08c1-175">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-175">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="a08c1-176">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="a08c1-176">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="a08c1-177">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="a08c1-177">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="a08c1-178">Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a08c1-178">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="a08c1-179">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="a08c1-179">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="a08c1-180">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk** categoría.</span><span class="sxs-lookup"><span data-stu-id="a08c1-180">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="a08c1-181">Haga clic en el proyecto OneWayReceive en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a08c1-181">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="a08c1-182">Enlazar y dar de alta la orquestación</span><span class="sxs-lookup"><span data-stu-id="a08c1-182">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="a08c1-183">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-183">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="a08c1-184">Haga clic en el **actualizar** botón en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] barra de herramientas de consola de administración o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a08c1-184">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="a08c1-185">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-185">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="a08c1-186">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a08c1-186">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="a08c1-187">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a08c1-187">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="a08c1-188">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="a08c1-188">**Parameter**</span></span>|<span data-ttu-id="a08c1-189">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a08c1-189">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="a08c1-190">Host</span><span class="sxs-lookup"><span data-stu-id="a08c1-190">Host</span></span>|<span data-ttu-id="a08c1-191">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="a08c1-191">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="a08c1-192">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="a08c1-192">FileSendPort</span></span>|<span data-ttu-id="a08c1-193">TIBCOEMSOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="a08c1-193">TIBCOEMSOneWayFileSP</span></span>|  
    |<span data-ttu-id="a08c1-194">TibcoEMSOneWayReceiveOperation</span><span class="sxs-lookup"><span data-stu-id="a08c1-194">TibcoEMSOneWayReceiveOperation</span></span>|<span data-ttu-id="a08c1-195">TIBCOEMSOneWayRP</span><span class="sxs-lookup"><span data-stu-id="a08c1-195">TIBCOEMSOneWayRP</span></span>|  
  
6.  <span data-ttu-id="a08c1-196">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a08c1-196">Click **OK**.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="a08c1-197">Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="a08c1-197">Start the orchestration</span></span>  
  
-   <span data-ttu-id="a08c1-198">En el [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a08c1-198">In the [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="verify-that-the-application-receives-a-message"></a><span data-ttu-id="a08c1-199">Comprobar que la aplicación recibe un mensaje</span><span class="sxs-lookup"><span data-stu-id="a08c1-199">Verify that the application receives a message</span></span>  
  
-   <span data-ttu-id="a08c1-200">Abra la carpeta a la que el puerto de envío de archivos debe enviar elementos y compruebe que se generó un documento de salida.</span><span class="sxs-lookup"><span data-stu-id="a08c1-200">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span> <span data-ttu-id="a08c1-201">Este archivo debe contener los resultados de la consulta que el adaptador de BizTalk para TIBCO Enterprise Message Service ha procesado.</span><span class="sxs-lookup"><span data-stu-id="a08c1-201">This file should contain the results of the query that was processed by the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="a08c1-202">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="a08c1-202">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="a08c1-203">El adaptador TIBCO EMS recibe un mensaje del sistema TIBCO y lo publica en el cuadro de mensajes como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a08c1-203">The TIBCO EMS adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="a08c1-204">La orquestación se suscribe a este mensaje publicado para que el motor de mensajería de BizTalk active una instancia de la orquestación y envíe el mensaje a ésta.</span><span class="sxs-lookup"><span data-stu-id="a08c1-204">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="a08c1-205">La instancia de orquestación publica el mensaje en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a08c1-205">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="a08c1-206">El puerto de envío de archivos se suscribe a este mensaje, por lo que BizTalk envía el mensaje al adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="a08c1-206">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="a08c1-207">El adaptador de archivos escribe un mensaje que contiene el conjunto de resultados en la carpeta de salida designada.</span><span class="sxs-lookup"><span data-stu-id="a08c1-207">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08c1-208">Vea también</span><span class="sxs-lookup"><span data-stu-id="a08c1-208">See Also</span></span>  
 <span data-ttu-id="a08c1-209">[Tutorial: Usar el adaptador de BizTalk para TIBCO Enterprise Message Service para enviar datos](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="a08c1-209">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span></span>  
 <span data-ttu-id="a08c1-210">[Tutoriales: Usar el adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="a08c1-210">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="a08c1-211">Introducción</span><span class="sxs-lookup"><span data-stu-id="a08c1-211">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)