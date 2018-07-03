---
title: 'Tutorial: Crear una aplicación de BizTalk que utiliza el adaptador de MQSeries | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- MQSeries adapters, tutorial
- MQSeries adapters, testing
- tutorials, MQSeries adapters
- MQSeries adapters, IBM WebSphere MQ queues
- testing, MQSeries adapters
- MQSeries adapters, queues
- configuring [MQSeries adapters], tutorial
ms.assetid: e9e169e4-d41c-4e5d-b165-7bd36b481f24
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c086c69dee4318b9ab15f8746291594a815870
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024530"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-mqseries-adapter"></a><span data-ttu-id="34be2-102">Tutorial: Crear una aplicación de BizTalk que usa el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="34be2-102">Walkthrough: Creating a BizTalk Application That Uses the MQSeries Adapter</span></span>
<span data-ttu-id="34be2-103">Esta sección le muestra cómo crear una sencilla aplicación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que utilice el adaptador de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="34be2-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application that uses the MQSeries adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34be2-104">La aplicación supone que tiene instalado IBM WebSphere MQ, componente del servidor para las plataformas de Windows, en el mismo equipo que BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="34be2-104">The application assumes that you have installed the IBM WebSphere MQ, server component for Windows platforms on the same computer as BizTalk Server.</span></span> <span data-ttu-id="34be2-105">Asimismo, supone que todavía no ha creado ningún puerto de envío o ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="34be2-105">It also assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="34be2-106">Si dispone de puertos de envío o ubicaciones de recepción existentes, sustituya los nombres correspondientes cuando siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="34be2-106">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="34be2-107">La aplicación es una sencilla aplicación de enrutamiento por contenidos que sólo utiliza un puerto de envío o una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="34be2-107">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="34be2-108">La ubicación de recepción lee de una cola de IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="34be2-108">The receive location reads from an IBM WebSphere MQ queue.</span></span> <span data-ttu-id="34be2-109">El puerto de envío obtiene el mensaje a partir de la ubicación de recepción y lo envía a una cola diferente de IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="34be2-109">The send port takes the message from the receive location and sends it to a different IBM WebSphere MQ queue.</span></span>  
  
 <span data-ttu-id="34be2-110">Para crear la aplicación, debe crear las colas de IBM WebSphere MQ, configurar el puerto de envío y la ubicación de recepción de BizTalk Server, iniciar el puerto de envío, habilitar la ubicación de recepción y colocar un mensaje de prueba en la cola.</span><span class="sxs-lookup"><span data-stu-id="34be2-110">To create the application, you have to create the IBM WebSphere MQ queues, set up the BizTalk Server receive location and send port, start the send port and enable the receive location, and put a test message in the queue.</span></span>  
  
 <span data-ttu-id="34be2-111">Si dispone de los permisos necesarios para instalar IBM WebSphere MQ, puede crear colas de IBM WebSphere MQ mediante los cuadros de diálogo del adaptador y omitir el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="34be2-111">If you have the required permissions to the IBM WebSphere MQ installation, you can create the IBM WebSphere MQ queues through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="34be2-112">Si no dispone de este acceso, puede crear colas mediante IBM WebSphere MQ, componentes cliente para el explorador de las plataformas de Windows.</span><span class="sxs-lookup"><span data-stu-id="34be2-112">If you do not have such access, you can create the queues using the IBM WebSphere MQ, client components for Windows platforms Explorer.</span></span> <span data-ttu-id="34be2-113">Para crear las colas mediante el complemento de IBM WebSphere MQ Explorer, realice el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="34be2-113">To create the queues through the IBM WebSphere MQ Explorer snap-in, perform the following procedure.</span></span>  
  
## <a name="to-create-the-ibm-websphere-mq-queues-through-the-ibm-websphere-mq-explorer"></a><span data-ttu-id="34be2-114">Para crear las colas de IBM WebSphere MQ mediante IBM WebSphere MQ Explorer</span><span class="sxs-lookup"><span data-stu-id="34be2-114">To create the IBM WebSphere MQ queues through the IBM WebSphere MQ Explorer</span></span>  
 <span data-ttu-id="34be2-115">Para crear las colas de IBM WebSphere MQ mediante IBM WebSphere MQ Explorer, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34be2-115">Follow these steps to create the IBM WebSphere MQ queues through the IBM WebSphere MQ Explorer:</span></span>  
  
