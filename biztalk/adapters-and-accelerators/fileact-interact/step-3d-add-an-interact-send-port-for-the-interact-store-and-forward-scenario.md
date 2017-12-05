---
title: "Paso 3D: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd126d9a-f4e4-429e-bab0-8b4c9c555e36
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11b4e17a4435c5d9e6e99cd3ed471fa8819923e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="5a04e-102">Paso 3D: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de reenvío</span><span class="sxs-lookup"><span data-stu-id="5a04e-102">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="5a04e-103">Completa [paso 3c: agregar un puerto de envío de archivo para capturar el mensaje Sw:HandleRequest para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md) antes de comenzar este paso.</span><span class="sxs-lookup"><span data-stu-id="5a04e-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="5a04e-104">Agregar un puerto de envío INTERACT</span><span class="sxs-lookup"><span data-stu-id="5a04e-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="5a04e-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5a04e-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="5a04e-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="5a04e-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="5a04e-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_IA_SendRequest_SnF.</span><span class="sxs-lookup"><span data-stu-id="5a04e-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="5a04e-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **INTERACT**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="5a04e-110">En el **propiedades de transporte interactuar** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a04e-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5a04e-111">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="5a04e-111">**Use this**</span></span>|<span data-ttu-id="5a04e-112">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="5a04e-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5a04e-113">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="5a04e-113">**Password**</span></span>|<span data-ttu-id="5a04e-114">Establecer la contraseña según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="5a04e-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="5a04e-115">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="5a04e-115">**User name**</span></span>|<span data-ttu-id="5a04e-116">Defina el nombre de usuario según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="5a04e-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="5a04e-117">**Formato de mensaje**</span><span class="sxs-lookup"><span data-stu-id="5a04e-117">**Message format**</span></span>|<span data-ttu-id="5a04e-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="5a04e-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="5a04e-119">**Indicador de sin repudio**</span><span class="sxs-lookup"><span data-stu-id="5a04e-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="5a04e-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="5a04e-120">**FALSE**</span></span>|  
    |<span data-ttu-id="5a04e-121">**Tipo de solicitud**</span><span class="sxs-lookup"><span data-stu-id="5a04e-121">**Request Type**</span></span>|<span data-ttu-id="5a04e-122">Escriba la correspondiente \<RequestType\> cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="5a04e-122">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5a04e-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="5a04e-123">**ResponseCrypto**</span></span>|<span data-ttu-id="5a04e-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="5a04e-124">**FALSE**</span></span>|  
    |<span data-ttu-id="5a04e-125">**Solicitante**</span><span class="sxs-lookup"><span data-stu-id="5a04e-125">**Requestor**</span></span>|<span data-ttu-id="5a04e-126">Escriba la correspondiente \<RequestorDN\> cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="5a04e-126">Type the appropriate \<RequestorDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5a04e-127">**Servicio de respuesta**</span><span class="sxs-lookup"><span data-stu-id="5a04e-127">**Responder**</span></span>|<span data-ttu-id="5a04e-128">Escriba la correspondiente \<ResponderDN\> cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="5a04e-128">Type the appropriate \<ResponderDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5a04e-129">**Nombre del servicio**</span><span class="sxs-lookup"><span data-stu-id="5a04e-129">**Service Name**</span></span>|<span data-ttu-id="5a04e-130">Escriba la correspondiente \<nombre del servicio\>, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="5a04e-130">Type the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5a04e-131">**Notificación de entrega**</span><span class="sxs-lookup"><span data-stu-id="5a04e-131">**Delivery Notification**</span></span>|<span data-ttu-id="5a04e-132">En la lista desplegable, seleccione **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="5a04e-133">**Cola de notificación**</span><span class="sxs-lookup"><span data-stu-id="5a04e-133">**Notify queue**</span></span>|<span data-ttu-id="5a04e-134">Escriba el nombre de la cola apropiada, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="5a04e-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="5a04e-135">Si solo carga va a transferirse, conjunto MessageFormat a "Carga" en la interacción puerto de recepción y puerto de envío de interacción.</span><span class="sxs-lookup"><span data-stu-id="5a04e-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="5a04e-136">Establecer las canalizaciones de envío y recepción en PassThru.</span><span class="sxs-lookup"><span data-stu-id="5a04e-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="5a04e-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="5a04e-138">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a04e-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="5a04e-139">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="5a04e-139">**Use this**</span></span>|<span data-ttu-id="5a04e-140">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="5a04e-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5a04e-141">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="5a04e-141">**Send handler**</span></span>|<span data-ttu-id="5a04e-142">En la lista desplegable, seleccione el host de interacción.</span><span class="sxs-lookup"><span data-stu-id="5a04e-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="5a04e-143">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="5a04e-143">**Send pipeline**</span></span>|<span data-ttu-id="5a04e-144">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="5a04e-145">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="5a04e-145">**Receive pipeline**</span></span>|<span data-ttu-id="5a04e-146">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="5a04e-147">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a04e-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="5a04e-148">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="5a04e-148">**Use this**</span></span>|<span data-ttu-id="5a04e-149">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="5a04e-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5a04e-150">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="5a04e-150">**Property**</span></span>|<span data-ttu-id="5a04e-151">En la lista desplegable, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="5a04e-152">**Operador**</span><span class="sxs-lookup"><span data-stu-id="5a04e-152">**Operator**</span></span>|<span data-ttu-id="5a04e-153">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="5a04e-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="5a04e-154">**Valor**</span><span class="sxs-lookup"><span data-stu-id="5a04e-154">**Value**</span></span>|<span data-ttu-id="5a04e-155">Tutorial_IA_InputRequest_SnF de tipo.</span><span class="sxs-lookup"><span data-stu-id="5a04e-155">Type Tutorial_IA_InputRequest_SnF.</span></span>|  
    |<span data-ttu-id="5a04e-156">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="5a04e-156">**Group by**</span></span>|<span data-ttu-id="5a04e-157">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5a04e-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="5a04e-158">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5a04e-158">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="5a04e-159">Complete los pasos</span><span class="sxs-lookup"><span data-stu-id="5a04e-159">Complete steps</span></span>
 <span data-ttu-id="5a04e-160">[Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a04e-160">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="5a04e-161">[Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a04e-161">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="5a04e-162">[Paso 3B: agregar un INTERACTÚE ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a04e-162">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="5a04e-163">Paso 3C: Agregar un puerto de envío de ARCHIVOS para capturar el mensaje Sw:HandleRequest para el escenario de almacenamiento y reenvío de InterAct</span><span class="sxs-lookup"><span data-stu-id="5a04e-163">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  