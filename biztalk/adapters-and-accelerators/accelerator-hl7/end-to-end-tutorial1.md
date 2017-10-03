---
title: To-End SimulationTutorial1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.endtoendtutorial
helpviewer_keywords:
- end-to-end tutorial, about the tutorial
- end-to-end tutorial
- tutorials, end-to-end tutorial
ms.assetid: 90625edc-70a0-42c9-a2fb-8eeb5465d766
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90dc31ac286f8ce1e38d9a511eb319828d8ae939
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="20987-102">Tutorial de extremo a extremo</span><span class="sxs-lookup"><span data-stu-id="20987-102">End-to-End Tutorial</span></span>
<span data-ttu-id="20987-103">Este tutorial contiene los pasos detallados que describen cómo usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para facilitar procesos empresariales en un escenario de suscriptor y el publicador.</span><span class="sxs-lookup"><span data-stu-id="20987-103">This tutorial contains detailed steps that describe how you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a subscriber and publisher scenario.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20987-104">Para utilizar este tutorial, debe instalar las herramientas de prueba al instalar BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="20987-104">To use this tutorial, you must install the test tools when installing BTAHL7.</span></span> <span data-ttu-id="20987-105">Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba en orden para que funcione correctamente este tutorial.</span><span class="sxs-lookup"><span data-stu-id="20987-105">If you performed a typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="20987-106">En el **personalizada** pantalla de la instalación personalizada de BTAHL7, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **instancias de prueba** desde el **artefactos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="20987-106">At the **Custom Setup** screen of the BTAHL7 custom installation, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="20987-107">Para obtener más información, consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span><span class="sxs-lookup"><span data-stu-id="20987-107">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="declarative-scenario"></a><span data-ttu-id="20987-108">Escenario de declaración</span><span class="sxs-lookup"><span data-stu-id="20987-108">Declarative Scenario</span></span>  
 <span data-ttu-id="20987-109">Este tutorial utiliza el escenario declarativa o publicación/suscripción.</span><span class="sxs-lookup"><span data-stu-id="20987-109">This tutorial uses the publish/subscribe or declarative scenario.</span></span> <span data-ttu-id="20987-110">En el escenario declarativo, el flujo de trabajo es similar al que se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="20987-110">In the declarative scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="20987-111">La lista numerada de la figura siguiente describe el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="20987-111">The numbered list following the figure describes the workflow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
<span data-ttu-id="20987-112">Ilustración que muestra el flujo de trabajo para el escenario declarativo</span><span class="sxs-lookup"><span data-stu-id="20987-112">Figure showing the flow of business for the declarative scenario</span></span>  
  
1.  <span data-ttu-id="20987-113">El flujo de trabajo comienza cuando el publicador, por ejemplo, una descarga de admisión y sistema de transferencia, envía un mensaje a suscriptores específicos.</span><span class="sxs-lookup"><span data-stu-id="20987-113">The workflow begins when the publisher, for example, an Admissions Discharge and Transfer system, sends a message to specific subscribers.</span></span> <span data-ttu-id="20987-114">El publicador en el flujo de trabajo es "Tutorial_ADTSystem" y el mensaje se denomina "**ADT ^ A103**."</span><span class="sxs-lookup"><span data-stu-id="20987-114">The publisher in the workflow is "Tutorial_ADTSystem", and the message is called "**ADT^A103**."</span></span>  
  
2.  <span data-ttu-id="20987-115">El mensaje se enruta al motor de interfaz de BTAHL7, que a su vez recibe, procesa, valida, vuelve a dar formato y, a continuación, enruta el mensaje a los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="20987-115">The message is routed to the BTAHL7 Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to subscribers.</span></span>  
  
3.  <span data-ttu-id="20987-116">Los suscriptores en este escenario son un sistema de información de salud (Tutorial_HISystem) y un sistema de farmacia (Tutorial_RXSystem).</span><span class="sxs-lookup"><span data-stu-id="20987-116">The subscribers in this scenario are a Hospital Information System (Tutorial_HISystem) and a Pharmacy System (Tutorial_RXSystem).</span></span> <span data-ttu-id="20987-117">Este escenario utiliza tipos de adaptador de archivo y MLLP.</span><span class="sxs-lookup"><span data-stu-id="20987-117">This scenario uses both File and MLLP adapter types.</span></span> <span data-ttu-id="20987-118">El publicador no es necesario tener en cuenta los suscriptores y BTAHL7 adecuadamente envía una confirmación al publicador después de procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="20987-118">The publisher does not need to be aware of the subscribers and BTAHL7 appropriately sends an acknowledgment to the publisher after processing the message.</span></span>  
  
