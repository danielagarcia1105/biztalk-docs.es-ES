---
title: "Cómo ejecutar el servicio de la solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c33b914ecbb9f385e5546d100b7572b4b48b6a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-run-the-service-oriented-solution"></a><span data-ttu-id="88825-102">Cómo ejecutar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="88825-102">How to Run the Service Oriented Solution</span></span>
<span data-ttu-id="88825-103">Los pasos siguientes describen cómo ejecutar y validar la solución orientada a servicios en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="88825-103">The following steps describe how to run and validate the service oriented solution on a single computer.</span></span> <span data-ttu-id="88825-104">Una vez iniciado el simulador de seguimiento de pago, puede enviar solicitudes utilizando el transporte SOAP o MQSeries (con procedimientos independientes para las versiones de adaptador en línea de la solución orientada a servicios).</span><span class="sxs-lookup"><span data-stu-id="88825-104">After starting the Payment Tracker simulator, you can send requests using either the SOAP or MQSeries transport (with separate procedures for the adapter and inline versions of the service oriented solution).</span></span>  
  
-   [<span data-ttu-id="88825-105">Enviar solicitudes con el transporte SOAP utilizando la aplicación de cliente (versión de código auxiliar)</span><span class="sxs-lookup"><span data-stu-id="88825-105">Send requests by SOAP transport using the client application (stub version)</span></span>](#step1)  
  
-   [<span data-ttu-id="88825-106">Enviar solicitudes utilizando la aplicación de cliente (versión de adaptador)</span><span class="sxs-lookup"><span data-stu-id="88825-106">Send requests using the client application (adapter version)</span></span>](#step3)  
  
-   [<span data-ttu-id="88825-107">Enviar solicitudes utilizando la aplicación de cliente (versión en línea)</span><span class="sxs-lookup"><span data-stu-id="88825-107">Send requests using the client application (inline version)</span></span>](#step5)  
  
##  <a name="step1"></a><span data-ttu-id="88825-108">Enviar solicitudes con el transporte SOAP utilizando la aplicación de cliente (versión de código auxiliar)</span><span class="sxs-lookup"><span data-stu-id="88825-108">Send requests by SOAP transport using the client application (stub version)</span></span>  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a><span data-ttu-id="88825-109">Para enviar solicitudes con el transporte SOAP utilizando la aplicación de cliente (versión de código auxiliar)</span><span class="sxs-lookup"><span data-stu-id="88825-109">To send requests by SOAP transport using the client application (stub version)</span></span>  
  
1.  <span data-ttu-id="88825-110">Abra un símbolo del sistema, cambie el directorio a la \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release y, a continuación, ejecute BTSScnSOSimpleClient.exe.</span><span class="sxs-lookup"><span data-stu-id="88825-110">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
2.  <span data-ttu-id="88825-111">Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-111">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
3.  <span data-ttu-id="88825-112">Escriba cualquier número de 16 dígitos en el **número de cuenta** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-112">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
4.  <span data-ttu-id="88825-113">Seleccione **SOAP (WS Call)** y **código auxiliar** en el **Select Transport and Parameters** cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="88825-113">Select **SOAP (WS Call)** and **Stub** in the **Select Transport and Parameters** group box.</span></span>  
  
5.  <span data-ttu-id="88825-114">Escriba la dirección URL siguiente en la **URL** cuadro de texto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="88825-114">Type the following URL in the **URL** text box, for example:</span></span>  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  <span data-ttu-id="88825-115">Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-115">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
8.  <span data-ttu-id="88825-116">Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-116">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
9. <span data-ttu-id="88825-117">Haga clic en **obtener mi Saldo**.</span><span class="sxs-lookup"><span data-stu-id="88825-117">Click **Get my balance**.</span></span>  
  
10. <span data-ttu-id="88825-118">La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="88825-118">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
     <span data-ttu-id="88825-119">![Ejecutar la aplicación de cliente para la versión de código auxiliar](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span><span class="sxs-lookup"><span data-stu-id="88825-119">![Run the client application for the stub version](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="88825-120">Enviar solicitudes utilizando la aplicación de cliente (versión de adaptador)</span><span class="sxs-lookup"><span data-stu-id="88825-120">Send requests using the client application (adapter version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a><span data-ttu-id="88825-121">Para enviar solicitudes utilizando la aplicación de cliente (versión de adaptador)</span><span class="sxs-lookup"><span data-stu-id="88825-121">To send requests using the client application (adapter version)</span></span>  
  
1.  <span data-ttu-id="88825-122">Abra un símbolo del sistema, cambie al directorio \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug y, a continuación, ejecute el siguiente comando para iniciar el Simulador de seguimiento de pago:</span><span class="sxs-lookup"><span data-stu-id="88825-122">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug and, then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="88825-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*Nombre del Administrador de cola* `> 5 [<` *definición de canal*`>]`</span><span class="sxs-lookup"><span data-stu-id="88825-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88825-124">La definición de canal es opcional si MQSeries Server no es remoto.</span><span class="sxs-lookup"><span data-stu-id="88825-124">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    -   <span data-ttu-id="88825-125">Deje que el simulador de seguimiento de pago se ejecute.</span><span class="sxs-lookup"><span data-stu-id="88825-125">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="88825-126">Abra un símbolo del sistema, cambie el directorio a la \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release y, a continuación, ejecute BTSScnSOSimpleClient.exe.</span><span class="sxs-lookup"><span data-stu-id="88825-126">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
3.  <span data-ttu-id="88825-127">En BTSScnSOSimpleClient.exe, envíe una solicitud mediante el transporte SOAP del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="88825-127">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="88825-128">Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-128">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="88825-129">Escriba cualquier número de 16 dígitos en el **número de cuenta** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-129">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="88825-130">Seleccione **SOAP (WS Call)** y **adaptador** en el **Select Transport and Parameters** cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="88825-130">Select **SOAP (WS Call)** and **Adapter** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="88825-131">Escriba la dirección URL siguiente en la **URL** cuadro de texto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="88825-131">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="88825-132">Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-132">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="88825-133">Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-133">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="88825-134">Haga clic en **obtener mi Saldo**.</span><span class="sxs-lookup"><span data-stu-id="88825-134">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="88825-135">La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="88825-135">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="88825-136">![Ejecutar la aplicación cliente para la versión del adaptador](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span><span class="sxs-lookup"><span data-stu-id="88825-136">![Run the client application for the adapter version](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span></span>  
  
4.  <span data-ttu-id="88825-137">En BTSScnSOSimpleClient.exe, envíe solicitudes mediante el transporte MQSeries del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="88825-137">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="88825-138">Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-138">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="88825-139">Escriba un número de 16 dígitos en el **número de cuenta** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-139">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="88825-140">Seleccione **MQSeries** en el **Select Transport and Parameters** cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="88825-140">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="88825-141">Tipo de \< *nombre del Administrador de cola* \> en el **Administrador de cola** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-141">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="88825-142">QM_\<*el nombre del equipo* \> es el valor predeterminado de \< *nombre del Administrador de cola*\>.</span><span class="sxs-lookup"><span data-stu-id="88825-142">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="88825-143">Tipo de `AdapterSOAInputQueue` en el **Input Queue** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-143">Type `AdapterSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="88825-144">Tipo de `AdapterSOAOutputQueue` en el **cola de salida** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-144">Type `AdapterSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="88825-145">Tipo de \< *definición de canal* \> en el **definición de canal** cuadro.</span><span class="sxs-lookup"><span data-stu-id="88825-145">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="88825-146">S_\<*el nombre del equipo*\>/TCP /\<*el nombre del equipo*\>(1414) es el valor predeterminado de \<  *Definición de canal*\>.</span><span class="sxs-lookup"><span data-stu-id="88825-146">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="88825-147">Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-147">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="88825-148">Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-148">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="88825-149">Haga clic en **obtener mi Saldo**.</span><span class="sxs-lookup"><span data-stu-id="88825-149">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="88825-150">La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="88825-150">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="88825-151">![Ejecutar la aplicación cliente para la versión del adaptador](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span><span class="sxs-lookup"><span data-stu-id="88825-151">![Run the client application for the adapter version](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span></span>  
  
##  <a name="step5"></a><span data-ttu-id="88825-152">Enviar solicitudes utilizando la aplicación de cliente (versión en línea)</span><span class="sxs-lookup"><span data-stu-id="88825-152">Send requests using the client application (inline version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a><span data-ttu-id="88825-153">Para enviar solicitudes utilizando la aplicación de cliente (versión en línea)</span><span class="sxs-lookup"><span data-stu-id="88825-153">To send requests using the client application (inline version)</span></span>  
  
1.  <span data-ttu-id="88825-154">Abra un símbolo del sistema, cambie al directorio \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug y, a continuación, ejecute el siguiente comando para iniciar el Simulador de seguimiento de pago:</span><span class="sxs-lookup"><span data-stu-id="88825-154">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug, and then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="88825-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*Nombre del Administrador de cola* `> 5 [<` *definición de canal*`>]`</span><span class="sxs-lookup"><span data-stu-id="88825-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88825-156">La definición de canal es opcional si MQSeries Server no es remoto.</span><span class="sxs-lookup"><span data-stu-id="88825-156">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88825-157">Omita este paso si el simulador de seguimiento de pago ya se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="88825-157">Skip this step if the PaymentTracker simulator is already running.</span></span>  
  
    -   <span data-ttu-id="88825-158">Deje que el simulador de seguimiento de pago se ejecute.</span><span class="sxs-lookup"><span data-stu-id="88825-158">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="88825-159">En el **consola de administración de BizTalk Server**, expanda **BTSScn.SO.CustomerService**, haga clic en **ubicaciones de recepción**, haga clic en  **PaymentTrackingSystemOutputQueue** en el panel derecho y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="88825-159">In the **BizTalk Server Administration Console**, expand **BTSScn.SO.CustomerService**, click **Receive Locations**, right-click **PaymentTrackingSystemOutputQueue** in the right pane, and then click **Disable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88825-160">La versión adaptador y la versión en línea utilizan la misma cola MQSeries, LastPaymentsOutputQueue.</span><span class="sxs-lookup"><span data-stu-id="88825-160">The adapter version and inline version uses the same MQSeries queue, LastPaymentsOutputQueue.</span></span> <span data-ttu-id="88825-161">Para evitar la condición de anticipación entre dos versiones, deshabilite la escucha de la ubicación de recepción de la versión adaptador en la cola MQSeries.</span><span class="sxs-lookup"><span data-stu-id="88825-161">To avoid the race condition between two versions, disable the adapter version's receive location listening on the MQSeries queue.</span></span>  
  
3.  <span data-ttu-id="88825-162">Abra un símbolo del sistema, cambie el directorio a la \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release y, a continuación, ejecute BTSScnSOSimpleClient.exe.</span><span class="sxs-lookup"><span data-stu-id="88825-162">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
4.  <span data-ttu-id="88825-163">En BTSScnSOSimpleClient.exe, envíe una solicitud mediante el transporte SOAP del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="88825-163">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="88825-164">Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-164">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="88825-165">Escriba cualquier número de 16 dígitos en el **número de cuenta** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-165">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="88825-166">Seleccione **SOAP (WS Call)** y **en línea** en el **Select Transport and Parameters** cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="88825-166">Select **SOAP (WS Call)** and **Inline** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="88825-167">Escriba la dirección URL siguiente en la **URL** cuadro de texto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="88825-167">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="88825-168">Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-168">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="88825-169">Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-169">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="88825-170">Haga clic en **obtener mi Saldo**.</span><span class="sxs-lookup"><span data-stu-id="88825-170">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="88825-171">La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="88825-171">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="88825-172">![Ejecutar la aplicación cliente para la versión en línea](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="88825-172">![Run the client application for the inline version](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span></span>  
  
5.  <span data-ttu-id="88825-173">En BTSScnSOSimpleClient.exe, envíe solicitudes mediante el transporte MQSeries del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="88825-173">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="88825-174">Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-174">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="88825-175">Escriba un número de 16 dígitos en el **número de cuenta** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-175">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="88825-176">Seleccione **MQSeries** en el **Select Transport and Parameters** cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="88825-176">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="88825-177">Tipo de \< *nombre del Administrador de cola* \> en el **Administrador de cola** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-177">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="88825-178">QM_\<*el nombre del equipo* \> es el valor predeterminado de \< *nombre del Administrador de cola*\>.</span><span class="sxs-lookup"><span data-stu-id="88825-178">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="88825-179">Tipo de `InlineSOAInputQueue` en el **Input Queue** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-179">Type `InlineSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="88825-180">Tipo de `InlineSOAOutputQueue` en el **cola de salida** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-180">Type `InlineSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="88825-181">Tipo de \< *definición de canal* \> en el **definición de canal** cuadro.</span><span class="sxs-lookup"><span data-stu-id="88825-181">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="88825-182">S_\<*el nombre del equipo*\>/TCP /\<*el nombre del equipo*\>(1414) es el valor predeterminado de \<  *Definición de canal*\>.</span><span class="sxs-lookup"><span data-stu-id="88825-182">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="88825-183">Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-183">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="88825-184">Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="88825-184">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="88825-185">Haga clic en **obtener mi Saldo**.</span><span class="sxs-lookup"><span data-stu-id="88825-185">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="88825-186">La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="88825-186">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="88825-187">![Ejecutar la aplicación cliente para la versión en línea](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="88825-187">![Run the client application for the inline version](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88825-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="88825-188">See Also</span></span>  
 <span data-ttu-id="88825-189">[Antes de instalar la solución orientada a servicios](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="88825-189">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="88825-190">[Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="88825-190">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="88825-191">[Cómo instalar las versiones de adaptador del servicio y en línea solución orientada a servicios](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="88825-191">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="88825-192">Configurar el equipo del desarrollador para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="88825-192">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)