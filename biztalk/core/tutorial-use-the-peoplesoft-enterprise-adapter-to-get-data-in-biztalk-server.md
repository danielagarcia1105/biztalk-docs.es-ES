---
title: 'Tutorial: Usar el adaptador de BizTalk para PeopleSoft Enterprise para recuperar datos de PeopleSoft Enterprise | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c173fa4c-911e-4fa3-813f-e8f36b0049a5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9728e642a1ad9e03e550a652757d33038cbab79d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993429"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-retrieve-data-from-peoplesoft-enterprise"></a><span data-ttu-id="a1797-102">Tutorial: Uso del adaptador de BizTalk para PeopleSoft Enterprise para recuperar datos de PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1797-102">Tutorial: Using the BizTalk Adapter for PeopleSoft Enterprise to Retrieve Data from PeopleSoft Enterprise</span></span>
<span data-ttu-id="a1797-103">El adaptador de BizTalk para PeopleSoft Enterprise se puede usar para ejecutar una consulta en un sistema PeopleSoft y devolver los resultados de la misma.</span><span class="sxs-lookup"><span data-stu-id="a1797-103">The BizTalk Adapter for PeopleSoft Enterprise can be used to execute a query against a PeopleSoft system and return the results of the query.</span></span> <span data-ttu-id="a1797-104">En este tutorial se describe un ejemplo de SDK que muestra esta función.</span><span class="sxs-lookup"><span data-stu-id="a1797-104">This walkthrough describes an SDK sample that illustrates this functionality.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="a1797-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a1797-105">Prerequisites</span></span>  

- <span data-ttu-id="a1797-106">La plataforma Java 2 debe estar instalada en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a1797-106">The Java 2 Platform must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise Geis running on.</span></span>  

- <span data-ttu-id="a1797-107">El archivo JAR de PeopleSoft Java objeto adaptador, **psjoa.jar** se deben copiar en una carpeta que sea accesible para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecuta el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a1797-107">The PeopleSoft Java Object Adapter JAR file, **psjoa.jar** should be copied to a folder that is accessible to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- <span data-ttu-id="a1797-108">Para crear e implementar el ejemplo, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debe instalarse en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se esté ejecutando el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a1797-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="a1797-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1797-109">What This Sample Does</span></span>  
 <span data-ttu-id="a1797-110">Este ejemplo toma un archivo XML de una carpeta, envía el archivo a una orquestación y, luego, usa el adaptador de BizTalk para PeopleSoft Enterprise para ejecutar una consulta en un sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="a1797-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for PeopleSoft Enterprise to execute a query against a PeopleSoft system.</span></span> <span data-ttu-id="a1797-111">El resultado de la consulta se escribe en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a1797-111">The result of the query is written to an XML file.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="a1797-112">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="a1797-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="a1797-113">Este ejemplo se ha diseñado en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se ha creado para mostrar las funciones básicas relacionadas con el uso del adaptador de BizTalk para PeopleSoft Enterprise con una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a1797-113">This sample was designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and was created to illustrate basic functionality using the BizTalk Adapter for PeopleSoft Enterprise with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="a1797-114">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1797-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="a1797-115">El ejemplo se encuentra en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="a1797-115">The sample is located in the following folder:</span></span>  

 <span data-ttu-id="a1797-116">\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend</span><span class="sxs-lookup"><span data-stu-id="a1797-116">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend</span></span>  

 <span data-ttu-id="a1797-117">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="a1797-117">The following table shows the files in this sample and describes their purpose.</span></span>  


