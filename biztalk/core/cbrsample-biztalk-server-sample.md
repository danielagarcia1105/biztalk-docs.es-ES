---
title: CBRSample (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, routing
- messages, filters
- outbound maps
- examples, messages
- messages, routing
- examples, outbound maps
- examples, filters
- messages, examples
ms.assetid: 8fba494c-9257-4eed-8b6a-867056147c2c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b772bc44d4a745d5bfa330e7df7fcadcf2c020db
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22234732"
---
# <a name="cbrsample-biztalk-server-sample"></a><span data-ttu-id="2f8de-102">CBRSample (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="2f8de-102">CBRSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="2f8de-103">El ejemplo CBRSample muestra cómo aplicar filtros y una asignación de salida para transformar y enrutar mensajes de instancias basándose en su contenido.</span><span class="sxs-lookup"><span data-stu-id="2f8de-103">The CBRSample sample demonstrates how to apply filters and an outbound map to transform and route instance messages based on content.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="2f8de-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-104">What This Sample Does</span></span>  
 <span data-ttu-id="2f8de-105">Este ejemplo muestra el enrutamiento de un mensaje que contiene nombre, dirección e información de contacto de una de dos carpetas basándose en el código de país.</span><span class="sxs-lookup"><span data-stu-id="2f8de-105">This sample demonstrates the routing of a message containing name, address, and contact information to one of two folders based on country code.</span></span> <span data-ttu-id="2f8de-106">En concreto, este ejemplo realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f8de-106">Specifically, this sample does the following:</span></span>  
  
1.  <span data-ttu-id="2f8de-107">Define un formato de mensaje de ejemplo que contiene información básica de una persona, incluida la identidad con Id. de usuario y nombre completo, dirección con código de país e información de contacto telefónico.</span><span class="sxs-lookup"><span data-stu-id="2f8de-107">Defines a sample message format containing basic information about a person including identity with user ID and full name, address with country code, and phone contact information.</span></span>  
  
2.  <span data-ttu-id="2f8de-108">Promueve la **CountryCode** propiedad en el documento de entrada para que se puede usar en un filtro de puertos para controlar la transformación y el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2f8de-108">Promotes the **CountryCode** property in the input document so that it can be used in a port filter to control transformation and routing.</span></span>  
  
3.  <span data-ttu-id="2f8de-109">Transforma el mensaje en una versión canadiense cuando **CountryCode** es igual a 200 o una versión estadounidense cuando **CountryCode**es igual a 100.</span><span class="sxs-lookup"><span data-stu-id="2f8de-109">Transforms the message into a Canadian version when **CountryCode** is equal to 200 or a U.S. version when **CountryCode**is equal to 100.</span></span> <span data-ttu-id="2f8de-110">Dos transformaciones pasan a través de todos los datos excepto intermedio iniciales (**inicial**).</span><span class="sxs-lookup"><span data-stu-id="2f8de-110">Both transforms pass through all data except middle initial (**Initial**).</span></span> <span data-ttu-id="2f8de-111">La versión canadiense también asigna **estado** a **provincia** y **ZipCode** a **PinCode**.</span><span class="sxs-lookup"><span data-stu-id="2f8de-111">The Canadian version also maps **State** to **Province** and **ZipCode** to **PinCode**.</span></span>  
  
4.  <span data-ttu-id="2f8de-112">Enruta los mensajes estadounidenses al directorio US y los mensajes canadienses al directorio CAN.</span><span class="sxs-lookup"><span data-stu-id="2f8de-112">Routes U.S. messages to the US directory and Canadian messages to the CAN directory.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="2f8de-113">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="2f8de-113">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="2f8de-114">El diseño se basa en las canalizaciones XML de envío y recepción predeterminadas, la promoción de propiedades, los filtros de suscripción y las asignaciones de salida en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enrutar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="2f8de-114">The design relies on the default send and receive XML pipelines, property promotion, subscription filters, and outbound maps within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to route messages.</span></span> <span data-ttu-id="2f8de-115">En la tabla siguiente se muestran los elementos de diseño y su justificación.</span><span class="sxs-lookup"><span data-stu-id="2f8de-115">The following table shows design elements and their justification.</span></span>  
  
|<span data-ttu-id="2f8de-116">Elemento de diseño</span><span class="sxs-lookup"><span data-stu-id="2f8de-116">Design element</span></span>|<span data-ttu-id="2f8de-117">Razones seleccionadas</span><span class="sxs-lookup"><span data-stu-id="2f8de-117">Reason(s) selected</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="2f8de-118">Canalización de recepción XML predeterminada</span><span class="sxs-lookup"><span data-stu-id="2f8de-118">Default XML receive pipeline</span></span>|<span data-ttu-id="2f8de-119">-La canalización XMLReceive admite la promoción de propiedad; la canalización PassThruReceive no.</span><span class="sxs-lookup"><span data-stu-id="2f8de-119">-   The XMLReceive pipeline supports property promotion; the PassThruReceive pipeline does not.</span></span><br /><span data-ttu-id="2f8de-120">-El mensaje entrante está en formato XML y no necesita procesamiento más allá de desensamblado básico y la resolución de entidades.</span><span class="sxs-lookup"><span data-stu-id="2f8de-120">-   The inbound message is already in XML format and does not require processing beyond basic disassembly and party resolution.</span></span>|  
|<span data-ttu-id="2f8de-121">Promoción de propiedades</span><span class="sxs-lookup"><span data-stu-id="2f8de-121">Property promotion</span></span>|<span data-ttu-id="2f8de-122">-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]depende de los campos de propiedades para efectuar el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2f8de-122">-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]depends upon property fields to do routing.</span></span> <span data-ttu-id="2f8de-123">Los campos distintivos los utilizan las orquestaciones y no se pueden usar para enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2f8de-123">Distinguished fields are used by orchestrations and cannot be used for routing.</span></span>|  
|<span data-ttu-id="2f8de-124">Filtro de suscripción</span><span class="sxs-lookup"><span data-stu-id="2f8de-124">Subscription filter</span></span>|<span data-ttu-id="2f8de-125">-El filtro de suscripción realiza el enrutamiento real mediante la captura de mensajes que cumplen uno o varios criterios basados en campos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="2f8de-125">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>|  
|<span data-ttu-id="2f8de-126">Asignación de salida</span><span class="sxs-lookup"><span data-stu-id="2f8de-126">Outbound map</span></span>|<span data-ttu-id="2f8de-127">-Las asignaciones transforman datos de un formato a otro.</span><span class="sxs-lookup"><span data-stu-id="2f8de-127">-   Maps transform data from one format to another.</span></span> <span data-ttu-id="2f8de-128">El ejemplo asigna un mensaje entrante a un formato estadounidense o canadiense.</span><span class="sxs-lookup"><span data-stu-id="2f8de-128">The sample maps an inbound message to either a U.S. or Canadian format.</span></span>|  
|<span data-ttu-id="2f8de-129">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="2f8de-129">XMLTransmit</span></span>|<span data-ttu-id="2f8de-130">-Realiza el ensamblado básico de los mensajes XML salientes; la canalización PassThruTransmit no ofrece compatibilidad adicional.</span><span class="sxs-lookup"><span data-stu-id="2f8de-130">-   Performs basic assembly of outgoing XML messages; the PassThruTransmit pipeline provides no additional support.</span></span>|  
  
 <span data-ttu-id="2f8de-131">Este patrón básico puede ampliarse y utilizarse para escenarios más complejos.</span><span class="sxs-lookup"><span data-stu-id="2f8de-131">This basic pattern can be extended and used for more complex scenarios.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="2f8de-132">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-132">Where to Find This Sample</span></span>  
 <span data-ttu-id="2f8de-133">En este ejemplo se encuentra en <`Samples Path>`\Messaging\CBRSample\\.</span><span class="sxs-lookup"><span data-stu-id="2f8de-133">This sample is located at <`Samples Path>`\Messaging\CBRSample\\.</span></span>  
  
 <span data-ttu-id="2f8de-134">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="2f8de-134">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="2f8de-135">Archivos</span><span class="sxs-lookup"><span data-stu-id="2f8de-135">File(s)</span></span>|<span data-ttu-id="2f8de-136">Description</span><span class="sxs-lookup"><span data-stu-id="2f8de-136">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f8de-137">CBRDataCAN.Xml, CBRDataUS.Xml</span><span class="sxs-lookup"><span data-stu-id="2f8de-137">CBRDataCAN.Xml, CBRDataUS.Xml</span></span>|<span data-ttu-id="2f8de-138">Los archivos de entrada de ejemplo que se ajustan al esquema definido en el archivo CBRInputSchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="2f8de-138">Sample input files that conform to the schema defined in the file CBRInputSchema.xsd.</span></span>|  
