---
title: 'Tutorial: Usar el adaptador de BizTalk para TIBCO Enterprise Message Service para enviar datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1912d594-3839-4e04-bc40-93bd7cc0b309
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19cf0dee6bfc4535e627b6cfccfb0c0babaee909
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975389"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-send-data"></a><span data-ttu-id="60c75-102">Tutorial: Usar el adaptador de BizTalk para TIBCO Enterprise Message Service para enviar datos</span><span class="sxs-lookup"><span data-stu-id="60c75-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data</span></span>
<span data-ttu-id="60c75-103">El adaptador de BizTalk para TIBCO Enterprise Message Service (EMS) se puede usar para enviar datos a un sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="60c75-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to send data to a TIBCO system.</span></span> <span data-ttu-id="60c75-104">En este tutorial se describe un ejemplo de SDK que ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="60c75-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="60c75-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="60c75-105">Prerequisites</span></span>  

- <span data-ttu-id="60c75-106">El adaptador de BizTalk para TIBCO EMS requiere que se agregue la API TIBCO EMS C#, TIBCO.EMS.dll, a la memoria caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="60c75-106">BizTalk Adapter for TIBCO EMS requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="60c75-107">Para obtener más información acerca de cómo instalar el ensamblado, vea [TIBCO Enterprise Message Service requisitos y limitaciones](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span><span class="sxs-lookup"><span data-stu-id="60c75-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  

- <span data-ttu-id="60c75-108">Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="60c75-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="60c75-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="60c75-109">What This Sample Does</span></span>  
 <span data-ttu-id="60c75-110">Este ejemplo recoge un archivo XML de una carpeta de archivos, lo envía a la orquestación y, a continuación, usa el adaptador de BizTalk para TIBCO Enterprise Message Service para crear un registro en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="60c75-110">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to create a record in the TIBCO system.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="60c75-111">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="60c75-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="60c75-112">Este ejemplo, diseñado en Visual Studio, muestra la funcionalidad básica, el adaptador de BizTalk para TIBCO Enterprise Message Service con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="60c75-112">This sample, designed in Visual Studio, illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="60c75-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="60c75-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="60c75-114">La ubicación predeterminada para el ejemplo es</span><span class="sxs-lookup"><span data-stu-id="60c75-114">The default location for the sample is</span></span>  

 <span data-ttu-id="60c75-115">C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span><span class="sxs-lookup"><span data-stu-id="60c75-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span></span>  

 <span data-ttu-id="60c75-116">En la tabla siguiente se enumeran y describen los archivos del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="60c75-116">The following table lists and describes the files in the sample.</span></span>  

|<span data-ttu-id="60c75-117">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="60c75-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="60c75-118">**Descripción del archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="60c75-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="60c75-119">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="60c75-119">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="60c75-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="60c75-120">OneWaySend.sln</span></span>|<span data-ttu-id="60c75-121">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="60c75-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="60c75-122">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="60c75-122">Schema.xsd</span></span>|<span data-ttu-id="60c75-123">Archivo de esquema de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="60c75-123">Schema file for the application.</span></span>|  
|<span data-ttu-id="60c75-124">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="60c75-124">Orchestration.odx</span></span>|<span data-ttu-id="60c75-125">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="60c75-125">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="60c75-126">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="60c75-126">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="60c75-127">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="60c75-127">The strong naming key file.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="60c75-128">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="60c75-128">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="60c75-129">Crear una nueva instancia del adaptador de BizTalk para TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="60c75-129">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  

1. <span data-ttu-id="60c75-130">Inicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60c75-130">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="60c75-131">Haga clic en **iniciar**, **todos los programas**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="60c75-131">Click **Start**, **All Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="60c75-132">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="60c75-132">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="60c75-133">Haga clic en **adaptadores** y apuntar a **New**, **adaptador** para mostrar el **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60c75-133">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="60c75-134">Escriba un valor para el **nombre** campo, por ejemplo **TIBCO EMS**.</span><span class="sxs-lookup"><span data-stu-id="60c75-134">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  