|                               <span data-ttu-id="a1797-118">**Nombre de archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="a1797-118">**Runtime Project Filename**</span></span>                                |                                                                                                                                                                           <span data-ttu-id="a1797-119">**Descripción del archivo de proyecto en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="a1797-119">**Runtime Project File Description**</span></span>                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="a1797-120">TwoWaySend.btproj,</span><span class="sxs-lookup"><span data-stu-id="a1797-120">TwoWaySend.btproj,</span></span><br /><br /> <span data-ttu-id="a1797-121">TwoWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="a1797-121">TwoWaySend.sln</span></span>                       |                                                                                                                                                                      <span data-ttu-id="a1797-122">Archivos de proyectos y soluciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1797-122">Project and solution files for the application.</span></span>                                                                                                                                                                      |
| <span data-ttu-id="a1797-123">LOCATIONService.xsd,</span><span class="sxs-lookup"><span data-stu-id="a1797-123">LOCATIONService.xsd,</span></span><br /><br /> <span data-ttu-id="a1797-124">LOCATIONService_1.xsd,</span><span class="sxs-lookup"><span data-stu-id="a1797-124">LOCATIONService_1.xsd,</span></span><br /><br /> <span data-ttu-id="a1797-125">LOCATIONService_2.xsd</span><span class="sxs-lookup"><span data-stu-id="a1797-125">LOCATIONService_2.xsd</span></span> | <span data-ttu-id="a1797-126">Archivos de esquema para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1797-126">Schema files for the application.</span></span> <span data-ttu-id="a1797-127">**Nota:** los archivos de esquema de adaptador en el proyecto se crearon originalmente con el **Asistente para agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="a1797-127">**Note:**  The adapter schema files in the project were originally created using the **Add Adapter Metadata Wizard**.</span></span> <span data-ttu-id="a1797-128">Para obtener más información sobre el Asistente para agregar metadatos de adaptador, vea el tema "Cómo agregar metadatos del adaptador a un proyecto de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1797-128">For more information on the Add Adapter Metadata Wizard see the topic "How to Add Adapter Metadata to a BizTalk Project" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span> |
|                                 <span data-ttu-id="a1797-129">PeopleSoftTwoWaySend.odx</span><span class="sxs-lookup"><span data-stu-id="a1797-129">PeopleSoftTwoWaySend.odx</span></span>                                  |                                                                                                                                                                        <span data-ttu-id="a1797-130">La orquestación usada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1797-130">The orchestration used by the application.</span></span>                                                                                                                                                                         |
|                                 <span data-ttu-id="a1797-131">PeopleSoftTwoWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="a1797-131">PeopleSoftTwoWaySend.snk</span></span>                                  |                                                                                                                                                                                <span data-ttu-id="a1797-132">Archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a1797-132">The strong naming key file.</span></span>                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="a1797-133">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1797-133">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a><span data-ttu-id="a1797-134">Crear una nueva instancia del adaptador de PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1797-134">Create a new instance of the PeopleSoft Enterprise adapter</span></span>  

1. <span data-ttu-id="a1797-135">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a1797-135">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="a1797-136">Haga clic en **iniciar**, **programas**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a1797-136">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="a1797-137">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="a1797-137">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="a1797-138">Haga clic en **adaptadores** y apuntar a **New**, **adaptador** para mostrar el **propiedades del adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-138">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="a1797-139">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoft**.</span><span class="sxs-lookup"><span data-stu-id="a1797-139">Enter a value for the **Name** field, for example **PeopleSoft**.</span></span>  

5. <span data-ttu-id="a1797-140">Seleccione **PeopleSoft Enterprise (r)** en la lista de adaptadores disponibles en el **adaptador** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-140">Select **PeopleSoft Enterprise(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-solicit-response-biztalk-send-port"></a><span data-ttu-id="a1797-141">Crear un puerto de envío de petición-respuesta de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a1797-141">Create a Solicit-Response BizTalk Send Port</span></span>  

1. <span data-ttu-id="a1797-142">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="a1797-142">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="a1797-143">Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío de petición-respuesta estático** para mostrar el **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-143">Right-click **Send Ports** and point to **New**, **Static Solicit-Response Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="a1797-144">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWaySP**.</span><span class="sxs-lookup"><span data-stu-id="a1797-144">Enter a value for the **Name** field, for example **PeopleSoftTwoWaySP**.</span></span>  

4. <span data-ttu-id="a1797-145">Seleccione el adaptador de PeopleSoft en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte**cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-145">Select the PeopleSoft adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a1797-146">Este valor es el nombre especificado cuando se creó el adaptador de PeopleSoft Enterprise en la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a1797-146">This value is the name that was specified when the PeopleSoft Enterprise adapter was created in the Administration Console.</span></span>  

