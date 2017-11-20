---
title: "API de BAM en una expresión de orquestación (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, BAM
- examples, orchestrations
- BAM, examples
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26b9cbc21eb93cad52a421b7df0912a37708978c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a><span data-ttu-id="cdfa9-102">API de BAM desde una expresión de orquestación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="cdfa9-102">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>
<span data-ttu-id="cdfa9-103">En este ejemplo se demuestra cómo realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cdfa9-103">This sample demonstrates how to:</span></span>  
  
-   <span data-ttu-id="cdfa9-104">Usar la API de BAM en una expresión de orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdfa9-104">Use the BAM API from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration expression.</span></span>  
  
-   <span data-ttu-id="cdfa9-105">Realizar el seguimiento de elementos repetitivos en un mensaje como instancias de actividad individuales.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-105">Track repeating items inside a message as separate activity instances.</span></span>  
  
-   <span data-ttu-id="cdfa9-106">Crear una relación entre los datos de BAM supervisados mediante un perfil de seguimiento y los datos de BAM supervisados mediante una API de BAM.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-106">Create a relationship between BAM data that is tracked by using a tracking profile, and BAM data tracked by using the BAM API.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="cdfa9-107">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdfa9-107">Where to Find This Sample</span></span>  
 <span data-ttu-id="cdfa9-108">Puede encontrar este ejemplo en  *\<ruta de ejemplos >*\BAM\BamFromExpression.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-108">You can find this sample at *\<Samples Path>*\BAM\BamFromExpression.</span></span>  
  
 <span data-ttu-id="cdfa9-109">En la siguiente tabla se enumeran los archivos de este ejemplo y se describe el propósito de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-109">The following table lists the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="cdfa9-110">Archivo</span><span class="sxs-lookup"><span data-stu-id="cdfa9-110">File</span></span>|<span data-ttu-id="cdfa9-111">Description</span><span class="sxs-lookup"><span data-stu-id="cdfa9-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="cdfa9-112">BamDefinition.xls</span><span class="sxs-lookup"><span data-stu-id="cdfa9-112">BamDefinition.xls</span></span>|<span data-ttu-id="cdfa9-113">Hoja de estilo de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-113">BAM definition stylesheet.</span></span>|  
|<span data-ttu-id="cdfa9-114">BamDefinition.xml</span><span class="sxs-lookup"><span data-stu-id="cdfa9-114">BamDefinition.xml</span></span>|<span data-ttu-id="cdfa9-115">Definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-115">BAM definition.</span></span>|  
|<span data-ttu-id="cdfa9-116">BamFromExpression.btproj</span><span class="sxs-lookup"><span data-stu-id="cdfa9-116">BamFromExpression.btproj</span></span>|<span data-ttu-id="cdfa9-117">Proyecto de archivo de seguimiento de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdfa9-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tracking file project.</span></span>|  
|<span data-ttu-id="cdfa9-118">BamFromExpression.sln</span><span class="sxs-lookup"><span data-stu-id="cdfa9-118">BamFromExpression.sln</span></span>|<span data-ttu-id="cdfa9-119">Solución de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdfa9-119">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution.</span></span>|  
|<span data-ttu-id="cdfa9-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="cdfa9-120">Cleanup.bat</span></span>|<span data-ttu-id="cdfa9-121">Archivo por lotes que se usa para anular la implementación del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-121">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="cdfa9-122">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="cdfa9-122">InputMessage.xml</span></span>|<span data-ttu-id="cdfa9-123">Mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-123">Input message.</span></span>|  
|<span data-ttu-id="cdfa9-124">Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="cdfa9-124">Orchestration1.odx</span></span>|<span data-ttu-id="cdfa9-125">Orquestación.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-125">Orchestration.</span></span>|  
|<span data-ttu-id="cdfa9-126">PoSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="cdfa9-126">PoSchema.xsd</span></span>|<span data-ttu-id="cdfa9-127">Esquema del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-127">Purchase order schema.</span></span>|  
|<span data-ttu-id="cdfa9-128">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="cdfa9-128">PropertySchema.xsd</span></span>|<span data-ttu-id="cdfa9-129">Esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-129">Property schema.</span></span>|  
|<span data-ttu-id="cdfa9-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="cdfa9-130">Setup.bat</span></span>|<span data-ttu-id="cdfa9-131">Archivo por lotes para compilar e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-131">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="cdfa9-132">QueryBam.sql</span><span class="sxs-lookup"><span data-stu-id="cdfa9-132">QueryBam.sql</span></span>|<span data-ttu-id="cdfa9-133">Script de SQL.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-133">SQL script.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="cdfa9-134">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdfa9-134">How to Use This Sample</span></span>  
 <span data-ttu-id="cdfa9-135">Use los procedimientos siguientes para crear el perfil de seguimiento, ejecutar el ejemplo y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-135">Use the following procedures to create the tracking profile, run the sample, and view the results.</span></span>  
  
