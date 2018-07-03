---
title: 'Tutorial: Usar el adaptador de BizTalk para PeopleSoft Enterprise para escribir datos en PeopleSoft Enterprise | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 837dd4db-576d-41c1-9fe8-e1e46861270b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9663512bf84fefc56b8db0050cbed7ffa3997780
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012309"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-write-data-to-peoplesoft-enterprise"></a><span data-ttu-id="2d26b-102">Tutorial: Usar el adaptador de BizTalk para PeopleSoft Enterprise para escribir datos en PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="2d26b-102">Tutorial: Using the BizTalk Adapter for PeopleSoft Enterprise to Write Data to PeopleSoft Enterprise</span></span>
<span data-ttu-id="2d26b-103">El adaptador de BizTalk para PeopleSoft Enterprise se puede usar para escribir datos en un sistema PeopleSoft con información recibida de un socio comercial o de una aplicación interna.</span><span class="sxs-lookup"><span data-stu-id="2d26b-103">The BizTalk Adapter for PeopleSoft Enterprise can be used to write data to a PeopleSoft System with information received from a trading partner or internal application.</span></span> <span data-ttu-id="2d26b-104">En este tutorial se describe un ejemplo de SDK que muestra esta función.</span><span class="sxs-lookup"><span data-stu-id="2d26b-104">This walkthrough describes an SDK sample that illustrates this functionality.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="2d26b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2d26b-105">Prerequisites</span></span>  

- <span data-ttu-id="2d26b-106">La plataforma Java 2 debe estar instalada en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se esté ejecutando el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d26b-106">The Java 2 Platform must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- <span data-ttu-id="2d26b-107">El archivo JAR de PeopleSoft Java objeto adaptador, **psjoa.jar** se deben copiar en una carpeta que sea accesible para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecuta el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d26b-107">The PeopleSoft Java Object Adapter JAR file, **psjoa.jar** should be copied to a folder that is accessible to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- <span data-ttu-id="2d26b-108">Para crear e implementar el ejemplo, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debe instalarse en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se esté ejecutando el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d26b-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="2d26b-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d26b-109">What This Sample Does</span></span>  
 <span data-ttu-id="2d26b-110">En este ejemplo, se selecciona un archivo XML de una carpeta, se envía a una orquestación y, a continuación se usa el adaptador de BizTalk para PeopleSoft Enterprise para crear un registro en el sistema PeopleSoft a partir de los datos del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2d26b-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for PeopleSoft Enterprise to create a record in the PeopleSoft system from the data in the XML file.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="2d26b-111">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="2d26b-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="2d26b-112">Este ejemplo se ha diseñado en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se ha creado para mostrar las funciones básicas relacionadas con el uso del adaptador de BizTalk para PeopleSoft Enterprise con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2d26b-112">This sample was designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and was created to illustrate basic functionality using the BizTalk Adapter for PeopleSoft Enterprise with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="2d26b-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d26b-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="2d26b-114">El ejemplo se encuentra en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="2d26b-114">The sample is located in the following folder:</span></span>  

 <span data-ttu-id="2d26b-115">\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span><span class="sxs-lookup"><span data-stu-id="2d26b-115">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span></span>  

 <span data-ttu-id="2d26b-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="2d26b-116">The following table shows the files in this sample and describes their purpose.</span></span>  


