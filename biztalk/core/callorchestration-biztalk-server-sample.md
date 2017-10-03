---
title: CallOrchestration (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, calling
- examples, orchestrations
ms.assetid: 0c4194f0-c1e2-419a-8a1a-a3c96e8d2667
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6460091297e34609365989739f58ed1f04204c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="callorchestration-biztalk-server-sample"></a><span data-ttu-id="58db2-102">CallOrchestration (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="58db2-102">CallOrchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="58db2-103">El ejemplo de CallOrchestration muestra cómo llamar a una orquestación de BizTalk desde otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="58db2-103">The CallOrchestration sample demonstrates how to call one BizTalk orchestration from another orchestration.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="58db2-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="58db2-104">What This Sample Does</span></span>  
 <span data-ttu-id="58db2-105">Este ejemplo muestra una orquestación que llama a otra orquestación mediante los pasos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="58db2-105">This sample demonstrates one orchestration calling another orchestration using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="58db2-106">La orquestación principal recibe un mensaje de pedido.</span><span class="sxs-lookup"><span data-stu-id="58db2-106">The primary orchestration receives a purchase order (PO) message.</span></span>  
  
2.  <span data-ttu-id="58db2-107">La orquestación principal llama a la secundaria para determinar el precio de envío del pedido.</span><span class="sxs-lookup"><span data-stu-id="58db2-107">The primary orchestration calls the secondary orchestration to determine the shipping price for the PO.</span></span>  
  
3.  <span data-ttu-id="58db2-108">La orquestación secundaria calcula el precio de envío solicitado y lo devuelve a la orquestación primaria.</span><span class="sxs-lookup"><span data-stu-id="58db2-108">The secondary orchestration calculates the requested shipping price and returns it to the primary orchestration.</span></span>  
  
4.  <span data-ttu-id="58db2-109">La orquestación principal actualiza el mensaje de pedido con el precio de envío.</span><span class="sxs-lookup"><span data-stu-id="58db2-109">The primary orchestration updates the PO message with the returned shipping price.</span></span>  
  
5.  <span data-ttu-id="58db2-110">La orquestación principal guarda el mensaje de pedido actualizado en una carpeta para que lo inspeccione.</span><span class="sxs-lookup"><span data-stu-id="58db2-110">The primary orchestration puts the updated PO message into a folder for your inspection.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="58db2-111">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="58db2-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="58db2-112">El objetivo principal de este ejemplo consiste en mostrar cómo llamar a una orquestación desde otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="58db2-112">The primary purpose of this sample is to show you how to call an orchestration from within another orchestration.</span></span> <span data-ttu-id="58db2-113">La posibilidad de llamar a orquestaciones permite dividir los procesos empresariales en componentes reutilizables.</span><span class="sxs-lookup"><span data-stu-id="58db2-113">The ability to call orchestrations gives you a way to divide your business processes into reusable components.</span></span> <span data-ttu-id="58db2-114">Puede descomponer sus procesos comunes en orquestaciones independientes para que otras personas puedan reutilizarlos.</span><span class="sxs-lookup"><span data-stu-id="58db2-114">You can factor your common processes out into separate orchestrations for others to re-use.</span></span>  
  
 <span data-ttu-id="58db2-115">En este ejemplo, el **orquestación de llamada** forma en receivePO.odx invoca findShippingPrice.odx y espera a que la orquestación anidada, findShippingPrice.odx, para calcular y devolver el precio de envío antes de enviar la compra orden.</span><span class="sxs-lookup"><span data-stu-id="58db2-115">In this sample, the **Call Orchestration** shape in receivePO.odx invokes findShippingPrice.odx and waits for the nested orchestration, findShippingPrice.odx, to calculate and return the shipping price before sending the purchase order.</span></span> <span data-ttu-id="58db2-116">La orquestación findShippingPrice.odx utiliza la siguiente lógica para calcular el precio de envío:</span><span class="sxs-lookup"><span data-stu-id="58db2-116">The orchestration findShippingPrice.odx uses the following logic to calculate the shipping price:</span></span>  
  
```  
If ( weight * shippingRate ) < minShippingPrice Then  
    shippingPrice = minShippingPrice  
Else  
    shippingPrice = weight * shippingRate  
End If  
```  
  
 <span data-ttu-id="58db2-117">El archivo de pedido de entrada de ejemplo, InputPO.xml, especifica un peso de 20, lo que da como resultado que el mensaje de pedido de salida haya cambiado el precio de envío de 10 a 20.</span><span class="sxs-lookup"><span data-stu-id="58db2-117">The sample input PO file, InputPO.xml, specifies a weight of 20, resulting in the output PO message having its shipping price changed from 10 to 20.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58db2-118">No puede llamar a una transacción de larga ejecución desde una orquestación atómica.</span><span class="sxs-lookup"><span data-stu-id="58db2-118">You cannot call a long-running transaction from an atomic orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58db2-119">La diferencia entre utilizar el **orquestación de llamada** forma y el **Iniciar orquestación** forma es que al llamar a una orquestación, el llamador espera a que la orquestación anidada finalice antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="58db2-119">The difference between using the **Call Orchestration** shape and the **Start Orchestration** shape is that when calling an orchestration, the caller waits for the nested orchestration to return before continuing.</span></span> <span data-ttu-id="58db2-120">Al iniciar una orquestación desde una orquestación, una vez que el autor de la llamada inicia la acción, pasa al siguiente paso del flujo de procesos.</span><span class="sxs-lookup"><span data-stu-id="58db2-120">When starting an orchestration from an orchestration, after the caller initiates the action, the caller moves forward to the next step in the process flow.</span></span> <span data-ttu-id="58db2-121">La orquestación invocada por el autor de la llamada se ejecuta de forma independiente hasta que finaliza el flujo de procesos.</span><span class="sxs-lookup"><span data-stu-id="58db2-121">The orchestration that was invoked by the caller runs independently until it finishes the process flow.</span></span> <span data-ttu-id="58db2-122">Para obtener más información, consulte [cómo configurar la forma de orquestación llame a](../core/how-to-configure-the-call-orchestration-shape.md).</span><span class="sxs-lookup"><span data-stu-id="58db2-122">For more information, see [How to Configure the Call Orchestration Shape](../core/how-to-configure-the-call-orchestration-shape.md).</span></span> <span data-ttu-id="58db2-123">Consulte también [cómo configurar la forma de orquestación iniciar](../core/how-to-configure-the-start-orchestration-shape.md).</span><span class="sxs-lookup"><span data-stu-id="58db2-123">Also see [How to Configure the Start Orchestration Shape](../core/how-to-configure-the-start-orchestration-shape.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="58db2-124">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="58db2-124">Where to Find This Sample</span></span>  
 <span data-ttu-id="58db2-125">\<*Ejemplos de ruta de acceso*> \Orchestrations\CallOrchestration\\</span><span class="sxs-lookup"><span data-stu-id="58db2-125">\<*Samples Path*>\Orchestrations\CallOrchestration\\</span></span>  
  
 <span data-ttu-id="58db2-126">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="58db2-126">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="58db2-127">Archivos</span><span class="sxs-lookup"><span data-stu-id="58db2-127">File(s)</span></span>|<span data-ttu-id="58db2-128">Description</span><span class="sxs-lookup"><span data-stu-id="58db2-128">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58db2-129">CallOrchestration.btproj, CallOrchestration.sln</span><span class="sxs-lookup"><span data-stu-id="58db2-129">CallOrchestration.btproj, CallOrchestration.sln</span></span>|<span data-ttu-id="58db2-130">Archivos de proyectos y de soluciones de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58db2-130">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="58db2-131">CallOrchestrationBinding.xml</span><span class="sxs-lookup"><span data-stu-id="58db2-131">CallOrchestrationBinding.xml</span></span>|<span data-ttu-id="58db2-132">Se utiliza para la instalación automatizada, como el enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="58db2-132">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="58db2-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="58db2-133">Cleanup.bat</span></span>|<span data-ttu-id="58db2-134">Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="58db2-134">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="58db2-135">Quita los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="58db2-135">Removes send and receive ports.</span></span> <span data-ttu-id="58db2-136">Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="58db2-136">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="58db2-137">findShippingPrice.odx</span><span class="sxs-lookup"><span data-stu-id="58db2-137">findShippingPrice.odx</span></span>|<span data-ttu-id="58db2-138">La orquestación de BizTalk que sirve como orquestación secundaria llamada desde la orquestación principal, receivePO.odx.</span><span class="sxs-lookup"><span data-stu-id="58db2-138">BizTalk orchestration that serves as a secondary orchestration, called from the primary orchestration, receivePO.odx.</span></span>|  
|<span data-ttu-id="58db2-139">InputPO.xml</span><span class="sxs-lookup"><span data-stu-id="58db2-139">InputPO.xml</span></span>|<span data-ttu-id="58db2-140">El mensaje de pedido de entrada de ejemplo que se ajusta al esquema definido en el archivo PO.xsd.</span><span class="sxs-lookup"><span data-stu-id="58db2-140">Sample input PO message that conforms to the schema defined in the file PO.xsd.</span></span>|  
|<span data-ttu-id="58db2-141">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="58db2-141">PO.xsd</span></span>|<span data-ttu-id="58db2-142">El esquema que define la estructura de mensajes de pedidos entrantes, como el archivo de entrada de ejemplo InputPO.xml, y define la promoción de propiedades de los tres elementos del esquema.</span><span class="sxs-lookup"><span data-stu-id="58db2-142">Schema that defines the structure of inbound PO messages such as the sample input file InputPO.xml, and defines property promotion for all three elements in the schema.</span></span>|  
|<span data-ttu-id="58db2-143">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="58db2-143">PropertySchema.xsd</span></span>|<span data-ttu-id="58db2-144">El archivo de esquema de propiedad que participa en la promoción de propiedades de los tres elementos del esquema PO.xsd.</span><span class="sxs-lookup"><span data-stu-id="58db2-144">Property schema file that participates in property promotion for all three elements in the schema PO.xsd.</span></span>|  
|<span data-ttu-id="58db2-145">receivePO.odx</span><span class="sxs-lookup"><span data-stu-id="58db2-145">receivePO.odx</span></span>|<span data-ttu-id="58db2-146">La orquestación de BizTalk que sirve como orquestación principal en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58db2-146">BizTalk orchestration that serves as the primary orchestration in this sample.</span></span> <span data-ttu-id="58db2-147">Recupera los mensajes de pedido de la carpeta de recepción y llama a la otra orquestación, findShippingPrice.odx, para calcular y actualizar el precio de envío.</span><span class="sxs-lookup"><span data-stu-id="58db2-147">It retrieves PO messages from the receive folder and then calls the other orchestration, findShippingPrice.odx, to calculate and update the shipping price.</span></span>|  
|<span data-ttu-id="58db2-148">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="58db2-148">Setup.bat</span></span>|<span data-ttu-id="58db2-149">Se utiliza para crear e iniciar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58db2-149">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="58db2-150">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="58db2-150">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-callorchestration-sample"></a><span data-ttu-id="58db2-151">Para crear e iniciar el ejemplo de CallOrchestration</span><span class="sxs-lookup"><span data-stu-id="58db2-151">To build and initialize the CallOrchestration sample</span></span>  
  
1.  <span data-ttu-id="58db2-152">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="58db2-152">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="58db2-153">\<*Ejemplos de ruta de acceso*> \Orchestrations\CallOrchestration\\</span><span class="sxs-lookup"><span data-stu-id="58db2-153">\<*Samples Path*>\Orchestrations\CallOrchestration\\</span></span>  
  
2.  <span data-ttu-id="58db2-154">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="58db2-154">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="58db2-155">Crea las carpetas de entrada (In) y salida (Out) de este ejemplo en la carpeta CallOrchestration.</span><span class="sxs-lookup"><span data-stu-id="58db2-155">Creates the input (In) and output (Out) folders for this sample in the CallOrchestration folder.</span></span>  
  
    -   <span data-ttu-id="58db2-156">Compila e implementa el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] que contiene las dos orquestaciones de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58db2-156">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project, containing both orchestrations, for this sample.</span></span>  
  
    -   <span data-ttu-id="58db2-157">Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="58db2-157">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="58db2-158">Habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="58db2-158">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58db2-159">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="58db2-159">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="58db2-160">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="58db2-160">Running This Sample</span></span>  
  
#### <a name="to-run-the-callorchestration-sample"></a><span data-ttu-id="58db2-161">Para ejecutar el ejemplo de CallOrchestration</span><span class="sxs-lookup"><span data-stu-id="58db2-161">To run the CallOrchestration sample</span></span>  
  
1.  <span data-ttu-id="58db2-162">Guarde una copia del archivo InputPO.xml en la carpeta In.</span><span class="sxs-lookup"><span data-stu-id="58db2-162">Put a copy of the file InputPO.xml into the In folder.</span></span>  
  
2.  <span data-ttu-id="58db2-163">Observe el archivo de pedido XML actualizado creado en la carpeta Out.</span><span class="sxs-lookup"><span data-stu-id="58db2-163">Observe the updated XML PO file created in the Out folder.</span></span> <span data-ttu-id="58db2-164">Contiene el mensaje de pedido original, modificado para incluir el costo de envío calculado del modo explicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="58db2-164">It contains the original PO message, modified to include a shipping cost calculated as explained earlier.</span></span> <span data-ttu-id="58db2-165">El formato del nombre de este archivo es \< *MessageID*> .xml, donde  *\<MessageID >* es el GUID generado para identificar de forma exclusiva el mensaje.</span><span class="sxs-lookup"><span data-stu-id="58db2-165">The format of the name of this file is \<*MessageID*>.xml, where *\<MessageID>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="58db2-166">Desinstalar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="58db2-166">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-callorchestration-sample"></a><span data-ttu-id="58db2-167">Para desinstalar el ejemplo CallOrchestration</span><span class="sxs-lookup"><span data-stu-id="58db2-167">To uninstall the CallOrchestration sample</span></span>  
  
1.  <span data-ttu-id="58db2-168">En una ventana de comandos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="58db2-168">In a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="58db2-169">\<*Ejemplos de ruta de acceso*> \Orchestrations\CallOrchestration\\</span><span class="sxs-lookup"><span data-stu-id="58db2-169">\<*Samples Path*>\Orchestrations\CallOrchestration\\</span></span>  
  
2.  <span data-ttu-id="58db2-170">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="58db2-170">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58db2-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="58db2-171">See Also</span></span>  
 [<span data-ttu-id="58db2-172">Orquestaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="58db2-172">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)