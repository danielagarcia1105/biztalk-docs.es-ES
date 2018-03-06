---
title: "API de BAM en el ejemplo de expresión de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5413940eaba97e6f68d5e068e26625f320e6e817
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a><span data-ttu-id="a3c98-102">API de BAM desde una expresión de orquestación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="a3c98-102">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>
<span data-ttu-id="a3c98-103">En este ejemplo se demuestra cómo realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3c98-103">This sample demonstrates how to:</span></span>  
  
-   <span data-ttu-id="a3c98-104">Usar la API de BAM en una expresión de orquestación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a3c98-104">Use the BAM API from a BizTalk Server orchestration expression.</span></span>  
  
-   <span data-ttu-id="a3c98-105">Realizar el seguimiento de elementos repetitivos en un mensaje como instancias de actividad individuales.</span><span class="sxs-lookup"><span data-stu-id="a3c98-105">Track repeating items inside a message as separate activity instances.</span></span>  
  
-   <span data-ttu-id="a3c98-106">Crear una relación entre los datos de BAM supervisados mediante un perfil de seguimiento y los datos de BAM supervisados mediante una API de BAM.</span><span class="sxs-lookup"><span data-stu-id="a3c98-106">Create a relationship between BAM data that is tracked by using a tracking profile, and BAM data tracked by using the BAM API.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="a3c98-107">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c98-107">Where to Find This Sample</span></span>  
 <span data-ttu-id="a3c98-108">Puede encontrar este ejemplo en  *\<ruta de ejemplos\>*\BAM\BamFromExpression.</span><span class="sxs-lookup"><span data-stu-id="a3c98-108">You can find this sample at *\<Samples Path\>*\BAM\BamFromExpression.</span></span>  
  
 <span data-ttu-id="a3c98-109">En la siguiente tabla se enumeran los archivos de este ejemplo y se describe el propósito de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="a3c98-109">The following table lists the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="a3c98-110">Archivo</span><span class="sxs-lookup"><span data-stu-id="a3c98-110">File</span></span>|<span data-ttu-id="a3c98-111">Description</span><span class="sxs-lookup"><span data-stu-id="a3c98-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="a3c98-112">BamDefinition.xls</span><span class="sxs-lookup"><span data-stu-id="a3c98-112">BamDefinition.xls</span></span>|<span data-ttu-id="a3c98-113">Hoja de estilo de definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="a3c98-113">BAM definition stylesheet.</span></span>|  
|<span data-ttu-id="a3c98-114">BamDefinition.xml</span><span class="sxs-lookup"><span data-stu-id="a3c98-114">BamDefinition.xml</span></span>|<span data-ttu-id="a3c98-115">Definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="a3c98-115">BAM definition.</span></span>|  
|<span data-ttu-id="a3c98-116">BamFromExpression.btproj</span><span class="sxs-lookup"><span data-stu-id="a3c98-116">BamFromExpression.btproj</span></span>|<span data-ttu-id="a3c98-117">Seguimiento de archivo de proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a3c98-117">Visual Studio tracking file project.</span></span>|  
|<span data-ttu-id="a3c98-118">BamFromExpression.sln</span><span class="sxs-lookup"><span data-stu-id="a3c98-118">BamFromExpression.sln</span></span>|<span data-ttu-id="a3c98-119">Solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a3c98-119">Visual Studio solution.</span></span>|  
|<span data-ttu-id="a3c98-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="a3c98-120">Cleanup.bat</span></span>|<span data-ttu-id="a3c98-121">Archivo por lotes que se usa para anular la implementación del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-121">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="a3c98-122">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="a3c98-122">InputMessage.xml</span></span>|<span data-ttu-id="a3c98-123">Mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="a3c98-123">Input message.</span></span>|  
|<span data-ttu-id="a3c98-124">Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="a3c98-124">Orchestration1.odx</span></span>|<span data-ttu-id="a3c98-125">Orquestación.</span><span class="sxs-lookup"><span data-stu-id="a3c98-125">Orchestration.</span></span>|  
|<span data-ttu-id="a3c98-126">PoSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="a3c98-126">PoSchema.xsd</span></span>|<span data-ttu-id="a3c98-127">Esquema del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="a3c98-127">Purchase order schema.</span></span>|  
|<span data-ttu-id="a3c98-128">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="a3c98-128">PropertySchema.xsd</span></span>|<span data-ttu-id="a3c98-129">Esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a3c98-129">Property schema.</span></span>|  
|<span data-ttu-id="a3c98-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="a3c98-130">Setup.bat</span></span>|<span data-ttu-id="a3c98-131">Archivo por lotes para compilar e implementar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-131">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="a3c98-132">QueryBam.sql</span><span class="sxs-lookup"><span data-stu-id="a3c98-132">QueryBam.sql</span></span>|<span data-ttu-id="a3c98-133">Script de SQL.</span><span class="sxs-lookup"><span data-stu-id="a3c98-133">SQL script.</span></span>|  
  