|                               <span data-ttu-id="2d26b-117">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="2d26b-117">**Runtime Project Filename**</span></span>                                |                                                                                                                                                                           <span data-ttu-id="2d26b-118">**Descripción del archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="2d26b-118">**Runtime Project File Description**</span></span>                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="2d26b-119">OneWaySend.btproj,</span><span class="sxs-lookup"><span data-stu-id="2d26b-119">OneWaySend.btproj,</span></span><br /><br /> <span data-ttu-id="2d26b-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="2d26b-120">OneWaySend.sln</span></span>                       |                                                                                                                                                                      <span data-ttu-id="2d26b-121">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d26b-121">Project and solution files for the application.</span></span>                                                                                                                                                                      |
| <span data-ttu-id="2d26b-122">LOCATIONService.xsd,</span><span class="sxs-lookup"><span data-stu-id="2d26b-122">LOCATIONService.xsd,</span></span><br /><br /> <span data-ttu-id="2d26b-123">LOCATIONService_1.xsd,</span><span class="sxs-lookup"><span data-stu-id="2d26b-123">LOCATIONService_1.xsd,</span></span><br /><br /> <span data-ttu-id="2d26b-124">LOCATIONService_2.xsd</span><span class="sxs-lookup"><span data-stu-id="2d26b-124">LOCATIONService_2.xsd</span></span> | <span data-ttu-id="2d26b-125">Archivos de esquema para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d26b-125">Schema files for the application.</span></span> <span data-ttu-id="2d26b-126">**Nota:** los archivos de esquema de adaptador en el proyecto se crearon originalmente con el **Asistente para agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-126">**Note:**  The adapter schema files in the project were originally created using the **Add Adapter Metadata Wizard**.</span></span> <span data-ttu-id="2d26b-127">Para obtener más información sobre el Asistente para agregar metadatos de adaptador, vea el tema "Cómo agregar metadatos del adaptador a un proyecto de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d26b-127">For more information on the Add Adapter Metadata Wizard see the topic "How to Add Adapter Metadata to a BizTalk Project" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span> |
|                                 <span data-ttu-id="2d26b-128">PeopleSoftOneWaySend.odx</span><span class="sxs-lookup"><span data-stu-id="2d26b-128">PeopleSoftOneWaySend.odx</span></span>                                  |                                                                                                                                                                        <span data-ttu-id="2d26b-129">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d26b-129">The orchestration used by the application.</span></span>                                                                                                                                                                         |
|                                 <span data-ttu-id="2d26b-130">PeopleSoftOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="2d26b-130">PeopleSoftOneWaySend.snk</span></span>                                  |                                                                                                                                                                                <span data-ttu-id="2d26b-131">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="2d26b-131">The strong naming key file.</span></span>                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="2d26b-132">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d26b-132">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a><span data-ttu-id="2d26b-133">Crear una nueva instancia del adaptador de PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="2d26b-133">Create a new instance of the PeopleSoft Enterprise adapter</span></span>  

1. <span data-ttu-id="2d26b-134">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2d26b-134">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="2d26b-135">Haga clic en **iniciar**, **todos los programas**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-135">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="2d26b-136">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-136">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="2d26b-137">Haga clic en **adaptadores** y apuntar a **New**, **adaptador...**</span><span class="sxs-lookup"><span data-stu-id="2d26b-137">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="2d26b-138">para mostrar el **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-138">to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="2d26b-139">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoft**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-139">Enter a value for the **Name** field, for example **PeopleSoft**.</span></span>  

5. <span data-ttu-id="2d26b-140">Seleccione **PeopleSoft Enterprise (r)** en la lista de adaptadores disponibles en el **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-140">Select **PeopleSoft Enterprise(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="2d26b-141">Crear un puerto de envío de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2d26b-141">Create a BizTalk Send Port</span></span>  

1. <span data-ttu-id="2d26b-142">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-142">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="2d26b-143">Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío unidireccional estático** para mostrar el **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-143">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="2d26b-144">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftOneWaySP**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-144">Enter a value for the **Name** field, for example **PeopleSoftOneWaySP**.</span></span>  

4. <span data-ttu-id="2d26b-145">Seleccione el adaptador de PeopleSoft en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte**cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-145">Select the PeopleSoft adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2d26b-146">Este valor es el nombre que se especificó cuando se creó el adaptador PeopleSoft Enterprise en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d26b-146">This value is the name that was specified when the PeopleSoft Enterprise adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