5. <span data-ttu-id="a1797-147">Escriba los siguientes valores para el **propiedades de adaptador necesarias**:</span><span class="sxs-lookup"><span data-stu-id="a1797-147">Enter the following values for the **Adapter Required Properties**:</span></span>  


   |       <span data-ttu-id="a1797-148">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="a1797-148">**Property**</span></span>       |                                                                                                                                        <span data-ttu-id="a1797-149">**Value**</span><span class="sxs-lookup"><span data-stu-id="a1797-149">**Value**</span></span>                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="a1797-150">Ruta de acceso de servidor de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a1797-150">Application server path</span></span>  | <span data-ttu-id="a1797-151">Equipo y ubicación de puerto de PeopleSoft Server, por ejemplo, //PSServer:8888.</span><span class="sxs-lookup"><span data-stu-id="a1797-151">PeopleSoft Server's machine and port location, for example //PSServer:8888.</span></span> <span data-ttu-id="a1797-152">**Nota:** si no especifica un número de puerto, se usa el puerto predeterminado 9000 por lo que en el ejemplo anterior puede escribir el valor de //PSServer si PeopleSoft Server usa el valor de puerto predeterminado 9000.</span><span class="sxs-lookup"><span data-stu-id="a1797-152">**Note:**  If you do not specify a port number, the default port of 9000 is used so in the example above you could enter a value of //PSServer if the PeopleSoft Server uses the default port value of 9000.</span></span> |
   |        <span data-ttu-id="a1797-153">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="a1797-153">JAVA_HOME</span></span>         |                                                                                          <span data-ttu-id="a1797-154">Ruta de acceso para el directorio principal asociado a los archivos SDK de la plataforma Java 2, por ejemplo, C:\j2sdk1.4.2_08</span><span class="sxs-lookup"><span data-stu-id="a1797-154">Path to the home directory associated with the Java 2 Platform SDK files, for example C:\j2sdk1.4.2_08</span></span>                                                                                          |
   |         <span data-ttu-id="a1797-155">Contraseña</span><span class="sxs-lookup"><span data-stu-id="a1797-155">Password</span></span>         |                                                                                                                 <span data-ttu-id="a1797-156">Contraseña usada al conectar con el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="a1797-156">Password used when connecting to the PeopleSoft system.</span></span>                                                                                                                  |
   | <span data-ttu-id="a1797-157">Archivos JAR de PeopleSoft 8.x</span><span class="sxs-lookup"><span data-stu-id="a1797-157">PeopleSoft 8.x JAR files</span></span> |                                                                                          <span data-ttu-id="a1797-158">Ubicación del archivo JAR de PeopleSoft Java objeto adaptador **psjoa.jar**, por ejemplo, C:\JARS\psjoa.jar.</span><span class="sxs-lookup"><span data-stu-id="a1797-158">Location of the PeopleSoft Java Object Adapter JAR file, **psjoa.jar**, for example C:\JARS\psjoa.jar.</span></span>                                                                                          |
   |        <span data-ttu-id="a1797-159">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="a1797-159">User name</span></span>         |                                                                                                                    <span data-ttu-id="a1797-160">Nombre de usuario para conectar con el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="a1797-160">Username for connecting to the PeopleSoft system.</span></span>                                                                                                                     |


6. <span data-ttu-id="a1797-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-161">Click **OK**.</span></span>  

7. <span data-ttu-id="a1797-162">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a1797-162">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown.</span></span>  

8. <span data-ttu-id="a1797-163">Seleccione el **XMLReceive** canalización en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-163">Select the **XMLReceive** pipeline from the list of pipelines available in the **Receive pipeline** dropdown and click **OK**.</span></span>  

9. <span data-ttu-id="a1797-164">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="a1797-164">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-one-way-biztalk-send-port"></a><span data-ttu-id="a1797-165">Crear un puerto de envío unidireccional de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a1797-165">Create a One-Way BizTalk Send Port</span></span>  

1. <span data-ttu-id="a1797-166">Cree la carpeta de destino que va a usar el puerto de envío, por ejemplo, C:\Files\Out.</span><span class="sxs-lookup"><span data-stu-id="a1797-166">Create a target folder to be used by the send port, for example C:\Files\Out.</span></span>  

