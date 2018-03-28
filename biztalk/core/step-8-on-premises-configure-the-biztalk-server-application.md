---
title: 'Paso 8 (de forma local): Configurar la aplicación de BizTalk Server | Documentos de Microsoft'
ms.custom: ''
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa411b7ca828a45aa0d5e58212bb48195c48180f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a><span data-ttu-id="ae02a-102">Paso 8 (de forma local): Configurar la aplicación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ae02a-102">Step 8 (On Premises): Configure the BizTalk Server Application</span></span>
<span data-ttu-id="ae02a-103">En el paso anterior, creó una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae02a-103">In the previous step you created a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="ae02a-104">En este paso, compilará, implementará y configurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae02a-104">In this step, you’ll build, deploy, and configure the application.</span></span>  
  
## <a name="build-and-deploy-the-application"></a><span data-ttu-id="ae02a-105">Compilar e implementar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae02a-105">Build and deploy the application</span></span>  
  
1.  <span data-ttu-id="ae02a-106">En Visual Studio, haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-106">In Visual Studio, right-click the solution name in the Solution Explorer, and click **Build**.</span></span>  
  
2.  <span data-ttu-id="ae02a-107">El proceso de implementación necesita que el ensamblado esté firmado de forma segura.</span><span class="sxs-lookup"><span data-stu-id="ae02a-107">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="ae02a-108">Debe firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="ae02a-108">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  
  
    1.  <span data-ttu-id="ae02a-109">En el Explorador de soluciones, haga clic en el **OrderProcessingDemo** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-109">In Solution Explorer, right-click the **OrderProcessingDemo** project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="ae02a-110">Haga clic en el **firma** pestaña y seleccione la **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="ae02a-110">Click the **Signing** tab, and select the **Sign the assembly** checkbox.</span></span>  
  
    3.  <span data-ttu-id="ae02a-111">En la lista desplegable de la **elegir un archivo de clave de nombre seguro** cuadro, seleccione  **\<nuevo... \>**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-111">From the drop-down list in the **Choose a strong name key file** box, select **\<New…\>**.</span></span>  
  
    4.  <span data-ttu-id="ae02a-112">En el **crear clave de nombre seguro** diálogo cuadro, escriba un nombre para el archivo de clave, por ejemplo `OrderProcessingDemo.snk`.</span><span class="sxs-lookup"><span data-stu-id="ae02a-112">In the **Create Strong Name Key** dialog box, enter a name for the key file, for example `OrderProcessingDemo.snk`.</span></span> <span data-ttu-id="ae02a-113">Desactive la casilla para proteger el archivo de clave con una contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-113">Clear the checkbox for protecting the key file with a password, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ae02a-114">Haga clic en el **implementación** ficha, en el cuadro a la derecha del **nombre de la aplicación**, tipo `OrderProcessingDemo`.</span><span class="sxs-lookup"><span data-stu-id="ae02a-114">Click the **Deployment** tab, in the box to the right of **Application Name**, type `OrderProcessingDemo`.</span></span>  
  
4.  <span data-ttu-id="ae02a-115">En la lista desplegable en el cuadro a la derecha del **volver a implementar**, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-115">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
5.  <span data-ttu-id="ae02a-116">En el Explorador de soluciones, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-116">In Solution Explorer, right-click **OrderProcessingDemo**, and then click **Deploy**.</span></span>  <span data-ttu-id="ae02a-117">En la ventana de salida se debe ver:</span><span class="sxs-lookup"><span data-stu-id="ae02a-117">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
## <a name="configure-the-application"></a><span data-ttu-id="ae02a-118">Configurar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae02a-118">Configure the application</span></span>  
  