5. <span data-ttu-id="60c75-135">Seleccione **TIBCO Enterprise Message System** en la lista de adaptadores disponibles en el **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-135">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="60c75-136">Crear un puerto de envío de BizTalk</span><span class="sxs-lookup"><span data-stu-id="60c75-136">Create a BizTalk Send Port</span></span>  

1. <span data-ttu-id="60c75-137">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="60c75-137">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="60c75-138">Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío unidireccional estático** para mostrar el **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60c75-138">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="60c75-139">Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWaySP**.</span><span class="sxs-lookup"><span data-stu-id="60c75-139">Enter a value for the **Name** field, for example **TIBCOEMSOneWaySP**.</span></span>  

4. <span data-ttu-id="60c75-140">Seleccione el adaptador TIBCO EMS en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60c75-140">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="60c75-141">Este valor es el nombre que se especificó al crear el adaptador de TIBCO Enterprise Message System en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60c75-141">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

5. <span data-ttu-id="60c75-142">Escriba valores para el **definición de la conexión de servidor**:</span><span class="sxs-lookup"><span data-stu-id="60c75-142">Enter values for the **Server Connection definition**:</span></span>  


   | <span data-ttu-id="60c75-143">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="60c75-143">**Property**</span></span> |                                <span data-ttu-id="60c75-144">**Value**</span><span class="sxs-lookup"><span data-stu-id="60c75-144">**Value**</span></span>                                |
   |--------------|-------------------------------------------------------------------------|
   | <span data-ttu-id="60c75-145">Destino</span><span class="sxs-lookup"><span data-stu-id="60c75-145">Destination</span></span>  |               <span data-ttu-id="60c75-146">Nombre de cola o tema de destino de servidor.</span><span class="sxs-lookup"><span data-stu-id="60c75-146">The server destination queue or topic name.</span></span>               |
   | <span data-ttu-id="60c75-147">Número de puerto</span><span class="sxs-lookup"><span data-stu-id="60c75-147">Port number</span></span>  | <span data-ttu-id="60c75-148">Puerto en el que el servidor TIBCO está escuchando.</span><span class="sxs-lookup"><span data-stu-id="60c75-148">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="60c75-149">Valor predeterminado es 7222.</span><span class="sxs-lookup"><span data-stu-id="60c75-149">Default value is 7222.</span></span> |
   | <span data-ttu-id="60c75-150">Nombre del servidor</span><span class="sxs-lookup"><span data-stu-id="60c75-150">Server Name</span></span>  |                    <span data-ttu-id="60c75-151">Nombre del servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="60c75-151">The name of the TIBCO EMS server.</span></span>                    |