## <a name="create-the-tracking-profile"></a><span data-ttu-id="a3c98-134">Crear el perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a3c98-134">Create the tracking profile</span></span>  
  
1.  <span data-ttu-id="a3c98-135">Abra un símbolo del sistema como administrador y ejecute  *\<ruta de ejemplos\>*\BAM\BAMFromExpression\Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="a3c98-135">Open a command prompt as Administrator, and run *\<Samples Path\>*\BAM\BAMFromExpression\Setup.bat.</span></span> <span data-ttu-id="a3c98-136">Setup.bat inicializa la infraestructura de BAM para este ejemplo e implementa la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="a3c98-136">Setup.bat initializes the BAM infrastructure for this sample, and deploys the BAM activity.</span></span>  
  
2.  <span data-ttu-id="a3c98-137">Desde el **programas** > **Microsoft BizTalk Server**, haga clic en **Editor de perfiles de seguimiento**, y **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-137">From your **Programs** > **Microsoft BizTalk Server**, right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>
  
3.  <span data-ttu-id="a3c98-138">En el panel izquierdo de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar una definición de actividad de BAM**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-138">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
4.  <span data-ttu-id="a3c98-139">En el **nombre de definición de actividad de BAM** sección de la **Importar definición de actividad de BAM** cuadro de diálogo, seleccione **FromExpressionPo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-139">In the **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **FromExpressionPo**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a3c98-140">En el panel derecho de la **Editor de perfiles de seguimiento** ventana, haga clic en **haga clic aquí para seleccionar un origen de eventos**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-140">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
6.  <span data-ttu-id="a3c98-141">En el **nombre de ensamblado** sección de la **seleccionar ensamblado primario de origen de eventos** cuadro de diálogo, seleccione **Microsoft.Samples.BizTalk.BamFromExpression**y, a continuación, haga clic en  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-141">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamFromExpression**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="a3c98-142">En el **nombre de la orquestación** sección de la **Seleccionar orquestación** cuadro de diálogo, seleccione **BamFromExpression.Orchestration1**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-142">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamFromExpression.Orchestration1**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="a3c98-143">Haga clic en el **Receive_1** forma y, a continuación, haga clic en **esquema de carga de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-143">Right-click the **Receive_1** shape, and then click **Message Payload Schema**.</span></span>  
  
9. <span data-ttu-id="a3c98-144">Expanda  **\<esquema\>**, expanda **PurchaseOrder**, expanda **de**y, a continuación, arrastre **PoID** a la derecha panel para **ActivityID** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-144">Expand **\<Schema\>**, expand **PurchaseOrder**, expand **From**, and then drag **PoID** in the right pane to **ActivityID** in the left pane.</span></span>  
  
10. <span data-ttu-id="a3c98-145">Arrastre los elementos siguientes del panel derecho y suéltelos en los nodos con nombre del panel izquierdo:</span><span class="sxs-lookup"><span data-stu-id="a3c98-145">Drag the following elements from the right pane, and drop them onto the named nodes in the left pane:</span></span>  
  
    |<span data-ttu-id="a3c98-146">De</span><span class="sxs-lookup"><span data-stu-id="a3c98-146">From</span></span>|<span data-ttu-id="a3c98-147">A</span><span class="sxs-lookup"><span data-stu-id="a3c98-147">To</span></span>|  
    |----------|--------|  
    |<span data-ttu-id="a3c98-148">Nombre</span><span class="sxs-lookup"><span data-stu-id="a3c98-148">Name</span></span>|<span data-ttu-id="a3c98-149">De</span><span class="sxs-lookup"><span data-stu-id="a3c98-149">From</span></span>|  
    |<span data-ttu-id="a3c98-150">State</span><span class="sxs-lookup"><span data-stu-id="a3c98-150">State</span></span>|<span data-ttu-id="a3c98-151">State</span><span class="sxs-lookup"><span data-stu-id="a3c98-151">State</span></span>|  
    |<span data-ttu-id="a3c98-152">City</span><span class="sxs-lookup"><span data-stu-id="a3c98-152">City</span></span>|<span data-ttu-id="a3c98-153">City</span><span class="sxs-lookup"><span data-stu-id="a3c98-153">City</span></span>|  
    |<span data-ttu-id="a3c98-154">Teléfono</span><span class="sxs-lookup"><span data-stu-id="a3c98-154">Phone</span></span>|<span data-ttu-id="a3c98-155">Teléfono</span><span class="sxs-lookup"><span data-stu-id="a3c98-155">Phone</span></span>|  
    |<span data-ttu-id="a3c98-156">Total</span><span class="sxs-lookup"><span data-stu-id="a3c98-156">Total</span></span>|<span data-ttu-id="a3c98-157">PoTotal</span><span class="sxs-lookup"><span data-stu-id="a3c98-157">PoTotal</span></span>|  
  
