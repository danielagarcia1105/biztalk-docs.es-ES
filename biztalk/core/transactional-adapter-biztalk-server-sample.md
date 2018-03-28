---
title: Adaptador transaccional (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31a13377-cc89-4763-ad1b-508a16fc9708
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f934857103952a035159cc08678c8ce8c8e51a56
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="transactional-adapter-biztalk-server-sample"></a><span data-ttu-id="85127-102">Adaptador transaccional (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="85127-102">Transactional Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="85127-103">En el ejemplo de adaptador transaccional se muestra cómo crear y usar una transacción explícita de Microsoft DTC (Coordinador de transacciones distribuidas) para una base de datos durante el procesamiento de un mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85127-103">The Transactional Adapter sample demonstrates how to create and use an explicit Microsoft Distributed Transaction Coordinator (MSDTC) transaction against a database during processing of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="85127-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="85127-104">What This Sample Does</span></span>  
 <span data-ttu-id="85127-105">Este ejemplo contiene un adaptador de recepción que ejecuta una instrucción SQL en un intervalo especificado por el usuario para obtener datos de una base de datos de SQL Server mediante una transacción de MSDTC.</span><span class="sxs-lookup"><span data-stu-id="85127-105">This sample contains a receive adapter which runs a SQL statement at a user-specified interval to obtain data from a SQL Server database using an MSDTC transaction.</span></span> <span data-ttu-id="85127-106">Los datos se envían posteriormente a la base de datos de cuadro de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en forma de mensaje en el contexto de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="85127-106">The data is then submitted to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database in the form of a message under the context of the same transaction.</span></span>  
  
 <span data-ttu-id="85127-107">El adaptador de envío correspondiente ejecuta un procedimiento almacenado de SQL especificado por el usuario y para ello utiliza los datos de un mensaje de BizTalk en el contexto de una transacción.</span><span class="sxs-lookup"><span data-stu-id="85127-107">The corresponding send adapter runs a user-specified SQL stored procedure using input from a BizTalk message in the context of a transaction.</span></span> <span data-ttu-id="85127-108">Usa datos específicos de ese mensaje para encontrar el mensaje correspondiente y eliminarlo de la base de datos de cuadro de mensajes de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="85127-108">It uses specific data from that message to locate and delete the corresponding message from the Message Box database under that same transaction.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="85127-109">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="85127-109">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="85127-110">La solución de este ejemplo incluye dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="85127-110">This sample has two projects in its solution.</span></span> <span data-ttu-id="85127-111">El primero es el proyecto administrativo (Admin) que se utiliza antes del tiempo de ejecución para permitir que un usuario configure las ubicaciones de recepción y los puertos de envío que usan el adaptador.</span><span class="sxs-lookup"><span data-stu-id="85127-111">The first is the administrative project (Admin) which is used prior to runtime to allow a user to configure the receive locations and send ports that use this adapter.</span></span> <span data-ttu-id="85127-112">El segundo es el proyecto de tiempo de ejecución (Runtime) que se ejecuta cuando los adaptadores de recepción y envío están en ejecución.</span><span class="sxs-lookup"><span data-stu-id="85127-112">The second is the runtime project (Runtime) that runs when the send and receive adapters are executing.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="85127-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="85127-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="85127-114">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="85127-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="85127-115">\<*Ejemplos de ruta de acceso*\>\Samples\AdaptersDevelopment\TransactionalAdapter.</span><span class="sxs-lookup"><span data-stu-id="85127-115">\<*Samples Path*\>\Samples\AdaptersDevelopment\TransactionalAdapter.</span></span> <span data-ttu-id="85127-116">El proyecto de configuración administrativa se encuentra en la carpeta \Admin, y el de tiempo de ejecución, en la carpeta \Runtime.</span><span class="sxs-lookup"><span data-stu-id="85127-116">The administrative configuration project is located in the \Admin folder, while the runtime project exists in the \Runtime folder.</span></span>  
  
 <span data-ttu-id="85127-117">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="85127-117">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="85127-118">Nombre del archivo del proyecto Admin</span><span class="sxs-lookup"><span data-stu-id="85127-118">Admin Project Filename</span></span>|<span data-ttu-id="85127-119">Descripción del archivo del proyecto Admin</span><span class="sxs-lookup"><span data-stu-id="85127-119">Admin Project File Description</span></span>|  
|----------------------------|------------------------------------|  
|<span data-ttu-id="85127-120">TransactionalAdmin.csproj</span><span class="sxs-lookup"><span data-stu-id="85127-120">TransactionalAdmin.csproj</span></span>|<span data-ttu-id="85127-121">Archivo del proyecto administrativo del adaptador utilizado para la configuración anterior al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="85127-121">Adapter administrative project file used for pre-runtime configuration</span></span>|  
|<span data-ttu-id="85127-122">TransactionalReceiveHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="85127-122">TransactionalReceiveHandler.xsd</span></span>|<span data-ttu-id="85127-123">XSD de las propiedades del controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="85127-123">XSD for receive handler properties</span></span>|  
|<span data-ttu-id="85127-124">TransactionalReceiveLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="85127-124">TransactionalReceiveLocation.xsd</span></span>|<span data-ttu-id="85127-125">XSD de las propiedades de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="85127-125">XSD for receive location properties</span></span>|  
|<span data-ttu-id="85127-126">TransactionalTransmitLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="85127-126">TransactionalTransmitLocation.xsd</span></span>|<span data-ttu-id="85127-127">XSD de las propiedades de la ubicación de transmisión.</span><span class="sxs-lookup"><span data-stu-id="85127-127">XSD for transmit location properties</span></span>|  
|<span data-ttu-id="85127-128">TransactionalTransmitHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="85127-128">TransactionalTransmitHandler.xsd</span></span>|<span data-ttu-id="85127-129">XSD de las propiedades del controlador de transmisión.</span><span class="sxs-lookup"><span data-stu-id="85127-129">XSD for transmit handler properties</span></span>|  
|<span data-ttu-id="85127-130">TransactionalAdapterManagement.cs</span><span class="sxs-lookup"><span data-stu-id="85127-130">TransactionalAdapterManagement.cs</span></span>|<span data-ttu-id="85127-131">Administración de la configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="85127-131">Adapter configuration management.</span></span> <span data-ttu-id="85127-132">Contiene GetConfigSchema, que invoca el marco de trabajo de adaptadores de BizTalk para devolver un esquema de configuración XSD para cada uno de los (cuatro) tipos posibles de configuración compatibles.</span><span class="sxs-lookup"><span data-stu-id="85127-132">Contains GetConfigSchema which is invoked by the BizTalk Adapter Framework to return an XSD configuration schema for each of the (four) possible configuration types it supports.</span></span>|  
  
|<span data-ttu-id="85127-133">Nombre del archivo del proyecto de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="85127-133">Runtime Project Filename</span></span>|<span data-ttu-id="85127-134">Descripción del archivo del proyecto de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="85127-134">Runtime Project File Description</span></span>|  
|------------------------------|--------------------------------------|  
|<span data-ttu-id="85127-135">Transactional.csproj</span><span class="sxs-lookup"><span data-stu-id="85127-135">Transactional.csproj</span></span>|<span data-ttu-id="85127-136">Archivo del proyecto de tiempo de ejecución del adaptador.</span><span class="sxs-lookup"><span data-stu-id="85127-136">Adapter runtime project file</span></span>|  
|<span data-ttu-id="85127-137">TransactionalAsyncBatch.cs</span><span class="sxs-lookup"><span data-stu-id="85127-137">TransactionalAsyncBatch.cs</span></span>|<span data-ttu-id="85127-138">Realiza la implementación asíncrona de la parte de envío del adaptador.</span><span class="sxs-lookup"><span data-stu-id="85127-138">Asynchronous implementation of the send part of the adapter</span></span>|  
|<span data-ttu-id="85127-139">TransactionalDeleteBatch.cs</span><span class="sxs-lookup"><span data-stu-id="85127-139">TransactionalDeleteBatch.cs</span></span>|<span data-ttu-id="85127-140">Elimina un lote de mensajes y votos para confirmar o anular una transacción.</span><span class="sxs-lookup"><span data-stu-id="85127-140">Deletes a batch of messages and votes to commit or abort a transaction</span></span>|  
|<span data-ttu-id="85127-141">TransactionalProperties.cs</span><span class="sxs-lookup"><span data-stu-id="85127-141">TransactionalProperties.cs</span></span>|<span data-ttu-id="85127-142">Extrae y establece las propiedades de configuración.</span><span class="sxs-lookup"><span data-stu-id="85127-142">Extracts and sets configuration properties</span></span>|  
|<span data-ttu-id="85127-143">TransactionalReceiver.cs</span><span class="sxs-lookup"><span data-stu-id="85127-143">TransactionalReceiver.cs</span></span>|<span data-ttu-id="85127-144">Crea y administra los extremos de recepción.</span><span class="sxs-lookup"><span data-stu-id="85127-144">Creates and manages receive endpoints</span></span>|  
|<span data-ttu-id="85127-145">TransactionalReceiverEndpoint.cs</span><span class="sxs-lookup"><span data-stu-id="85127-145">TransactionalReceiverEndpoint.cs</span></span>|<span data-ttu-id="85127-146">Realiza la escucha o sondeo real de cada una de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="85127-146">Actual listening or polling for each receive location</span></span>|  
|<span data-ttu-id="85127-147">TransactionalTransmitter.cs</span><span class="sxs-lookup"><span data-stu-id="85127-147">TransactionalTransmitter.cs</span></span>|<span data-ttu-id="85127-148">Acepta un lote de mensajes del motor de mensajería que se va a transmitir.</span><span class="sxs-lookup"><span data-stu-id="85127-148">Accepts a batch of messages from the Messaging Engine to be transmitted</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="85127-149">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="85127-149">How to Use This Sample</span></span>  
 <span data-ttu-id="85127-150">El propósito de este ejemplo es constituir un marco de trabajo que pueda utilizarse para la creación de adaptadores de recepción y envío personalizados mediante transacciones explícitas.</span><span class="sxs-lookup"><span data-stu-id="85127-150">This sample is meant as a framework for you to use in creating custom send and receive adapters using explicit transactions.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="85127-151">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="85127-151">Building and Initializing This Sample</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="85127-152">Si la instalación de BizTalk es de 64 bits o se modifica la ubicación de la instalación, OutboundAssemblyPath, InboundAssemblyPath y AdapterMgmtAssemblyPath deben cambiarse según corresponda.</span><span class="sxs-lookup"><span data-stu-id="85127-152">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  
  
#### <a name="create-a-strong-name-key-for-the-transactional-adapter-sample"></a><span data-ttu-id="85127-153">Crear una clave de nombre seguro para el ejemplo de adaptador transaccional</span><span class="sxs-lookup"><span data-stu-id="85127-153">Create a Strong Name Key for the Transactional Adapter sample</span></span>  
  
1.  <span data-ttu-id="85127-154">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="85127-154">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="85127-155">En el símbolo del sistema, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="85127-155">At the command prompt, type the following and then press enter:</span></span>  
  
    ```  
    cd \Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Runtime  
    ```  
  
3.  <span data-ttu-id="85127-156">En el símbolo del sistema, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="85127-156">At the command prompt, type the following and then press enter:</span></span>  
  
    ```  
    sn –k TransactionalAdapter.snk  
    ```  
  
4.  <span data-ttu-id="85127-157">En el símbolo del sistema, escriba **salir**, y, a continuación, presione ENTRAR para cerrar la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="85127-157">At the command prompt, type **exit**, and then press enter to close the command prompt window.</span></span>  
  
#### <a name="build-the-transactional-adapter-solution"></a><span data-ttu-id="85127-158">Compile la solución de adaptador transaccional</span><span class="sxs-lookup"><span data-stu-id="85127-158">Build the Transactional Adapter Solution</span></span>  
  
1.  <span data-ttu-id="85127-159">Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.</span><span class="sxs-lookup"><span data-stu-id="85127-159">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="85127-160">Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter y haga doble clic en **TransactionalAdapter.sln** para abrir esta solución en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85127-160">Browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter, and double-click **TransactionalAdapter.sln** to open this solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="85127-161">Para compilar tanto de los proyectos de adaptador transaccional (Admin y Runtime) en el Explorador de soluciones, haga clic en **solución TransactionalAdapter**y, a continuación, haga clic en **volver a generar**.</span><span class="sxs-lookup"><span data-stu-id="85127-161">To build both of the Transactional Adapter projects (Admin and Runtime) in Solution Explorer, right-click **Solution TransactionalAdapter**, and then click **Rebuild**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="85127-162">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="85127-162">Running This Sample</span></span>  
  
#### <a name="register-the-transactional-adapter"></a><span data-ttu-id="85127-163">Registrar el adaptador transaccional</span><span class="sxs-lookup"><span data-stu-id="85127-163">Register the Transactional Adapter</span></span>  
  
1.  <span data-ttu-id="85127-164">En el Explorador de Windows, vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin.</span><span class="sxs-lookup"><span data-stu-id="85127-164">In Windows Explorer, navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin.</span></span>  
  
2.  <span data-ttu-id="85127-165">Para agregar los datos del adaptador transaccional al registro, haga doble clic en **TransactionalAdmin.reg**.</span><span class="sxs-lookup"><span data-stu-id="85127-165">To add the transactional adapter data to the registry, double-click **TransactionalAdmin.reg**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85127-166">**TransactionalAdmin.reg** incluye rutas codificadas de forma rígida a C:\Program Files\Microsoft BizTalk Server\\.</span><span class="sxs-lookup"><span data-stu-id="85127-166">**TransactionalAdmin.reg** includes hard-coded paths to C:\Program Files\Microsoft BizTalk Server\\.</span></span> <span data-ttu-id="85127-167">Si no instaló BizTalk Server en la ubicación predeterminada o si actualizó la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a partir de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], deberá modificar el archivo TransactionalAdmin.reg con las rutas apropiadas.</span><span class="sxs-lookup"><span data-stu-id="85127-167">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the default location or if you upgraded your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from a previous version, you must modify the file TransactionalAdmin.reg with the appropriate paths.</span></span> <span data-ttu-id="85127-168">Actualice las rutas asociadas a los valores "InboundAssemblyPath", "OutboundAssemblyPath" y "AdapterMgmtAssemblyPath" para que señalen a la ubicación correcta de los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="85127-168">Update the paths associated with the "InboundAssemblyPath", "OutboundAssemblyPath", and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="85127-169">Si instala BizTalk en un equipo de 64 bits, cambie todas las instancias de la entrada de registro HKEY_CLASSES_ROOT\CLSID\ a HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ en el **TransactionalAdmin.reg** archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="85127-169">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **TransactionalAdmin.reg** registry file.</span></span>  
  
3.  <span data-ttu-id="85127-170">En el **Editor del registro** cuadro de diálogo, haga clic en **Sí** para agregar el adaptador de ejemplo en el registro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85127-170">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="85127-171">Para cerrar el Explorador de Windows, haga clic en **archivo**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="85127-171">To close Windows Explorer, click **File**, and then click **Close**.</span></span>  
  
#### <a name="add-the-transactional-adapter-to-biztalk-server"></a><span data-ttu-id="85127-172">Agregar el adaptador transaccional a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="85127-172">Add the Transactional Adapter to BizTalk Server</span></span>  
  
1.  <span data-ttu-id="85127-173">Haga clic en el **iniciar** menú, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, seleccione **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="85127-173">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="85127-174">En el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda la **administración de BizTalk Server** de árbol, expanda el **grupo de BizTalk** del árbol y, a continuación, expanda el **configuración de plataforma** árbol.</span><span class="sxs-lookup"><span data-stu-id="85127-174">In the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **BizTalk Server Administration** tree, expand the **BizTalk Group** tree, and then expand the **Platform Settings**  tree.</span></span>  
  
3.  <span data-ttu-id="85127-175">Haga clic en **adaptadores**, haga clic en **New**y, a continuación, haga clic en **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="85127-175">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="85127-176">En el **propiedades del adaptador** diálogo cuadro, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="85127-176">In the **Adapter Properties** dialog box, do the following.</span></span>  
  
    |<span data-ttu-id="85127-177">Use</span><span class="sxs-lookup"><span data-stu-id="85127-177">Use this</span></span>|<span data-ttu-id="85127-178">Para</span><span class="sxs-lookup"><span data-stu-id="85127-178">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="85127-179">Nombre</span><span class="sxs-lookup"><span data-stu-id="85127-179">Name</span></span>|<span data-ttu-id="85127-180">Tipo de **TransactionalAdapter**.</span><span class="sxs-lookup"><span data-stu-id="85127-180">Type **TransactionalAdapter**.</span></span>|  
    |<span data-ttu-id="85127-181">Adaptador</span><span class="sxs-lookup"><span data-stu-id="85127-181">Adapter</span></span>|<span data-ttu-id="85127-182">Seleccione **Txn** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="85127-182">Select **Txn** from the drop-down list.</span></span> <span data-ttu-id="85127-183">Esta entrada aparece como resultado de ejecutar el **TransactionalAdmin.reg** archivo anteriormente.</span><span class="sxs-lookup"><span data-stu-id="85127-183">This entry appears as a result of running the **TransactionalAdmin.reg** file previously.</span></span>|  
    |<span data-ttu-id="85127-184">Description</span><span class="sxs-lookup"><span data-stu-id="85127-184">Description</span></span>|<span data-ttu-id="85127-185">Tipo de **adaptador transaccional de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="85127-185">Type **Sample Transactional Adapter**.</span></span>|  
  
5.  <span data-ttu-id="85127-186">Haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="85127-186">Click **OK.**</span></span> <span data-ttu-id="85127-187">El adaptador aparece en la lista de adaptadores de la ventana derecha de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="85127-187">The adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  
  
#### <a name="create-a-receive-port-and-location-that-uses-the-adapter"></a><span data-ttu-id="85127-188">Crear un puerto y una ubicación de recepción que utilicen el adaptador</span><span class="sxs-lookup"><span data-stu-id="85127-188">Create a Receive Port and Location that uses the Adapter</span></span>  
  
1.  <span data-ttu-id="85127-189">Expanda el **grupo de BizTalk [nombre del servidor]** nodo [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **aplicaciones** nodo, expanda **BizTalk Application 1** nodo.</span><span class="sxs-lookup"><span data-stu-id="85127-189">Expand the **BizTalk Group[server name]** node in [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **Applications** node, expand **BizTalk Application 1** node.</span></span>  
  
2.  <span data-ttu-id="85127-190">Haga clic en **puertos de recepción**y, a continuación, haga clic en **New**, seleccione **puerto de recepción unidireccional.**</span><span class="sxs-lookup"><span data-stu-id="85127-190">Right-click **Receive Ports**, and then click **New**, select **One-Way Receive Port.**</span></span>  
  
3.  <span data-ttu-id="85127-191">Para **nombre**, escriba **TxnReceivePort1**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85127-191">For **Name**, enter **TxnReceivePort1**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="85127-192">Haga clic en el **ubicaciones de recepción** nodo, haga clic en **New**y, a continuación, seleccione **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="85127-192">Right-click the **Receive Locations** node, click **New**, and then select **One-Way Receive Location**.</span></span>  
  
5.  <span data-ttu-id="85127-193">En el**seleccionar un puerto de recepción** cuadro de diálogo, seleccione **TxnReceivePort1**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85127-193">In the**Select a Receive Port** dialog box, select **TxnReceivePort1**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="85127-194">En el **propiedades de ubicación de recepción** cuadro de diálogo, en la **General** , escriba **TxnReceiveLocation1** para **nombre**.</span><span class="sxs-lookup"><span data-stu-id="85127-194">In the **Receive Location Properties** dialog box, under the **General** tab, enter **TxnReceiveLocation1** for **Name**.</span></span> <span data-ttu-id="85127-195">Asegúrese del **puerto de recepción** etiqueta muestra **TxnReceivePort1**.</span><span class="sxs-lookup"><span data-stu-id="85127-195">Ensure the **Receive Port** label displays **TxnReceivePort1**.</span></span>  
  
7.  <span data-ttu-id="85127-196">En el**tipo** cuadro de lista desplegable en el **transporte** marco, seleccione **TransactionalAdapter.**</span><span class="sxs-lookup"><span data-stu-id="85127-196">In the**Type** dropdown list box, in the **Transport** frame, select **TransactionalAdapter.**</span></span>  
  
8.  <span data-ttu-id="85127-197">En el **recepción \*\*\* canalización** cuadro, asegúrese de **PassThruReceive** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="85127-197">In the **Receive****Pipeline** box, ensure **PassThruReceive** is selected.</span></span> <span data-ttu-id="85127-198">Deje el resto de las propiedades con los valores de configuración predeterminados.</span><span class="sxs-lookup"><span data-stu-id="85127-198">Leave the rest of the properties with their default settings.</span></span>  
  
9. <span data-ttu-id="85127-199">Haga clic en el **configurar** situado junto a la **tipo** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="85127-199">Click the **Configure** button next to the **Type** drop down box.</span></span> <span data-ttu-id="85127-200">Con ello, se muestra un cuadro de diálogo específico para este adaptador.</span><span class="sxs-lookup"><span data-stu-id="85127-200">This displays a dialog specific to this adapter.</span></span> <span data-ttu-id="85127-201">Especifique lo siguiente según sea necesario, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85127-201">Specify the following as you see appropriate, then click **OK**.</span></span>  
  
    |<span data-ttu-id="85127-202">Propiedad</span><span class="sxs-lookup"><span data-stu-id="85127-202">Property</span></span>|<span data-ttu-id="85127-203">Configuración</span><span class="sxs-lookup"><span data-stu-id="85127-203">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="85127-204">Cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="85127-204">Connection String</span></span>|<span data-ttu-id="85127-205">La cadena de conexión de base de datos de SQL utilizada para efectuar la conexión con la base de datos Northwind y la autenticación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="85127-205">The SQL database connection string used to connect and authenticate with the Northwind database.</span></span> <span data-ttu-id="85127-206">Posteriormente, se ejecutará un script de SQL que usará esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="85127-206">We will later run a SQL script that will use this database.</span></span>|  
    |<span data-ttu-id="85127-207">Texto de comando</span><span class="sxs-lookup"><span data-stu-id="85127-207">Command Text</span></span>|<span data-ttu-id="85127-208">Las instrucciones SQL que se ejecutan para la base de datos Northwind para obtener datos que se colocarán en el mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="85127-208">The SQL statements that are executed against the Northwind database to obtain data to put into a BizTalk Message.</span></span>|  
    |<span data-ttu-id="85127-209">Cookie</span><span class="sxs-lookup"><span data-stu-id="85127-209">Cookie</span></span>|<span data-ttu-id="85127-210">Forma parte del URI, por lo que es preciso especificar un valor único, como el nombre de la ubicación de recepción; por ejemplo: TxnReceiveLocation1.</span><span class="sxs-lookup"><span data-stu-id="85127-210">Comprises part of the URI so enter a unique value, such as the name of the receive location, for instance: TxnReceiveLocation1.</span></span>|  
    |<span data-ttu-id="85127-211">Unidad de intervalo de sondeo</span><span class="sxs-lookup"><span data-stu-id="85127-211">Polling Interval Unit</span></span>|<span data-ttu-id="85127-212">El número de unidades de medida de tiempo para el sondeo de los datos.</span><span class="sxs-lookup"><span data-stu-id="85127-212">The number of units of time measure for the polling of the data.</span></span> <span data-ttu-id="85127-213">Establezca este valor como segundos.</span><span class="sxs-lookup"><span data-stu-id="85127-213">Set this to seconds.</span></span>|  
    |<span data-ttu-id="85127-214">Intervalo de sondeo</span><span class="sxs-lookup"><span data-stu-id="85127-214">Polling Interval</span></span>|<span data-ttu-id="85127-215">La unidad de medida de tiempo para el sondeo de los datos.</span><span class="sxs-lookup"><span data-stu-id="85127-215">The unit of time measure for the polling of the data.</span></span> <span data-ttu-id="85127-216">Establezca este valor como 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="85127-216">Set this to 15 seconds.</span></span>|  
  
10. <span data-ttu-id="85127-217">Haga clic en **Aceptar** para cerrar el cuadro de diálogo Configurar, a continuación, **Aceptar** otra vez para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo para volver a la [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85127-217">Click **OK** to close the Configure dialog box, then **OK** again to close the **Receive Location Properties** dialog box to return to the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
#### <a name="create-a-send-port-and-send-handler-that-use-the-adapter"></a><span data-ttu-id="85127-218">Crear un puerto y un controlador de envío que utilicen el adaptador</span><span class="sxs-lookup"><span data-stu-id="85127-218">Create a Send Port and Send Handler that use the Adapter</span></span>  
  
1.  <span data-ttu-id="85127-219">Con el **BizTalk Application 1** nodo expandido, haga clic en **puertos de envío**y, a continuación, haga clic en **New**y seleccione **enviar Puerto unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="85127-219">With the **BizTalk Application 1** node still expanded, right-click **Send Ports**, and then click **New**, and select **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="85127-220">En el **nombre** , escriba **TxnSendPort1**.</span><span class="sxs-lookup"><span data-stu-id="85127-220">In the **Name** field, enter **TxnSendPort1**.</span></span>  
  
3.  <span data-ttu-id="85127-221">En el **transporte** marco, en la **tipo** lista desplegable, seleccione**TransactionalAdapter**`.`</span><span class="sxs-lookup"><span data-stu-id="85127-221">In the **Transport** frame, in the **Type** drop-down list, select**TransactionalAdapter**`.`</span></span>  
  
4.  <span data-ttu-id="85127-222">En el **canalización de envío** cuadro, asegúrese de **PassThruTransmit** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="85127-222">In the **Send Pipeline** box, ensure **PassThruTransmit** is selected.</span></span>  
  
5.  <span data-ttu-id="85127-223">Haga clic en el **configurar** situado junto a la **transporte** lista desplegable. En el cuadro de diálogo que aparece, especifique lo siguiente según sea necesario, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85127-223">Click the **Configure** button next to the **transport** drop-down list.In the dialog that appears specify the following as you see appropriate, then click **OK**.</span></span>  
  
    |<span data-ttu-id="85127-224">Propiedad</span><span class="sxs-lookup"><span data-stu-id="85127-224">Property</span></span>|<span data-ttu-id="85127-225">Configuración</span><span class="sxs-lookup"><span data-stu-id="85127-225">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="85127-226">Cookie</span><span class="sxs-lookup"><span data-stu-id="85127-226">Cookie</span></span>|<span data-ttu-id="85127-227">Forma parte del URI: especificar un valor único, como el nombre de la ubicación de recepción, por ejemplo: **TxnSendPort1**.</span><span class="sxs-lookup"><span data-stu-id="85127-227">Comprises part of the URI - Enter a unique value here such as the name of the receive location, for instance: **TxnSendPort1**.</span></span>|  
    |<span data-ttu-id="85127-228">Cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="85127-228">Connection String</span></span>|<span data-ttu-id="85127-229">La cadena de conexión de base de datos de SQL utilizada para efectuar la conexión con la base de datos Northwind y la autenticación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="85127-229">The SQL database connection string used to connect and authenticate with the Northwind database.</span></span> <span data-ttu-id="85127-230">Lo más probable es que sea el mismo que se utiliza para configurar el **TxnReceiveLocation1** ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="85127-230">It will most likely be the same one used to configure the **TxnReceiveLocation1** receive location.</span></span>|  
    |<span data-ttu-id="85127-231">Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="85127-231">Stored Procedure</span></span>|<span data-ttu-id="85127-232">El nombre del procedimiento almacenado que se ejecuta para sondear la base de datos - **sp_txnProc**.</span><span class="sxs-lookup"><span data-stu-id="85127-232">The stored procedure name that gets executed to poll the database - **sp_txnProc**.</span></span> <span data-ttu-id="85127-233">El cuerpo del mensaje se entrega a la que BizTalk el procedimiento almacenado como un parámetro de cadena denominado @Data.</span><span class="sxs-lookup"><span data-stu-id="85127-233">The body of the BizTalk message is given to that stored procedure as a string parameter called @Data.</span></span> <span data-ttu-id="85127-234">Por ejemplo, el usuario en este caso más adelante configurará el procedimiento almacenado con el nombre **sp_txnProc**.</span><span class="sxs-lookup"><span data-stu-id="85127-234">For example, the user will in this case later configure the stored procedure with the name **sp_txnProc**.</span></span> <span data-ttu-id="85127-235">El tiempo de ejecución del adaptador ejecutará el equivalente de esta llamada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="85127-235">The runtime of the adapter would execute the equivalent of this call to the database.</span></span><br /><br /> <span data-ttu-id="85127-236">exec sp_txnProc @Data = "el contenido del mensaje de BizTalk"</span><span class="sxs-lookup"><span data-stu-id="85127-236">exec sp_txnProc @Data = “the contents of the BizTalk message”</span></span>|  
  
6.  <span data-ttu-id="85127-237">En el panel de navegación izquierdo, haga clic en **filtro**.</span><span class="sxs-lookup"><span data-stu-id="85127-237">In the left navigation pane, click **Filter**.</span></span>  
  
7.  <span data-ttu-id="85127-238">En el editor de expresiones de filtro, especifique la siguiente expresión con el fin de configurar una suscripción para este puerto de envío de modo que pueda recibir cualquier mensaje que reciba el puerto de recepción TxnReceivePort1.</span><span class="sxs-lookup"><span data-stu-id="85127-238">In the filter expression editor, enter the following expression to set up a subscription for this send port to receive any messages received by the TxnReceivePort1 receive port.</span></span>  
  
     <span data-ttu-id="85127-239">Especifique estos valores:**BTS. ReceivePortName == TxnReceivePort1**</span><span class="sxs-lookup"><span data-stu-id="85127-239">Enter these values:**BTS.ReceivePortName== TxnReceivePort1**</span></span>  
  
    1.  <span data-ttu-id="85127-240">`(property)`  **BTS.ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="85127-240">`(property)`  **BTS.ReceivePortName**</span></span>  
  
    2.  <span data-ttu-id="85127-241">`(operator)`  **==**</span><span class="sxs-lookup"><span data-stu-id="85127-241">`(operator)`  **==**</span></span>  
  
    3.  <span data-ttu-id="85127-242">`(value)`  **TxnReceivePort1**</span><span class="sxs-lookup"><span data-stu-id="85127-242">`(value)`  **TxnReceivePort1**</span></span>  
  
8.  <span data-ttu-id="85127-243">Use los valores predeterminados para el resto de las propiedades del adaptador y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85127-243">Use the default values for the remainder of the adapter properties and select **OK**.</span></span>  
  
## <a name="run-the-sample"></a><span data-ttu-id="85127-244">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="85127-244">Run the sample</span></span>  
  
1.  <span data-ttu-id="85127-245">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**, seleccione **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="85127-245">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, select **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="85127-246">En el **conectar al servidor** diálogo cuadro, asegúrese de que **tipo de servidor** está establecido en **motor de base de datos**y escriba las credenciales para autenticarse en el servidor de base de datos, a continuación, seleccione  **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="85127-246">In the **Connect to Server** dialog box, make sure **Server Type** is set to **Database Engine**, and enter credentials to authenticate to the database server, then select **Connect**.</span></span>  
  
3.  <span data-ttu-id="85127-247">Seleccione el **nueva consulta** botón de barra de herramientas y pegue lo siguiente en la nueva ventana de consulta para insertar una tabla de prueba, datos de prueba y una prueba de procedimiento almacenan en la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="85127-247">Select the **New Query** toolbar button and paste the following into the new query window to insert a test table, test data, and a test stored procedure into the Northwind database.</span></span> <span data-ttu-id="85127-248">Seleccione el **Execute** botón de barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="85127-248">Select the **Execute** toolbar button.</span></span>  
  
    ```  
    use [Northwind]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[scratch]') and OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    drop table [dbo].[scratch]  
    GO  
    CREATE TABLE [dbo].[scratch] (  
         [id] [int] IDENTITY (1, 1) NOT NULL ,  
         [msg] [nvarchar] (4000) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    GRANT SELECT , UPDATE , INSERT ON [dbo].[scratch] TO [public]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[sp_txnProc]') and OBJECTPROPERTY(id, N'IsProcedure') = 1)  
    drop procedure [dbo].[sp_txnProc]  
    GO  
    CREATE PROCEDURE [dbo].[sp_txnProc] @Data nvarchar (4000)  
    AS   
    INSERT scratch ( msg ) values ( @Data )  
    GO  
    GRANT EXECUTE ON [dbo].[sp_txnProc] TO [public]  
    GO  
    ```  
  
4.  <span data-ttu-id="85127-249">En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda la **puertos de envío** nodo, seleccione el **TxnSendPort1** puerto de envío y seleccione **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="85127-249">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **Send Ports** node, select the **TxnSendPort1** send port, and select **Start**.</span></span>  
  
5.  <span data-ttu-id="85127-250">En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda la **ReceiveLocations** nodo, seleccione el **TxnRecieveLocation1** ubicación de recepción y, a continuación, seleccione **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="85127-250">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the **ReceiveLocations** node, select the **TxnRecieveLocation1** receive location, and then select **Enable**.</span></span>  
  
6.  <span data-ttu-id="85127-251">Una vez habilitada la ubicación de recepción, se efectuará automáticamente un sondeo de los datos de la base de datos en los intervalos designados.</span><span class="sxs-lookup"><span data-stu-id="85127-251">Once the receive location is enabled, it will automatically poll the database at the designated intervals for data.</span></span>  
  
## <a name="classes-or-methods-used-in-the-sample"></a><span data-ttu-id="85127-252">Las clases o métodos utilizados en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="85127-252">Classes or Methods Used in the sample</span></span>  
* <span data-ttu-id="85127-253">IBTTransmitterBatch (interfaz) (COM)</span><span class="sxs-lookup"><span data-stu-id="85127-253">IBTTransmitterBatch Interface (COM)</span></span>
  
* <span data-ttu-id="85127-254">IBTTransportProxy (interfaz) (COM)</span><span class="sxs-lookup"><span data-stu-id="85127-254">IBTTransportProxy Interface (COM)</span></span>

<span data-ttu-id="85127-255">Estos métodos se describen [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="85127-255">These methods are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="85127-256">Vea también</span><span class="sxs-lookup"><span data-stu-id="85127-256">See Also</span></span>  
 <span data-ttu-id="85127-257">[Ejemplos de adaptador: desarrollo](../core/adapter-samples-development.md) </span><span class="sxs-lookup"><span data-stu-id="85127-257">[Adapter Samples - Development](../core/adapter-samples-development.md) </span></span>  
 [<span data-ttu-id="85127-258">Registro de un adaptador</span><span class="sxs-lookup"><span data-stu-id="85127-258">Registering an Adapter</span></span>](../core/registering-an-adapter.md)