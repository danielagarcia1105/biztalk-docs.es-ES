---
title: Cómo ejecutar la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, validating
- process management solution tutorial, submitting orders
- process management solution tutorial, stopping orders
- process management solution tutorial, updating orders
ms.assetid: cb77651e-e16c-49dc-9f8a-88584cd68a8b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3997fb18e7498ab2bc5f8c77b53740fb87ab6f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257628"
---
# <a name="how-to-run-the-business-process-management-solution"></a><span data-ttu-id="37861-102">Cómo ejecutar la solución de administración de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="37861-102">How to Run the Business Process Management Solution</span></span>
<span data-ttu-id="37861-103">Los pasos siguientes describen cómo ejecutar y validar la solución de administración de proceso empresarial en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="37861-103">The following steps describe how to run and validate the Business Process Management solution on a single computer.</span></span>  
  
-   [<span data-ttu-id="37861-104">Iniciar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="37861-104">Start the Business Process Management Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="37861-105">Ejecutar y validar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="37861-105">Run and validate the Business Process Management Solution</span></span>](#step3)  
  
## <a name="prerequisites"></a><span data-ttu-id="37861-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="37861-106">Prerequisites</span></span>  
 <span data-ttu-id="37861-107">Antes de ejecutar la solución BPM, debe realizar los pasos descritos en [cómo instalar la solución de administración de procesos empresariales](../core/how-to-install-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="37861-107">Before running the BPM solution, you must perform the steps in [How to Install the Business Process Management Solution](../core/how-to-install-the-business-process-management-solution.md).</span></span>  
  
##  <a name="step1"></a><span data-ttu-id="37861-108">Iniciar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="37861-108">Start the Business Process Management Solution</span></span>  
  
#### <a name="to-start-the-business-process-management-solution"></a><span data-ttu-id="37861-109">Para iniciar la solución de administración de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="37861-109">To start the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="37861-110">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="37861-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="37861-111">En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**, expanda **instancias de Host**, Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="37861-111">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="37861-112">En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="37861-112">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
    1.  <span data-ttu-id="37861-113">Haga clic en BTSScn.BPM.MessagingApp, haga clic en **iniciar**y, a continuación, haga clic en **iniciar** en el **Iniciar aplicación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="37861-113">Right-click BTSScn.BPM.MessagingApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    2.  <span data-ttu-id="37861-114">Haga clic en BTSScn.BPM.OrderBrokerApp, haga clic en **iniciar**y, a continuación, haga clic en **iniciar** en el **Iniciar aplicación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="37861-114">Right-click BTSScn.BPM.OrderBrokerApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    3.  <span data-ttu-id="37861-115">Haga clic en BTSScn.BPM.CableOrderApp, haga clic en **iniciar**y, a continuación, haga clic en **iniciar** en el **Iniciar aplicación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="37861-115">Right-click BTSScn.BPM.CableOrderApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    4.  <span data-ttu-id="37861-116">Haga clic en BTSScn.BPM.OrderBrokerApp.Test y haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="37861-116">Right-click BTSScn.BPM.OrderBrokerApp.Test, and click **Stop**.</span></span> <span data-ttu-id="37861-117">En el **detener aplicación** cuadro de diálogo, seleccione **detención completa: finalizar instancia**y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="37861-117">In the **Stop Application** dialog box, select **Full Stop - Terminate instance**, and then click **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37861-118">Para insertar información en la base de datos de historial.</span><span class="sxs-lookup"><span data-stu-id="37861-118">To insert information in the history database.</span></span> <span data-ttu-id="37861-119">la orquestación OrderBroker utiliza el puerto de envío historyport, donde la **notificación de entrega** se establece la propiedad **transmitido**.</span><span class="sxs-lookup"><span data-stu-id="37861-119">the OrderBroker orchestration uses the HistoryPort send port of which the **Delivery Notification** property is set **Transmitted**.</span></span> <span data-ttu-id="37861-120">El puerto de envío está enlazado con el grupo de envío HistoryInsert-SPG, que incluye los puertos de envío HistoryInsert-SP y HistoryInsert-Test-SP.</span><span class="sxs-lookup"><span data-stu-id="37861-120">The send port is bounded to the HistoryInsert-SPG send group which includes the HistoryInsert-SP and HistoryInsert-Test-SP send ports.</span></span> <span data-ttu-id="37861-121">En estos dos puertos de envío el motor de mensajes publicará dos mensajes de confirmación a la orquestación OrderBroker.</span><span class="sxs-lookup"><span data-stu-id="37861-121">For these two send ports the message engine will publish two acknowledgment messages to the OrderBroker orchestration.</span></span> <span data-ttu-id="37861-122">Con esto, la orquestación se suspende debido a la existencia de mensajes sin consumir.</span><span class="sxs-lookup"><span data-stu-id="37861-122">It makes the orchestration suspended due to unconsumed messages.</span></span> <span data-ttu-id="37861-123">Para evitar esta situación, debe dar de baja uno de los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="37861-123">To avoid this situation, you must unenlist one of the send ports.</span></span> <span data-ttu-id="37861-124">En este tutorial, se dará de alta el puerto de envío HistoryInsert-Test-SP mediante la detención total de la aplicación BTSScn.BPM.OrderBrokerApp.Test.</span><span class="sxs-lookup"><span data-stu-id="37861-124">In this walkthrough, unenlist HistoryInsert-Test-SP send port by fully stopping the BTSScn.BPM.OrderBrokerApp.Test application.</span></span> <span data-ttu-id="37861-125">Para obtener más información acerca de la orquestación OrderBroker, vea [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="37861-125">For more information about the OrderBroker orchestration, see [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).</span></span> <span data-ttu-id="37861-126">Para obtener más información acerca de **notificación de entrega** propiedad, vea [confirmaciones utilizando](../core/using-acknowledgments.md).</span><span class="sxs-lookup"><span data-stu-id="37861-126">For more information about **Delivery Notification** property, see [Using Acknowledgments](../core/using-acknowledgments.md).</span></span>  
  
4.  <span data-ttu-id="37861-127">Ejecute el simulador de instalaciones como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="37861-127">Run the Facilities Simulator as follows:</span></span>  
  
    1.  <span data-ttu-id="37861-128">Abra un símbolo del sistema y cambie el directorio a la carpeta %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="37861-128">Open a command prompt, change the directory to the %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="37861-129">Escriba `BTSScnBPMFacilities.exe` y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="37861-129">Type `BTSScnBPMFacilities.exe`, and then press ENTER.</span></span> <span data-ttu-id="37861-130">Mantenga el simulador de instalaciones en ejecución.</span><span class="sxs-lookup"><span data-stu-id="37861-130">Keep the FacilitiesSimulator running.</span></span> <span data-ttu-id="37861-131">Esta aplicación simula las instalaciones que procesan sistemas de servidor en Southridge Video.</span><span class="sxs-lookup"><span data-stu-id="37861-131">This application simulates the facilities processing back-end systems at Southridge Video.</span></span>  
  
    3.  <span data-ttu-id="37861-132">En el simulador de instalaciones, escriba las siguientes colas de recepción y transmisión:</span><span class="sxs-lookup"><span data-stu-id="37861-132">In the FacilitiesSimulator, type the following receive and transmit queues:</span></span>  
  
        |<span data-ttu-id="37861-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="37861-133">Name</span></span>|<span data-ttu-id="37861-134">Valor</span><span class="sxs-lookup"><span data-stu-id="37861-134">Value</span></span>|  
        |----------|-----------|  
        |<span data-ttu-id="37861-135">**Cola de recepción**</span><span class="sxs-lookup"><span data-stu-id="37861-135">**Receive Queue**</span></span>|`.\private$\ToFacilitiesQ`|  
        |<span data-ttu-id="37861-136">**Cola de transmisión**</span><span class="sxs-lookup"><span data-stu-id="37861-136">**Transmit Queue**</span></span>|`.\private$\FromFacilitiesQ`|  
  
    4.  <span data-ttu-id="37861-137">En el simulador de instalaciones, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="37861-137">In the FacilitiesSimulator, Click **Start**.</span></span>  
  
5.  <span data-ttu-id="37861-138">Ejecute el servidor de operaciones como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="37861-138">Run the Operation Server as follows:</span></span>  
  
    1.  <span data-ttu-id="37861-139">Abra un símbolo del sistema nuevo y cambie el directorio actual a la carpeta %BTSSolutionsPath%\BPM\OperationsServer\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="37861-139">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\OperationsServer\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="37861-140">Tipo `BTSScnBPMOperations.exe 8881` en el símbolo del sistema y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="37861-140">Type `BTSScnBPMOperations.exe 8881` at the command prompt, and then press ENTER.</span></span> <span data-ttu-id="37861-141">Mantenga el servidor de operaciones en ejecución.</span><span class="sxs-lookup"><span data-stu-id="37861-141">Keep the Operation Server running.</span></span> <span data-ttu-id="37861-142">El servidor de operaciones escucha en el puerto TCP, 8881, para recibir mensajes de error del adaptador Ops.</span><span class="sxs-lookup"><span data-stu-id="37861-142">The Operation Server listens on the TCP port, 8881, to receive error messages from the Ops Adapter.</span></span> <span data-ttu-id="37861-143">Muestra los mensajes de error que recibe el adaptador Ops.</span><span class="sxs-lookup"><span data-stu-id="37861-143">It displays the error messages received by the Ops Adapter.</span></span>  
  
6.  <span data-ttu-id="37861-144">Ejecute el sistema de suministro de cable como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="37861-144">Run the Cable Provisioning System as follows:</span></span>  
  
    1.  <span data-ttu-id="37861-145">Abra un símbolo del sistema nuevo y cambie el directorio actual a la carpeta %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="37861-145">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="37861-146">Escriba `BTSScnBPMProvisioning.exe 8880` y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="37861-146">Type `BTSScnBPMProvisioning.exe 8880`, and then press ENTER.</span></span> <span data-ttu-id="37861-147">A continuación, mantenga el sistema de suministro de cable en ejecución.</span><span class="sxs-lookup"><span data-stu-id="37861-147">Then, keep the Cable Provisioning System running.</span></span> <span data-ttu-id="37861-148">El sistema de suministro de Cable escucha en el puerto TPC 8880.</span><span class="sxs-lookup"><span data-stu-id="37861-148">The Cable Provisioning System listens on the TCP port, 8880.</span></span> <span data-ttu-id="37861-149">Esta aplicación simula un sistema de pedidos de back-end y muestra los pedidos finales.</span><span class="sxs-lookup"><span data-stu-id="37861-149">This application simulates a back-end order system, and displays the final orders.</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="37861-150">Ejecutar y validar la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="37861-150">Run and validate the Business Process Management Solution</span></span>  
  
#### <a name="to-submit-a-new-order-and-validate-the-solution"></a><span data-ttu-id="37861-151">Para enviar un pedido nuevo y validar la solución.</span><span class="sxs-lookup"><span data-stu-id="37861-151">To submit a new order and validate the solution</span></span>  
  
1.  <span data-ttu-id="37861-152">En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-152">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="37861-153">En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order.**</span><span class="sxs-lookup"><span data-stu-id="37861-153">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order.**</span></span>  
  
    |<span data-ttu-id="37861-154">Entrada</span><span class="sxs-lookup"><span data-stu-id="37861-154">Entry</span></span>|<span data-ttu-id="37861-155">Valor</span><span class="sxs-lookup"><span data-stu-id="37861-155">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="37861-156">Customer ID</span><span class="sxs-lookup"><span data-stu-id="37861-156">Customer ID</span></span>|<span data-ttu-id="37861-157">1</span><span class="sxs-lookup"><span data-stu-id="37861-157">1</span></span>|  
    |<span data-ttu-id="37861-158">Order ID</span><span class="sxs-lookup"><span data-stu-id="37861-158">Order ID</span></span>|<span data-ttu-id="37861-159">1</span><span class="sxs-lookup"><span data-stu-id="37861-159">1</span></span>|  
    |<span data-ttu-id="37861-160">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="37861-160">Sequence Number</span></span>|<span data-ttu-id="37861-161">1</span><span class="sxs-lookup"><span data-stu-id="37861-161">1</span></span>|  
    |<span data-ttu-id="37861-162">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="37861-162">Service Type Code</span></span>|<span data-ttu-id="37861-163">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="37861-163">New Standard Service</span></span>|  
  
3.  <span data-ttu-id="37861-164">En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-164">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="37861-165">**Id. de pedido de cliente identificador 1 1 número de secuencia 1**</span><span class="sxs-lookup"><span data-stu-id="37861-165">**Customer ID 1 Order ID 1 Sequence Number 1**</span></span>  
  
4.  <span data-ttu-id="37861-166">Valide el pedido realizado en el símbolo del sistema ejecutando el sistema de suministro de cable.</span><span class="sxs-lookup"><span data-stu-id="37861-166">Validate that the placed order at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="37861-167">La aplicación muestra mensajes que informan de que el pedido enviado se ha analizado, activado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="37861-167">The application display the messages that the submitted order is analyzed, activated, and then completed.</span></span>  
  
5.  <span data-ttu-id="37861-168">Validar que el número total de mensajes se incrementa en uno en el simulador de instalaciones.</span><span class="sxs-lookup"><span data-stu-id="37861-168">Validate that the number of the total messages is incremented by one on the Facilities Simulator.</span></span>  
  
#### <a name="to-submit-a-duplicate-while-the-biztalk-server-is-processing-the-original-order"></a><span data-ttu-id="37861-169">Para enviar un duplicado mientras que el servidor BizTalk está procesando el pedido original</span><span class="sxs-lookup"><span data-stu-id="37861-169">To submit a duplicate while the BizTalk Server is processing the original order</span></span>  
  
1.  <span data-ttu-id="37861-170">En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-170">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="37861-171">En el simulador de instalaciones, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="37861-171">In the FacilitiesSimulator, click **Stop**.</span></span> <span data-ttu-id="37861-172">Impide que los pedidos enviados continúen procesándose.</span><span class="sxs-lookup"><span data-stu-id="37861-172">It prevents submitted orders from being processed further.</span></span>  
  
3.  <span data-ttu-id="37861-173">En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order** dos veces para simular los pedidos duplicados.</span><span class="sxs-lookup"><span data-stu-id="37861-173">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order** twice to simulate duplicated orders.</span></span>  
  
    |<span data-ttu-id="37861-174">Entrada</span><span class="sxs-lookup"><span data-stu-id="37861-174">Entry</span></span>|<span data-ttu-id="37861-175">Valor</span><span class="sxs-lookup"><span data-stu-id="37861-175">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="37861-176">Customer ID</span><span class="sxs-lookup"><span data-stu-id="37861-176">Customer ID</span></span>|<span data-ttu-id="37861-177">2</span><span class="sxs-lookup"><span data-stu-id="37861-177">2</span></span>|  
    |<span data-ttu-id="37861-178">Order ID</span><span class="sxs-lookup"><span data-stu-id="37861-178">Order ID</span></span>|<span data-ttu-id="37861-179">1</span><span class="sxs-lookup"><span data-stu-id="37861-179">1</span></span>|  
    |<span data-ttu-id="37861-180">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="37861-180">Sequence Number</span></span>|<span data-ttu-id="37861-181">1</span><span class="sxs-lookup"><span data-stu-id="37861-181">1</span></span>|  
    |<span data-ttu-id="37861-182">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="37861-182">Service Type Code</span></span>|<span data-ttu-id="37861-183">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="37861-183">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="37861-184">En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-184">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="37861-185">**Id. de pedido de cliente Id. de 2 1 número de secuencia 1**</span><span class="sxs-lookup"><span data-stu-id="37861-185">**Customer ID 2 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="37861-186">En el simulador de instalaciones, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="37861-186">In the FacilitiesSimulator, click **Start**.</span></span> <span data-ttu-id="37861-187">En el simulador de instalaciones haga clic en Iniciar. Se reanudarán las orquestaciones que esperan las respuestas del simulador de instalaciones.</span><span class="sxs-lookup"><span data-stu-id="37861-187">The orchestrations waiting for the responses from the Facilities Simulator will resume.</span></span> <span data-ttu-id="37861-188">Simula que se envía un pedido duplicado mientras se está procesando el primer pedido.</span><span class="sxs-lookup"><span data-stu-id="37861-188">It simulates that a duplicate order is submitted while the first order is being processed.</span></span>  
  
6.  <span data-ttu-id="37861-189">Compruebe los pedidos realizado en el símbolo del sistema ejecutando el sistema de suministro de cable.</span><span class="sxs-lookup"><span data-stu-id="37861-189">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="37861-190">La aplicación muestra  mensajes que informan de que sólo el primer pedido se ha analizado, activado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="37861-190">The application displays the messages that only the first order is analyzed, activated, and then completed.</span></span>  
  
7.  <span data-ttu-id="37861-191">Compruebe el mensaje de error para los pedidos duplicados en el símbolo del sistema ejecutando el servidor de operaciones.</span><span class="sxs-lookup"><span data-stu-id="37861-191">Check the error message for the duplicated orders at the command prompt running the Operation Server.</span></span>  
  
#### <a name="to-update-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="37861-192">Para actualizar un pedido mientras que el servidor BizTalk está procesando el pedido.</span><span class="sxs-lookup"><span data-stu-id="37861-192">To update an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="37861-193">En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-193">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="37861-194">En el simulador de instalaciones, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="37861-194">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="37861-195">En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order**.</span><span class="sxs-lookup"><span data-stu-id="37861-195">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="37861-196">Entrada</span><span class="sxs-lookup"><span data-stu-id="37861-196">Entry</span></span>|<span data-ttu-id="37861-197">Valor</span><span class="sxs-lookup"><span data-stu-id="37861-197">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="37861-198">Customer ID</span><span class="sxs-lookup"><span data-stu-id="37861-198">Customer ID</span></span>|<span data-ttu-id="37861-199">3</span><span class="sxs-lookup"><span data-stu-id="37861-199">3</span></span>|  
    |<span data-ttu-id="37861-200">Order ID</span><span class="sxs-lookup"><span data-stu-id="37861-200">Order ID</span></span>|<span data-ttu-id="37861-201">1</span><span class="sxs-lookup"><span data-stu-id="37861-201">1</span></span>|  
    |<span data-ttu-id="37861-202">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="37861-202">Sequence Number</span></span>|<span data-ttu-id="37861-203">1</span><span class="sxs-lookup"><span data-stu-id="37861-203">1</span></span>|  
    |<span data-ttu-id="37861-204">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="37861-204">Service Type Code</span></span>|<span data-ttu-id="37861-205">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="37861-205">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="37861-206">En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-206">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="37861-207">**Id. de pedido de cliente Id. de 3 1 número de secuencia 1**</span><span class="sxs-lookup"><span data-stu-id="37861-207">**Customer ID 3 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="37861-208">En el **Southridge Video Customer Service Rep Order Entry Form** página, especifique un pedido actualizado en la tabla siguiente y, a continuación, haga clic en **Submit Order**.</span><span class="sxs-lookup"><span data-stu-id="37861-208">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter an updated order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="37861-209">Entrada</span><span class="sxs-lookup"><span data-stu-id="37861-209">Entry</span></span>|<span data-ttu-id="37861-210">Valor</span><span class="sxs-lookup"><span data-stu-id="37861-210">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="37861-211">Customer ID</span><span class="sxs-lookup"><span data-stu-id="37861-211">Customer ID</span></span>|<span data-ttu-id="37861-212">3</span><span class="sxs-lookup"><span data-stu-id="37861-212">3</span></span>|  
    |<span data-ttu-id="37861-213">Order ID</span><span class="sxs-lookup"><span data-stu-id="37861-213">Order ID</span></span>|<span data-ttu-id="37861-214">1</span><span class="sxs-lookup"><span data-stu-id="37861-214">1</span></span>|  
    |<span data-ttu-id="37861-215">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="37861-215">Sequence Number</span></span>|<span data-ttu-id="37861-216">2</span><span class="sxs-lookup"><span data-stu-id="37861-216">2</span></span>|  
    |<span data-ttu-id="37861-217">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="37861-217">Service Type Code</span></span>|<span data-ttu-id="37861-218">New Deluxe Service</span><span class="sxs-lookup"><span data-stu-id="37861-218">New Deluxe Service</span></span>|  
  
6.  <span data-ttu-id="37861-219">En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-219">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="37861-220">**Id. de pedido de cliente Id. de 3 1 número de secuencia 2**</span><span class="sxs-lookup"><span data-stu-id="37861-220">**Customer ID 3 Order ID 1 Sequence Number 2**</span></span>  
  
7.  <span data-ttu-id="37861-221">En el simulador de instalaciones, haga clic en **iniciar**</span><span class="sxs-lookup"><span data-stu-id="37861-221">In the FacilitiesSimulator, click **Start**</span></span>  
  
8.  <span data-ttu-id="37861-222">Compruebe el mensaje de resultado en el **Southridge Video Customer Service Rep Order Entry Form** página.</span><span class="sxs-lookup"><span data-stu-id="37861-222">Check the result message on the **Southridge Video Customer Service Rep Order Entry Form** page.</span></span>  
  
9. <span data-ttu-id="37861-223">Compruebe los pedidos realizado en el símbolo del sistema ejecutando el sistema de suministro de cable.</span><span class="sxs-lookup"><span data-stu-id="37861-223">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="37861-224">La aplicación muestra mensajes que informan de que se han analizado dos pedidos, pero sólo se ha activado y finalizado el pedido actualizado.</span><span class="sxs-lookup"><span data-stu-id="37861-224">The application displays the messages that two orders are analyzed, but only the updated order is activated and completed.</span></span>  
  
10. <span data-ttu-id="37861-225">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **Visor de eventos**y, a continuación, compruebe una advertencia nueva que la se interrumpió el pedido original.</span><span class="sxs-lookup"><span data-stu-id="37861-225">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the original order was interrupted.</span></span>  
  
11. <span data-ttu-id="37861-226">Compruebe el mensaje de error de enrutamiento en el símbolo del sistema ejecutando el servidor de operaciones.</span><span class="sxs-lookup"><span data-stu-id="37861-226">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37861-227">Habrá un error en el registro de sucesos y en el servidor de operaciones.</span><span class="sxs-lookup"><span data-stu-id="37861-227">There will be an error in the event log and in the operations server.</span></span> <span data-ttu-id="37861-228">El mensaje de respuesta del sistema de instalaciones ya no corresponde a una instancia del proceso empresarial ya que finalizó por la interrupción causada por el pedido nuevo con un número de secuencia superior.</span><span class="sxs-lookup"><span data-stu-id="37861-228">The response message from the Facilities System no longer correlates back to an instance of the business process as it was terminated by the interruption caused by the new order with a higher sequence number.</span></span> <span data-ttu-id="37861-229">Por lo tanto, el mensaje de respuesta está huérfano y se enruta al servidor de operaciones.</span><span class="sxs-lookup"><span data-stu-id="37861-229">Therefore response message is orphaned and will get routed to the operations server.</span></span> <span data-ttu-id="37861-230">Para obtener más información acerca de las actualizaciones de pedido, vea [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md).</span><span class="sxs-lookup"><span data-stu-id="37861-230">For more information about order updates, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
12. <span data-ttu-id="37861-231">Abra el mensaje más reciente de la carpeta %SystemDrive%:\BPMTest\HistoryUpdate-SP con el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="37861-231">Open the latest message in the %SystemDrive%:\BPMTest\HistoryUpdate-SP folder with Notepad.</span></span> <span data-ttu-id="37861-232">Comprobar **CustName**, **OrderNum**, **OrderSeqNum**, y **estado** campos para ver si el mensaje se ha creado para el pedido nuevo y la **Estado** campo es **completado**.</span><span class="sxs-lookup"><span data-stu-id="37861-232">Check **CustName**, **OrderNum**, **OrderSeqNum**, and **Status** fields to see if the message has been created for the new order and the **Status** field is **COMPLETED**.</span></span>  
  
#### <a name="to-terminate-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="37861-233">Para finalizar un pedido mientras que el servidor BizTalk está procesando el pedido</span><span class="sxs-lookup"><span data-stu-id="37861-233">To terminate an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="37861-234">En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-234">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="37861-235">En el simulador de instalaciones, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="37861-235">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="37861-236">En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order**.</span><span class="sxs-lookup"><span data-stu-id="37861-236">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="37861-237">Entrada</span><span class="sxs-lookup"><span data-stu-id="37861-237">Entry</span></span>|<span data-ttu-id="37861-238">Valor</span><span class="sxs-lookup"><span data-stu-id="37861-238">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="37861-239">Customer ID</span><span class="sxs-lookup"><span data-stu-id="37861-239">Customer ID</span></span>|<span data-ttu-id="37861-240">4</span><span class="sxs-lookup"><span data-stu-id="37861-240">4</span></span>|  
    |<span data-ttu-id="37861-241">Order ID</span><span class="sxs-lookup"><span data-stu-id="37861-241">Order ID</span></span>|<span data-ttu-id="37861-242">1</span><span class="sxs-lookup"><span data-stu-id="37861-242">1</span></span>|  
    |<span data-ttu-id="37861-243">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="37861-243">Sequence Number</span></span>|<span data-ttu-id="37861-244">1</span><span class="sxs-lookup"><span data-stu-id="37861-244">1</span></span>|  
    |<span data-ttu-id="37861-245">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="37861-245">Service Type Code</span></span>|<span data-ttu-id="37861-246">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="37861-246">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="37861-247">En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-247">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="37861-248">**Id. de pedido de cliente Id. de 4 1 número de secuencia 1**</span><span class="sxs-lookup"><span data-stu-id="37861-248">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="37861-249">En el **Southridge Video Customer Service Rep Order Entry Form** página, haga clic en **Finalizar orden**.</span><span class="sxs-lookup"><span data-stu-id="37861-249">On the **Southridge Video Customer Service Rep Order Entry Form** page, click **Terminate Order**.</span></span>  
  
6.  <span data-ttu-id="37861-250">En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:</span><span class="sxs-lookup"><span data-stu-id="37861-250">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="37861-251">**Id. de pedido de cliente Id. de 4 1 número de secuencia 1**</span><span class="sxs-lookup"><span data-stu-id="37861-251">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
7.  <span data-ttu-id="37861-252">En el simulador de instalaciones, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="37861-252">In the FacilitiesSimulator, click **Start**.</span></span>  
  
8.  <span data-ttu-id="37861-253">Compruebe los pedidos realizado en el símbolo del sistema ejecutando el sistema de suministro de cable.</span><span class="sxs-lookup"><span data-stu-id="37861-253">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="37861-254">La aplicación muestra mensajes que informan de que el pedido sólo se ha analizado y activado.</span><span class="sxs-lookup"><span data-stu-id="37861-254">The application displays the messages that order is only analyzed and activated.</span></span>  
  
9. <span data-ttu-id="37861-255">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **Visor de eventos**y, a continuación, compruebe una advertencia nueva que la se finalizó el pedido por usuario.</span><span class="sxs-lookup"><span data-stu-id="37861-255">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the order was terminated by user.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37861-256">Para obtener más información sobre cómo finalizar pedidos, vea [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md).</span><span class="sxs-lookup"><span data-stu-id="37861-256">For more information about terminating orders, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
10. <span data-ttu-id="37861-257">Compruebe el mensaje de error de enrutamiento en el símbolo del sistema ejecutando el servidor de operaciones.</span><span class="sxs-lookup"><span data-stu-id="37861-257">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37861-258">Vea también</span><span class="sxs-lookup"><span data-stu-id="37861-258">See Also</span></span>  
 <span data-ttu-id="37861-259">[Antes de instalar la solución de administración de procesos empresariales](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="37861-259">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="37861-260">Configuración del equipo del desarrollador para la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="37861-260">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)