2. <span data-ttu-id="a1797-167">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="a1797-167">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

3. <span data-ttu-id="a1797-168">Haga clic en **puertos de envío** y apuntar a **New**, **puerto de envío unidireccional estático** para mostrar el **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-168">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port** to display the **Send Port Properties** dialog.</span></span>  

4. <span data-ttu-id="a1797-169">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWayFileSP**.</span><span class="sxs-lookup"><span data-stu-id="a1797-169">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileSP**.</span></span>  

5. <span data-ttu-id="a1797-170">Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-170">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

6. <span data-ttu-id="a1797-171">Escriba la ubicación de la carpeta que creó anteriormente para la **carpeta de destino** propiedad y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-171">Enter the location of the folder that you created earlier for the **Destination Folder** property and click **OK**.</span></span>  

7. <span data-ttu-id="a1797-172">Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en el **canalización de envío** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-172">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="a1797-173">Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="a1797-173">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="a1797-174">Crear un puerto de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="a1797-174">Create a file receive port</span></span>  

1. <span data-ttu-id="a1797-175">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="a1797-175">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="a1797-176">Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional** para mostrar el cuadro de diálogo Propiedades de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a1797-176">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="a1797-177">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWayFileRP**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-177">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="a1797-178">Crear una ubicación de recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="a1797-178">Create a file receive location</span></span>  

1.  <span data-ttu-id="a1797-179">Cree la carpeta que la ubicación de recepción de archivos supervisará, por ejemplo, C:\Files\In.</span><span class="sxs-lookup"><span data-stu-id="a1797-179">Create a folder to be monitored by the file receive location, for example C:\Files\In.</span></span>  

2.  <span data-ttu-id="a1797-180">Con el botón secundario del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción** para mostrar el **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-180">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="a1797-181">Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftTwoWayFileRL**.</span><span class="sxs-lookup"><span data-stu-id="a1797-181">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileRL**.</span></span>  

4.  <span data-ttu-id="a1797-182">Seleccione **archivo** en la lista de adaptadores disponibles en el **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-182">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="a1797-183">Escriba la ubicación de la carpeta que creó anteriormente para la **carpetas de recepción** propiedad y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-183">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="a1797-184">Seleccione **XMLReceive** en la lista de canalizaciones disponibles en el **canalización de recepción** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-184">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="a1797-185">Haga clic en la ubicación de recepción y haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-185">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a><span data-ttu-id="a1797-186">Modificar la propiedad del espacio de nombres de destino del esquema del adaptador</span><span class="sxs-lookup"><span data-stu-id="a1797-186">Modify the Adapter schema target namespace property</span></span>  

