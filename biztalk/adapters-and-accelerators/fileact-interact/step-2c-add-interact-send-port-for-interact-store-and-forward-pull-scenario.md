---
title: "Paso 2c: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de avance (extracción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2fe383d80c467376852067026a7c5a4fe4640ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="589a7-102">Paso 2c: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="589a7-102">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="589a7-103">Antes de comenzar este paso, debe completar [paso 2B: Agregar archivo puertos de envío para capturar el mensaje Sw:HandleRequest para el almacén de interacción y el escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).</span><span class="sxs-lookup"><span data-stu-id="589a7-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).</span></span>  
  
### <a name="to-add-an-interact-send-port"></a><span data-ttu-id="589a7-104">Para agregar un puerto de envío INTERACT</span><span class="sxs-lookup"><span data-stu-id="589a7-104">To add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="589a7-105">Iniciar **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="589a7-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="589a7-106">En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="589a7-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="589a7-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="589a7-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="589a7-108">En el **propiedades de puerto de envío** ventana, nombre el puerto de envío **Tutorial_IA_SendRequest_SnF**.</span><span class="sxs-lookup"><span data-stu-id="589a7-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="589a7-109">En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **INTERACT**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="589a7-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="589a7-110">En el **propiedades de transporte interactuar** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="589a7-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="589a7-111">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="589a7-111">**Use this**</span></span>|<span data-ttu-id="589a7-112">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="589a7-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="589a7-113">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="589a7-113">**Password**</span></span>|<span data-ttu-id="589a7-114">Establecer la contraseña según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="589a7-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="589a7-115">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="589a7-115">**User name**</span></span>|<span data-ttu-id="589a7-116">Defina el nombre de usuario según corresponda para la conectividad SAG.</span><span class="sxs-lookup"><span data-stu-id="589a7-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="589a7-117">**Formato de mensaje**</span><span class="sxs-lookup"><span data-stu-id="589a7-117">**Message format**</span></span>|<span data-ttu-id="589a7-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="589a7-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="589a7-119">**Indicador de sin repudio**</span><span class="sxs-lookup"><span data-stu-id="589a7-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="589a7-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="589a7-120">**FALSE**</span></span>|  
    |<span data-ttu-id="589a7-121">**Tipo de solicitud**</span><span class="sxs-lookup"><span data-stu-id="589a7-121">**Request Type**</span></span>|<span data-ttu-id="589a7-122">Escriba la correspondiente \<RequestType > cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="589a7-122">Type the appropriate \<RequestType> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="589a7-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="589a7-123">**ResponseCrypto**</span></span>|<span data-ttu-id="589a7-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="589a7-124">**FALSE**</span></span>|  
    |<span data-ttu-id="589a7-125">**Solicitante**</span><span class="sxs-lookup"><span data-stu-id="589a7-125">**Requestor**</span></span>|<span data-ttu-id="589a7-126">Escriba la correspondiente \<RequestorDN > cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="589a7-126">Type the appropriate \<RequestorDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="589a7-127">**Servicio de respuesta**</span><span class="sxs-lookup"><span data-stu-id="589a7-127">**Responder**</span></span>|<span data-ttu-id="589a7-128">Escriba la correspondiente \<ResponderDN > cadena, según su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="589a7-128">Type the appropriate \<ResponderDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="589a7-129">**Nombre del servicio**</span><span class="sxs-lookup"><span data-stu-id="589a7-129">**Service Name**</span></span>|<span data-ttu-id="589a7-130">Escriba la correspondiente \<nombre del servicio >, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="589a7-130">Type the appropriate \<service name>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="589a7-131">**Notificación de entrega**</span><span class="sxs-lookup"><span data-stu-id="589a7-131">**Delivery Notification**</span></span>|<span data-ttu-id="589a7-132">En la lista desplegable, seleccione **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="589a7-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="589a7-133">**Cola de notificación**</span><span class="sxs-lookup"><span data-stu-id="589a7-133">**Notify queue**</span></span>|<span data-ttu-id="589a7-134">Escriba el nombre de la cola apropiada, en función de su aprovisionamiento con SWIFT.</span><span class="sxs-lookup"><span data-stu-id="589a7-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="589a7-135">Si solo carga va a transferirse, conjunto MessageFormat a "Carga" en la interacción puerto de recepción y puerto de envío de interacción.</span><span class="sxs-lookup"><span data-stu-id="589a7-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="589a7-136">Establecer las canalizaciones de envío y recepción en PassThru.</span><span class="sxs-lookup"><span data-stu-id="589a7-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="589a7-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="589a7-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="589a7-138">En el **propiedades de puerto de envío** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="589a7-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="589a7-139">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="589a7-139">**Use this**</span></span>|<span data-ttu-id="589a7-140">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="589a7-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="589a7-141">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="589a7-141">**Send handler**</span></span>|<span data-ttu-id="589a7-142">En la lista desplegable, seleccione el host de interacción.</span><span class="sxs-lookup"><span data-stu-id="589a7-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="589a7-143">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="589a7-143">**Send pipeline**</span></span>|<span data-ttu-id="589a7-144">En la lista desplegable, seleccione **XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="589a7-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="589a7-145">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="589a7-145">**Receive pipeline**</span></span>|<span data-ttu-id="589a7-146">En la lista desplegable, seleccione **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="589a7-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="589a7-147">En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="589a7-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="589a7-148">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="589a7-148">**Use this**</span></span>|<span data-ttu-id="589a7-149">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="589a7-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="589a7-150">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="589a7-150">**Property**</span></span>|<span data-ttu-id="589a7-151">En la lista desplegable, seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="589a7-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="589a7-152">**Operador**</span><span class="sxs-lookup"><span data-stu-id="589a7-152">**Operator**</span></span>|<span data-ttu-id="589a7-153">En la lista desplegable, seleccione  **==** .</span><span class="sxs-lookup"><span data-stu-id="589a7-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="589a7-154">**Valor**</span><span class="sxs-lookup"><span data-stu-id="589a7-154">**Value**</span></span>|<span data-ttu-id="589a7-155">Tipo de **Tutorial_IA_InputRequest_SnF**.</span><span class="sxs-lookup"><span data-stu-id="589a7-155">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="589a7-156">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="589a7-156">**Group by**</span></span>|<span data-ttu-id="589a7-157">Dejar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="589a7-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="589a7-158">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="589a7-158">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589a7-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="589a7-159">See Also</span></span>  
 <span data-ttu-id="589a7-160">[Paso 2A: Agregar archivo ubicaciones de recepción para el almacén de interacción y el escenario de avance (extracción)](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="589a7-160">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="589a7-161">Paso 2B: agregar puertos de envío de archivo para capturar el mensaje Sw:HandleRequest para el almacén de interacción y el escenario de avance (extracción)</span><span class="sxs-lookup"><span data-stu-id="589a7-161">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)