1. <span data-ttu-id="34be2-116">Haga clic en **iniciar**, apunte a **programas**, apunte a **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.</span><span class="sxs-lookup"><span data-stu-id="34be2-116">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2. <span data-ttu-id="34be2-117">Haga doble clic en **administradores de cola**y, a continuación, haga doble clic en el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34be2-117">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="34be2-118">El Administrador de cola predeterminado se denomina normalmente ***** QM_ < nombre_equipo >* donde *nombre_equipo* es el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="34be2-118">The default queue manager is typically named **QM_***<machine_name>* where *machine_name* is the name of your computer.</span></span>  
  
3. <span data-ttu-id="34be2-119">Haga clic en **colas**, apunte a **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="34be2-119">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4. <span data-ttu-id="34be2-120">En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **BTStoMQS**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-120">In **Create Local Queue** dialog box, in **Queue Name**, type **BTStoMQS**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="34be2-121">Haga clic en **colas**, apunte a **New**y, a continuación, haga clic en **cola Local**.</span><span class="sxs-lookup"><span data-stu-id="34be2-121">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
6. <span data-ttu-id="34be2-122">En **Create Local Queue** cuadro de diálogo **nombre de la cola**, tipo **MQStoBTS**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-122">In **Create Local Queue** dialog box, in **Queue Name**, type **MQStoBTS**, and then click **OK**.</span></span>  
  
   <span data-ttu-id="34be2-123">En los siguientes pasos se crea el puerto de envío y la ubicación de recepción, se inicia el puerto de envío y la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="34be2-123">The next steps create the receive location and the send port, and start the send port and enable the receive location.</span></span> <span data-ttu-id="34be2-124">También se crean las colas de IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="34be2-124">They also create the IBM WebSphere MQ queues.</span></span>  
  
## <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="34be2-125">Para crear la ubicación de recepción y la cola de MQSeries</span><span class="sxs-lookup"><span data-stu-id="34be2-125">To create the receive location and the MQSeries queue</span></span>  
 <span data-ttu-id="34be2-126">Para crear la ubicación de recepción y la cola de MQSeries, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34be2-126">Follow these steps to create the receive location and the MQSeries queue:</span></span>  
  