5. <span data-ttu-id="2d26b-147">Escriba los siguientes valores para el **propiedades de adaptador necesarias**:</span><span class="sxs-lookup"><span data-stu-id="2d26b-147">Enter the following values for the **Adapter Required Properties**:</span></span>  


   |       <span data-ttu-id="2d26b-148">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="2d26b-148">**Property**</span></span>       |                                                                                                                                        <span data-ttu-id="2d26b-149">**Value**</span><span class="sxs-lookup"><span data-stu-id="2d26b-149">**Value**</span></span>                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="2d26b-150">Ruta de acceso de servidor de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2d26b-150">Application server path</span></span>  | <span data-ttu-id="2d26b-151">Equipo y ubicación de puerto de PeopleSoft Server, por ejemplo, //PSServer:8888.</span><span class="sxs-lookup"><span data-stu-id="2d26b-151">PeopleSoft Server's machine and port location, for example //PSServer:8888.</span></span> <span data-ttu-id="2d26b-152">**Nota:** si no especifica un número de puerto, se usa el puerto predeterminado 9000 por lo que en el ejemplo anterior puede escribir el valor de //PSServer si PeopleSoft Server usa el valor de puerto predeterminado 9000.</span><span class="sxs-lookup"><span data-stu-id="2d26b-152">**Note:**  If you do not specify a port number, the default port of 9000 is used so in the example above you could enter a value of //PSServer if the PeopleSoft Server uses the default port value of 9000.</span></span> |
   |        <span data-ttu-id="2d26b-153">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="2d26b-153">JAVA_HOME</span></span>         |                                                                                          <span data-ttu-id="2d26b-154">Ruta de acceso para el directorio principal asociado a los archivos SDK de la plataforma Java 2, por ejemplo, C:\j2sdk1.4.2_08</span><span class="sxs-lookup"><span data-stu-id="2d26b-154">Path to the home directory associated with the Java 2 Platform SDK files, for example C:\j2sdk1.4.2_08</span></span>                                                                                          |
   |         <span data-ttu-id="2d26b-155">Contraseña</span><span class="sxs-lookup"><span data-stu-id="2d26b-155">Password</span></span>         |                                                                                                                 <span data-ttu-id="2d26b-156">Contraseña usada al conectar con el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="2d26b-156">Password used when connecting to the PeopleSoft system.</span></span>                                                                                                                  |
   | <span data-ttu-id="2d26b-157">Archivos JAR de PeopleSoft 8.x</span><span class="sxs-lookup"><span data-stu-id="2d26b-157">PeopleSoft 8.x JAR files</span></span> |                                                                                          <span data-ttu-id="2d26b-158">Ubicación del archivo JAR de PeopleSoft Java objeto adaptador **psjoa.jar**, por ejemplo, C:\JARS\psjoa.jar.</span><span class="sxs-lookup"><span data-stu-id="2d26b-158">Location of the PeopleSoft Java Object Adapter JAR file, **psjoa.jar**, for example C:\JARS\psjoa.jar.</span></span>                                                                                          |
   |        <span data-ttu-id="2d26b-159">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="2d26b-159">User name</span></span>         |                                                                                                                    <span data-ttu-id="2d26b-160">Nombre de usuario para conectar con el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="2d26b-160">Username for connecting to the PeopleSoft system.</span></span>                                                                                                                     |


6. <span data-ttu-id="2d26b-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-161">Click **OK**.</span></span>  

7. <span data-ttu-id="2d26b-162">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-162">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="2d26b-163">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="2d26b-163">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="2d26b-164">Crear un puerto de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="2d26b-164">Create a file receive port</span></span>  

1. <span data-ttu-id="2d26b-165">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-165">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="2d26b-166">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional** para mostrar el cuadro de diálogo Propiedades de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2d26b-166">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="2d26b-167">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftOneWayFileRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-167">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="2d26b-168">Crear una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="2d26b-168">Create a file receive location</span></span>  

1.  <span data-ttu-id="2d26b-169">Cree una carpeta para que la supervise la ubicación de recepción del archivo, por ejemplo C:\Filesource.</span><span class="sxs-lookup"><span data-stu-id="2d26b-169">Create a folder to be monitored by the file receive location, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="2d26b-170">Con el botón secundario del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción** para mostrar el **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-170">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="2d26b-171">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftOneWayFileRL**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-171">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="2d26b-172">Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-172">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="2d26b-173">Escriba la ubicación de la carpeta que creó anteriormente para la **carpetas de recepción** propiedad y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-173">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="2d26b-174">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-174">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="2d26b-175">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-175">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a><span data-ttu-id="2d26b-176">Modificar la propiedad del espacio de nombres de destino del esquema del adaptador</span><span class="sxs-lookup"><span data-stu-id="2d26b-176">Modify the Adapter schema target namespace property</span></span>  