|<span data-ttu-id="2f8de-139">CBRInput2CANMap.btm, CBRInput2USMap.btm</span><span class="sxs-lookup"><span data-stu-id="2f8de-139">CBRInput2CANMap.btm, CBRInput2USMap.btm</span></span>|<span data-ttu-id="2f8de-140">Archivos de asignación para las transformaciones de formato canadiense y estadounidense, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2f8de-140">Map files for the Canadian and U.S. format transformations, respectively.</span></span>|  
|<span data-ttu-id="2f8de-141">CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd</span><span class="sxs-lookup"><span data-stu-id="2f8de-141">CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd</span></span>|<span data-ttu-id="2f8de-142">Archivos de esquema para el formato de entrada, el formato de salida canadiense y el formato de salida estadounidense, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2f8de-142">Schema files for the input format, the Canadian output format, and the U.S. output format, respectively.</span></span>|  
|<span data-ttu-id="2f8de-143">CBRPromotedPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="2f8de-143">CBRPromotedPropertySchema.xsd</span></span>|<span data-ttu-id="2f8de-144">Archivo de esquema de la propiedad promocionada que corresponde a la **CountryCode** elemento del XML de los archivos de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f8de-144">Schema file for the promoted property that corresponds to the **CountryCode** element in the XML input files.</span></span>|  
|<span data-ttu-id="2f8de-145">CBRSample.btproj, CBRSample.sln</span><span class="sxs-lookup"><span data-stu-id="2f8de-145">CBRSample.btproj, CBRSample.sln</span></span>|<span data-ttu-id="2f8de-146">Proyecto de BizTalk y archivos de solución para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f8de-146">BizTalk project and solution files for this sample.</span></span>|  
|<span data-ttu-id="2f8de-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="2f8de-147">Cleanup.bat</span></span>|<span data-ttu-id="2f8de-148">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="2f8de-148">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="2f8de-149">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="2f8de-149">Removes send and receive ports.</span></span> <span data-ttu-id="2f8de-150">Quita los directorios virtuales de Internet Information Services (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2f8de-150">Removes Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="2f8de-151">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="2f8de-151">Setup.bat</span></span>|<span data-ttu-id="2f8de-152">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f8de-152">Used to build and initialize this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="2f8de-153">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-153">How to Use This Sample</span></span>  
 <span data-ttu-id="2f8de-154">Use este ejemplo como ejemplo de trabajo de las acciones necesarias para enrutar un mensaje basándose en el contenido.</span><span class="sxs-lookup"><span data-stu-id="2f8de-154">Use this sample as a working example of the actions required to route a message based on content.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="2f8de-155">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-155">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="2f8de-156">Para crear e inicializar el ejemplo CBRSample, deberá crear e implementar el proyecto de BizTalk para este ejemplo, configurar la ubicación y el puerto de recepción, así como configurar dos puertos de envío diferentes.</span><span class="sxs-lookup"><span data-stu-id="2f8de-156">To build and initialize the CBRSample sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="2f8de-157">Para crear e implementar el proyecto de BizTalk para este ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-157">To build and deploy the BizTalk project for this sample</span></span>  
  