#### <a name="to-create-the-tracking-profile"></a><span data-ttu-id="cdfa9-136">Para crear el perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cdfa9-136">To create the tracking profile</span></span>  
  
1.  <span data-ttu-id="cdfa9-137">Abra un símbolo del sistema y ejecute  *\<ruta de ejemplos >*\BAM\BAMFromExpression\Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-137">Open a command prompt and run *\<Samples Path>*\BAM\BAMFromExpression\Setup.bat.</span></span> <span data-ttu-id="cdfa9-138">Si usa [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], abra el símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-138">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], open the command prompt as administrator.</span></span> <span data-ttu-id="cdfa9-139">Setup.bat inicializa la infraestructura de BAM para este ejemplo e implementa la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-139">Setup.bat initializes the BAM infrastructure for this sample, and deploys the BAM activity.</span></span>  
  
2.  <span data-ttu-id="cdfa9-140">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Editor de perfiles de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-140">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span> <span data-ttu-id="cdfa9-141">Si utilizas [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], haga clic en **Editor de perfiles de seguimiento** y, a continuación, haga clic en **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-141">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], right-click **Tracking Profile Editor** and then click **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="cdfa9-142">En el panel izquierdo de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar una definición de actividad de BAM**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-142">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
4.  <span data-ttu-id="cdfa9-143">En el **nombre de definición de actividad de BAM** sección de la **Importar definición de actividad de BAM** cuadro de diálogo, seleccione **FromExpressionPo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-143">In the **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **FromExpressionPo**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cdfa9-144">En el panel derecho de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar un origen de eventos**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-144">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
6.  <span data-ttu-id="cdfa9-145">En el **nombre de ensamblado** sección de la **seleccionar ensamblado primario de origen de eventos** cuadro de diálogo, seleccione **Microsoft.Samples.BizTalk.BamFromExpression**y, a continuación, haga clic en  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-145">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamFromExpression**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="cdfa9-146">En el **nombre de la orquestación** sección de la **Seleccionar orquestación** cuadro de diálogo, seleccione **BamFromExpression.Orchestration1**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-146">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamFromExpression.Orchestration1**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="cdfa9-147">Haga clic en el **Receive_1** forma y, a continuación, haga clic en **esquema de carga de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-147">Right-click the **Receive_1** shape, and then click **Message Payload Schema**.</span></span>  
  
9. <span data-ttu-id="cdfa9-148">Expanda  **\<esquema >**, expanda **PurchaseOrder**, expanda **de**y, a continuación, arrastre **PoID** en el panel derecho a  **ActivityID** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-148">Expand **\<Schema>**, expand **PurchaseOrder**, expand **From**, and then drag **PoID** in the right pane to **ActivityID** in the left pane.</span></span>  
  
