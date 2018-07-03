---
title: 'Paso 8 (local): Configurar la aplicación de BizTalk Server | Microsoft Docs'
ms.custom: ''
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b3eafcc5e49bb6fa360f1db4b6e92d9393068a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996845"
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a><span data-ttu-id="f6af4-102">Paso 8 (local): Configurar la aplicación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f6af4-102">Step 8 (On Premises): Configure the BizTalk Server Application</span></span>
<span data-ttu-id="f6af4-103">En el paso anterior, creó una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6af4-103">In the previous step you created a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="f6af4-104">En este paso, compilará, implementará y configurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f6af4-104">In this step, you’ll build, deploy, and configure the application.</span></span>  

## <a name="build-and-deploy-the-application"></a><span data-ttu-id="f6af4-105">Compilar e implementar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f6af4-105">Build and deploy the application</span></span>  

1.  <span data-ttu-id="f6af4-106">En Visual Studio, haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-106">In Visual Studio, right-click the solution name in the Solution Explorer, and click **Build**.</span></span>  

2.  <span data-ttu-id="f6af4-107">El proceso de implementación necesita que el ensamblado esté firmado de forma segura.</span><span class="sxs-lookup"><span data-stu-id="f6af4-107">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="f6af4-108">Debe firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="f6af4-108">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  

    1.  <span data-ttu-id="f6af4-109">En el Explorador de soluciones, haga clic en el **OrderProcessingDemo** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-109">In Solution Explorer, right-click the **OrderProcessingDemo** project, and then click **Properties**.</span></span>  

    2.  <span data-ttu-id="f6af4-110">Haga clic en el **firma** pestaña y seleccione el **firmar el ensamblado** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="f6af4-110">Click the **Signing** tab, and select the **Sign the assembly** checkbox.</span></span>  

    3.  <span data-ttu-id="f6af4-111">En la lista desplegable en el **elegir un archivo de clave de nombre seguro** cuadro, seleccione  **\<nuevo... \>**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-111">From the drop-down list in the **Choose a strong name key file** box, select **\<New…\>**.</span></span>  

    4.  <span data-ttu-id="f6af4-112">En el **crear clave de nombre seguro** diálogo cuadro, escriba un nombre para el archivo de clave, por ejemplo `OrderProcessingDemo.snk`.</span><span class="sxs-lookup"><span data-stu-id="f6af4-112">In the **Create Strong Name Key** dialog box, enter a name for the key file, for example `OrderProcessingDemo.snk`.</span></span> <span data-ttu-id="f6af4-113">Desactive la casilla de verificación para proteger el archivo de clave con una contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-113">Clear the checkbox for protecting the key file with a password, and then click **OK**.</span></span>  

3.  <span data-ttu-id="f6af4-114">Haga clic en el **implementación** ficha, en el cuadro a la derecha del **nombre de la aplicación**, tipo `OrderProcessingDemo`.</span><span class="sxs-lookup"><span data-stu-id="f6af4-114">Click the **Deployment** tab, in the box to the right of **Application Name**, type `OrderProcessingDemo`.</span></span>  

4.  <span data-ttu-id="f6af4-115">En la lista desplegable en el cuadro a la derecha del **volver a implementar**, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-115">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  

