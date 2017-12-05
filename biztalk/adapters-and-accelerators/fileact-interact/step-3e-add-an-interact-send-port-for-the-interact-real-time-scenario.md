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
ms.openlocfilehash: ec380c088f27fe09f518c385990e3801b5c019dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a><span data-ttu-id="3e4ed-102">Paso 3E: agregar un puerto de envío de interacción para el escenario en tiempo real de interactuar</span><span class="sxs-lookup"><span data-stu-id="3e4ed-102">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="3e4ed-103">Completa [paso 3D: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleResponse para el escenario de en tiempo real interactuar](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-103">Complete [Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="3e4ed-104">Agregar un puerto de envío INTERACT</span><span class="sxs-lookup"><span data-stu-id="3e4ed-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="3e4ed-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3e4ed-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="3e4ed-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="3e4ed-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendRequest_RealTime**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="3e4ed-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **INTERACT**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="3e4ed-110">En el **propiedades de transporte interactuar** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e4ed-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="3e4ed-111">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-111">**Use this**</span></span>|<span data-ttu-id="3e4ed-112">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3e4ed-113">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-113">**Password**</span></span>|<span data-ttu-id="3e4ed-114">Establecer la contraseña según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="3e4ed-115">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-115">**User name**</span></span>|<span data-ttu-id="3e4ed-116">Defina el nombre de usuario según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="3e4ed-117">**Modo del adaptador**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-117">**Adapter Mode**</span></span>|<span data-ttu-id="3e4ed-118">En la lista desplegable, seleccione **en tiempo real**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-118">From the drop-down list, select **RealTime**.</span></span>|  
    |<span data-ttu-id="3e4ed-119">**Formato de mensaje**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-119">**Message format**</span></span>|<span data-ttu-id="3e4ed-120">**InteractMessage**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-120">**InteractMessage**.</span></span>|  
    |<span data-ttu-id="3e4ed-121">**Indicador de sin repudio**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-121">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="3e4ed-122">**FALSE**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-122">**FALSE**.</span></span>|  
    |<span data-ttu-id="3e4ed-123">**Tipo de solicitud**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-123">**Request Type**</span></span>|<span data-ttu-id="3e4ed-124">Escriba la correspondiente \<RequestType\> cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-124">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3e4ed-125">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-125">**ResponseCrypto**</span></span>|<span data-ttu-id="3e4ed-126">**FALSE**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-126">**FALSE**.</span></span>|  
    |<span data-ttu-id="3e4ed-127">**Solicitante**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-127">**Requestor**</span></span>|<span data-ttu-id="3e4ed-128">Establézcalo en la correspondiente \<solicitante\> cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-128">Set it to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3e4ed-129">**Servicio de respuesta**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-129">**Responder**</span></span>|<span data-ttu-id="3e4ed-130">Establézcalo en la correspondiente \<Respondedor\> cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-130">Set it to the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3e4ed-131">**Nombre del servicio**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-131">**Service Name**</span></span>|<span data-ttu-id="3e4ed-132">Establézcalo en la correspondiente \<nombre del servicio\>, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-132">Set it to the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3e4ed-133">**Notificación de entrega**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-133">**Delivery Notification**</span></span>|<span data-ttu-id="3e4ed-134">En la lista desplegable, seleccione **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-134">From the drop-down list, select  **FALSE**.</span></span>|  
    |<span data-ttu-id="3e4ed-135">**Cola de notificación**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-135">**Notify queue**</span></span>|<span data-ttu-id="3e4ed-136">Escriba el nombre de la cola apropiada, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-136">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="3e4ed-137">Si solo carga va a transferirse, conjunto MessageFormat a "Payloadonly" en la interacción puerto de recepción y puerto de envío de interacción.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-137">If only payload is to be transferred, set the MessageFormat to “Payloadonly” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="3e4ed-138">Establezca la recepción y canalizaciones de envío a PassThru.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-138">Set the receive and send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="3e4ed-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-139">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3e4ed-140">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e4ed-140">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="3e4ed-141">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-141">**Use this**</span></span>|<span data-ttu-id="3e4ed-142">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-142">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3e4ed-143">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-143">**Send handler**</span></span>|<span data-ttu-id="3e4ed-144">En la lista desplegable, seleccione el host de interacción.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-144">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="3e4ed-145">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-145">**Send pipeline**</span></span>|<span data-ttu-id="3e4ed-146">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-146">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="3e4ed-147">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-147">**Receive pipeline**</span></span>|<span data-ttu-id="3e4ed-148">**XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-148">**XMLReceive**</span></span>|  
  
9. <span data-ttu-id="3e4ed-149">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e4ed-149">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="3e4ed-150">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-150">**Use this**</span></span>|<span data-ttu-id="3e4ed-151">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-151">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3e4ed-152">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-152">**Property**</span></span>|<span data-ttu-id="3e4ed-153">En la lista desplegable, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-153">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="3e4ed-154">**Operador**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-154">**Operator**</span></span>|<span data-ttu-id="3e4ed-155">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="3e4ed-155">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="3e4ed-156">**Valor**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-156">**Value**</span></span>|<span data-ttu-id="3e4ed-157">Tipo de **Tutorial_IA_InputRequest_RealTime**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-157">Type **Tutorial_IA_InputRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="3e4ed-158">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="3e4ed-158">**Group by**</span></span>|<span data-ttu-id="3e4ed-159">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-159">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="3e4ed-160">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3e4ed-160">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e4ed-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e4ed-161">See Also</span></span>  
 <span data-ttu-id="3e4ed-162">[Paso 3: Crear el envío y puertos de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3e4ed-162">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="3e4ed-163">[Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3e4ed-163">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="3e4ed-164">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3e4ed-164">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="3e4ed-165">[Paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el escenario en tiempo real de interactuar](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3e4ed-165">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="3e4ed-166">Paso 3D: Agregar un puerto de envío de ARCHIVOS para capturar el mensaje Sw:HandleResponse para el escenario de InterAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="3e4ed-166">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)