10. <span data-ttu-id="cdfa9-149">Arrastre los elementos siguientes del panel derecho y suéltelos en los nodos con nombre del panel izquierdo:</span><span class="sxs-lookup"><span data-stu-id="cdfa9-149">Drag the following elements from the right pane, and drop them onto the named nodes in the left pane:</span></span>  
  
    |<span data-ttu-id="cdfa9-150">De</span><span class="sxs-lookup"><span data-stu-id="cdfa9-150">From</span></span>|<span data-ttu-id="cdfa9-151">Para</span><span class="sxs-lookup"><span data-stu-id="cdfa9-151">To</span></span>|  
    |----------|--------|  
    |<span data-ttu-id="cdfa9-152">Nombre</span><span class="sxs-lookup"><span data-stu-id="cdfa9-152">Name</span></span>|<span data-ttu-id="cdfa9-153">De</span><span class="sxs-lookup"><span data-stu-id="cdfa9-153">From</span></span>|  
    |<span data-ttu-id="cdfa9-154">State</span><span class="sxs-lookup"><span data-stu-id="cdfa9-154">State</span></span>|<span data-ttu-id="cdfa9-155">State</span><span class="sxs-lookup"><span data-stu-id="cdfa9-155">State</span></span>|  
    |<span data-ttu-id="cdfa9-156">City</span><span class="sxs-lookup"><span data-stu-id="cdfa9-156">City</span></span>|<span data-ttu-id="cdfa9-157">City</span><span class="sxs-lookup"><span data-stu-id="cdfa9-157">City</span></span>|  
    |<span data-ttu-id="cdfa9-158">Teléfono</span><span class="sxs-lookup"><span data-stu-id="cdfa9-158">Phone</span></span>|<span data-ttu-id="cdfa9-159">Teléfono</span><span class="sxs-lookup"><span data-stu-id="cdfa9-159">Phone</span></span>|  
    |<span data-ttu-id="cdfa9-160">Total</span><span class="sxs-lookup"><span data-stu-id="cdfa9-160">Total</span></span>|<span data-ttu-id="cdfa9-161">PoTotal</span><span class="sxs-lookup"><span data-stu-id="cdfa9-161">PoTotal</span></span>|  
  