5.  <span data-ttu-id="f6af4-116">En el Explorador de soluciones, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-116">In Solution Explorer, right-click **OrderProcessingDemo**, and then click **Deploy**.</span></span>  <span data-ttu-id="f6af4-117">En la ventana de salida se debe ver:</span><span class="sxs-lookup"><span data-stu-id="f6af4-117">The Output window should display:</span></span>  

    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  

    ```  

## <a name="configure-the-application"></a><span data-ttu-id="f6af4-118">Configurar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f6af4-118">Configure the application</span></span>  

1. <span data-ttu-id="f6af4-119">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6af4-119">Click **Start**, point to **All Programs**, point to **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="f6af4-120">En el árbol de consola en el panel izquierdo, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-120">In the console tree on the left pane, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  

3. <span data-ttu-id="f6af4-121">Expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **OrderProcessingDemo**y, a continuación, haga clic en **orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-121">Expand **BizTalk Group**, expand **Applications**, expand **OrderProcessingDemo**, and then click **Orchestrations**.</span></span> <span data-ttu-id="f6af4-122">Verá que el **OrderProcessingDemo.OrderProcessing** se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f6af4-122">You will see that the **OrderProcessingDemo.OrderProcessing** orchestration is deployed.</span></span>  

4. <span data-ttu-id="f6af4-123">En la orquestación, creó un puerto lógico (**ReceiveSO**) para recibir mensajes de la cola de Service Bus.</span><span class="sxs-lookup"><span data-stu-id="f6af4-123">In the orchestration, you created a logical port (**ReceiveSO**) to receive messages from the Service Bus Queue.</span></span> <span data-ttu-id="f6af4-124">En este paso, se crea un puerto de recepción físico para asignar al puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="f6af4-124">In this step, you create a physical receive port to map to the logical port.</span></span>  

   1. <span data-ttu-id="f6af4-125">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **Unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-125">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

   2. <span data-ttu-id="f6af4-126">En la pestaña **General** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6af4-126">On the **General** tab, do the following:</span></span>  


      |                <span data-ttu-id="f6af4-127">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-127">Use this</span></span>                |     <span data-ttu-id="f6af4-128">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-128">To do this</span></span>      |
      |----------------------------------------|---------------------|
      |                <span data-ttu-id="f6af4-129">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="f6af4-129">**Name**</span></span>                | <span data-ttu-id="f6af4-130">Tipo **ReceiveSO**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-130">Type **ReceiveSO**.</span></span> |
      | <span data-ttu-id="f6af4-131">**Habilitar enrutamiento para mensajes con errores**</span><span class="sxs-lookup"><span data-stu-id="f6af4-131">**Enable routing for failed messages**</span></span> |       <span data-ttu-id="f6af4-132">(clear)</span><span class="sxs-lookup"><span data-stu-id="f6af4-132">(clear)</span></span>       |


   3. <span data-ttu-id="f6af4-133">Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-133">Click **Receive Locations**, and then click **New**.</span></span>  

   4. <span data-ttu-id="f6af4-134">Desde el cuadro de diálogo Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6af4-134">From Receive Location1 – Receive Location Properties dialog box, do the following:</span></span>  


      |       <span data-ttu-id="f6af4-135">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-135">Use this</span></span>       |              <span data-ttu-id="f6af4-136">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-136">To do this</span></span>              |
      |----------------------|--------------------------------------|
      |       <span data-ttu-id="f6af4-137">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="f6af4-137">**Name**</span></span>       |      <span data-ttu-id="f6af4-138">Tipo **ReceiveOrders_SO**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-138">Type **ReceiveOrders_SO**.</span></span>      |
      |       <span data-ttu-id="f6af4-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f6af4-139">**Type**</span></span>       |       <span data-ttu-id="f6af4-140">Seleccione **SB-Messaging**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-140">Select **SB-Messaging**.</span></span>       |
      | <span data-ttu-id="f6af4-141">**Controlador de recepción**</span><span class="sxs-lookup"><span data-stu-id="f6af4-141">**Receive handler**</span></span>  | <span data-ttu-id="f6af4-142">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-142">Select **BizTalkServerApplication**.</span></span> |
      | <span data-ttu-id="f6af4-143">**Canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="f6af4-143">**Receive pipeline**</span></span> |        <span data-ttu-id="f6af4-144">Seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-144">Select **XMLReceive**.</span></span>        |


   5. <span data-ttu-id="f6af4-145">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-145">Click **Configure**.</span></span>  

   6. <span data-ttu-id="f6af4-146">Desde el cuadro de diálogo Propiedades de transporte SB-Messaging, en el **General** ficha, para **cola o la dirección URL de suscripción**, escriba **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi** .</span><span class="sxs-lookup"><span data-stu-id="f6af4-146">From SB-Messaging Transport Properties dialog box, on the **General** tab, for **Queue or Subscription URL**, enter **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**.</span></span> <span data-ttu-id="f6af4-147">En este caso, *mynamespace* es el espacio de nombres de Service Bus y *queueordersedi* es la cola de Service Bus que creó en [(Azure) del paso 3: crear una cola de Service Bus](../core/step-3-for-azure-create-a-service-bus-queue.md).</span><span class="sxs-lookup"><span data-stu-id="f6af4-147">Here, *mynamespace* is the Service Bus namespace and *queueordersedi* is the Service Bus Queue that you created in [Step 3 (For Azure): Create a Service Bus Queue](../core/step-3-for-azure-create-a-service-bus-queue.md).</span></span>  

   7. <span data-ttu-id="f6af4-148">Desde el cuadro de diálogo Propiedades de transporte SB-Messaging, en el **autenticación** ficha, especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6af4-148">From SB-Messaging Transport Properties dialog box, on the **Authentication** tab, specify the following values:</span></span>  

      |<span data-ttu-id="f6af4-149">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-149">Use this</span></span>|<span data-ttu-id="f6af4-150">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-150">To do this</span></span>|  
      |--------------|----------------|  
      |<span data-ttu-id="f6af4-151">**Uri de STS de Access Control Service**</span><span class="sxs-lookup"><span data-stu-id="f6af4-151">**Access Control Service STS Uri**</span></span>|<span data-ttu-id="f6af4-152">Escriba `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span><span class="sxs-lookup"><span data-stu-id="f6af4-152">Type `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span></span>|  
      |<span data-ttu-id="f6af4-153">**Nombre del emisor**</span><span class="sxs-lookup"><span data-stu-id="f6af4-153">**Issuer name**</span></span>|<span data-ttu-id="f6af4-154">Especifique el nombre del emisor.</span><span class="sxs-lookup"><span data-stu-id="f6af4-154">Specify the issuer name.</span></span> <span data-ttu-id="f6af4-155">Normalmente esto se establece en `owner`.</span><span class="sxs-lookup"><span data-stu-id="f6af4-155">Typically this is set to `owner`.</span></span>|  
      |<span data-ttu-id="f6af4-156">**Clave del emisor**</span><span class="sxs-lookup"><span data-stu-id="f6af4-156">**Issuer key**</span></span>|<span data-ttu-id="f6af4-157">Especifique la clave del emisor.</span><span class="sxs-lookup"><span data-stu-id="f6af4-157">Specify the issuer key.</span></span>|  

      > [!NOTE]
      >  <span data-ttu-id="f6af4-158">Puede obtener los valores para el emisor de la dirección URL de cola, dirección URL de ACS, nombre y la clave de la [Portal de administración de Windows Azure CTP](http://go.microsoft.com/fwlink/p/?LinkId=202886).</span><span class="sxs-lookup"><span data-stu-id="f6af4-158">You can get the values for the Queue URL, ACS URL, issuer name and key from the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886).</span></span>  

   8. <span data-ttu-id="f6af4-159">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f6af4-159">Click **OK** until you exit all the dialog boxes.</span></span>  

5. <span data-ttu-id="f6af4-160">En la orquestación, creó un puerto lógico (**SendToSQL**) para enviar mensajes a la **SalesOrder** tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="f6af4-160">In the orchestration, you created a logical port (**SendToSQL**) to send messages to the **SalesOrder** database table.</span></span> <span data-ttu-id="f6af4-161">En este paso, se crea un puerto de envío físico para asignar al puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="f6af4-161">In this step, you create a physical send port to map to the logical port.</span></span>  

   1. <span data-ttu-id="f6af4-162">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-162">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

   2. <span data-ttu-id="f6af4-163">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6af4-163">On the General tab, do the following:</span></span>  


      |     <span data-ttu-id="f6af4-164">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-164">Use this</span></span>      |              <span data-ttu-id="f6af4-165">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-165">To do this</span></span>              |
      |-------------------|--------------------------------------|
      |     <span data-ttu-id="f6af4-166">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="f6af4-166">**Name**</span></span>      |         <span data-ttu-id="f6af4-167">Tipo **SendToSQL**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-167">Type **SendToSQL**.</span></span>          |
      |     <span data-ttu-id="f6af4-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f6af4-168">**Type**</span></span>      |         <span data-ttu-id="f6af4-169">Seleccione **WCF-SQL**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-169">Select **WCF-SQL**.</span></span>          |
      | <span data-ttu-id="f6af4-170">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="f6af4-170">**Send handler**</span></span>  | <span data-ttu-id="f6af4-171">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-171">Select **BizTAlkServerApplication**.</span></span> |
      | <span data-ttu-id="f6af4-172">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="f6af4-172">**Send pipeline**</span></span> |     <span data-ttu-id="f6af4-173">Seleccione **PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-173">Select **PassThruTransmit**.</span></span>     |


   3. <span data-ttu-id="f6af4-174">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-174">Click **Configure**.</span></span>  

   4. <span data-ttu-id="f6af4-175">Propiedades de transporte WCF-SQL en el **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6af4-175">From WCF-SQL Transport Properties, on the **General** tab, do the following:</span></span>  


      |     <span data-ttu-id="f6af4-176">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-176">Use this</span></span>      |                                                                                                                                                                                    <span data-ttu-id="f6af4-177">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-177">To do this</span></span>                                                                                                                                                                                    |
      |-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      | <span data-ttu-id="f6af4-178">**Dirección (URI)**</span><span class="sxs-lookup"><span data-stu-id="f6af4-178">**Address (URI)**</span></span> | <span data-ttu-id="f6af4-179">Tipo **mssql://computername/database_instance_name/databasename**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-179">Type **mssql://computername/database_instance_name/databasename**.</span></span> <span data-ttu-id="f6af4-180">Por ejemplo, para conectarse a un **DemoDB** base de datos en el equipo local que se ejecutan en la instancia de base de datos predeterminada, escriba `mssql://.//DemoDB`</span><span class="sxs-lookup"><span data-stu-id="f6af4-180">For example, to connect to a **DemoDB** database on the local computer running under the default database instance, enter `mssql://.//DemoDB`</span></span><br /><br /> <span data-ttu-id="f6af4-181">Para obtener más información, consulte [crear el URI de conexión de SQL Server](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="f6af4-181">For more information, see [Create the SQL Server connection URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span> |
      |    <span data-ttu-id="f6af4-182">**Acción**</span><span class="sxs-lookup"><span data-stu-id="f6af4-182">**Action**</span></span>     |                                                                                                                                                                     <span data-ttu-id="f6af4-183">Tipo **TableOp/Insert/dbo/SalesOrder**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-183">Type **TableOp/Insert/dbo/SalesOrder**.</span></span>                                                                                                                                                                      |


   5. <span data-ttu-id="f6af4-184">Propiedades de transporte WCF-SQL en el **credenciales** ficha, seleccione **no use Single Sign-On**y especifique las credenciales (distingue mayúsculas de minúsculas) para conectarse a SQL Server de base de datos que especificó en el cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="f6af4-184">From WCF-SQL Transport Properties, on the **Credentials** tab, select **Do not use Single Sign-On**, and specify credentials (case-sensitive) to connect to the SQL Server database you specified in the connection string.</span></span> <span data-ttu-id="f6af4-185">Si quiere conectase usando la autenticación de Windows, deje las credenciales en blanco.</span><span class="sxs-lookup"><span data-stu-id="f6af4-185">If you want to connect using Windows Authentication, leave the credentials blank.</span></span>  

   6. <span data-ttu-id="f6af4-186">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f6af4-186">Click **OK** until you exit all the dialog boxes.</span></span>  