1.  <span data-ttu-id="2f8de-158">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="2f8de-158">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="2f8de-159">`<Samples Path>` **\Messaging\CBRSample**</span><span class="sxs-lookup"><span data-stu-id="2f8de-159">`<Samples Path>` **\Messaging\CBRSample**</span></span>  
  
2.  <span data-ttu-id="2f8de-160">Ejecutar **Setup.bat**, que realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2f8de-160">Run **Setup.bat**, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="2f8de-161">Crea la entrada (**en**) y las carpetas de salida (**US** y **puede**) para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f8de-161">Creates the input (**In**) and output folders (**US** and **CAN**) for this sample.</span></span>  
  
    -   <span data-ttu-id="2f8de-162">Compila e implementa el proyecto de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f8de-162">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="2f8de-163">Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="2f8de-163">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f8de-164">Este ejemplo muestra la siguiente advertencia al crear y enlazar los puertos:</span><span class="sxs-lookup"><span data-stu-id="2f8de-164">This sample displays the following warning when creating and binding the ports:</span></span>  
    >   
    >  <span data-ttu-id="2f8de-165">**Advertencia: No se especifica para el controlador de recepción "CBRReceiveLocation"; de la ubicación de recepción Actualizando con el primer controlador de recepción cuyo tipo de transporte coincidente.**</span><span class="sxs-lookup"><span data-stu-id="2f8de-165">**Warning: Receive handler not specified for receive location "CBRReceiveLocation"; updating with first receive handler with matching transport type.**</span></span>  
    >   
    >  <span data-ttu-id="2f8de-166">Puede omitir esta advertencia de forma segura.</span><span class="sxs-lookup"><span data-stu-id="2f8de-166">You can safely ignore this warning.</span></span> <span data-ttu-id="2f8de-167">(Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).</span><span class="sxs-lookup"><span data-stu-id="2f8de-167">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f8de-168">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="2f8de-168">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f8de-169">Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="2f8de-169">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="2f8de-170">Utilice este par de claves para firmar el ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="2f8de-170">Use this key pair to sign the resulting assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f8de-171">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="2f8de-171">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="2f8de-172">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="2f8de-172">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a><span data-ttu-id="2f8de-173">Para preparar la configuración de la ubicación y el puerto de recepción, así como de los puertos de envío</span><span class="sxs-lookup"><span data-stu-id="2f8de-173">To prepare to configure the receive port and location, and the send ports</span></span>  
  
