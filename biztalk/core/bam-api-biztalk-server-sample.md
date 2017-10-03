---
title: API de BAM (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, APIs
- examples, BAM
- BAM, examples
- APIs, BAM
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9953bb5e8b1e9827189e5b618f2760297c5678
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-api-biztalk-server-sample"></a><span data-ttu-id="970b3-102">API de BAM (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="970b3-102">BAM API (BizTalk Server Sample)</span></span>
<span data-ttu-id="970b3-103">El ejemplo de API de BAM ilustra el modo de incorporar llamadas a la API de BAM en una aplicación para guardar información de claves que podrá supervisar.</span><span class="sxs-lookup"><span data-stu-id="970b3-103">The BAM API sample illustrates how to incorporate calls to the BAM API into an application to save key information that you can monitor.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="970b3-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="970b3-104">What This Sample Does</span></span>  
 <span data-ttu-id="970b3-105">En este ejemplo se implementa un escenario simple de compra.</span><span class="sxs-lookup"><span data-stu-id="970b3-105">This sample implements a simple purchasing scenario.</span></span> <span data-ttu-id="970b3-106">Genera pedidos de compra, procesa cada pedido de compra, crea envíos y crea y procesa facturas.</span><span class="sxs-lookup"><span data-stu-id="970b3-106">It generates purchase orders, processes each purchase order, creates shipments, and creates and processes invoices.</span></span> <span data-ttu-id="970b3-107">Según se ejecuta el ejemplo, crea y actualiza actividades BAM para reflejar los detalles y la disposición de los pedidos de compra y facturas.</span><span class="sxs-lookup"><span data-stu-id="970b3-107">As the sample runs, it creates and updates BAM activities to reflect the details and disposition of the purchase orders and invoices.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="970b3-108">Cómo y por qué se ha diseñado este ejemplo</span><span class="sxs-lookup"><span data-stu-id="970b3-108">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="970b3-109">Este ejemplo se ha diseñado para ilustrar cómo se usa BAM para almacenar información de una aplicación que no es una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="970b3-109">This sample was designed to illustrate how to use BAM to store information from an application that is not a BizTalk orchestration.</span></span> <span data-ttu-id="970b3-110">Aunque la aplicación es sencilla, ilustra diversos aspectos de BAM que es probable que use en una aplicación de producción.</span><span class="sxs-lookup"><span data-stu-id="970b3-110">While the application is simple, it illustrates several aspects of BAM that you are likely to use in a production application.</span></span> <span data-ttu-id="970b3-111">Entre ellas, figuran:</span><span class="sxs-lookup"><span data-stu-id="970b3-111">These include the following:</span></span>  
  
-   <span data-ttu-id="970b3-112">Varios subprocesos que contribuyen a una sola actividad</span><span class="sxs-lookup"><span data-stu-id="970b3-112">Multiple threads that contribute to a single activity</span></span>  
  
-   <span data-ttu-id="970b3-113">Creación de una relación entre dos actividades</span><span class="sxs-lookup"><span data-stu-id="970b3-113">Creating a relationship between two activities</span></span>  
  
-   <span data-ttu-id="970b3-114">Uso de una continuación para permitir que se pueda obtener acceso a la misma actividad con diferentes identificadores</span><span class="sxs-lookup"><span data-stu-id="970b3-114">Using a continuation to allow the same activity to be accessed with different IDs</span></span>  
  
 <span data-ttu-id="970b3-115">El ejemplo de API de BAM consta de tres clases principales: uno para procesar la compra ordena, una para procesar envíos y otra para procesar facturas.</span><span class="sxs-lookup"><span data-stu-id="970b3-115">The BAM API sample consists of three main classes: one to process purchase orders, one to process shipments, and one to process invoices.</span></span> <span data-ttu-id="970b3-116">Cada clase tiene un **RunOnce** método que recupera un mensaje de una cola y, a continuación, procesa el mensaje.</span><span class="sxs-lookup"><span data-stu-id="970b3-116">Each class has a **RunOnce** method that retrieves a message from a queue, and then processes the message.</span></span> <span data-ttu-id="970b3-117">Cada clase tiene también una **ejecutar** método que continuamente llama el **RunOnce** método.</span><span class="sxs-lookup"><span data-stu-id="970b3-117">Each class also has a **Run** method that continually calls the **RunOnce** method.</span></span>  
  
 <span data-ttu-id="970b3-118">El **RunOnce** método de la **PoApplication** clase hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="970b3-118">The **RunOnce** method of the **PoApplication** class does the following:</span></span>  
  
1.  <span data-ttu-id="970b3-119">Crea un mensaje XML que representa un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="970b3-119">Creates an XML message that represents a purchase order.</span></span>  
  
2.  <span data-ttu-id="970b3-120">Comienza una actividad BAMApiPo y se agrega a la información de actividad acerca del pedido de compra y cuándo se recibió.</span><span class="sxs-lookup"><span data-stu-id="970b3-120">Begins a BAMApiPo activity and adds to the activity information about the purchase order and when it was received.</span></span>  
  
3.  <span data-ttu-id="970b3-121">Aprueba arbitrariamente o rechaza el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="970b3-121">Arbitrarily approves or rejects the purchase order.</span></span>  
  
4.  <span data-ttu-id="970b3-122">Actualiza la actividad BAMApiPo para registrar el estado del pedido de compra (aceptado o rechazado).</span><span class="sxs-lookup"><span data-stu-id="970b3-122">Updates the BAMApiPo activity to record the status of the purchase order (accepted or rejected).</span></span>  
  
5.  <span data-ttu-id="970b3-123">Si se aceptó el pedido de compra, la **RunOnce** método también hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="970b3-123">If the purchase order was accepted, the **RunOnce** method also does the following:</span></span>  
  
    1.  <span data-ttu-id="970b3-124">Crea un mensaje XML para representar un paquete que se va a enviar y agrega el mensaje a la cola de envíos.</span><span class="sxs-lookup"><span data-stu-id="970b3-124">Creates an XML message to represent a package to be shipped, and adds the message to the queue of shipments.</span></span>  
  
    2.  <span data-ttu-id="970b3-125">Agrega el mensaje XML que representa el pedido de compra a la cola de pedidos de compra que se van a incluir en una factura.</span><span class="sxs-lookup"><span data-stu-id="970b3-125">Adds the XML message that represents the purchase order to the queue of purchase orders to be included in an invoice.</span></span>  
  
    3.  <span data-ttu-id="970b3-126">Permite la continuación de la actividad BAMApiPo.</span><span class="sxs-lookup"><span data-stu-id="970b3-126">Enables continuation for the BAMApiPo activity.</span></span>  
  
    4.  <span data-ttu-id="970b3-127">Finaliza la actividad BAMApiPo.</span><span class="sxs-lookup"><span data-stu-id="970b3-127">Ends the BAMApiPo activity.</span></span>  
  
 <span data-ttu-id="970b3-128">El **RunOnce** método de la **ShipmentApplication** clase hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="970b3-128">The **RunOnce** method of the **ShipmentApplication** class does the following:</span></span>  
  
1.  <span data-ttu-id="970b3-129">Recupera de su cola un mensaje XML que representa un paquete que se van a enviar.</span><span class="sxs-lookup"><span data-stu-id="970b3-129">Retrieves from its queue an XML message that represents a package to be shipped.</span></span>  
  
2.  <span data-ttu-id="970b3-130">Actualiza la actividad BAMApiPo para registrar la hora en la que se envió el paquete.</span><span class="sxs-lookup"><span data-stu-id="970b3-130">Updates the BAMApiPo activity to record the time that the package was shipped.</span></span>  
  
3.  <span data-ttu-id="970b3-131">Finaliza la actividad BAMApiPo.</span><span class="sxs-lookup"><span data-stu-id="970b3-131">Ends the BAMApiPo activity.</span></span>  
  
 <span data-ttu-id="970b3-132">El **RunOnce** método de la **InvoiceApplication** clase hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="970b3-132">The **RunOnce** method of the **InvoiceApplication** class does the following:</span></span>  
  
1.  <span data-ttu-id="970b3-133">Recupera de su cola un mensaje XML que representa un pedido de compra que se va a facturar.</span><span class="sxs-lookup"><span data-stu-id="970b3-133">Retrieves from its queue an XML message that represents a purchase order to be invoiced.</span></span>  
  
2.  <span data-ttu-id="970b3-134">Comienza una actividad BAMApiInvoice.</span><span class="sxs-lookup"><span data-stu-id="970b3-134">Begins a BAMApiInvoice activity.</span></span>  
  
3.  <span data-ttu-id="970b3-135">Crea una relación BAM entre la actividad BAMApiInvoice y la actividad BAMApiPo para el pedido de compra que se va a facturar.</span><span class="sxs-lookup"><span data-stu-id="970b3-135">Creates a BAM relationship between the BAMApiInvoice activity and the BAMApiPo activity for the purchase order that is being invoiced.</span></span>  
  
4.  <span data-ttu-id="970b3-136">Agrega a la actividad BAMApiPo información acerca de la factura y su hora de creación.</span><span class="sxs-lookup"><span data-stu-id="970b3-136">Adds to the BAMApiPo activity information about the invoice and the time it was created.</span></span>  
  
5.  <span data-ttu-id="970b3-137">Después de un retraso arbitrario para simular la espera a que se abone la factura, agrega a la actividad BAMApiInvoice la hora en que se pagó la factura.</span><span class="sxs-lookup"><span data-stu-id="970b3-137">After an arbitrary delay to simulate waiting for the invoice to be paid, adds to the BAMApiInvoice activity the time the invoice was paid.</span></span>  
  
6.  <span data-ttu-id="970b3-138">Finaliza la actividad BAMApiInvoice.</span><span class="sxs-lookup"><span data-stu-id="970b3-138">Ends the BAMApiInvoice activity.</span></span>  
  
 <span data-ttu-id="970b3-139">El **Main** método de la **MainApp** clase inicializa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="970b3-139">The **Main** method of the **MainApp** class initializes the application.</span></span> <span data-ttu-id="970b3-140">Realiza las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="970b3-140">It does the following:</span></span>  
  
1.  <span data-ttu-id="970b3-141">Crea un **DirectEventStream** objeto.</span><span class="sxs-lookup"><span data-stu-id="970b3-141">Creates a **DirectEventStream** object.</span></span>  
  
2.  <span data-ttu-id="970b3-142">Inicia varios subprocesos y llama a la **ejecutar** método de la **POApplication** objeto en cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="970b3-142">Starts several threads, and calls the **Run** method of the **POApplication** object in each thread.</span></span>  
  
3.  <span data-ttu-id="970b3-143">Inicia varios subprocesos y llama a la **ejecutar** método de la **ShipmentApplication** objeto en cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="970b3-143">Starts several threads, and calls the **Run** method of the **ShipmentApplication** object in each thread.</span></span>  
  
4.  <span data-ttu-id="970b3-144">Inicia varios subprocesos y llama a la **ejecutar** método de la **InvoiceApplication** objeto en cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="970b3-144">Starts several threads, and calls the **Run** method of the **InvoiceApplication** object in each thread.</span></span>  
  
 <span data-ttu-id="970b3-145">El **Global** clase define las constantes que se usan por la aplicación de ejemplo, como el número de subprocesos para crear y el porcentaje de los pedidos de compra para rechazar.</span><span class="sxs-lookup"><span data-stu-id="970b3-145">The **Global** class defines constants that are used by the sample application, such as the number of threads to create and the percentage of purchase orders to reject.</span></span>  
  
 <span data-ttu-id="970b3-146">Además de la solución [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], el ejemplo también contiene un archivo Microsoft [!INCLUDE[btsExcel](../includes/btsexcel-md.md)] que define las actividades.</span><span class="sxs-lookup"><span data-stu-id="970b3-146">In addition to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution, the sample also contains a Microsoft [!INCLUDE[btsExcel](../includes/btsexcel-md.md)] file that defines the activities.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="970b3-147">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="970b3-147">Where to Find This Sample</span></span>  
 <span data-ttu-id="970b3-148">Puede encontrar este ejemplo en  *\<ruta de ejemplos >*\BAM\BamApiSample.</span><span class="sxs-lookup"><span data-stu-id="970b3-148">You can find this sample at *\<Samples Path>*\BAM\BamApiSample.</span></span>  
  
 <span data-ttu-id="970b3-149">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="970b3-149">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="970b3-150">Archivo</span><span class="sxs-lookup"><span data-stu-id="970b3-150">File</span></span>|<span data-ttu-id="970b3-151">Description</span><span class="sxs-lookup"><span data-stu-id="970b3-151">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="970b3-152">BamApiSample.cs</span><span class="sxs-lookup"><span data-stu-id="970b3-152">BamApiSample.cs</span></span>|<span data-ttu-id="970b3-153">Aplicación instrumentada.</span><span class="sxs-lookup"><span data-stu-id="970b3-153">Instrumented application.</span></span>|  
|<span data-ttu-id="970b3-154">BamApiSample.csproj</span><span class="sxs-lookup"><span data-stu-id="970b3-154">BamApiSample.csproj</span></span>|<span data-ttu-id="970b3-155">Proyecto de aplicación instrumentada.</span><span class="sxs-lookup"><span data-stu-id="970b3-155">Instrumented application project.</span></span>|  
|<span data-ttu-id="970b3-156">BamApiSample.sln</span><span class="sxs-lookup"><span data-stu-id="970b3-156">BamApiSample.sln</span></span>|<span data-ttu-id="970b3-157">Solución de aplicación instrumentada.</span><span class="sxs-lookup"><span data-stu-id="970b3-157">Instrumented application solution.</span></span>|  
|<span data-ttu-id="970b3-158">BamApiSample.xls</span><span class="sxs-lookup"><span data-stu-id="970b3-158">BamApiSample.xls</span></span>|<span data-ttu-id="970b3-159">Hoja de estilos de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="970b3-159">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="970b3-160">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="970b3-160">Cleanup.bat</span></span>|<span data-ttu-id="970b3-161">Archivo por lotes para quitar archivos de ejemplo implementados.</span><span class="sxs-lookup"><span data-stu-id="970b3-161">Batch file to remove deployed sample files.</span></span>|  
|<span data-ttu-id="970b3-162">Input.txt</span><span class="sxs-lookup"><span data-stu-id="970b3-162">Input.txt</span></span>|<span data-ttu-id="970b3-163">Entrada de configuración del interceptor de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="970b3-163">Sample interceptor configuration input.</span></span>|  
|<span data-ttu-id="970b3-164">InterceptorConfig.cs</span><span class="sxs-lookup"><span data-stu-id="970b3-164">InterceptorConfig.cs</span></span>|<span data-ttu-id="970b3-165">Código de configuración de interceptor del ejemplo de API.</span><span class="sxs-lookup"><span data-stu-id="970b3-165">Interceptor configuration code for API sample.</span></span>|  
|<span data-ttu-id="970b3-166">InterceptorConfig.csproj</span><span class="sxs-lookup"><span data-stu-id="970b3-166">InterceptorConfig.csproj</span></span>|<span data-ttu-id="970b3-167">Proyecto de configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="970b3-167">Interceptor configuration project.</span></span>|  
|<span data-ttu-id="970b3-168">Invoice_config.xml</span><span class="sxs-lookup"><span data-stu-id="970b3-168">Invoice_config.xml</span></span>|<span data-ttu-id="970b3-169">Configuración del interceptor de facturación.</span><span class="sxs-lookup"><span data-stu-id="970b3-169">Invoice interceptor configuration.</span></span>|  
|<span data-ttu-id="970b3-170">Invoice_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="970b3-170">Invoice_interceptor.bin</span></span>|<span data-ttu-id="970b3-171">Interceptor de facturación serializado.</span><span class="sxs-lookup"><span data-stu-id="970b3-171">Serialized invoice interceptor.</span></span>|  
|<span data-ttu-id="970b3-172">PurchaseOrder_config.xml</span><span class="sxs-lookup"><span data-stu-id="970b3-172">PurchaseOrder_config.xml</span></span>|<span data-ttu-id="970b3-173">Configuración del interceptor PurchaseOrder.</span><span class="sxs-lookup"><span data-stu-id="970b3-173">PurchaseOrder interceptor configuration.</span></span>|  
|<span data-ttu-id="970b3-174">PurchaseOrder_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="970b3-174">PurchaseOrder_interceptor.bin</span></span>|<span data-ttu-id="970b3-175">Interceptor PurchaseOrder serializado.</span><span class="sxs-lookup"><span data-stu-id="970b3-175">Serialized PurchaseOrder interceptor.</span></span>|  
|<span data-ttu-id="970b3-176">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="970b3-176">Setup.bat</span></span>|<span data-ttu-id="970b3-177">Archivo por lotes para implementar y dar de alta archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="970b3-177">Batch file to deploy and enlist sample files.</span></span>|  
|<span data-ttu-id="970b3-178">Shipment_config.xml</span><span class="sxs-lookup"><span data-stu-id="970b3-178">Shipment_config.xml</span></span>|<span data-ttu-id="970b3-179">Configuración del interceptor de envío.</span><span class="sxs-lookup"><span data-stu-id="970b3-179">Shipment interceptor configuration.</span></span>|  
|<span data-ttu-id="970b3-180">Shipment_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="970b3-180">Shipment_interceptor.bin</span></span>|<span data-ttu-id="970b3-181">Interceptor de envío serializado.</span><span class="sxs-lookup"><span data-stu-id="970b3-181">Serialized shipment interceptor.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="970b3-182">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="970b3-182">How to Use This Sample</span></span>  
 <span data-ttu-id="970b3-183">Use el procedimiento siguiente para ejecutar la API de BAM de ejemplo y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="970b3-183">Use the following procedure to run the BAM API sample and view the results.</span></span>  
  
#### <a name="to-run-the-bam-api-sample"></a><span data-ttu-id="970b3-184">Procedimiento para ejecutar el ejemplo de API de BAM</span><span class="sxs-lookup"><span data-stu-id="970b3-184">To run the BAM API sample</span></span>  
  
1.  <span data-ttu-id="970b3-185">Abra un símbolo del sistema y ejecute  *\<ruta de ejemplos >*\BAM\ BamApiSample\setup.bat.</span><span class="sxs-lookup"><span data-stu-id="970b3-185">Open a command prompt and run *\<Samples Path>*\BAM\ BamApiSample\setup.bat.</span></span> <span data-ttu-id="970b3-186">Si usa [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], abra el símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="970b3-186">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], open the command prompt as administrator.</span></span>  
  