6. <span data-ttu-id="60c75-152">Escriba valores para el **las credenciales de usuario**:</span><span class="sxs-lookup"><span data-stu-id="60c75-152">Enter values for the **User Credentials**:</span></span>  

   |<span data-ttu-id="60c75-153">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="60c75-153">**Property**</span></span>|<span data-ttu-id="60c75-154">**Value**</span><span class="sxs-lookup"><span data-stu-id="60c75-154">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="60c75-155">Contraseña</span><span class="sxs-lookup"><span data-stu-id="60c75-155">Password</span></span>|<span data-ttu-id="60c75-156">Contraseña para el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="60c75-156">The password for the TIBCO EMS server.</span></span>|  
   |<span data-ttu-id="60c75-157">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="60c75-157">User name</span></span>|<span data-ttu-id="60c75-158">Nombre de usuario para el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="60c75-158">The user name for the TIBCO EMS server.</span></span>|  

    <span data-ttu-id="60c75-159">Para obtener más información acerca de las propiedades, vea [crear controladores TIBCO Enterprise Message Service envía](../core/creating-tibco-enterprise-message-service-send-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="60c75-159">For more information about the properties, see [Creating  TIBCO Enterprise Message Service Send Handlers](../core/creating-tibco-enterprise-message-service-send-handlers.md).</span></span>  

7. <span data-ttu-id="60c75-160">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-160">Click **OK**.</span></span>  

8. <span data-ttu-id="60c75-161">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-161">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

9. <span data-ttu-id="60c75-162">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="60c75-162">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="60c75-163">Crear un puerto de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="60c75-163">Create a file receive port</span></span>  

1. <span data-ttu-id="60c75-164">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="60c75-164">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="60c75-165">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional** para mostrar el cuadro de diálogo Propiedades de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="60c75-165">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="60c75-166">Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayFileRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-166">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="60c75-167">Crear una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="60c75-167">Create a file receive location</span></span>  

1.  <span data-ttu-id="60c75-168">Cree una carpeta para la ubicación de recepción de archivos que se debe supervisar, por ejemplo, C:\Filesource.</span><span class="sxs-lookup"><span data-stu-id="60c75-168">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="60c75-169">Con el botón secundario del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción** para mostrar el **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60c75-169">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="60c75-170">Escriba un valor para el **nombre** campo, por ejemplo **TIBCOEMSOneWayFileRL**.</span><span class="sxs-lookup"><span data-stu-id="60c75-170">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="60c75-171">Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60c75-171">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="60c75-172">Escriba la ubicación de la carpeta que creó anteriormente para la **carpetas de recepción** propiedad y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-172">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="60c75-173">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-173">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="60c75-174">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-174">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="60c75-175">Generar una instancia de documento desde el esquema de adaptador</span><span class="sxs-lookup"><span data-stu-id="60c75-175">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="60c75-176">Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="60c75-176">Right-click Schema.xsd in Solution Explorer and click **Properties**.</span></span>  

2.  <span data-ttu-id="60c75-177">En la ventana Propiedades, haga clic para seleccionar el **nombre de archivo de instancia de salida** opción bajo el **General** categoría.</span><span class="sxs-lookup"><span data-stu-id="60c75-177">In the Properties window, click to select the **Output Instance Filename** option under the **General** category.</span></span>  

3.  <span data-ttu-id="60c75-178">Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60c75-178">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

4.  <span data-ttu-id="60c75-179">Especifique una carpeta y un nombre para la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="60c75-179">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="60c75-180">No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="60c75-180">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

5.  <span data-ttu-id="60c75-181">Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="60c75-181">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="60c75-182">Modificar la instancia de documento generada</span><span class="sxs-lookup"><span data-stu-id="60c75-182">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="60c75-183">Abra la instancia de documento generada en un editor de texto, tal como el Bloc de notas, y edite el contenido de la instancia de documento para garantizar que los datos van a generar un registro único en el sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="60c75-183">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="60c75-184">Por ejemplo, el código siguiente muestra la primera parte del archivo de datos:</span><span class="sxs-lookup"><span data-stu-id="60c75-184">For example the code below shows the first part of the data file:</span></span>  

    ```  
    <ns0:Root xmlns:ns0="http://TibcoEMSOne_WaySend.TibcoEMSOneWaySendSchema">  
      <Name>Punya Palit</Name>  
      <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  

2.  <span data-ttu-id="60c75-185">Guarde la instancia de documento modificada.</span><span class="sxs-lookup"><span data-stu-id="60c75-185">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="60c75-186">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="60c75-186">Build and deploy the project</span></span>  

1. <span data-ttu-id="60c75-187">Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="60c75-187">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="60c75-188">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="60c75-188">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="60c75-189">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk** categoría.</span><span class="sxs-lookup"><span data-stu-id="60c75-189">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  

4. <span data-ttu-id="60c75-190">Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **implementar** para compilar el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="60c75-190">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="60c75-191">Enlazar y dar de alta la orquestación</span><span class="sxs-lookup"><span data-stu-id="60c75-191">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="60c75-192">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="60c75-192">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="60c75-193">Haga clic en el **actualizar** botón en la barra de herramientas MMC o presione la **F5** en el teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="60c75-193">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="60c75-194">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60c75-194">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="60c75-195">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="60c75-195">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="60c75-196">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60c75-196">Specify the appropriate values for the binding options, for example:</span></span>  


   |     <span data-ttu-id="60c75-197">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="60c75-197">**Parameter**</span></span>      |        <span data-ttu-id="60c75-198">**Value**</span><span class="sxs-lookup"><span data-stu-id="60c75-198">**Value**</span></span>         |
   |------------------------|--------------------------|
   |          <span data-ttu-id="60c75-199">Host</span><span class="sxs-lookup"><span data-stu-id="60c75-199">Host</span></span>          | <span data-ttu-id="60c75-200">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="60c75-200">BizTalkServerApplication</span></span> |
   |    <span data-ttu-id="60c75-201">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="60c75-201">FileReceivePort</span></span>     |   <span data-ttu-id="60c75-202">TIBCOEMSOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="60c75-202">TIBCOEMSOneWayFileRP</span></span>   |
   | <span data-ttu-id="60c75-203">TibcoEMSOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="60c75-203">TibcoEMSOneWaySendPort</span></span> |     <span data-ttu-id="60c75-204">TIBCOEMSOneWaySP</span><span class="sxs-lookup"><span data-stu-id="60c75-204">TIBCOEMSOneWaySP</span></span>     |


6. <span data-ttu-id="60c75-205">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="60c75-205">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="60c75-206">Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="60c75-206">Start the orchestration</span></span>  

- <span data-ttu-id="60c75-207">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** para dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="60c75-207">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="60c75-208">Soltar una instancia de documento en la carpeta supervisada por la ubicación del archivo de recepción</span><span class="sxs-lookup"><span data-stu-id="60c75-208">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="60c75-209">Copie la instancia de documento que se creó anteriormente en la carpeta de recepción de archivos que la aplicación supervisa.</span><span class="sxs-lookup"><span data-stu-id="60c75-209">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  

#### <a name="verify-that-the-tibco-system-is-updated"></a><span data-ttu-id="60c75-210">Comprobar que el sistema TICBO está actualizado</span><span class="sxs-lookup"><span data-stu-id="60c75-210">Verify that the TIBCO system is updated</span></span>  

- <span data-ttu-id="60c75-211">Use la interfaz web de TIBCO para comprobar que el registro se creó a partir de los datos del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="60c75-211">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  

  <span data-ttu-id="60c75-212">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="60c75-212">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="60c75-213">El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="60c75-213">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="60c75-214">La orquestación se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk activará una instancia de la orquestación y enviará el mensaje a la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="60c75-214">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="60c75-215">La instancia de la orquestación procesa el mensaje mediante la lógica especificada en la orquestación y vuelve a publicar el mensaje en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="60c75-215">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="60c75-216">El puerto de envío de TIBCO se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de TIBCO.</span><span class="sxs-lookup"><span data-stu-id="60c75-216">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  

5.  <span data-ttu-id="60c75-217">El puerto de envío entrega el mensaje al adaptador de BizTalk para TIBCO Enterprise Message Service.</span><span class="sxs-lookup"><span data-stu-id="60c75-217">The send port hands the message to the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  

6.  <span data-ttu-id="60c75-218">El adaptador BizTalk para TIBCO Enterprise Message Service envía el mensaje al sistema TIBCO.</span><span class="sxs-lookup"><span data-stu-id="60c75-218">The BizTalk Adapter for TIBCO Enterprise Message Service sends the message to the TIBCO system.</span></span>  

## <a name="see-also"></a><span data-ttu-id="60c75-219">Vea también</span><span class="sxs-lookup"><span data-stu-id="60c75-219">See Also</span></span>  
 <span data-ttu-id="60c75-220">[Tutorial: Usar el adaptador de BizTalk para TIBCO Enterprise Message Service para recibir datos](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="60c75-220">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span></span>  
 <span data-ttu-id="60c75-221">[Tutoriales: Uso del adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="60c75-221">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="60c75-222">Introducción</span><span class="sxs-lookup"><span data-stu-id="60c75-222">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)