4.  <span data-ttu-id="20987-119">El publicador envía el ADT ^ A03 mensaje a través de un adaptador MLLP unidireccional (Tutorial_1WayReceivePort).</span><span class="sxs-lookup"><span data-stu-id="20987-119">The publisher sends the ADT^A03 message through a one-way MLLP adapter (Tutorial_1WayReceivePort).</span></span>  
  
5.  <span data-ttu-id="20987-120">El destino de este mensaje es el motor de interfaz de BTAHL7, por lo que el mensaje entrante contiene un mensaje de origen (MSH3 = Tutorial_ADTSystem) y un mensaje de destino (MSH5 = BTAHL7InterfaceEngine).</span><span class="sxs-lookup"><span data-stu-id="20987-120">The destination of this message is the BTAHL7 Interface Engine, so the incoming message contains a source message (MSH3 = Tutorial_ADTSystem) and a destination message (MSH5 = BTAHL7InterfaceEngine).</span></span>  
  
6.  <span data-ttu-id="20987-121">BTAHL7 genera una confirmación (ACK) después de validar correctamente el mensaje y, a continuación, envía la confirmación a la Tutorial_ADTSystem a través del adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="20987-121">BTAHL7 generates an acknowledgment (ACK) after appropriately validating the message, and then sends the acknowledgment to the Tutorial_ADTSystem through the File adapter.</span></span>  
  
7.  <span data-ttu-id="20987-122">El sistema de Tutorial_HISystem y el sistema Tutorial_RXSystem suscriben al mensaje ADT recibido por el motor de la interfaz de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="20987-122">The Tutorial_HISystem system and the Tutorial_RXSystem system subscribe to the ADT message received by the BTAHL7 Interface Engine.</span></span>  
  
8.  <span data-ttu-id="20987-123">La transformación se produce al especificar valores para los respectivos campos mediante el uso de la **MSH mapa** pestaña en el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="20987-123">The transformation occurs when you specify values for the respective fields by using the **MSH Map** tab in BTAHL7 Configuration Explorer.</span></span>  
  
     <span data-ttu-id="20987-124">Por ejemplo, la entidad Tutorial_RXSystem tiene MSH3 = BTHL7 especificado en el **MSH mapa** ficha. Por lo tanto, el mensaje recibido por el suscriptor tendrá "BTAHL7" como el valor para el campo MSH3.</span><span class="sxs-lookup"><span data-stu-id="20987-124">For example, the party Tutorial_RXSystem has MSH3=BTHL7 specified in the **MSH Map** tab. Therefore, the message received by the subscriber will have "BTAHL7" as the value for the MSH3 field.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20987-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20987-125">In this section</span></span>  
  
-   [<span data-ttu-id="20987-126">Comprobación de la instalación</span><span class="sxs-lookup"><span data-stu-id="20987-126">Testing Your Installation</span></span>](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [<span data-ttu-id="20987-127">Preparando para utilizar el Tutorial</span><span class="sxs-lookup"><span data-stu-id="20987-127">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [<span data-ttu-id="20987-128">Paso 1: Crear e implementar encabezado y esquemas de confirmación</span><span class="sxs-lookup"><span data-stu-id="20987-128">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="20987-129">Paso 2: Crear los esquemas comunes para v2.3.1</span><span class="sxs-lookup"><span data-stu-id="20987-129">Step 2: Create Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="20987-130">Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)</span><span class="sxs-lookup"><span data-stu-id="20987-130">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [<span data-ttu-id="20987-131">Paso 4: Crear el puerto de recepción para aceptar ADT ^ A03 mensajes desde sistemas ADT usa el adaptador MLLP</span><span class="sxs-lookup"><span data-stu-id="20987-131">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [<span data-ttu-id="20987-132">Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT usando el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="20987-132">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [<span data-ttu-id="20987-133">Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje en el sistema de recepción mediante el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="20987-133">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [<span data-ttu-id="20987-134">Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje a su usa el adaptador MLLP</span><span class="sxs-lookup"><span data-stu-id="20987-134">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [<span data-ttu-id="20987-135">Paso 8: Configurar la información de entidad</span><span class="sxs-lookup"><span data-stu-id="20987-135">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [<span data-ttu-id="20987-136">Paso 9: Reinicie el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="20987-136">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="20987-137">Paso 10: Comprobar el escenario de extremo a extremo</span><span class="sxs-lookup"><span data-stu-id="20987-137">Step 10: Verify the End-to-End Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a><span data-ttu-id="20987-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="20987-138">See also</span></span>
[<span data-ttu-id="20987-139">Empezar a trabajar con el Acelerador de BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="20987-139">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)