2.  <span data-ttu-id="970b3-187">Iniciar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y abra el  *\<ruta de ejemplos >*solución \bam\.</span><span class="sxs-lookup"><span data-stu-id="970b3-187">Start [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and open the *\<Samples Path>*\BAM\ BamApiSample\BamApiSample.sln solution.</span></span> <span data-ttu-id="970b3-188">Si está usando [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], inicie [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] como administrador.</span><span class="sxs-lookup"><span data-stu-id="970b3-188">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], start [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] as administrator.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="970b3-189">La línea `//#define Interceptor` del archivo BamApiSample.cs debe marcarse como comentario. No quite el signo “//” desde esta línea.</span><span class="sxs-lookup"><span data-stu-id="970b3-189">The line `//#define Interceptor` in the BamApiSample.cs file must be commented out. Do not remove the “//” from this line.</span></span> <span data-ttu-id="970b3-190">El ejemplo de API de BAM usa solo el código que no se encuentra dentro de una directiva de preprocesador `#if Interceptor`.</span><span class="sxs-lookup"><span data-stu-id="970b3-190">The BAM API sample uses only the code that is not inside an `#if Interceptor` preprocessor directive.</span></span>  
  
3.  <span data-ttu-id="970b3-191">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="970b3-191">Build the solution.</span></span>  
  