1.  <span data-ttu-id="2f8de-174">En **Microsoft SQL Management Studio**, seleccione la base de datos de administración de BizTalk correcta.</span><span class="sxs-lookup"><span data-stu-id="2f8de-174">In **Microsoft SQL Management Studio**, select the correct BizTalk Management database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f8de-175">La base de datos de administración de BizTalk también se denomina la base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2f8de-175">The BizTalk Management database is also referred to as the BizTalk Configuration database.</span></span>  
  
#### <a name="to-configure-enlist-and-start-the-us-send-port"></a><span data-ttu-id="2f8de-176">Para configurar, dé de alta e inicie el puerto de envío estadounidense</span><span class="sxs-lookup"><span data-stu-id="2f8de-176">To configure, enlist, and start the U.S. send port</span></span>  
  
1.  <span data-ttu-id="2f8de-177">En la consola de administración de BizTalk Server, expanda **puertos de envío**, haga clic en **CBRUSSendPort**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="2f8de-177">In the BizTalk Server Administration console, expand **Send Ports**, right-click **CBRUSSendPort**, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="2f8de-178">En el **propiedades de puerto de envío de unidireccional estático** cuadro de diálogo, en el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; filtros**y, a continuación, agregue una nueva fila estableciendo  **Propiedad** a **CBRSample.CountryCode**, dejando el **operador** columna establecida en **==** y la configuración de la **Valor** columna **100**.</span><span class="sxs-lookup"><span data-stu-id="2f8de-178">In the **Static One-Way Send Port Properties** dialog box, in the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Filters**, and then add a new row by setting **Property** to **CBRSample.CountryCode**, leaving the **Operator** column set to **==**, and setting the **Value** column to **100**.</span></span>  
  
3.  <span data-ttu-id="2f8de-179">En el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; asignaciones de salida**, establezca el **asignar para aplicar** propiedad **CBRSample.CBRInput2USMap**, y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f8de-179">In the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Outbound Maps**, set the **Map to apply** property to **CBRSample.CBRInput2USMap**, and then click **OK**.</span></span> <span data-ttu-id="2f8de-180">Puede que tenga que hacer clic en el botón de desplazamiento para ver la asignación.</span><span class="sxs-lookup"><span data-stu-id="2f8de-180">You may have to click the scroll button to bring the map into view.</span></span>  
  
#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a><span data-ttu-id="2f8de-181">Para configurar, dé de alta e inicie el puerto de envío canadiense</span><span class="sxs-lookup"><span data-stu-id="2f8de-181">To configure, enlist, and start the Canadian send port</span></span>  
  