11. <span data-ttu-id="a3c98-158">Haga clic en el icono de carpeta con la flecha (![botón con carpeta y seguridad &#45; flecha](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) para mostrar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a3c98-158">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) to display the orchestration.</span></span>  
  
12. <span data-ttu-id="a3c98-159">Arrastre el **Receive_1** forma en el panel derecho a **recibidos** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-159">Drag the **Receive_1** shape in the right pane to **Received** in the left pane.</span></span>  
  
13. <span data-ttu-id="a3c98-160">Arrastre el **Send_1** forma en el panel derecho a **enviar** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-160">Drag the **Send_1** shape in the right pane to **Send** in the left pane.</span></span>  
  
14. <span data-ttu-id="a3c98-161">Guarde el perfil de seguimiento para  *\<ruta de ejemplos\>*\BAM\BamFromExpression\ BamFromExpression.btt.</span><span class="sxs-lookup"><span data-stu-id="a3c98-161">Save the tracking profile to *\<Samples Path\>*\BAM\BamFromExpression\ BamFromExpression.btt.</span></span>  
  
15. <span data-ttu-id="a3c98-162">En el **herramientas** menú, haga clic en **aplicar perfil de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-162">On the **Tools** menu, click **Apply Tracking Profile**.</span></span>  
  
## <a name="build-and-initialize-this-sample"></a><span data-ttu-id="a3c98-163">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c98-163">Build and initialize this sample</span></span>  
  
<span data-ttu-id="a3c98-164">Implemente el perfil de seguimiento BamFromExpression.btt.</span><span class="sxs-lookup"><span data-stu-id="a3c98-164">Deploy the BamFromExpression.btt tracking profile.</span></span> <span data-ttu-id="a3c98-165">Vea [utilidad de administración de perfiles de cómo implementar perfiles de seguimiento con el seguimiento](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span><span class="sxs-lookup"><span data-stu-id="a3c98-165">See [How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span></span>  
  
## <a name="run-this-sample"></a><span data-ttu-id="a3c98-166">Ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c98-166">Run this sample</span></span>  
  
<span data-ttu-id="a3c98-167">Copie el archivo  *\<ruta de ejemplos\>*\BamFromExpression\InputMessage.xml a  *\<ruta de ejemplos\>*\BamFromExpression\Input.</span><span class="sxs-lookup"><span data-stu-id="a3c98-167">Copy the file *\<Samples Path\>*\BamFromExpression\InputMessage.xml to *\<Samples Path\>*\BamFromExpression\Input.</span></span>  
  
<span data-ttu-id="a3c98-168">En unos 10 segundos, aparecerá el mensaje de salida en  *\<ruta de ejemplos\>*\BamFromExpression\Output.</span><span class="sxs-lookup"><span data-stu-id="a3c98-168">In about 10 seconds the output message will appear in *\<Samples Path\>*\BamFromExpression\Output.</span></span>  
  
## <a name="view-the-bam-data"></a><span data-ttu-id="a3c98-169">Ver los datos de BAM</span><span class="sxs-lookup"><span data-stu-id="a3c98-169">View the BAM data</span></span>  
  
1.  <span data-ttu-id="a3c98-170">Abra SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a3c98-170">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="a3c98-171">En SQL Server Management Studio, expanda el servidor, expanda **bases de datos**, expanda **BAMPrimaryImport**y, a continuación, expanda **tablas**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-171">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="a3c98-172">Haga clic en **dbo.bam_FromExpressionPo_Completed**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-172">Right-click **dbo.bam_FromExpressionPo_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="a3c98-173">Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-173">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="a3c98-174">El contenido de la tabla bam_FromExpressionPo_Completed se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="a3c98-174">The contents of the bam_FromExpressionPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="a3c98-175">La fila con el identificador de actividad 123 representa el pedido de 345 USD incluido en el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="a3c98-175">The one row, which has an activity ID of 123, represents the purchase order for $345 that was contained in the input message.</span></span>  
  
4.  <span data-ttu-id="a3c98-176">Haga clic en **dbo.bam_FromExpressionPoItem_Completed**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-176">Right-click **dbo.bam_FromExpressionPoItem_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="a3c98-177">Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-177">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="a3c98-178">El contenido de la tabla bam_FromExpressionPoItem_Completed se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="a3c98-178">The contents of the bam_FromExpressionPoItem_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="a3c98-179">Las dos filas, que tienen actividad identificadores 123_0 y 123_1, representan los elementos del pedido de compra: MC Flash y descodificador de infrarrojos.</span><span class="sxs-lookup"><span data-stu-id="a3c98-179">The two rows, which have activity IDs 123_0 and 123_1, represent the items in the purchase order: Flash MC and Infrared Decoder.</span></span>  
  
5.  <span data-ttu-id="a3c98-180">Haga clic en **dbo.bam_FromExpressionPoItem_CompletedRelationships**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-180">Right-click **dbo.bam_FromExpressionPoItem_CompletedRelationships**, and then click **Open Table**.</span></span> <span data-ttu-id="a3c98-181">Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="a3c98-181">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="a3c98-182">El contenido de la tabla bam_FromExpressionPoItem_CompletedRelationships se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="a3c98-182">The contents of the bam_FromExpressionPoItem_CompletedRelationships table are displayed in the right pane.</span></span> <span data-ttu-id="a3c98-183">Cada fila de la tabla representa una relación entre una actividad FromExpressionPoItem y una actividad FromExpressionPo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-183">Each row in the table represents a relationship between a FromExpressionPoItem activity and a FromExpressionPo activity.</span></span> <span data-ttu-id="a3c98-184">El valor de la **ActivityID** columna hace referencia al identificador de la actividad FromExpressionPoItem.</span><span class="sxs-lookup"><span data-stu-id="a3c98-184">The value in the **ActivityID** column refers to the activity ID of the FromExpressionPoItem activity.</span></span> <span data-ttu-id="a3c98-185">El valor de la **ReferenceData** columna hace referencia al identificador de la actividad FromExpressionPo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-185">The value in the **ReferenceData** column refers to the activity ID of the FromExpressionPo activity.</span></span> <span data-ttu-id="a3c98-186">En este caso, ambos registros indican que los artículos MC Flash y descodificador de infrarrojos están asociados con el pedido de 345 USD.</span><span class="sxs-lookup"><span data-stu-id="a3c98-186">In this case, the two records indicate that the Flash MC and Infrared Decoder items are associated with the purchase order for $345.</span></span>  
  
## <a name="re-run-the-sample"></a><span data-ttu-id="a3c98-187">Vuelva a ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c98-187">Re-run the sample</span></span>  
  
1.  <span data-ttu-id="a3c98-188">Abra un símbolo del sistema como administrador y ejecute  *\<ruta de ejemplos\>*\BAM\BamFromExpression\Cleanup.bat para quitar el perfil de seguimiento y otras infraestructuras BAM.</span><span class="sxs-lookup"><span data-stu-id="a3c98-188">Open a command prompt as Administrator, and run *\<Samples Path\>*\BAM\BamFromExpression\Cleanup.bat to remove the tracking profile and other BAM infrastructure.</span></span> 
  
2.  <span data-ttu-id="a3c98-189">Ejecutar  *\<ruta de ejemplos\>*\BAM\BamFromExpression\Setup.bat para compilar el ejemplo e implementarlo.</span><span class="sxs-lookup"><span data-stu-id="a3c98-189">Run *\<Samples Path\>*\BAM\BamFromExpression\Setup.bat to compile the sample and deploy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c98-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3c98-190">See Also</span></span>  
 <span data-ttu-id="a3c98-191">[(Carpeta de ejemplos de BizTalk Server) de supervisión de la actividad de negocio](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="a3c98-191">[Business Activity Monitoring (BizTalk Server Samples Folder)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="a3c98-192">Relaciones de actividades</span><span class="sxs-lookup"><span data-stu-id="a3c98-192">Activity Relationships</span></span>](../core/activity-relationships.md)