1. <span data-ttu-id="a1797-187">Inicie [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y abra TwoWaySend.sln.</span><span class="sxs-lookup"><span data-stu-id="a1797-187">Launch [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and open TwoWaySend.sln.</span></span> <span data-ttu-id="a1797-188">Haga clic en **archivo**, **abierto**, **proyecto/solución** para mostrar el **Abrir proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-188">Click **File**, **Open**, **Project/Solution** to display the **Open Project** dialog.</span></span>  

2. <span data-ttu-id="a1797-189">Busque el archivo TwoWaySend.sln, haga clic en este archivo para seleccionarlo y haga clic en **abrir** para abrir la solución que contiene el proyecto de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1797-189">Browse to the TwoWaySend.sln file, click to select this file and click **Open** to open the solution that contains the sample project.</span></span>  

3. <span data-ttu-id="a1797-190">Haga clic en el **vista** menú y seleccione **el Explorador de soluciones** para mostrar el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="a1797-190">Click the **View** menu and select **Solution Explorer** to display the Solution Explorer.</span></span>  

4. <span data-ttu-id="a1797-191">Haga doble clic en el archivo LOCATIONService_1.xsd en el Explorador de soluciones para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="a1797-191">Double-click the LOCATIONService_1.xsd file in the Solution Explorer to open it.</span></span>  

5. <span data-ttu-id="a1797-192">Haga clic en el **esquema** nodo de LOCATIONService_1.xsd y seleccione el **propiedades** opción de menú para mostrar las propiedades para el esquema.</span><span class="sxs-lookup"><span data-stu-id="a1797-192">Right-click the **Schema** node of LOCATIONService_1.xsd and select the **Properties** menu option to display the properties for the schema.</span></span>  

6. <span data-ttu-id="a1797-193">Editar el **Target Namespace** propiedad que se va a usar los valores adecuados para el nombre del adaptador, por ejemplo el **Target Namespace** propiedad debe indicar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1797-193">Edit the **Target Namespace** property to use the appropriate values for the adapter name, for example the **Target Namespace** property should read as follows:</span></span>  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    <span data-ttu-id="a1797-194">Donde *PeopleSoft* es el nombre del adaptador de PeopleSoft, tal como se ve en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a1797-194">Where *PeopleSoft* is the name of the PeopleSoft adapter as viewed in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="a1797-195">Si el valor configurado para **Target Namespace** no coincide con el espacio de nombres especificado en la instancia de documento de entrada, a continuación, se producirá un error de enrutamiento cuando la instancia de documento de entrada se procesa mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1797-195">If the configured value for **Target Namespace** does not match the namespace specified in the input document instance then a routing failure will occur when the input document instance is processed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="a1797-196">Generar una instancia de documento desde el esquema de adaptador</span><span class="sxs-lookup"><span data-stu-id="a1797-196">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="a1797-197">Haga doble clic en **LOCATIONService_1.xsd** en el Explorador de soluciones para abrir el archivo en el Editor de esquemas.</span><span class="sxs-lookup"><span data-stu-id="a1797-197">Double-click **LOCATIONService_1.xsd** in Solution Explorer to open the file in Schema Editor.</span></span>  

2.  <span data-ttu-id="a1797-198">Haga clic en el **\<esquema\>** nodo Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades del nodo.</span><span class="sxs-lookup"><span data-stu-id="a1797-198">Right-click the **\<Schema\>** node in Schema Editor and click **Properties** to display properties for the node.</span></span>  

3.  <span data-ttu-id="a1797-199">Seleccione **obtener** en la lista de nodos disponibles en el **referencia raíz** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a1797-199">Select **Get** from the list of available nodes in the **Root Reference** dropdown box.</span></span> <span data-ttu-id="a1797-200">Esto debe hacerse para que cuando se genera una instancia de documento de ejemplo se generará desde el **obtener** nodo del esquema.</span><span class="sxs-lookup"><span data-stu-id="a1797-200">This should be done so that when you generate a sample document instance it will be generated from the **Get** node of the schema.</span></span>  

4.  <span data-ttu-id="a1797-201">Haga clic en **LOCATIONService_1.xsd** en el Explorador de soluciones y haga clic en **propiedades** para mostrar las propiedades en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="a1797-201">Right-click **LOCATIONService_1.xsd** in Solution Explorer and click **Properties** to display properties in the Properties window.</span></span>  

5.  <span data-ttu-id="a1797-202">En la ventana Propiedades, haga clic para seleccionar el **nombre de archivo de instancia de salida** opción.</span><span class="sxs-lookup"><span data-stu-id="a1797-202">In the Properties window, click to select the **Output Instance Filename** option.</span></span>  

6.  <span data-ttu-id="a1797-203">Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-203">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

7.  <span data-ttu-id="a1797-204">Especifique una carpeta y un nombre para la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="a1797-204">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a1797-205">No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.</span><span class="sxs-lookup"><span data-stu-id="a1797-205">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

8.  <span data-ttu-id="a1797-206">Haga clic en LOCATIONService_1.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="a1797-206">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

9. <span data-ttu-id="a1797-207">Haga clic en el **\<esquema\>** nodo Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades del nodo.</span><span class="sxs-lookup"><span data-stu-id="a1797-207">Right-click the **\<Schema\>** node in Schema Editor and click **Properties** to display the properties for the node.</span></span>  

10. <span data-ttu-id="a1797-208">Seleccione (**predeterminado)** en la lista de nodos disponibles en el **referencia raíz** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a1797-208">Select (**Default)** from the list of available nodes in the **Root Reference** dropdown box.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="a1797-209">Modificar la instancia de documento generada</span><span class="sxs-lookup"><span data-stu-id="a1797-209">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="a1797-210">Abra la instancia de documento generada en un editor de texto como el Bloc de notas y edite el contenido de la instancia de documento para asegurarse de que los datos de estos campos devolverán un registro existente:</span><span class="sxs-lookup"><span data-stu-id="a1797-210">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data in these fields will return an existing record:</span></span>  

    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
    <ns0:SETID>SHARE</ns0:SETID>  
    <ns0:LOCATION>WFKLOC</ns0:LOCATION>  
    <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="a1797-211">En el ejemplo anterior, *PeopleSoft* es un marcador de posición para el nombre real del adaptador según se ve en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a1797-211">In the example above, *PeopleSoft* is a placeholder for the actual name of the adapter as viewed in the BizTalk Administration Console.</span></span> <span data-ttu-id="a1797-212">*Recurso compartido* y *WFKLOC* son marcadores de posición para los valores usados para identificar un registro concreto en el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="a1797-212">*SHARE* and *WFKLOC* are placeholders for values used to identify a particular record in the PeopleSoft system.</span></span>  

2.  <span data-ttu-id="a1797-213">Guarde la instancia de documento modificada.</span><span class="sxs-lookup"><span data-stu-id="a1797-213">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="a1797-214">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="a1797-214">Build and deploy the project</span></span>  

1. <span data-ttu-id="a1797-215">Haga clic en el proyecto TwoWaySend en el Explorador de soluciones y haga clic en **propiedades** para mostrar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a1797-215">Right-click the TwoWaySend project in Solution Explorer and click **Properties** to display the Project Designer for the project.</span></span>  

2. <span data-ttu-id="a1797-216">Haga clic en el **implementación** ficha del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="a1797-216">Click the **Deployment** tab in the Project Designer.</span></span>  

3. <span data-ttu-id="a1797-217">Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="a1797-217">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="a1797-218">Haga clic en el proyecto TwoWaySend en el Explorador de soluciones y haga clic en **implementar** para compilar el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="a1797-218">Right-click the TwoWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="a1797-219">Enlazar y dar de alta la orquestación</span><span class="sxs-lookup"><span data-stu-id="a1797-219">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="a1797-220">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="a1797-220">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="a1797-221">Haga clic en el **actualizar** situado en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] barra de herramientas de consola de administración o presione la **F5** en el teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a1797-221">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console view.</span></span>  

3. <span data-ttu-id="a1797-222">Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a1797-222">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="a1797-223">Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a1797-223">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="a1797-224">Especifique los valores adecuados para las opciones de enlace, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a1797-224">Specify the appropriate values for the binding options, for example:</span></span>  


   |      <span data-ttu-id="a1797-225">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="a1797-225">**Parameter**</span></span>      |        <span data-ttu-id="a1797-226">**Value**</span><span class="sxs-lookup"><span data-stu-id="a1797-226">**Value**</span></span>         |
   |-------------------------|--------------------------|
   |          <span data-ttu-id="a1797-227">Host</span><span class="sxs-lookup"><span data-stu-id="a1797-227">Host</span></span>           | <span data-ttu-id="a1797-228">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="a1797-228">BizTalkServerApplication</span></span> |
   |     <span data-ttu-id="a1797-229">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="a1797-229">FileReceivePort</span></span>     |  <span data-ttu-id="a1797-230">PeopleSoftTwoWayFileRP</span><span class="sxs-lookup"><span data-stu-id="a1797-230">PeopleSoftTwoWayFileRP</span></span>  |
   | <span data-ttu-id="a1797-231">PeopleSoftTwoWaySend678</span><span class="sxs-lookup"><span data-stu-id="a1797-231">PeopleSoftTwoWaySend678</span></span> |    <span data-ttu-id="a1797-232">PeopleSoftTwoWaySP</span><span class="sxs-lookup"><span data-stu-id="a1797-232">PeopleSoftTwoWaySP</span></span>    |
   |      <span data-ttu-id="a1797-233">ResponsePort</span><span class="sxs-lookup"><span data-stu-id="a1797-233">ResponsePort</span></span>       |  <span data-ttu-id="a1797-234">PeopleSoftTwoWayFileSP</span><span class="sxs-lookup"><span data-stu-id="a1797-234">PeopleSoftTwoWayFileSP</span></span>  |


6. <span data-ttu-id="a1797-235">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="a1797-235">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="a1797-236">Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="a1797-236">Start the orchestration</span></span>  

- <span data-ttu-id="a1797-237">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** para dar de alta e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a1797-237">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="a1797-238">Soltar una instancia de documento en la carpeta supervisada por la ubicación del archivo de recepción</span><span class="sxs-lookup"><span data-stu-id="a1797-238">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="a1797-239">Copie la instancia de documento que creó anteriormente en la carpeta que la ubicación de recepción de archivos está configurada para supervisar.</span><span class="sxs-lookup"><span data-stu-id="a1797-239">Copy the document instance that was created earlier to the folder that the file receive location is configured to monitor.</span></span>  

#### <a name="verify-that-the-document-instance-was-processed-by-the-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="a1797-240">Comprobar que el adaptador de BizTalk para PeopleSoft Enterprise procesó la instancia de documento</span><span class="sxs-lookup"><span data-stu-id="a1797-240">Verify that the document instance was processed by the BizTalk Adapter for PeopleSoft Enterprise</span></span>  

- <span data-ttu-id="a1797-241">Abra la carpeta a la que el puerto de envío de archivos debe enviar elementos y compruebe que se generó un documento de salida.</span><span class="sxs-lookup"><span data-stu-id="a1797-241">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span> <span data-ttu-id="a1797-242">Este archivo debe contener los resultados de la consulta que ha procesado el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a1797-242">This file should contain the results of the query that was processed by the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

  <span data-ttu-id="a1797-243">Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:</span><span class="sxs-lookup"><span data-stu-id="a1797-243">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="a1797-244">El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a1797-244">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="a1797-245">La orquestación se suscribe a este mensaje publicado para que el motor de mensajería de BizTalk active una instancia de la orquestación y envíe el mensaje a ésta.</span><span class="sxs-lookup"><span data-stu-id="a1797-245">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="a1797-246">La instancia de orquestación publica el mensaje en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1797-246">The orchestration instance publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="a1797-247">El puerto de envío de petición-respuesta se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="a1797-247">The solicit-response send port subscribes to this published message so the BizTalk Messaging Engine sends the message to the PeopleSoft send port.</span></span>  

5.  <span data-ttu-id="a1797-248">El puerto de envío entrega el mensaje al adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a1797-248">The send port hands the message to the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

6.  <span data-ttu-id="a1797-249">El adaptador de BizTalk para PeopleSoft Enterprise ejecuta una instrucción Get en el sistema PeopleSoft usando los parámetros definidos en el archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="a1797-249">The BizTalk Adapter for PeopleSoft Enterprise executes a Get statement against the PeopleSoft system using the parameters defined in the input file.</span></span>  

7.  <span data-ttu-id="a1797-250">El adaptador de BizTalk para PeopleSoft Enterprise devuelve los resultados de la instrucción Get como mensaje de respuesta para el puerto de petición-respuesta de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a1797-250">The BizTalk Adapter for PeopleSoft Enterprise returns the results of the Get statement as the response message for the solicit-response port in the orchestration.</span></span>  

8.  <span data-ttu-id="a1797-251">La orquestación publica el conjunto de resultados en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1797-251">The orchestration publishes the result set to the MessageBox.</span></span>  

9. <span data-ttu-id="a1797-252">El puerto de envío de archivos se suscribe a este mensaje, por lo que BizTalk envía el mensaje al adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="a1797-252">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  

10. <span data-ttu-id="a1797-253">El adaptador de archivos escribe un mensaje que contiene el conjunto de resultados en la carpeta de salida designada.</span><span class="sxs-lookup"><span data-stu-id="a1797-253">The File adapter writes the message containing the result set to the designated output folder.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a1797-254">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1797-254">See Also</span></span>  
 [<span data-ttu-id="a1797-255">Tutoriales: Uso del adaptador de BizTalk para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1797-255">Tutorials: Using BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)