1.  <span data-ttu-id="ae02a-119">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae02a-119">Click **Start**, point to **All Programs**, point to **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="ae02a-120">En el árbol de consola en el panel izquierdo, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-120">In the console tree on the left pane, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="ae02a-121">Expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **OrderProcessingDemo**y, a continuación, haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-121">Expand **BizTalk Group**, expand **Applications**, expand **OrderProcessingDemo**, and then click **Orchestrations**.</span></span> <span data-ttu-id="ae02a-122">Verá que la **OrderProcessingDemo.OrderProcessing** se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ae02a-122">You will see that the **OrderProcessingDemo.OrderProcessing** orchestration is deployed.</span></span>  
  
4.  <span data-ttu-id="ae02a-123">En la orquestación, creó un puerto lógico (**ReceiveSO**) para recibir mensajes desde la cola de Bus de servicio.</span><span class="sxs-lookup"><span data-stu-id="ae02a-123">In the orchestration, you created a logical port (**ReceiveSO**) to receive messages from the Service Bus Queue.</span></span> <span data-ttu-id="ae02a-124">En este paso, se crea un puerto de recepción físico para asignar al puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="ae02a-124">In this step, you create a physical receive port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="ae02a-125">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-125">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
    2.  <span data-ttu-id="ae02a-126">En la pestaña **General** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae02a-126">On the **General** tab, do the following:</span></span>  
  
        |<span data-ttu-id="ae02a-127">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-127">Use this</span></span>|<span data-ttu-id="ae02a-128">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-128">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-129">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ae02a-129">**Name**</span></span>|<span data-ttu-id="ae02a-130">Tipo de **ReceiveSO**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-130">Type **ReceiveSO**.</span></span>|  
        |<span data-ttu-id="ae02a-131">**Habilitar enrutamiento para mensajes con errores**</span><span class="sxs-lookup"><span data-stu-id="ae02a-131">**Enable routing for failed messages**</span></span>|<span data-ttu-id="ae02a-132">(clear)</span><span class="sxs-lookup"><span data-stu-id="ae02a-132">(clear)</span></span>|  
  
    3.  <span data-ttu-id="ae02a-133">Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-133">Click **Receive Locations**, and then click **New**.</span></span>  
  
    4.  <span data-ttu-id="ae02a-134">Desde el cuadro de diálogo Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae02a-134">From Receive Location1 – Receive Location Properties dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="ae02a-135">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-135">Use this</span></span>|<span data-ttu-id="ae02a-136">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-136">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-137">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ae02a-137">**Name**</span></span>|<span data-ttu-id="ae02a-138">Tipo de **ReceiveOrders_SO**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-138">Type **ReceiveOrders_SO**.</span></span>|  
        |<span data-ttu-id="ae02a-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ae02a-139">**Type**</span></span>|<span data-ttu-id="ae02a-140">Seleccione **SB-Messaging**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-140">Select **SB-Messaging**.</span></span>|  
        |<span data-ttu-id="ae02a-141">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="ae02a-141">**Receive handler**</span></span>|<span data-ttu-id="ae02a-142">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-142">Select **BizTalkServerApplication**.</span></span>|  
        |<span data-ttu-id="ae02a-143">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="ae02a-143">**Receive pipeline**</span></span>|<span data-ttu-id="ae02a-144">Seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-144">Select **XMLReceive**.</span></span>|  
  
    5.  <span data-ttu-id="ae02a-145">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-145">Click **Configure**.</span></span>  
  
    6.  <span data-ttu-id="ae02a-146">Cuadro de diálogo Propiedades de transporte SB-Messaging en el **General** ficha, para **cola o la dirección URL de suscripción**, escriba **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-146">From SB-Messaging Transport Properties dialog box, on the **General** tab, for **Queue or Subscription URL**, enter **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**.</span></span> <span data-ttu-id="ae02a-147">En este caso, *mynamespace* es el espacio de nombres de Bus de servicio y *queueordersedi* es la cola de Bus de servicio que creó en [(para Azure) del paso 3: crear una cola de Bus de servicio](../core/step-3-for-azure-create-a-service-bus-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ae02a-147">Here, *mynamespace* is the Service Bus namespace and *queueordersedi* is the Service Bus Queue that you created in [Step 3 (For Azure): Create a Service Bus Queue](../core/step-3-for-azure-create-a-service-bus-queue.md).</span></span>  
  
    7.  <span data-ttu-id="ae02a-148">Cuadro de diálogo Propiedades de transporte SB-Messaging en el **autenticación** ficha, especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae02a-148">From SB-Messaging Transport Properties dialog box, on the **Authentication** tab, specify the following values:</span></span>  
  
        |<span data-ttu-id="ae02a-149">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-149">Use this</span></span>|<span data-ttu-id="ae02a-150">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-150">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-151">**Uri de STS del servicio de Control de acceso**</span><span class="sxs-lookup"><span data-stu-id="ae02a-151">**Access Control Service STS Uri**</span></span>|<span data-ttu-id="ae02a-152">Escriba `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span><span class="sxs-lookup"><span data-stu-id="ae02a-152">Type `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span></span>|  
        |<span data-ttu-id="ae02a-153">**Nombre del emisor**</span><span class="sxs-lookup"><span data-stu-id="ae02a-153">**Issuer name**</span></span>|<span data-ttu-id="ae02a-154">Especifique el nombre del emisor.</span><span class="sxs-lookup"><span data-stu-id="ae02a-154">Specify the issuer name.</span></span> <span data-ttu-id="ae02a-155">Normalmente se establece en `owner`.</span><span class="sxs-lookup"><span data-stu-id="ae02a-155">Typically this is set to `owner`.</span></span>|  
        |<span data-ttu-id="ae02a-156">**Clave del emisor**</span><span class="sxs-lookup"><span data-stu-id="ae02a-156">**Issuer key**</span></span>|<span data-ttu-id="ae02a-157">Especifique la clave del emisor.</span><span class="sxs-lookup"><span data-stu-id="ae02a-157">Specify the issuer key.</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="ae02a-158">Puede obtener los valores para el emisor de la dirección URL de cola, dirección URL de ACS, nombre y la clave de la [Portal de administración de Windows Azure CTP](http://go.microsoft.com/fwlink/p/?LinkId=202886).</span><span class="sxs-lookup"><span data-stu-id="ae02a-158">You can get the values for the Queue URL, ACS URL, issuer name and key from the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886).</span></span>  
  
    8.  <span data-ttu-id="ae02a-159">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae02a-159">Click **OK** until you exit all the dialog boxes.</span></span>  
  
5.  <span data-ttu-id="ae02a-160">En la orquestación, creó un puerto lógico (**SendToSQL**) para enviar mensajes a la **SalesOrder** tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ae02a-160">In the orchestration, you created a logical port (**SendToSQL**) to send messages to the **SalesOrder** database table.</span></span> <span data-ttu-id="ae02a-161">En este paso, se crea un puerto de envío físico para asignar al puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="ae02a-161">In this step, you create a physical send port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="ae02a-162">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-162">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="ae02a-163">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae02a-163">On the General tab, do the following:</span></span>  
  
        |<span data-ttu-id="ae02a-164">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-164">Use this</span></span>|<span data-ttu-id="ae02a-165">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-165">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-166">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ae02a-166">**Name**</span></span>|<span data-ttu-id="ae02a-167">Tipo de **SendToSQL**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-167">Type **SendToSQL**.</span></span>|  
        |<span data-ttu-id="ae02a-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ae02a-168">**Type**</span></span>|<span data-ttu-id="ae02a-169">Seleccione **WCF-SQL**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-169">Select **WCF-SQL**.</span></span>|  
        |<span data-ttu-id="ae02a-170">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="ae02a-170">**Send handler**</span></span>|<span data-ttu-id="ae02a-171">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-171">Select **BizTAlkServerApplication**.</span></span>|  
        |<span data-ttu-id="ae02a-172">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="ae02a-172">**Send pipeline**</span></span>|<span data-ttu-id="ae02a-173">Seleccione **PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-173">Select **PassThruTransmit**.</span></span>|  
  
    3.  <span data-ttu-id="ae02a-174">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-174">Click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="ae02a-175">Propiedades de transporte WCF-SQL en el **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae02a-175">From WCF-SQL Transport Properties, on the **General** tab, do the following:</span></span>  
  
        |<span data-ttu-id="ae02a-176">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-176">Use this</span></span>|<span data-ttu-id="ae02a-177">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-177">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-178">**Dirección (URI)**</span><span class="sxs-lookup"><span data-stu-id="ae02a-178">**Address (URI)**</span></span>|<span data-ttu-id="ae02a-179">Tipo de **mssql://computername/database_instance_name/databasename**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-179">Type **mssql://computername/database_instance_name/databasename**.</span></span> <span data-ttu-id="ae02a-180">Por ejemplo, para conectarse a un **DemoDB** en el equipo local que se ejecuta en la instancia de base de datos predeterminada de base de datos, escriba`mssql://.//DemoDB`</span><span class="sxs-lookup"><span data-stu-id="ae02a-180">For example, to connect to a **DemoDB** database on the local computer running under the default database instance, enter `mssql://.//DemoDB`</span></span><br /><br /> <span data-ttu-id="ae02a-181">Para obtener más información, consulte [crear el URI de conexión de SQL Server](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="ae02a-181">For more information, see [Create the SQL Server connection URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>|  
        |<span data-ttu-id="ae02a-182">**Acción**</span><span class="sxs-lookup"><span data-stu-id="ae02a-182">**Action**</span></span>|<span data-ttu-id="ae02a-183">Tipo de **TableOp/Insert/dbo/SalesOrder**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-183">Type **TableOp/Insert/dbo/SalesOrder**.</span></span>|  
  
    5.  <span data-ttu-id="ae02a-184">Propiedades de transporte WCF-SQL en el **credenciales** ficha, seleccione **no use Single Sign-On**y especifique las credenciales (distingue mayúsculas de minúsculas) para conectarse a la base de datos de SQL Server que especificó en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="ae02a-184">From WCF-SQL Transport Properties, on the **Credentials** tab, select **Do not use Single Sign-On**, and specify credentials (case-sensitive) to connect to the SQL Server database you specified in the connection string.</span></span> <span data-ttu-id="ae02a-185">Si quiere conectase usando la autenticación de Windows, deje las credenciales en blanco.</span><span class="sxs-lookup"><span data-stu-id="ae02a-185">If you want to connect using Windows Authentication, leave the credentials blank.</span></span>  
  
    6.  <span data-ttu-id="ae02a-186">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae02a-186">Click **OK** until you exit all the dialog boxes.</span></span>  
  
6.  <span data-ttu-id="ae02a-187">En la orquestación, creó un puerto lógico (**SendToFile**) para enviar mensajes a una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="ae02a-187">In the orchestration, you created a logical port (**SendToFile**) to send messages to a shared file location.</span></span> <span data-ttu-id="ae02a-188">En este paso, se crea un puerto de envío físico para asignar al puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="ae02a-188">In this step, you create a physical send port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="ae02a-189">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-189">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="ae02a-190">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae02a-190">On the General tab, do the following:</span></span>  
  
        |<span data-ttu-id="ae02a-191">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-191">Use this</span></span>|<span data-ttu-id="ae02a-192">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-192">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-193">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ae02a-193">**Name**</span></span>|<span data-ttu-id="ae02a-194">Tipo de **SendToFile**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-194">Type **SendToFile**.</span></span>|  
        |<span data-ttu-id="ae02a-195">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ae02a-195">**Type**</span></span>|<span data-ttu-id="ae02a-196">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-196">Select **File**.</span></span>|  
        |<span data-ttu-id="ae02a-197">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="ae02a-197">**Send handler**</span></span>|<span data-ttu-id="ae02a-198">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-198">Select **BizTAlkServerApplication**.</span></span>|  
        |<span data-ttu-id="ae02a-199">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="ae02a-199">**Send pipeline**</span></span>|<span data-ttu-id="ae02a-200">Seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-200">Select **XML Transmit**.</span></span>|  
  
    3.  <span data-ttu-id="ae02a-201">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-201">Click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="ae02a-202">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae02a-202">From File Transport Properties, do the following:</span></span>  
  
        |<span data-ttu-id="ae02a-203">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-203">Use this</span></span>|<span data-ttu-id="ae02a-204">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-204">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-205">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="ae02a-205">**Receive folder**</span></span>|<span data-ttu-id="ae02a-206">Especifique la ubicación donde desea enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae02a-206">Specify the location where you want to send the message.</span></span>|  
        |<span data-ttu-id="ae02a-207">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="ae02a-207">**File name**</span></span>|<span data-ttu-id="ae02a-208">Conservar **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-208">Retain **%MessageID%.xml**.</span></span>|  
  
    5.  <span data-ttu-id="ae02a-209">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae02a-209">Click **OK** until you exit all the dialog boxes.</span></span>  
  
7.  <span data-ttu-id="ae02a-210">Ahora debe enlazar los puertos físico y lógico para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae02a-210">You must now bind the physical and logical ports together to configure the application.</span></span>  
  
    1.  <span data-ttu-id="ae02a-211">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-211">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Configure**.</span></span>  
  
    2.  <span data-ttu-id="ae02a-212">Desde Configurar aplicación, en el panel izquierdo, haga clic en **OrderProcessing**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-212">From Configure Application, in the left pane, click **OrderProcessing**.</span></span>  
  
    3.  <span data-ttu-id="ae02a-213">Use los valores en la siguiente tabla para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae02a-213">Use the values in the following table to configure the application.</span></span>  
  
        |<span data-ttu-id="ae02a-214">Use</span><span class="sxs-lookup"><span data-stu-id="ae02a-214">Use this</span></span>|<span data-ttu-id="ae02a-215">Para</span><span class="sxs-lookup"><span data-stu-id="ae02a-215">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ae02a-216">Para **Host**</span><span class="sxs-lookup"><span data-stu-id="ae02a-216">For **Host**</span></span>|<span data-ttu-id="ae02a-217">Seleccione **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="ae02a-217">Select **BizTalkServerApplication**</span></span>|  
        |<span data-ttu-id="ae02a-218">Para el puerto lógico **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="ae02a-218">For logical port **ReceiveSO**</span></span>|<span data-ttu-id="ae02a-219">Seleccionar puerto físico **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="ae02a-219">Select physical port **ReceiveSO**</span></span>|  
        |<span data-ttu-id="ae02a-220">Para el puerto lógico **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="ae02a-220">For logical port **SendToSQL**</span></span>|<span data-ttu-id="ae02a-221">Seleccionar puerto físico **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="ae02a-221">Select physical port **SendToSQL**</span></span>|  
        |<span data-ttu-id="ae02a-222">Para el puerto lógico **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="ae02a-222">For logical port **SendToFile**</span></span>|<span data-ttu-id="ae02a-223">Seleccionar puerto físico **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="ae02a-223">Select physical port **SendToFile**</span></span>|  
  
    4.  <span data-ttu-id="ae02a-224">Haga clic en **Aceptar** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="ae02a-224">Click **OK** to save the configuration.</span></span>  
  
## <a name="start-the-application"></a><span data-ttu-id="ae02a-225">Iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ae02a-225">Start the application</span></span>  
  
1.  <span data-ttu-id="ae02a-226">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-226">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="ae02a-227">En el cuadro de diálogo, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ae02a-227">From the dialog, click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae02a-228">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae02a-228">See Also</span></span>  
 [<span data-ttu-id="ae02a-229">Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae02a-229">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)