6. <span data-ttu-id="f6af4-187">En la orquestación, creó un puerto lógico (**SendToFile**) para enviar mensajes a una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="f6af4-187">In the orchestration, you created a logical port (**SendToFile**) to send messages to a shared file location.</span></span> <span data-ttu-id="f6af4-188">En este paso, se crea un puerto de envío físico para asignar al puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="f6af4-188">In this step, you create a physical send port to map to the logical port.</span></span>  

   1. <span data-ttu-id="f6af4-189">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-189">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

   2. <span data-ttu-id="f6af4-190">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6af4-190">On the General tab, do the following:</span></span>  


      |     <span data-ttu-id="f6af4-191">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-191">Use this</span></span>      |              <span data-ttu-id="f6af4-192">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-192">To do this</span></span>              |
      |-------------------|--------------------------------------|
      |     <span data-ttu-id="f6af4-193">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="f6af4-193">**Name**</span></span>      |         <span data-ttu-id="f6af4-194">Tipo **SendToFile**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-194">Type **SendToFile**.</span></span>         |
      |     <span data-ttu-id="f6af4-195">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f6af4-195">**Type**</span></span>      |           <span data-ttu-id="f6af4-196">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-196">Select **File**.</span></span>           |
      | <span data-ttu-id="f6af4-197">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="f6af4-197">**Send handler**</span></span>  | <span data-ttu-id="f6af4-198">Seleccione **BizTAlkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-198">Select **BizTAlkServerApplication**.</span></span> |
      | <span data-ttu-id="f6af4-199">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="f6af4-199">**Send pipeline**</span></span> |       <span data-ttu-id="f6af4-200">Seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-200">Select **XML Transmit**.</span></span>       |


   3. <span data-ttu-id="f6af4-201">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-201">Click **Configure**.</span></span>  

   4. <span data-ttu-id="f6af4-202">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6af4-202">From File Transport Properties, do the following:</span></span>  


      |      <span data-ttu-id="f6af4-203">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-203">Use this</span></span>      |                        <span data-ttu-id="f6af4-204">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-204">To do this</span></span>                        |
      |--------------------|----------------------------------------------------------|
      | <span data-ttu-id="f6af4-205">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="f6af4-205">**Receive folder**</span></span> | <span data-ttu-id="f6af4-206">Especifique la ubicación donde desea enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f6af4-206">Specify the location where you want to send the message.</span></span> |
      |   <span data-ttu-id="f6af4-207">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="f6af4-207">**File name**</span></span>    |               <span data-ttu-id="f6af4-208">Conservar **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-208">Retain **%MessageID%.xml**.</span></span>                |


   5. <span data-ttu-id="f6af4-209">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f6af4-209">Click **OK** until you exit all the dialog boxes.</span></span>  

