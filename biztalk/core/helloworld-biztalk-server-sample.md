---
title: HelloWorld (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, messages
ms.assetid: 4416029a-ca76-45a4-b66c-b44cb71ded58
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77c9a45e6314a4fc36fca8604677d7bd4b69098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966613"
---
# <a name="helloworld-biztalk-server-sample"></a><span data-ttu-id="e5079-102">HelloWorld (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e5079-102">HelloWorld (BizTalk Server Sample)</span></span>
<span data-ttu-id="e5079-103">En el ejemplo HelloWorld se muestra cómo utilizar orquestaciones de BizTalk para convertir un mensaje XML (un pedido), a un tipo de mensaje (una factura) relacionado pero distinto.</span><span class="sxs-lookup"><span data-stu-id="e5079-103">The HelloWorld sample demonstrates how to use BizTalk orchestrations to convert an XML message (a purchase order) into a related, but distinct, type of message (an invoice).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e5079-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5079-104">What This Sample Does</span></span>  
 <span data-ttu-id="e5079-105">Este ejemplo se configura el **en** carpeta como ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e5079-105">This sample configures the **In** folder as a receive location.</span></span> <span data-ttu-id="e5079-106">Cuando coloca un archivo, por ejemplo, el archivo de ejemplo **SamplePOInput.xml**, en esta carpeta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa el mensaje mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e5079-106">When you place a file, such as the sample file **SamplePOInput.xml**, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message using the following steps:</span></span>  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e5079-107"> recupera el de mensajes de pedido XML desde la carpeta de ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e5079-107"> retrieves the XML purchase order message from the receive location folder.</span></span>  
  
2. <span data-ttu-id="e5079-108">La orquestación utiliza el archivo de asignación para crear una factura XML del pedido XML.</span><span class="sxs-lookup"><span data-stu-id="e5079-108">The orchestration uses the map file to create an XML invoice from the XML purchase order.</span></span>  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e5079-109"> coloca el mensaje de factura XML resultante en el adaptador de envío **Out** carpeta.</span><span class="sxs-lookup"><span data-stu-id="e5079-109"> places the resulting XML invoice message into the send adapter **Out** folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="e5079-110">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="e5079-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="e5079-111">En un contexto de intercambio de mensajes entre empresas, a menudo es necesario convertir mensajes entrantes recibidos de los socios comerciales a un formato que puedan reconocer las aplicaciones internas.</span><span class="sxs-lookup"><span data-stu-id="e5079-111">In an intercompany message-exchange scenario, it is often necessary to convert inbound messages received from trading partners into a format that internal applications can recognize.</span></span> <span data-ttu-id="e5079-112">Este ejemplo utiliza un **recepción** forma, un **transformar** forma y un **enviar** forma para lograr este resultado.</span><span class="sxs-lookup"><span data-stu-id="e5079-112">This sample uses a **Receive** shape, a **Transform** shape, and a **Send** shape to achieve this result.</span></span> <span data-ttu-id="e5079-113">El **transformar** forma desempeña una función importante en este ejemplo porque es donde se produce la conversión de formato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e5079-113">The **Transform** shape plays the important role in this sample because it is where the message format conversion occurs.</span></span> <span data-ttu-id="e5079-114">Arrastrar un **transformar** en la orquestación y dar forma a configurar el mensaje de origen, el nombre de mapa y el mensaje de destino para ella.</span><span class="sxs-lookup"><span data-stu-id="e5079-114">You drag a **Transform** shape into your orchestration and configure the source message, map name, and destination message for it.</span></span> <span data-ttu-id="e5079-115">Durante el tiempo de ejecución, el mensaje de origen se asigna al mensaje de destino mediante la asignación que designó.</span><span class="sxs-lookup"><span data-stu-id="e5079-115">During run time, the source message is mapped to the destination message by using the map you designated.</span></span>  
  
 <span data-ttu-id="e5079-116">Para obtener más información sobre la **transformar** forma, vea [cómo configurar la forma transformación](../core/how-to-configure-the-transform-shape.md).</span><span class="sxs-lookup"><span data-stu-id="e5079-116">For more information about the **Transform** shape, see [How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md).</span></span> <span data-ttu-id="e5079-117">Para obtener más información sobre la creación de un mapa, consulte [crear mapas de uso del asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).</span><span class="sxs-lookup"><span data-stu-id="e5079-117">For more information about building a map, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e5079-118">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5079-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="e5079-119">\<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="e5079-119">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span></span>  
  
 <span data-ttu-id="e5079-120">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="e5079-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e5079-121">Archivos</span><span class="sxs-lookup"><span data-stu-id="e5079-121">File(s)</span></span>|<span data-ttu-id="e5079-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5079-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5079-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="e5079-123">Cleanup.bat</span></span>|<span data-ttu-id="e5079-124">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="e5079-124">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="e5079-125">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="e5079-125">Removes send and receive ports.</span></span> <span data-ttu-id="e5079-126">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e5079-126">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="e5079-127">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="e5079-127">HelloOrchestration.odx</span></span>|<span data-ttu-id="e5079-128">Orquestación que coordina la conversión del pedido en una factura.</span><span class="sxs-lookup"><span data-stu-id="e5079-128">Orchestration that coordinates the conversion of the purchase order into an invoice.</span></span>|  
|<span data-ttu-id="e5079-129">HelloWorld.btproj HelloWorld.sln</span><span class="sxs-lookup"><span data-stu-id="e5079-129">HelloWorld.btproj, HelloWorld.sln</span></span>|<span data-ttu-id="e5079-130">Archivos de proyectos y de soluciones de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5079-130">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="e5079-131">HelloWorldBinding.xml</span><span class="sxs-lookup"><span data-stu-id="e5079-131">HelloWorldBinding.xml</span></span>|<span data-ttu-id="e5079-132">Se usa para la instalación automatizada, como el enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="e5079-132">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="e5079-133">InvoiceSchema.xsd POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="e5079-133">InvoiceSchema.xsd, POSchema.xsd</span></span>|<span data-ttu-id="e5079-134">Esquemas para los mensajes de factura y de pedido, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e5079-134">Schemas for the invoice and purchase order messages, respectively.</span></span>|  
|<span data-ttu-id="e5079-135">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="e5079-135">POToInvoice.btm</span></span>|<span data-ttu-id="e5079-136">Asignación para convertir el pedido en una factura.</span><span class="sxs-lookup"><span data-stu-id="e5079-136">Map for converting the purchase order to an invoice.</span></span>|  
|<span data-ttu-id="e5079-137">SamplePOInput.xml</span><span class="sxs-lookup"><span data-stu-id="e5079-137">SamplePOInput.xml</span></span>|<span data-ttu-id="e5079-138">Archivo de entrada de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5079-138">Sample input file.</span></span>|  
|<span data-ttu-id="e5079-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="e5079-139">Setup.bat</span></span>|<span data-ttu-id="e5079-140">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5079-140">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e5079-141">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5079-141">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a><span data-ttu-id="e5079-142">Para crear e iniciar el ejemplo HelloWorld</span><span class="sxs-lookup"><span data-stu-id="e5079-142">To build and initialize the HelloWorld sample</span></span>  
  
1. <span data-ttu-id="e5079-143">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="e5079-143">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="e5079-144">\<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="e5079-144">\<*Samples Path*\>\Orchestrations\HelloWorld</span></span>  
  
2. <span data-ttu-id="e5079-145">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e5079-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="e5079-146">Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5079-146">Creates the input (In) and output (Out) folders for this sample in the following folder:</span></span>  
  
      <span data-ttu-id="e5079-147">\<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="e5079-147">\<*Samples Path*\>\Orchestrations\HelloWorld</span></span>  
  
   - <span data-ttu-id="e5079-148">Compila el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5079-148">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
   - <span data-ttu-id="e5079-149">Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e5079-149">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports to the orchestration.</span></span>  
  
   - <span data-ttu-id="e5079-150">Habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="e5079-150">Enables the receive location, and starts the send port.</span></span> <span data-ttu-id="e5079-151">Da de alta e inicia la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e5079-151">Enlists and starts orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5079-152">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="e5079-152">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="e5079-153">Lo puede confirmar si ve sus registros de sucesos.</span><span class="sxs-lookup"><span data-stu-id="e5079-153">You can confirm this by viewing your event logs.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="e5079-154">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5079-154">Running This Sample</span></span>  
  
#### <a name="to-run-the-helloworld-sample"></a><span data-ttu-id="e5079-155">Para ejecutar el ejemplo HelloWorld</span><span class="sxs-lookup"><span data-stu-id="e5079-155">To run the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="e5079-156">Pegue una copia del archivo SamplePOInput.xml en la **en** carpeta.</span><span class="sxs-lookup"><span data-stu-id="e5079-156">Paste a copy of the file SamplePOInput.xml into the **In** folder.</span></span>  
  
2.  <span data-ttu-id="e5079-157">Observe el archivo .xml creado en el **Out** carpeta.</span><span class="sxs-lookup"><span data-stu-id="e5079-157">Observe the .xml file created in the **Out** folder.</span></span> <span data-ttu-id="e5079-158">Este archivo contiene la factura XML construida del archivo de entrada SamplePOInput.xml.</span><span class="sxs-lookup"><span data-stu-id="e5079-158">This file contains the XML invoice constructed from the input file SamplePOInput.xml.</span></span> <span data-ttu-id="e5079-159">El formato del nombre de este archivo es \< *MessageID*\>.xml, donde *\<MessageID\>* es el GUID generado para identificar de forma única el mensaje .</span><span class="sxs-lookup"><span data-stu-id="e5079-159">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="e5079-160">Desinstalar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5079-160">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-helloworld-sample"></a><span data-ttu-id="e5079-161">Para desinstalar el ejemplo HelloWorld</span><span class="sxs-lookup"><span data-stu-id="e5079-161">To uninstall the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="e5079-162">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="e5079-162">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="e5079-163">\<*Ejemplos de la ruta de acceso*\>\Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="e5079-163">\<*Samples Path*\>\Orchestrations\HelloWorld\\</span></span>  
  
2.  <span data-ttu-id="e5079-164">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="e5079-164">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5079-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5079-165">See Also</span></span>  
 [<span data-ttu-id="e5079-166">Orquestaciones (carpetas de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e5079-166">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)