1.  <span data-ttu-id="34be2-127">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el valor predeterminado aplicación (**BizTalk Application 1** de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="34be2-127">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the default application (**BizTalk Application 1** by default).</span></span>  
  
2.  <span data-ttu-id="34be2-128">Haga clic en el **puertos de recepción** nodo, haga clic en **New**y seleccione **Puerto unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="34be2-128">Right-click the **Receive Ports** node, click **New**, and select **One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="34be2-129">En el **propiedades de puerto de recepción** cuadro de diálogo el **nombre** , escriba **MQStoBTS**.</span><span class="sxs-lookup"><span data-stu-id="34be2-129">In the **Receive Port Properties** dialog box, in the **Name** box, type **MQStoBTS**.</span></span>  
  
4.  <span data-ttu-id="34be2-130">En el panel izquierdo, haga clic en **ubicaciones de recepción**y en el panel derecho, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="34be2-130">In the left pane, click **Receive Locations**, and in the right pane, click **New**.</span></span>  
  
5.  <span data-ttu-id="34be2-131">En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba **MQStoBTS**.</span><span class="sxs-lookup"><span data-stu-id="34be2-131">In the **Receive Location Properties** dialog box, in the **Name** box, type **MQStoBTS**.</span></span>  
  
6.  <span data-ttu-id="34be2-132">Seleccione **MQSeries** en la lista desplegable lista junto a la **tipo** opción.</span><span class="sxs-lookup"><span data-stu-id="34be2-132">Select **MQSeries** from the drop-down list next to the **Type** option.</span></span>  
  
7.  <span data-ttu-id="34be2-133">En el **transporte** sección, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-133">In the **Transport** section, click **Configure**.</span></span>  
  
8.  <span data-ttu-id="34be2-134">En el **propiedades de transporte MQSeries** cuadro de diálogo el **intervalo de sondeo** , escriba **1**.</span><span class="sxs-lookup"><span data-stu-id="34be2-134">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **1**.</span></span>  
  
9. <span data-ttu-id="34be2-135">En el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="34be2-135">In the **Queue Definition** box, click the ellipsis (**…**) button.</span></span>  
  
10. <span data-ttu-id="34be2-136">En el **definición de la cola** cuadro de diálogo el **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="34be2-136">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
11. <span data-ttu-id="34be2-137">En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34be2-137">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
12. <span data-ttu-id="34be2-138">En el **cola** , escriba **MQStoBTS**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-138">In the **Queue** box, type **MQStoBTS**, and then click **Export**.</span></span>  
  
13. <span data-ttu-id="34be2-139">En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** y **Aceptar** para volver a la **recepción Propiedades de la ubicación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="34be2-139">In the **Export** dialog box, click **Create Queue**,and then click **OK** and **OK** again to return to the **Receive Location Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="34be2-140">En el **controlador de recepción** cuadro, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="34be2-140">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
15. <span data-ttu-id="34be2-141">En el **canalización de recepción** cuadro, seleccione **PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="34be2-141">In the **Receive Pipeline** box, select **PassThruReceive**.</span></span>  
  
16. <span data-ttu-id="34be2-142">Haga clic en **Aceptar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="34be2-142">Click **OK** to apply changes.</span></span>  
  
## <a name="to-create-the-send-port-and-the-mqseries-queue"></a><span data-ttu-id="34be2-143">Para crear el puerto de envío y la cola de MQSeries</span><span class="sxs-lookup"><span data-stu-id="34be2-143">To create the send port and the MQSeries queue</span></span>  
 <span data-ttu-id="34be2-144">Para crear el puerto de envío y la cola de MQSeries, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34be2-144">Follow these steps to create the send port and the MQSeries queue:</span></span>  
  
1.  <span data-ttu-id="34be2-145">Haga clic en **puertos de envío**, haga clic en **New**y seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="34be2-145">Right-click **Send Ports**, click **New**, and select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="34be2-146">En el **propiedades de puerto de envío** cuadro de diálogo el **nombre** , escriba **BTStoMQS.**</span><span class="sxs-lookup"><span data-stu-id="34be2-146">In the **Send Port Properties** dialog box, in the **Name** box, type **BTStoMQS.**</span></span>  
  
3.  <span data-ttu-id="34be2-147">Seleccione **MQSeries** en la lista desplegable lista junto a la **tipo** opción.</span><span class="sxs-lookup"><span data-stu-id="34be2-147">Select **MQSeries** from the drop-down list next to the **Type** option.</span></span>  
  
4.  <span data-ttu-id="34be2-148">En el **transporte** sección, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-148">In the **Transport** section, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="34be2-149">En el **propiedades de transporte MQSeries** cuadro de diálogo el **definición de la cola** cuadro, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="34be2-149">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (**…**) button.</span></span>  
  
6.  <span data-ttu-id="34be2-150">En el **definición de la cola** cuadro de diálogo el **nombre del servidor** , escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="34be2-150">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
7.  <span data-ttu-id="34be2-151">En el **Administrador de cola** , seleccione el Administrador de cola predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34be2-151">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
8.  <span data-ttu-id="34be2-152">En el **cola** , escriba **BTStoMQS**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-152">In the **Queue** box, type **BTStoMQS**, and then click **Export**.</span></span>  
  
9. <span data-ttu-id="34be2-153">En el **exportar** cuadro de diálogo, haga clic en **Create Queue**y, a continuación, haga clic en **Aceptar** y **Aceptar** para volver a la **puerto de envío Propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="34be2-153">In the **Export** dialog box, click **Create Queue**, and then click **OK** and **OK** again to return to the **Send Port Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="34be2-154">En el **canalización de envío** cuadro, seleccione **PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="34be2-154">In the **Send Pipeline** box, select **PassThruTransmit**.</span></span>  
  
11. <span data-ttu-id="34be2-155">Haga clic para seleccionar **filtros** en el panel izquierdo y, a continuación, configure las opciones de filtro en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="34be2-155">Click to select **Filters** in the left pane, and then configure filter options in the right pane.</span></span>  
  
12. <span data-ttu-id="34be2-156">En el **propiedad** lista desplegable, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="34be2-156">In the **Property** drop-down list, select **BTS.ReceivePortName**.</span></span>  
  
13. <span data-ttu-id="34be2-157">En el **valor** , escriba **MQStoBTS**.</span><span class="sxs-lookup"><span data-stu-id="34be2-157">In the **Value** box, type **MQStoBTS**.</span></span>  
  
14. <span data-ttu-id="34be2-158">Haga clic en **Aceptar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="34be2-158">Click **OK** to apply changes.</span></span>  
  
## <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="34be2-159">Para habilitar la ubicación de recepción e iniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="34be2-159">To enable the receive location and start the send port</span></span>  
 <span data-ttu-id="34be2-160">Para habilitar la ubicación de recepción e iniciar el puerto de envío, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34be2-160">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1. <span data-ttu-id="34be2-161">Haga clic en el **MQStoBTS** ubicación de recepción y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-161">Right-click the **MQStoBTS** receive location, and then click **Enable**.</span></span>  
  
2. <span data-ttu-id="34be2-162">Haga clic en el **BTStoMQS** puerto de envío y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-162">Right-click the **BTStoMQS** send port, and then click **Start**.</span></span>  
  
   <span data-ttu-id="34be2-163">El paso siguiente es comprobar la aplicación mediante el envío de un mensaje de prueba a la cola de recepción.</span><span class="sxs-lookup"><span data-stu-id="34be2-163">The next step is to test the application by sending a test message to the receive queue.</span></span>  
  
## <a name="to-test-the-application"></a><span data-ttu-id="34be2-164">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="34be2-164">To test the application</span></span>  
 <span data-ttu-id="34be2-165">Para probar la aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34be2-165">Follow these steps to test the application:</span></span>  
  
1. <span data-ttu-id="34be2-166">Haga clic en **iniciar**, apunte a **programas**, apunte a **IBM WebSphere MQ**y, a continuación, haga clic en **WebSphere MQ Explorer**.</span><span class="sxs-lookup"><span data-stu-id="34be2-166">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2. <span data-ttu-id="34be2-167">Haga clic en **MQStoBTS**y, a continuación, haga clic en **Put Test Message**.</span><span class="sxs-lookup"><span data-stu-id="34be2-167">Right-click **MQStoBTS**, and then click **Put Test Message**.</span></span>  
  
3. <span data-ttu-id="34be2-168">En el **datos del mensaje** , escriba un mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="34be2-168">In the **Message Data** box, type a test message.</span></span> <span data-ttu-id="34be2-169">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-169">Click **OK**.</span></span>  
  
   <span data-ttu-id="34be2-170">Después de escribir los datos, el **Current Depth** para el **MQStoBTS** cola es uno (1).</span><span class="sxs-lookup"><span data-stu-id="34be2-170">After you enter the data, the **Current Depth** for the **MQStoBTS** queue is one (1).</span></span> <span data-ttu-id="34be2-171">Cuando la aplicación procesa el mensaje, el recuento vuelve a cero (0) y el **Current Depth** para **BTStoMQS** se convierte en uno (1).</span><span class="sxs-lookup"><span data-stu-id="34be2-171">When the application processes the message, the count returns to zero (0) and the **Current Depth** for **BTStoMQS** becomes one (1).</span></span> <span data-ttu-id="34be2-172">También puede ver el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="34be2-172">You can also view the content of the message.</span></span>  
  
## <a name="to-view-the-message"></a><span data-ttu-id="34be2-173">Para ver el mensaje</span><span class="sxs-lookup"><span data-stu-id="34be2-173">To view the message</span></span>  
 <span data-ttu-id="34be2-174">Para ver el mensaje, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34be2-174">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="34be2-175">Haga doble clic en el **BTStoMQS** cola.</span><span class="sxs-lookup"><span data-stu-id="34be2-175">Double-click the **BTStoMQS** queue.</span></span>  
  
2.  <span data-ttu-id="34be2-176">Haga doble clic en el mensaje y, a continuación, seleccione el **datos** hoja.</span><span class="sxs-lookup"><span data-stu-id="34be2-176">Double-click the message, and then select the **Data** sheet.</span></span> <span data-ttu-id="34be2-177">Puede ver el texto del mensaje en el **datos del mensaje** cuadro.</span><span class="sxs-lookup"><span data-stu-id="34be2-177">You can view the text of the message in the **Message Data** box.</span></span>  
  
3.  <span data-ttu-id="34be2-178">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34be2-178">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34be2-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="34be2-179">See Also</span></span>  
 <span data-ttu-id="34be2-180">[¿Qué es el adaptador de MQSeries?](../core/what-is-the-mqseries-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="34be2-180">[What Is the MQSeries Adapter?](../core/what-is-the-mqseries-adapter.md) </span></span>  
 [<span data-ttu-id="34be2-181">Arquitectura del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="34be2-181">MQSeries Adapter Architecture</span></span>](../core/mqseries-adapter-architecture.md)