11. <span data-ttu-id="cdfa9-162">Haga clic en el icono de carpeta con la flecha (![botón con carpeta y seguridad &#45; flecha](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) para mostrar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-162">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) to display the orchestration.</span></span>  
  
12. <span data-ttu-id="cdfa9-163">Arrastre el **Receive_1** forma en el panel derecho a **recibidos** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-163">Drag the **Receive_1** shape in the right pane to **Received** in the left pane.</span></span>  
  
13. <span data-ttu-id="cdfa9-164">Arrastre el **Send_1** forma en el panel derecho a **enviar** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-164">Drag the **Send_1** shape in the right pane to **Send** in the left pane.</span></span>  
  
14. <span data-ttu-id="cdfa9-165">Guarde el perfil de seguimiento para  *\<ruta de ejemplos >*\BAM\BamFromExpression\ BamFromExpression.btt.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-165">Save the tracking profile to *\<Samples Path>*\BAM\BamFromExpression\ BamFromExpression.btt.</span></span>  
  
15. <span data-ttu-id="cdfa9-166">En el **herramientas** menú, haga clic en **aplicar perfil de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-166">On the **Tools** menu, click **Apply Tracking Profile**.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="cdfa9-167">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdfa9-167">To build and initialize this sample</span></span>  
  
-   <span data-ttu-id="cdfa9-168">Implemente el perfil de seguimiento BamFromExpression.btt.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-168">Deploy the BamFromExpression.btt tracking profile.</span></span> <span data-ttu-id="cdfa9-169">Para obtener más información, consulte [cómo implementar perfiles de seguimiento con la utilidad de administración de perfiles de seguimiento](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span><span class="sxs-lookup"><span data-stu-id="cdfa9-169">For more information, see [How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="cdfa9-170">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdfa9-170">To run this sample</span></span>  
  
-   <span data-ttu-id="cdfa9-171">Copie el archivo  *\<ruta de ejemplos >*\BamFromExpression\InputMessage.xml a  *\<ruta de ejemplos >*\BamFromExpression\Input.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-171">Copy the file *\<Samples Path>*\BamFromExpression\InputMessage.xml to *\<Samples Path>*\BamFromExpression\Input.</span></span>  
  
     <span data-ttu-id="cdfa9-172">En unos 10 segundos, aparecerá el mensaje de salida en  *\<ruta de ejemplos >*\BamFromExpression\Output.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-172">In about 10 seconds the output message will appear in *\<Samples Path>*\BamFromExpression\Output.</span></span>  
  
#### <a name="to-view-the-bam-data"></a><span data-ttu-id="cdfa9-173">Para ver los datos de BAM</span><span class="sxs-lookup"><span data-stu-id="cdfa9-173">To view the BAM data</span></span>  
  
1.  <span data-ttu-id="cdfa9-174">Abra SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-174">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="cdfa9-175">En SQL Server Management Studio, expanda el servidor, expanda **bases de datos**, expanda **BAMPrimaryImport**y, a continuación, expanda **tablas**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-175">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="cdfa9-176">Haga clic en **dbo.bam_FromExpressionPo_Completed**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-176">Right-click **dbo.bam_FromExpressionPo_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="cdfa9-177">Si utilizas [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-177">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="cdfa9-178">El contenido de la tabla bam_FromExpressionPo_Completed se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-178">The contents of the bam_FromExpressionPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="cdfa9-179">La fila con el identificador de actividad 123 representa el pedido de 345 USD incluido en el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-179">The one row, which has an activity ID of 123, represents the purchase order for $345 that was contained in the input message.</span></span>  
  
4.  <span data-ttu-id="cdfa9-180">Haga clic en **dbo.bam_FromExpressionPoItem_Completed**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-180">Right-click **dbo.bam_FromExpressionPoItem_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="cdfa9-181">Si utilizas [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-181">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="cdfa9-182">El contenido de la tabla bam_FromExpressionPoItem_Completed se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-182">The contents of the bam_FromExpressionPoItem_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="cdfa9-183">Las dos filas, que tienen actividad identificadores 123_0 y 123_1, representan los elementos del pedido de compra: MC Flash y descodificador de infrarrojos.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-183">The two rows, which have activity IDs 123_0 and 123_1, represent the items in the purchase order: Flash MC and Infrared Decoder.</span></span>  
  
5.  <span data-ttu-id="cdfa9-184">Haga clic en **dbo.bam_FromExpressionPoItem_CompletedRelationships**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-184">Right-click **dbo.bam_FromExpressionPoItem_CompletedRelationships**, and then click **Open Table**.</span></span> <span data-ttu-id="cdfa9-185">Si utilizas [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-185">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="cdfa9-186">El contenido de la tabla bam_FromExpressionPoItem_CompletedRelationships se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-186">The contents of the bam_FromExpressionPoItem_CompletedRelationships table are displayed in the right pane.</span></span> <span data-ttu-id="cdfa9-187">Cada fila de la tabla representa una relación entre una actividad FromExpressionPoItem y una actividad FromExpressionPo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-187">Each row in the table represents a relationship between a FromExpressionPoItem activity and a FromExpressionPo activity.</span></span> <span data-ttu-id="cdfa9-188">El valor de la **ActivityID** columna hace referencia al identificador de la actividad FromExpressionPoItem.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-188">The value in the **ActivityID** column refers to the activity ID of the FromExpressionPoItem activity.</span></span> <span data-ttu-id="cdfa9-189">El valor de la **ReferenceData** columna hace referencia al identificador de la actividad FromExpressionPo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-189">The value in the **ReferenceData** column refers to the activity ID of the FromExpressionPo activity.</span></span> <span data-ttu-id="cdfa9-190">En este caso, ambos registros indican que los artículos MC Flash y descodificador de infrarrojos están asociados con el pedido de 345 USD.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-190">In this case, the two records indicate that the Flash MC and Infrared Decoder items are associated with the purchase order for $345.</span></span>  
  
#### <a name="to-re-run-the-sample"></a><span data-ttu-id="cdfa9-191">Para volver a ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdfa9-191">To re-run the sample</span></span>  
  
1.  <span data-ttu-id="cdfa9-192">Abra un símbolo del sistema y ejecute  *\<ruta de ejemplos >*\BAM\BamFromExpression\Cleanup.bat para quitar el perfil de seguimiento y otras infraestructuras BAM.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-192">Open a command prompt and run *\<Samples Path>*\BAM\BamFromExpression\Cleanup.bat to remove the tracking profile and other BAM infrastructure.</span></span> <span data-ttu-id="cdfa9-193">Si usa [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], abra el símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-193">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], open the command prompt as administrator.</span></span>  
  
2.  <span data-ttu-id="cdfa9-194">Ejecutar  *\<ruta de ejemplos >*\BAM\BamFromExpression\Setup.bat para compilar el ejemplo e implementarlo.</span><span class="sxs-lookup"><span data-stu-id="cdfa9-194">Run *\<Samples Path>*\BAM\BamFromExpression\Setup.bat to compile the sample and deploy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfa9-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdfa9-195">See Also</span></span>  
 <span data-ttu-id="cdfa9-196">[(Carpeta de ejemplos de BizTalk Server) de supervisión de la actividad de negocio](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="cdfa9-196">[Business Activity Monitoring (BizTalk Server Samples Folder)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="cdfa9-197">Relaciones de actividad</span><span class="sxs-lookup"><span data-stu-id="cdfa9-197">Activity Relationships</span></span>](../core/activity-relationships.md)