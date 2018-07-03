---
title: To-End SimulationTutorial1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.endtoendtutorial
helpviewer_keywords:
- end-to-end tutorial, about the tutorial
- end-to-end tutorial
- tutorials, end-to-end tutorial
ms.assetid: 90625edc-70a0-42c9-a2fb-8eeb5465d766
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264a6eee008b9b327185c931ad4e5ac60cdc995a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000741"
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="ca162-102">Tutorial de extremo a otro</span><span class="sxs-lookup"><span data-stu-id="ca162-102">End-to-End Tutorial</span></span>
<span data-ttu-id="ca162-103">Este tutorial contiene los pasos detallados que describen cómo utilizar Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para facilitar procesos empresariales en un escenario de suscriptor y el publicador.</span><span class="sxs-lookup"><span data-stu-id="ca162-103">This tutorial contains detailed steps that describe how you use Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a subscriber and publisher scenario.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca162-104">Para usar este tutorial, debe instalar las herramientas de prueba al instalar BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="ca162-104">To use this tutorial, you must install the test tools when installing BTAHL7.</span></span> <span data-ttu-id="ca162-105">Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba para este tutorial funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca162-105">If you performed a typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="ca162-106">En el **instalación personalizada** pantalla de la instalación personalizada de BTAHL7, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **delasinstanciasdeprueba** desde el **artefactos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="ca162-106">At the **Custom Setup** screen of the BTAHL7 custom installation, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="ca162-107">Para obtener más información, consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span><span class="sxs-lookup"><span data-stu-id="ca162-107">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="declarative-scenario"></a><span data-ttu-id="ca162-108">Escenario de declaración</span><span class="sxs-lookup"><span data-stu-id="ca162-108">Declarative Scenario</span></span>  
 <span data-ttu-id="ca162-109">Este tutorial usa el escenario declarativa o publicación/suscripción.</span><span class="sxs-lookup"><span data-stu-id="ca162-109">This tutorial uses the publish/subscribe or declarative scenario.</span></span> <span data-ttu-id="ca162-110">En el escenario declarativo, el flujo de negocio es similar al que se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca162-110">In the declarative scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="ca162-111">La lista numerada de la figura siguiente describe el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ca162-111">The numbered list following the figure describes the workflow.</span></span>  
  
 <span data-ttu-id="ca162-112">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")</span><span class="sxs-lookup"><span data-stu-id="ca162-112">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")</span></span>  
<span data-ttu-id="ca162-113">Ilustración que muestra el flujo de negocio para el escenario declarativo</span><span class="sxs-lookup"><span data-stu-id="ca162-113">Figure showing the flow of business for the declarative scenario</span></span>  
  
1.  <span data-ttu-id="ca162-114">El flujo de trabajo comienza cuando el publicador, por ejemplo, una estancia de pacientes y del sistema de transferencia, envía un mensaje a suscriptores específicos.</span><span class="sxs-lookup"><span data-stu-id="ca162-114">The workflow begins when the publisher, for example, an Admissions Discharge and Transfer system, sends a message to specific subscribers.</span></span> <span data-ttu-id="ca162-115">El publicador en el flujo de trabajo es "Tutorial_ADTSystem" y el mensaje se denomina "**ADT ^ A103**."</span><span class="sxs-lookup"><span data-stu-id="ca162-115">The publisher in the workflow is "Tutorial_ADTSystem", and the message is called "**ADT^A103**."</span></span>  
  
2.  <span data-ttu-id="ca162-116">El mensaje se enruta al motor de interfaz de BTAHL7, que a su vez recibe, procesa, valida, vuelve a dar formato y, a continuación, enruta el mensaje a los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="ca162-116">The message is routed to the BTAHL7 Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to subscribers.</span></span>  
  
3.  <span data-ttu-id="ca162-117">Los suscriptores en este escenario son un sistema de información de Hospital (Tutorial_HISystem) y un sistema de farmacia (Tutorial_RXSystem).</span><span class="sxs-lookup"><span data-stu-id="ca162-117">The subscribers in this scenario are a Hospital Information System (Tutorial_HISystem) and a Pharmacy System (Tutorial_RXSystem).</span></span> <span data-ttu-id="ca162-118">Este escenario utiliza tipos de adaptador de archivo y de MLLP.</span><span class="sxs-lookup"><span data-stu-id="ca162-118">This scenario uses both File and MLLP adapter types.</span></span> <span data-ttu-id="ca162-119">El publicador no necesita ser consciente de los suscriptores y BTAHL7 adecuadamente envía una confirmación al publicador después de procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ca162-119">The publisher does not need to be aware of the subscribers and BTAHL7 appropriately sends an acknowledgment to the publisher after processing the message.</span></span>  
  