7. <span data-ttu-id="f6af4-210">Ahora debe enlazar los puertos físico y lógico para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f6af4-210">You must now bind the physical and logical ports together to configure the application.</span></span>  

   1. <span data-ttu-id="f6af4-211">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-211">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Configure**.</span></span>  

   2. <span data-ttu-id="f6af4-212">Desde Configurar aplicación, en el panel izquierdo, haga clic en **OrderProcessing**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-212">From Configure Application, in the left pane, click **OrderProcessing**.</span></span>  

   3. <span data-ttu-id="f6af4-213">Use los valores en la siguiente tabla para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f6af4-213">Use the values in the following table to configure the application.</span></span>  


      |            <span data-ttu-id="f6af4-214">Use</span><span class="sxs-lookup"><span data-stu-id="f6af4-214">Use this</span></span>             |             <span data-ttu-id="f6af4-215">Para</span><span class="sxs-lookup"><span data-stu-id="f6af4-215">To do this</span></span>              |
      |---------------------------------|-------------------------------------|
      |          <span data-ttu-id="f6af4-216">Para **Host**</span><span class="sxs-lookup"><span data-stu-id="f6af4-216">For **Host**</span></span>           | <span data-ttu-id="f6af4-217">Seleccione **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="f6af4-217">Select **BizTalkServerApplication**</span></span> |
      | <span data-ttu-id="f6af4-218">Para el puerto lógico **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="f6af4-218">For logical port **ReceiveSO**</span></span>  | <span data-ttu-id="f6af4-219">Seleccionar puerto físico **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="f6af4-219">Select physical port **ReceiveSO**</span></span>  |
      | <span data-ttu-id="f6af4-220">Para el puerto lógico **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="f6af4-220">For logical port **SendToSQL**</span></span>  | <span data-ttu-id="f6af4-221">Seleccionar puerto físico **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="f6af4-221">Select physical port **SendToSQL**</span></span>  |
      | <span data-ttu-id="f6af4-222">Para el puerto lógico **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="f6af4-222">For logical port **SendToFile**</span></span> | <span data-ttu-id="f6af4-223">Seleccionar puerto físico **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="f6af4-223">Select physical port **SendToFile**</span></span> |


   4. <span data-ttu-id="f6af4-224">Haga clic en **Aceptar** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="f6af4-224">Click **OK** to save the configuration.</span></span>  

## <a name="start-the-application"></a><span data-ttu-id="f6af4-225">Iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f6af4-225">Start the application</span></span>  

1. <span data-ttu-id="f6af4-226">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-226">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Start**.</span></span>  

2. <span data-ttu-id="f6af4-227">En el cuadro de diálogo, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f6af4-227">From the dialog, click **Start**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f6af4-228">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6af4-228">See Also</span></span>  
 [<span data-ttu-id="f6af4-229">Tutorial 4: Crear una aplicación híbrida con BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6af4-229">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)