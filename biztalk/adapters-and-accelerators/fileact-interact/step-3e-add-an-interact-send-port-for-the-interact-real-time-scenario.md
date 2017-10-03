---
title: "Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcb78fd556e72e4ca19e1d5172826a813f23eb24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a><span data-ttu-id="0d6c4-102">Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="0d6c4-102">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="0d6c4-103">Completa [paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-103">Complete [Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="0d6c4-104">Agregar un puerto de envío INTERACT</span><span class="sxs-lookup"><span data-stu-id="0d6c4-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="0d6c4-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0d6c4-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="0d6c4-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="0d6c4-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendRequest_RealTime**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="0d6c4-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **INTERACT**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="0d6c4-110">En el **propiedades de transporte interactuar** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d6c4-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="0d6c4-111">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-111">**Use this**</span></span>|<span data-ttu-id="0d6c4-112">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0d6c4-113">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-113">**Password**</span></span>|<span data-ttu-id="0d6c4-114">Establecer la contraseña según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="0d6c4-115">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-115">**User name**</span></span>|<span data-ttu-id="0d6c4-116">Defina el nombre de usuario según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="0d6c4-117">**Modo del adaptador**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-117">**Adapter Mode**</span></span>|<span data-ttu-id="0d6c4-118">En la lista desplegable, seleccione **en tiempo real**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-118">From the drop-down list, select **RealTime**.</span></span>|  
    |<span data-ttu-id="0d6c4-119">**Formato de mensaje**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-119">**Message format**</span></span>|<span data-ttu-id="0d6c4-120">**InteractMessage**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-120">**InteractMessage**.</span></span>|  
    |<span data-ttu-id="0d6c4-121">**Indicador de sin repudio**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-121">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="0d6c4-122">**FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-122">**FALSE**.</span></span>|  
    |<span data-ttu-id="0d6c4-123">**Tipo de solicitud**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-123">**Request Type**</span></span>|<span data-ttu-id="0d6c4-124">Escriba la correspondiente \<RequestType > cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-124">Type the appropriate \<RequestType> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="0d6c4-125">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-125">**ResponseCrypto**</span></span>|<span data-ttu-id="0d6c4-126">**FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-126">**FALSE**.</span></span>|  
    |<span data-ttu-id="0d6c4-127">**Solicitante**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-127">**Requestor**</span></span>|<span data-ttu-id="0d6c4-128">Establézcalo en la correspondiente \<solicitante > cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-128">Set it to the appropriate \<Requestor> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="0d6c4-129">**Servicio de respuesta**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-129">**Responder**</span></span>|<span data-ttu-id="0d6c4-130">Establézcalo en la correspondiente \<Respondedor > cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-130">Set it to the appropriate \<Responder> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="0d6c4-131">**Nombre del servicio**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-131">**Service Name**</span></span>|<span data-ttu-id="0d6c4-132">Establézcalo en la correspondiente \<nombre del servicio >, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-132">Set it to the appropriate \<service name>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="0d6c4-133">**Notificación de entrega**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-133">**Delivery Notification**</span></span>|<span data-ttu-id="0d6c4-134">En la lista desplegable, seleccione **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-134">From the drop-down list, select  **FALSE**.</span></span>|  
    |<span data-ttu-id="0d6c4-135">**Cola de notificación**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-135">**Notify queue**</span></span>|<span data-ttu-id="0d6c4-136">Escriba el nombre de la cola apropiada, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-136">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="0d6c4-137">Si solo carga va a transferirse, conjunto MessageFormat a "Payloadonly" en la interacción puerto de recepción y puerto de envío de interacción.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-137">If only payload is to be transferred, set the MessageFormat to “Payloadonly” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="0d6c4-138">Establezca la recepción y canalizaciones de envío a PassThru.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-138">Set the receive and send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="0d6c4-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-139">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="0d6c4-140">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d6c4-140">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="0d6c4-141">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-141">**Use this**</span></span>|<span data-ttu-id="0d6c4-142">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-142">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0d6c4-143">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-143">**Send handler**</span></span>|<span data-ttu-id="0d6c4-144">En la lista desplegable, seleccione el host de interacción.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-144">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="0d6c4-145">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-145">**Send pipeline**</span></span>|<span data-ttu-id="0d6c4-146">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-146">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="0d6c4-147">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-147">**Receive pipeline**</span></span>|<span data-ttu-id="0d6c4-148">**XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-148">**XMLReceive**</span></span>|  
  
9. <span data-ttu-id="0d6c4-149">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d6c4-149">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="0d6c4-150">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-150">**Use this**</span></span>|<span data-ttu-id="0d6c4-151">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-151">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0d6c4-152">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-152">**Property**</span></span>|<span data-ttu-id="0d6c4-153">En la lista desplegable, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-153">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="0d6c4-154">**Operador**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-154">**Operator**</span></span>|<span data-ttu-id="0d6c4-155">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="0d6c4-155">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="0d6c4-156">**Valor**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-156">**Value**</span></span>|<span data-ttu-id="0d6c4-157">Tipo de **Tutorial_IA_InputRequest_RealTime**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-157">Type **Tutorial_IA_InputRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="0d6c4-158">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="0d6c4-158">**Group by**</span></span>|<span data-ttu-id="0d6c4-159">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-159">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="0d6c4-160">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d6c4-160">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6c4-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d6c4-161">See Also</span></span>  
 <span data-ttu-id="0d6c4-162">[Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0d6c4-162">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0d6c4-163">[Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0d6c4-163">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0d6c4-164">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0d6c4-164">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0d6c4-165">[Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0d6c4-165">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="0d6c4-166">Paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="0d6c4-166">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)