4.  <span data-ttu-id="970b3-192">Ejecutar  *\<ejemplos de ruta de acceso >*\BAM\BamApiSample\bin\debug\BamApiSample.exe.</span><span class="sxs-lookup"><span data-stu-id="970b3-192">Run *\<Samples Path>*\BAM\BamApiSample\bin\debug\BamApiSample.exe.</span></span>  
  
     <span data-ttu-id="970b3-193">El resultado será similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="970b3-193">The output will resemble the following:</span></span>  
  
    ```  
    ...  
    New Purchase Order #17 Received  
    8 was shipped as pkg#87  
    New Purchase Order #18 Received.  
    Shipping package pkg#87 via DHL  
    13 was Approved.  
    18 was Rejected.  
    17 was Rejected.  
    11 was shipped as pkg#114  
    16 wsas Rejected.  
    Shipping package pkg#114 via DHL  
    Invoice #5 send for {2 5 1 9 4 8 11 }  
    Package pkg#49 was delivered  
    New Purchase Order #19 Received.  
    ...  
    ```  
  
5.  <span data-ttu-id="970b3-194">Al cabo de un minuto aproximadamente, presione CTRL+C o cierre la ventana del símbolo del sistema para detener el programa BamApiSample.</span><span class="sxs-lookup"><span data-stu-id="970b3-194">After a minute or so, press CTRL+C or close the Command Prompt window to stop the BamApiSample program.</span></span>  
  