1. <span data-ttu-id="2d26b-177">Inicie [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y abra OneWaySend.sln.</span><span class="sxs-lookup"><span data-stu-id="2d26b-177">Launch [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and open OneWaySend.sln.</span></span> <span data-ttu-id="2d26b-178">Haga clic en **archivo**, **abierto**, **proyecto o solución...**</span><span class="sxs-lookup"><span data-stu-id="2d26b-178">Click **File**, **Open**, **Project/Solution…**</span></span> <span data-ttu-id="2d26b-179">para mostrar el **Abrir proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-179">to display the **Open Project** dialog.</span></span>  

2. <span data-ttu-id="2d26b-180">Busque el archivo OneWaySend.sln, haga clic en este archivo para seleccionarlo y haga clic en **abrir** para abrir la solución que contiene el proyecto de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-180">Browse to the OneWaySend.sln file, click to select this file and click **Open** to open the solution that contains the sample project.</span></span>  

3. <span data-ttu-id="2d26b-181">Haga clic en el **vista** menú y seleccione **el Explorador de soluciones** para mostrar el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="2d26b-181">Click the **View** menu and select **Solution Explorer** to display the Solution Explorer.</span></span>  

4. <span data-ttu-id="2d26b-182">Haga doble clic en el archivo LOCATIONService_1.xsd en el Explorador de soluciones para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-182">Double-click the LOCATIONService_1.xsd file in the Solution Explorer to open it.</span></span>  

5. <span data-ttu-id="2d26b-183">Haga clic en el **esquema** nodo de LOCATIONService_1.xsd y seleccione el **propiedades** opción de menú para mostrar las propiedades para el esquema.</span><span class="sxs-lookup"><span data-stu-id="2d26b-183">Right-click the **Schema** node of LOCATIONService_1.xsd and select the **Properties** menu option to display the properties for the schema.</span></span>  

6. <span data-ttu-id="2d26b-184">Editar el **Target Namespace** propiedad que se va a usar los valores adecuados para el nombre del adaptador, por ejemplo el **Target Namespace** propiedad debe indicar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d26b-184">Edit the **Target Namespace** property to use the appropriate values for the adapter name, for example the **Target Namespace** property should read as follows:</span></span>  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    <span data-ttu-id="2d26b-185">Donde *PeopleSoft* es el nombre del adaptador de PeopleSoft, tal como se ve en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2d26b-185">Where *PeopleSoft* is the name of the PeopleSoft adapter as viewed in the BizTalk Administration Console.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="2d26b-186">Si el valor configurado para **Target Namespace** no coincide con el espacio de nombres especificado en la instancia de documento de entrada, a continuación, se producirá un error de enrutamiento cuando la instancia de documento de entrada se procesa mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d26b-186">If the configured value for **Target Namespace** does not match the namespace specified in the input document instance then a routing failure will occur when the input document instance is processed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="2d26b-187">Generar una instancia de documento desde el esquema de adaptador</span><span class="sxs-lookup"><span data-stu-id="2d26b-187">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="2d26b-188">Haga doble clic en **LOCATIONService_1.xsd** en el Explorador de soluciones para abrir el archivo en el Editor de esquemas.</span><span class="sxs-lookup"><span data-stu-id="2d26b-188">Double-click **LOCATIONService_1.xsd** in the Solution Explorer to open the file in the Schema Editor.</span></span>  

2.  <span data-ttu-id="2d26b-189">Haga clic en el **\<esquema\>** nodo en el Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades del nodo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-189">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  

3.  <span data-ttu-id="2d26b-190">Seleccione **CreateEx** en la lista de nodos disponibles en el **referencia raíz** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d26b-190">Select **CreateEx** from the list of available nodes in the **Root Reference** dropdown box.</span></span> <span data-ttu-id="2d26b-191">Esto debe hacerse para que cuando se genera una instancia de documento de ejemplo se generará desde el **CreateEx** nodo del esquema.</span><span class="sxs-lookup"><span data-stu-id="2d26b-191">This should be done so that when you generate a sample document instance it will be generated from the **CreateEx** node of the schema.</span></span>  

4.  <span data-ttu-id="2d26b-192">Haga clic en LOCATIONService_1.xsd en el Explorador de soluciones y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-192">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Properties**.</span></span>  

5.  <span data-ttu-id="2d26b-193">En la ventana Propiedades, haga clic para seleccionar el **nombre de archivo de instancia de salida** opción bajo el **General** sección.</span><span class="sxs-lookup"><span data-stu-id="2d26b-193">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  

6.  <span data-ttu-id="2d26b-194">Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-194">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

7.  <span data-ttu-id="2d26b-195">Especifique una carpeta y un nombre para la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-195">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2d26b-196">No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="2d26b-196">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

8.  <span data-ttu-id="2d26b-197">Haga clic en LOCATIONService_1.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="2d26b-197">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

9. <span data-ttu-id="2d26b-198">Haga clic en el **\<esquema\>** nodo en el Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades del nodo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-198">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  

10. <span data-ttu-id="2d26b-199">Seleccione (**predeterminado)** en la lista de nodos disponibles en el **referencia raíz** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2d26b-199">Select (**Default)** from the list of available nodes in the **Root Reference** dropdown box.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="2d26b-200">Modificar la instancia de documento generada</span><span class="sxs-lookup"><span data-stu-id="2d26b-200">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="2d26b-201">Abra la instancia de documento generada en un editor de texto, como por ejemplo el Bloc de notas, y edite el contenido de la instancia de documento para asegurarse de que los datos de estos campos generen un registro único en el sistema PeopleSoft, por ejemplo, en el archivo XML a continuación se describen los campos de un registro que definen una ubicación:</span><span class="sxs-lookup"><span data-stu-id="2d26b-201">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data in these fields will generate a unique record in the PeopleSoft system, for example the XML file below describes the fields in a record that define a location:</span></span>  

    ```  
    <ns0:CreateEx xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>9991</ns0:LOCATION>  
      <ns0:interactiveMode>true</ns0:interactiveMode>  
       <ns0:properties>  
        <ns0:LOCATION_TBL_sequence>  
          <ns0:LOCATION_TBL>  
            <ns0:COUNTRY>USA</ns0:COUNTRY>  
            <ns0:DESCR>Adapter Test</ns0:DESCR>  
            <ns0:EFFDT>2006-05-31</ns0:EFFDT>  
            <ns0:EFF_STATUS>A</ns0:EFF_STATUS>  
            <ns0:SETID>SHARE</ns0:SETID>  
          </ns0:LOCATION_TBL>  
        </ns0:LOCATION_TBL_sequence>  
      </ns0:properties>  
    </ns0:CreateEx>  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="2d26b-202">En el ejemplo anterior, *PeopleSoft* es un marcador de posición para el nombre real del adaptador según se ve en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2d26b-202">In the example above, *PeopleSoft* is a placeholder for the actual name of the adapter as viewed in the BizTalk Administration Console.</span></span>  

2.  <span data-ttu-id="2d26b-203">Guarde la instancia de documento modificada.</span><span class="sxs-lookup"><span data-stu-id="2d26b-203">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="2d26b-204">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="2d26b-204">Build and deploy the project</span></span>  

1. <span data-ttu-id="2d26b-205">Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="2d26b-205">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer.</span></span>  

2. <span data-ttu-id="2d26b-206">Haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="2d26b-206">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="2d26b-207">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-207">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="2d26b-208">Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **implementar** para compilar el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="2d26b-208">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="2d26b-209">Enlazar y dar de alta la orquestación</span><span class="sxs-lookup"><span data-stu-id="2d26b-209">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="2d26b-210">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="2d26b-210">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="2d26b-211">Haga clic en el **actualizar** botón en la barra de herramientas MMC o presione la **F5** en el teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2d26b-211">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console view.</span></span>  

3. <span data-ttu-id="2d26b-212">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2d26b-212">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="2d26b-213">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2d26b-213">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="2d26b-214">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2d26b-214">Specify the appropriate values for the binding options, for example:</span></span>  


   |      <span data-ttu-id="2d26b-215">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="2d26b-215">**Parameter**</span></span>       |        <span data-ttu-id="2d26b-216">**Value**</span><span class="sxs-lookup"><span data-stu-id="2d26b-216">**Value**</span></span>         |
   |--------------------------|--------------------------|
   |           <span data-ttu-id="2d26b-217">Host</span><span class="sxs-lookup"><span data-stu-id="2d26b-217">Host</span></span>           | <span data-ttu-id="2d26b-218">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="2d26b-218">BizTalkServerApplication</span></span> |
   |     <span data-ttu-id="2d26b-219">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="2d26b-219">FileReceivePort</span></span>      |  <span data-ttu-id="2d26b-220">PeopleSoftOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="2d26b-220">PeopleSoftOneWayFileRP</span></span>  |
   | <span data-ttu-id="2d26b-221">PeopleSoftOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="2d26b-221">PeopleSoftOneWaySendPort</span></span> |    <span data-ttu-id="2d26b-222">PeopleSoftOneWaySP</span><span class="sxs-lookup"><span data-stu-id="2d26b-222">PeopleSoftOneWaySP</span></span>    |


6. <span data-ttu-id="2d26b-223">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="2d26b-223">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="2d26b-224">Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="2d26b-224">Start the orchestration</span></span>  

- <span data-ttu-id="2d26b-225">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** para dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2d26b-225">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="2d26b-226">Soltar una instancia de documento en la carpeta supervisada por la ubicación del archivo de recepción</span><span class="sxs-lookup"><span data-stu-id="2d26b-226">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="2d26b-227">Copie la instancia de documento que creó anteriormente en la carpeta que la ubicación de recepción de archivos está configurada para supervisar.</span><span class="sxs-lookup"><span data-stu-id="2d26b-227">Copy the document instance that was created earlier to the folder that the file receive location is configured to monitor.</span></span>  

#### <a name="verify-that-the-peoplesoft-system-is-updated"></a><span data-ttu-id="2d26b-228">Comprobar que se actualiza el sistema PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="2d26b-228">Verify that the PeopleSoft system is updated</span></span>  

- <span data-ttu-id="2d26b-229">Use la interfaz web de PeopleSoft para comprobar que se creó el registro a partir de los datos del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2d26b-229">Use the PeopleSoft web interface to verify that the record was created from the data in the XML file.</span></span>  

  <span data-ttu-id="2d26b-230">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="2d26b-230">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="2d26b-231">El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2d26b-231">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="2d26b-232">La orquestación se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk activará una instancia de la orquestación y enviará el mensaje a la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="2d26b-232">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="2d26b-233">La instancia de la orquestación procesa el mensaje mediante la lógica especificada en la orquestación y vuelve a publicar el mensaje en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2d26b-233">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="2d26b-234">El puerto de envío de PeopleSoft se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="2d26b-234">The PeopleSoft send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the PeopleSoft send port.</span></span>  

5.  <span data-ttu-id="2d26b-235">El puerto de envío entrega el mensaje al adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d26b-235">The send port hands the message to the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

6.  <span data-ttu-id="2d26b-236">BizTalk Adapter para PeopleSoft Enterprise invoca el método CreateEx para crear un registro mediante los datos del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2d26b-236">The BizTalk Adapter for PeopleSoft Enterprise invokes the CreateEx method to create a record using the data in the XML file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2d26b-237">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d26b-237">See Also</span></span>  
 [<span data-ttu-id="2d26b-238">Tutoriales: Uso del adaptador de BizTalk para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="2d26b-238">Tutorials: Using BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)