1.  <span data-ttu-id="2f8de-182">En la consola de administración de BizTalk Server, expanda **puertos de envío**, haga clic en **CBRCANSendPort**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="2f8de-182">In the BizTalk Server Administration console, expand **Send Ports**, right-click **CBRCANSendPort**, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="2f8de-183">En el **propiedades de puerto de envío de unidireccional estático** cuadro de diálogo, en el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; filtros**y, a continuación, agregue una nueva fila estableciendo  **Propiedad** a **CBRSample.CountryCode**, dejando el **operador** columna establecida en **==** y la configuración de la **Valor** columna **200**.</span><span class="sxs-lookup"><span data-stu-id="2f8de-183">In the **Static One-Way Send Port Properties** dialog box, in the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Filters**, and then add a new row by setting **Property** to **CBRSample.CountryCode**, leaving the **Operator** column set to **==**, and setting the **Value** column to **200**.</span></span>  
  
3.  <span data-ttu-id="2f8de-184">En el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; asignaciones de salida**, establezca el **asignar para aplicar** propiedad **CBRSample.CBRInput2CANMap** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f8de-184">In the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Outbound Maps**, set the **Map to apply** property to **CBRSample.CBRInput2CANMap**, and then click **OK**.</span></span>  
  
 <span data-ttu-id="2f8de-185">Mediante estos pasos se conecta el puerto de envío al puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2f8de-185">These steps connect the send port to the receive port.</span></span> <span data-ttu-id="2f8de-186">El ejemplo utiliza las propiedades promocionadas para enrutar los documentos.</span><span class="sxs-lookup"><span data-stu-id="2f8de-186">The sample uses promoted properties to route the documents.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2f8de-187"> está preparado para trabajar con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f8de-187"> is ready now to work with this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="2f8de-188">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-188">Running This Sample</span></span>  
 <span data-ttu-id="2f8de-189">Utilice el siguiente procedimiento para ejecutar el ejemplo CBRSample.</span><span class="sxs-lookup"><span data-stu-id="2f8de-189">Use the following procedure to run the CBRSample sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="2f8de-190">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-190">To run this sample</span></span>  
  
1.  <span data-ttu-id="2f8de-191">Copie los archivos de entrada, **CBRDataCAN.xml** y **CBRDataUS.xml**, en la carpeta de entrada siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f8de-191">Copy the input files, **CBRDataCAN.xml** and **CBRDataUS.xml**, into the following input folder:</span></span>  
  
     <span data-ttu-id="2f8de-192">`<Samples Path>` **\Messaging\CBRSample\In**</span><span class="sxs-lookup"><span data-stu-id="2f8de-192">`<Samples Path>` **\Messaging\CBRSample\In**</span></span>  
  
2.  <span data-ttu-id="2f8de-193">Observe cómo cada uno de estos archivos se transforma y enrutan a uno de los siguientes dos carpetas de salida en función del valor de sus **CountryCode** elemento (100 frente a 200):</span><span class="sxs-lookup"><span data-stu-id="2f8de-193">Observe how each of these files is transformed and routed to one of the following two output folders based on the value of their **CountryCode** element (100 versus 200):</span></span>  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2f8de-194"> transforma y enruta el archivo de entrada **CBRDataCAN.xml** a la carpeta:</span><span class="sxs-lookup"><span data-stu-id="2f8de-194"> transforms and routes the input file **CBRDataCAN.xml** to the folder:</span></span>  
  
         <span data-ttu-id="2f8de-195">`<Samples Path>` **\Messaging\CBRSample\CAN**</span><span class="sxs-lookup"><span data-stu-id="2f8de-195">`<Samples Path>` **\Messaging\CBRSample\CAN**</span></span>  
  
    -   <span data-ttu-id="2f8de-196">BizTalk Server transforma y enruta el archivo de entrada **CBRDataUS.xml** a la carpeta:</span><span class="sxs-lookup"><span data-stu-id="2f8de-196">BizTalk Server transforms and routes the input file **CBRDataUS.xml** to the folder:</span></span>  
  
         <span data-ttu-id="2f8de-197">`<Samples Path>` **\Messaging\CBRSample\US**</span><span class="sxs-lookup"><span data-stu-id="2f8de-197">`<Samples Path>` **\Messaging\CBRSample\US**</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="2f8de-198">Clases o métodos usados en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f8de-198">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="2f8de-199">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2f8de-199">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8de-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f8de-200">See Also</span></span>  
 <span data-ttu-id="2f8de-201">[Canalizaciones predeterminadas](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="2f8de-201">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="2f8de-202">[Cómo configurar asignaciones de salida para un puerto de envío](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="2f8de-202">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="2f8de-203">Messaging (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="2f8de-203">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)