#### <a name="to-view-the-results-of-running-the-bam-api-sample"></a><span data-ttu-id="970b3-195">Procedimiento para ver los resultados de ejecutar el ejemplo de API de BAM</span><span class="sxs-lookup"><span data-stu-id="970b3-195">To view the results of running the BAM API sample</span></span>  
  
1.  <span data-ttu-id="970b3-196">Abra SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="970b3-196">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="970b3-197">En SQL Server Management Studio, expanda el servidor, expanda **bases de datos**, expanda **BAMPrimaryImport**y, a continuación, expanda **tablas**.</span><span class="sxs-lookup"><span data-stu-id="970b3-197">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="970b3-198">Haga clic en **dbo.bam_BAMApiInvoice_Active** y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="970b3-198">Right-click **dbo.bam_BAMApiInvoice_Active** and then click **Open Table**.</span></span> <span data-ttu-id="970b3-199">Si utilizas [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="970b3-199">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="970b3-200">El contenido de la tabla bam_BAMApiInvoice_Active se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="970b3-200">The contents of the bam_BAMApiInvoice_Active table are displayed in the right pane.</span></span> <span data-ttu-id="970b3-201">Cada fila de la tabla representa una actividad BAMApiInvoice que se ha iniciado, pero que no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="970b3-201">Each row in the table represents a BAMApiInvoice activity that has been started, but  has not been completed.</span></span>  
  
4.  <span data-ttu-id="970b3-202">Haga clic en **dbo.bam_BAMApiPo_Completed** y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="970b3-202">Right-click **dbo.bam_BAMApiPo_Completed** and then click **Open Table**.</span></span> <span data-ttu-id="970b3-203">Si utilizas [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="970b3-203">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="970b3-204">El contenido de la tabla bam_BAMApiPo_Completed se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="970b3-204">The contents of the bam_BAMApiPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="970b3-205">Cada fila de la tabla representa una actividad BAMApiPo que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="970b3-205">Each row in the table represents a BAMApiPo activity that has been completed.</span></span>