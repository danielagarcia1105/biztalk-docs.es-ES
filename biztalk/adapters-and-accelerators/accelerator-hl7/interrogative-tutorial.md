---
title: Tutorial interrogative | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b35a5bc8ba7574df7499fef5d63a100993c4201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interrogative-tutorial"></a><span data-ttu-id="12f38-102">Tutorial interrogative</span><span class="sxs-lookup"><span data-stu-id="12f38-102">Interrogative Tutorial</span></span>
<span data-ttu-id="12f38-103">Este tutorial contiene los pasos detallados que describen cómo usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para facilitar procesos empresariales en un escenario de consulta/respuesta.</span><span class="sxs-lookup"><span data-stu-id="12f38-103">This tutorial contains detailed steps that describe how you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a Query/Response scenario.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12f38-104">Para utilizar este tutorial, debe instalar las herramientas de prueba MLLP.</span><span class="sxs-lookup"><span data-stu-id="12f38-104">To use this tutorial, you must install the MLLP test tools.</span></span> <span data-ttu-id="12f38-105">Estas herramientas no se instalan mediante una instalación típica de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="12f38-105">These tools are not installed by a Typical installation of BTAHL7.</span></span> <span data-ttu-id="12f38-106">Debe ejecutar una instalación personalizada y seleccione **herramienta de prueba de MLLP** desde la carpeta del adaptador y **instancias de prueba** desde la carpeta de artefactos.</span><span class="sxs-lookup"><span data-stu-id="12f38-106">You must run a Custom installation and select **MLLP Test Tool** from the Adapter folder and **Test Instances** from the Artifacts folder.</span></span> <span data-ttu-id="12f38-107">Si se instalan las herramientas de prueba, el sistema contendrá la carpeta \< *unidad*: > \Program BizTalk \<versión > Accelerator for HL7\SDK\MLLP utilidades.</span><span class="sxs-lookup"><span data-stu-id="12f38-107">If the test tools are installed, your system will contain the folder \<*drive*:>\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\MLLP Utilities.</span></span> <span data-ttu-id="12f38-108">Vea [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span><span class="sxs-lookup"><span data-stu-id="12f38-108">See [install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="interrogative-scenario"></a><span data-ttu-id="12f38-109">Escenario interrogative</span><span class="sxs-lookup"><span data-stu-id="12f38-109">Interrogative Scenario</span></span>  
 <span data-ttu-id="12f38-110">Este tutorial utiliza el escenario de Interrogative o consulta/respuesta.</span><span class="sxs-lookup"><span data-stu-id="12f38-110">This tutorial uses the Query/Response or Interrogative scenario.</span></span> <span data-ttu-id="12f38-111">En este escenario, el flujo de trabajo es similar al que se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="12f38-111">In this scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="12f38-112">La lista numerada de la figura siguiente describe el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="12f38-112">The numbered list following the figure describes the workflow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")  
  
1.  <span data-ttu-id="12f38-113">El flujo de trabajo comienza cuando un sistema de admisión de descarga y transferir (ADT) envía una consulta en el sistema de información de salud.</span><span class="sxs-lookup"><span data-stu-id="12f38-113">The workflow begins when an Admissions Discharge and Transfer (ADT) system sends a query to the Hospital Information System.</span></span> <span data-ttu-id="12f38-114">El mensaje HL7 utiliza el "**consulta ^ Q01**" esquema.</span><span class="sxs-lookup"><span data-stu-id="12f38-114">The HL7 message uses the "**QRY^Q01**" schema.</span></span> <span data-ttu-id="12f38-115">En el tutorial, la utilidad MllpSend simula el ADT sistema envía el mensaje de consulta para el sistema de información de Hospital aprovechando el ADT puerto de recepción en el motor de integración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="12f38-115">In the tutorial, the MllpSend utility simulates the ADT system sending the query message to the Hospital Information System through the ADT receive port in the BTAHL7 Integration Engine.</span></span>  
  
2.  <span data-ttu-id="12f38-116">El motor de integración de BTAHL7 recibe el mensaje de consulta desde el sistema ADT y lo valida.</span><span class="sxs-lookup"><span data-stu-id="12f38-116">The BTAHL7 Integration Engine receives the query message from the ADT system and validates it.</span></span> <span data-ttu-id="12f38-117">A continuación, la canalización de BTAHL7 envía una confirmación al ADT.</span><span class="sxs-lookup"><span data-stu-id="12f38-117">Then, the BTAHL7 pipeline sends an acknowledgment back to ADT.</span></span>  
  