4.  <span data-ttu-id="ca162-120">El publicador envía el ADT ^ A03 mensaje a través de un adaptador de MLLP unidireccional (Tutorial_1WayReceivePort).</span><span class="sxs-lookup"><span data-stu-id="ca162-120">The publisher sends the ADT^A03 message through a one-way MLLP adapter (Tutorial_1WayReceivePort).</span></span>  
  
5.  <span data-ttu-id="ca162-121">El destino de este mensaje es el motor de la interfaz de BTAHL7, por lo que el mensaje entrante contiene un mensaje de origen (MSH3 = Tutorial_ADTSystem) y un mensaje de destino (MSH5 = BTAHL7InterfaceEngine).</span><span class="sxs-lookup"><span data-stu-id="ca162-121">The destination of this message is the BTAHL7 Interface Engine, so the incoming message contains a source message (MSH3 = Tutorial_ADTSystem) and a destination message (MSH5 = BTAHL7InterfaceEngine).</span></span>  
  
6.  <span data-ttu-id="ca162-122">BTAHL7 genera una confirmación (ACK) después de validar correctamente el mensaje y, a continuación, envía la confirmación a la Tutorial_ADTSystem a través del adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="ca162-122">BTAHL7 generates an acknowledgment (ACK) after appropriately validating the message, and then sends the acknowledgment to the Tutorial_ADTSystem through the File adapter.</span></span>  
  
7.  <span data-ttu-id="ca162-123">El sistema Tutorial_HISystem y el sistema Tutorial_RXSystem suscriben al mensaje ADT recibido por el motor de la interfaz de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="ca162-123">The Tutorial_HISystem system and the Tutorial_RXSystem system subscribe to the ADT message received by the BTAHL7 Interface Engine.</span></span>  
  
8.  <span data-ttu-id="ca162-124">La transformación se produce al especificar valores para los campos correspondientes usando el **asignación de MSH** ficha en el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="ca162-124">The transformation occurs when you specify values for the respective fields by using the **MSH Map** tab in BTAHL7 Configuration Explorer.</span></span>  
  
     <span data-ttu-id="ca162-125">Por ejemplo, la entidad Tutorial_RXSystem tiene MSH3 = BTHL7 especificado en el **asignación de MSH** ficha. Por lo tanto, el mensaje recibido por el suscriptor tendrá "BTAHL7" como el valor del campo MSH3.</span><span class="sxs-lookup"><span data-stu-id="ca162-125">For example, the party Tutorial_RXSystem has MSH3=BTHL7 specified in the **MSH Map** tab. Therefore, the message received by the subscriber will have "BTAHL7" as the value for the MSH3 field.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca162-126">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ca162-126">In this section</span></span>  
  
-   [<span data-ttu-id="ca162-127">Probar la instalación</span><span class="sxs-lookup"><span data-stu-id="ca162-127">Testing Your Installation</span></span>](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [<span data-ttu-id="ca162-128">Preparación para usar el tutorial</span><span class="sxs-lookup"><span data-stu-id="ca162-128">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [<span data-ttu-id="ca162-129">Paso 1: Crear e implementar esquemas de encabezado y confirmación</span><span class="sxs-lookup"><span data-stu-id="ca162-129">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="ca162-130">Paso 2: Creación de esquemas comunes para v2.3.1</span><span class="sxs-lookup"><span data-stu-id="ca162-130">Step 2: Create Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="ca162-131">Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)</span><span class="sxs-lookup"><span data-stu-id="ca162-131">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [<span data-ttu-id="ca162-132">Paso 4: Crear el puerto de recepción para aceptar mensajes ADT^A03 desde sistemas ADT mediante el adaptador de MLLP</span><span class="sxs-lookup"><span data-stu-id="ca162-132">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [<span data-ttu-id="ca162-133">Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT mediante el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="ca162-133">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [<span data-ttu-id="ca162-134">Paso 6: Crear un puerto de envío para entregar el mensaje ADT^A03 al sistema RX mediante el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="ca162-134">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [<span data-ttu-id="ca162-135">Paso 7: Crear un puerto de envío para entregar el mensaje ADT^A03 a HIS mediante el adaptador de MLLP</span><span class="sxs-lookup"><span data-stu-id="ca162-135">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [<span data-ttu-id="ca162-136">Paso 8: Configurar la información de entidad</span><span class="sxs-lookup"><span data-stu-id="ca162-136">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [<span data-ttu-id="ca162-137">Paso 9: Reiniciar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ca162-137">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="ca162-138">Paso 10: Comprobar el escenario integral</span><span class="sxs-lookup"><span data-stu-id="ca162-138">Step 10: Verify the End-to-End Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a><span data-ttu-id="ca162-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca162-139">See also</span></span>
[<span data-ttu-id="ca162-140">Introducción al Acelerador de BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="ca162-140">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)