3.  <span data-ttu-id="12f38-118">El motor de la interfaz de BTAHL7 procesa el mensaje y, a continuación, el puerto de envío el mensaje de consulta en el destino de HIS de terceros a través de la HIS de rutas.</span><span class="sxs-lookup"><span data-stu-id="12f38-118">The BTAHL7 Interface Engine processes the message, and then routes the query message to the HIS destination party through the HIS send port.</span></span>  
  
4.  <span data-ttu-id="12f38-119">Después de recibir la confirmación de la consulta original, el sistema ADT esperará una respuesta.</span><span class="sxs-lookup"><span data-stu-id="12f38-119">After receiving the acknowledgment from the original query, the ADT system waits for a response.</span></span> <span data-ttu-id="12f38-120">El sistema de información de salud envían un mensaje de respuesta a través de la HIS puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="12f38-120">The Hospital Information System sends a response message back through the HIS receive port.</span></span> <span data-ttu-id="12f38-121">Para este tutorial, la utilidad MllpSend simula el sistema de información de salud enviar el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="12f38-121">For this tutorial, the MllpSend utility simulates the Hospital Information System sending the response message.</span></span>  
  
5.  <span data-ttu-id="12f38-122">El motor de la interfaz de BTAHL7 procesa el mensaje de respuesta y, a continuación, se enruta a la entidad de destino a través del puerto de envío ADT.</span><span class="sxs-lookup"><span data-stu-id="12f38-122">The BTAHL7 Interface Engine processes the response message and then routes it to the destination party through the ADT send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12f38-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="12f38-123">In this section</span></span>  
  
-   [<span data-ttu-id="12f38-124">Preparando para utilizar el Tutorial</span><span class="sxs-lookup"><span data-stu-id="12f38-124">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [<span data-ttu-id="12f38-125">Paso 1: Crear e implementar encabezado común y esquemas de confirmación</span><span class="sxs-lookup"><span data-stu-id="12f38-125">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="12f38-126">Paso 2: Crear los esquemas comunes para V2.4</span><span class="sxs-lookup"><span data-stu-id="12f38-126">Step 2: Create Common Schemas for V2.4</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [<span data-ttu-id="12f38-127">Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)</span><span class="sxs-lookup"><span data-stu-id="12f38-127">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [<span data-ttu-id="12f38-128">Paso 4: Crear el puerto de recepción para aceptar mensajes de consulta ADT</span><span class="sxs-lookup"><span data-stu-id="12f38-128">Step 4: Create the Receive Port for Accepting ADT Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [<span data-ttu-id="12f38-129">Paso 5: Crear el puerto de recepción para aceptar los mensajes</span><span class="sxs-lookup"><span data-stu-id="12f38-129">Step 5: Create the Receive Port for Accepting HIS Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [<span data-ttu-id="12f38-130">Paso 6: Crear un puerto de envío para entregar los mensajes de consulta</span><span class="sxs-lookup"><span data-stu-id="12f38-130">Step 6: Create a Send Port to Deliver Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [<span data-ttu-id="12f38-131">Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta</span><span class="sxs-lookup"><span data-stu-id="12f38-131">Step 7: Create a Send Port to Deliver Response Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [<span data-ttu-id="12f38-132">Paso 8: Configurar la información de entidad</span><span class="sxs-lookup"><span data-stu-id="12f38-132">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [<span data-ttu-id="12f38-133">Paso 9: Reinicie el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="12f38-133">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [<span data-ttu-id="12f38-134">Paso 10: Comprobar el escenario Interrogative</span><span class="sxs-lookup"><span data-stu-id="12f38-134">Step 10: Verify the Interrogative Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a><span data-ttu-id="12f38-135">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="12f38-135">Next step</span></span>  
 [<span data-ttu-id="12f38-136">Preparando para utilizar el Tutorial</span><span class="sxs-lookup"><span data-stu-id="12f38-136">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a><span data-ttu-id="12f38-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="12f38-137">See Also</span></span>  
[<span data-ttu-id="12f38-138">Empezar a trabajar con el Acelerador de BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="12f38-138">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)