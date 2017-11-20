---
title: 'Paso 13: Crear y configurar puertos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 256b1618313605f0847d9328abfd003f41ac61cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-13-create-and-configure-ports"></a><span data-ttu-id="2bd9f-102">Paso 13: Crear y configurar puertos</span><span class="sxs-lookup"><span data-stu-id="2bd9f-102">Step 13: Create and Configure Ports</span></span>
<span data-ttu-id="2bd9f-103">En este paso, usa al Asistente para configuración de puertos para crear y configurar puertos en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-103">In this step, you use the Port Configuration Wizard to create and configure ports in Orchestration Designer.</span></span> <span data-ttu-id="2bd9f-104">Puertos especifican cómo la orquestación envía y recibe mensajes del servidor de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-104">Ports specify how your orchestration sends and receives messages to and from business processes.</span></span> <span data-ttu-id="2bd9f-105">Cada puerto tiene un tipo, una dirección y un enlace.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-105">Each port has a type, a direction, and a binding.</span></span> <span data-ttu-id="2bd9f-106">Las propiedades de combinación determinan la dirección de comunicación, el patrón de comunicación, la ubicación a o desde el que [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] envía o recibe el mensaje y cómo tiene lugar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-106">The properties together determine the direction of communication, the pattern of communication, the location to or from which [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] sends or receives the message, and how the communication takes place.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="2bd9f-107">usa el adaptador de protocolo de nivel inferior (MLLP) como mínimo como un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-107"> uses the Minimum Lower Layer Protocol (MLLP) adapter as a send port.</span></span> <span data-ttu-id="2bd9f-108">El adaptador MLLP utiliza la comunicación de sockets TCP para comunicarse con otras aplicaciones, como aplicaciones de laboratorio, aplicaciones seguros y las aplicaciones de línea de negocio heredadas.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-108">The MLLP adapter uses TCP sockets communication to interface with other applications, such as laboratory applications, insurance applications, and legacy line-of-business applications.</span></span> <span data-ttu-id="2bd9f-109">Representa el adaptador de envío de MLLP un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador:</span><span class="sxs-lookup"><span data-stu-id="2bd9f-109">The MLLP Send Adapter represents a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adapter that is:</span></span>  
  
-   <span data-ttu-id="2bd9f-110">Personalizar.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-110">Customized.</span></span> <span data-ttu-id="2bd9f-111">El adaptador sólo se distribuye con [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], en lugar de envío con [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd9f-111">The adapter only ships with [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], as opposed to shipping with [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
-   <span data-ttu-id="2bd9f-112">Protocolo/transporte.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-112">Protocol/Transport.</span></span> <span data-ttu-id="2bd9f-113">El adaptador no es un aplicación o adaptador de datos.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-113">The adapter is not an application or data adapter.</span></span>  
  
-   <span data-ttu-id="2bd9f-114">Estático.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-114">Static.</span></span> <span data-ttu-id="2bd9f-115">La configuración del adaptador no implica una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-115">The adapter configuration does not involve a custom user interface.</span></span>  
  
-   <span data-ttu-id="2bd9f-116">Asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-116">Asynchronous.</span></span> <span data-ttu-id="2bd9f-117">El adaptador no bloquea el subproceso de motor de mensajería, lo que permite un mayor rendimiento de todos los adaptadores que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hosts.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-117">The adapter does not block the Messaging Engine thread, which enables increased performance of all adapters that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hosts.</span></span>  
  
-   <span data-ttu-id="2bd9f-118">Sin transacciones.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-118">Nontransacted.</span></span> <span data-ttu-id="2bd9f-119">El adaptador no es una recepción de transacción o enviar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-119">The adapter is not a transacted receive or send [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adapter.</span></span>  
  
-   <span data-ttu-id="2bd9f-120">Regular.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-120">Regular.</span></span> <span data-ttu-id="2bd9f-121">El adaptador no se ejecuta en un proceso de aplicación diferente.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-121">The adapter does not run in a separate application process.</span></span>  
  
-   <span data-ttu-id="2bd9f-122">Unidireccionales y bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-122">Both One-Way and Two-Way.</span></span> <span data-ttu-id="2bd9f-123">El adaptador admite unidireccionales y de solicitud-respuesta o petición-respuesta modos de interacción.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-123">The adapter supports both One-way and Request-Response/Solicit-Response modes of interaction.</span></span>  
  
 <span data-ttu-id="2bd9f-124">El adaptador MLLP puede enviar mensajes individuales o mensajes en un lote.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-124">The MLLP adapter can submit individual messages or submit messages in a batch.</span></span> <span data-ttu-id="2bd9f-125">El principio de un mensaje MLLP se marca con un carácter de contenedor, 0x0b hexadecimal (también conocido como el bloque de inicio o SB carácter), y se marca el final del mensaje mediante la combinación de un carácter hexadecimal de 0x1c (también conocido como el carácter de bloque final o EB) inmediatamente seguido del carácter de 0x0d (retorno de carro).</span><span class="sxs-lookup"><span data-stu-id="2bd9f-125">The beginning of an MLLP message is marked with a wrapper character, hexadecimal 0x0b (also known as the Start Block or SB character), and the end of the message is marked by the combination of a hexadecimal 0x1c character (also known as the End Block or EB character) immediately followed by the 0x0d character (Carriage Return).</span></span> <span data-ttu-id="2bd9f-126">Contadores de rendimiento de BTAHL7 contar solo estos caracteres de contenedor para los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-126">BTAHL7 performance counters only count these wrapper characters for sent messages.</span></span> <span data-ttu-id="2bd9f-127">Contadores de rendimiento de BTAHL7 no cuentan estos caracteres de contenedor al recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-127">BTAHL7 performance counters do not count these wrapper characters when receiving messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bd9f-128">El protocolo MLLP estándar no permite caracteres en 0 x 20 en la carga del mensaje puesto que interfiere con la capacidad para detectar los caracteres de SB y EB.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-128">The MLLP protocol standard does not allow characters under 0x20 in the message payload because it interferes with the ability to detect the SB and EB characters.</span></span> <span data-ttu-id="2bd9f-129">Puede configurar los valores de carácter SB y EB, por lo que tenga cuidado con este problema al realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-129">You can configure the SB and EB character values, so be wary of this issue when making changes.</span></span>  
  
 <span data-ttu-id="2bd9f-130">En este paso, configurará el adaptador MLLP y el adaptador SOAP.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-130">In this step, you configure the MLLP adapter and SOAP adapter.</span></span>  
  
### <a name="to-create-and-configure-the-ports"></a><span data-ttu-id="2bd9f-131">Para crear y configurar los puertos</span><span class="sxs-lookup"><span data-stu-id="2bd9f-131">To create and configure the ports</span></span>  
  
1.  <span data-ttu-id="2bd9f-132">En el Diseñador de orquestaciones, arrastre la **puerto** forma del cuadro de herramientas hasta la superficie de puerto en el lado izquierdo de la vista Diseño y coloque la forma para que alinea horizontalmente con el **DoorbellReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-132">In Orchestration Designer, drag the **Port** shape from the Toolbox to the Port Surface on the left side of the Design view surface, and drop the shape so that it aligns horizontally with the **DoorbellReceive** shape.</span></span>  
  
2.  <span data-ttu-id="2bd9f-133">En el **Asistente para configuración de puertos**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-133">In the **Port Configuration Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2bd9f-134">En el **propiedades de puerto** página, en la **nombre** , escriba **SOAPReceivePort**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-134">On the **Port Properties** page, in the **Name** field, type **SOAPReceivePort**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2bd9f-135">En el **seleccionar un tipo de puerto** página, escriba la información siguiente y, a continuación, haga clic en **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-135">On the **Select a Port Type** page, enter the following information, and then click **Next** to continue.</span></span>  
  
    |<span data-ttu-id="2bd9f-136">Use</span><span class="sxs-lookup"><span data-stu-id="2bd9f-136">Use this</span></span>|<span data-ttu-id="2bd9f-137">Para</span><span class="sxs-lookup"><span data-stu-id="2bd9f-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2bd9f-138">**Nombre de tipo de puerto**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-138">**Port Type Name**</span></span>|<span data-ttu-id="2bd9f-139">Tipo de **SOAPReceivePortType**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-139">Type **SOAPReceivePortType**.</span></span>|  
    |<span data-ttu-id="2bd9f-140">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-140">**Communication Pattern**</span></span>|<span data-ttu-id="2bd9f-141">Seleccione **unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-141">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="2bd9f-142">**Restricciones de acceso**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-142">**Access Restrictions**</span></span>|<span data-ttu-id="2bd9f-143">Seleccione **público: sin límite**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-143">Select **Public - no limit**.</span></span>|  
  
5.  <span data-ttu-id="2bd9f-144">En el **enlace de puerto** página, haga clic en **siguiente** para aceptar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-144">On the **Port Binding** page, click **Next** to accept the default values.</span></span>  
  
6.  <span data-ttu-id="2bd9f-145">En el **completar el Asistente para puertos** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-145">On the **Completing the Port Wizard** page, click **Finish**.</span></span>  
  
7.  <span data-ttu-id="2bd9f-146">Arrastre el **puerto** forma del cuadro de herramientas hasta la superficie de puerto en el lado derecho de la vista Diseño y coloque la forma para que alinea horizontalmente con el **DoorbellSend** forma.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-146">Drag the **Port** shape from the Toolbox to the Port Surface on the right side of the Design view surface, and drop the shape so that it aligns horizontally with the **DoorbellSend** shape.</span></span>  
  
8.  <span data-ttu-id="2bd9f-147">Mediante el **Asistente para configuración de puertos** como hizo en los pasos del 2 al 7, cree un puerto de envío adicionales con los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bd9f-147">Using the **Port Configuration Wizard** as you did in steps 2 through 7, create an additional send port using the following parameters:</span></span>  
  
    |<span data-ttu-id="2bd9f-148">Propiedad</span><span class="sxs-lookup"><span data-stu-id="2bd9f-148">Property</span></span>|<span data-ttu-id="2bd9f-149">Parámetro</span><span class="sxs-lookup"><span data-stu-id="2bd9f-149">Parameter</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="2bd9f-150">**Nombre de propiedades de puerto**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-150">**Port Properties Name**</span></span>|<span data-ttu-id="2bd9f-151">MLLPSendPort</span><span class="sxs-lookup"><span data-stu-id="2bd9f-151">MLLPSendPort</span></span>|  
    |<span data-ttu-id="2bd9f-152">**Nombre de tipo de puerto**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-152">**Port Type Name**</span></span>|<span data-ttu-id="2bd9f-153">MLLPSendPortType</span><span class="sxs-lookup"><span data-stu-id="2bd9f-153">MLLPSendPortType</span></span>|  
    |<span data-ttu-id="2bd9f-154">**Patrón de comunicación**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-154">**Communication Pattern**</span></span>|<span data-ttu-id="2bd9f-155">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="2bd9f-155">One-Way</span></span>|  
    |<span data-ttu-id="2bd9f-156">**Restricciones de acceso**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-156">**Access Restrictions**</span></span>|<span data-ttu-id="2bd9f-157">Público: sin límite</span><span class="sxs-lookup"><span data-stu-id="2bd9f-157">Public - no limit</span></span>|  
    |<span data-ttu-id="2bd9f-158">**Enlace de puerto**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-158">**Port Binding**</span></span>|<span data-ttu-id="2bd9f-159">Especificar más tarde</span><span class="sxs-lookup"><span data-stu-id="2bd9f-159">Specify Later</span></span>|  
    |<span data-ttu-id="2bd9f-160">**Dirección de puerto de comunicación**</span><span class="sxs-lookup"><span data-stu-id="2bd9f-160">**Port direction of communication**</span></span>|<span data-ttu-id="2bd9f-161">Siempre enviaré los mensajes en este puerto.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-161">I'll always be sending messages on this port.</span></span>|  
  
9. <span data-ttu-id="2bd9f-162">En el **Vista orquestación** ventana, con el **tipos**, **tipos de puertos**, y **SOAPReceivePortType** nodos expandidos, expanda  **Operation_1**y, a continuación, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-162">In the **Orchestration View** window, with the **Types**, **Ports Types**, and **SOAPReceivePortType** nodes expanded, expand **Operation_1**, and then click **Request**.</span></span>  
  
10. <span data-ttu-id="2bd9f-163">En el **propiedades** ventana, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7_Project.Doorbell** .</span><span class="sxs-lookup"><span data-stu-id="2bd9f-163">In the **Properties** window, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7_Project.Doorbell**.</span></span>  
  
11. <span data-ttu-id="2bd9f-164">En el **Vista orquestación** ventana, expanda **MLLPSendPortType**, expanda **Operation_1**y, a continuación, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-164">In the **Orchestration View** window, expand **MLLPSendPortType**, expand **Operation_1**, and then click **Request**.</span></span>  
  
12. <span data-ttu-id="2bd9f-165">En el **propiedades** ventana, en la lista desplegable para **tipo de mensaje**, expanda **tipos de mensaje de varias partes**y, a continuación, haga clic en **BTAHL7_ Project.DoorbellFinalMessageType**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-165">In the **Properties** window, in the drop-down list for **Message Type**, expand **Multi-part Message Types**, and then click **BTAHL7_Project.DoorbellFinalMessageType**.</span></span>  
  
13. <span data-ttu-id="2bd9f-166">En el **nombre** , escriba **respuesta**, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-166">In the **Name** field, type **Response**, then press **Enter**.</span></span>  
  
14. <span data-ttu-id="2bd9f-167">En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellReceive** forma acción.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-167">On the orchestration Design view surface, click the **DoorbellReceive** action shape.</span></span>  
  
15. <span data-ttu-id="2bd9f-168">En el **propiedades** ventana, en la lista desplegable para **mensaje**, seleccione **DoorbellInputMessage**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-168">In the **Properties** window, in the drop-down list for **Message**, select **DoorbellInputMessage**.</span></span>  
  
16. <span data-ttu-id="2bd9f-169">En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellSend** forma.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-169">On the orchestration Design view surface, click the **DoorbellSend** shape.</span></span>  
  
17. <span data-ttu-id="2bd9f-170">En el **propiedades** ventana, en la lista desplegable para **mensaje**, seleccione **DoorbellFinalMessage**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-170">In the **Properties** window, in the drop-down list for **Message**, select **DoorbellFinalMessage**.</span></span>  
  
18. <span data-ttu-id="2bd9f-171">Haga clic en el indicador verde en el **SOAPReceivePort** y arrástrelo hasta el indicador verde el **DoorbellReceive** recibir de forma que se va a conectar el **SOAPReceivePort** a la  **DoorbellReceive** forma recepción.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-171">Click the green handle in the **SOAPReceivePort** and drag it to the green handle on the **DoorbellReceive** receive shape to connect the **SOAPReceivePort** to the **DoorbellReceive** receive shape.</span></span>  
  
19. <span data-ttu-id="2bd9f-172">Haga clic en el indicador verde en el **DoorbellSend** forma y arrástrelo hasta el indicador verde el **MLLPSendPort** puerto para conectar el **DoorbellSend** forma de envío para el **MLLPSendPort** puerto.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-172">Click the green handle in the **DoorbellSend** shape and drag it to the green handle on the **MLLPSendPort** port to connect the **DoorbellSend** send shape to the **MLLPSendPort** port.</span></span>  
  
20. <span data-ttu-id="2bd9f-173">Haga clic en el **el Explorador de soluciones** ficha en la Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-173">Click the **Solution Explorer** tab under the Orchestration View.</span></span>  
  
21. <span data-ttu-id="2bd9f-174">En el Explorador de soluciones, haga clic en **BTAHL7V22Common**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-174">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Build**.</span></span> <span data-ttu-id="2bd9f-175">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-175">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bd9f-176">Si no aparece ningún mensaje de correcto, solucionar problemas de la solución.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-176">If no success message appears, troubleshoot the solution.</span></span>  
  
22. <span data-ttu-id="2bd9f-177">Haga clic en **BTAHL7 proyecto**y haga clic en **implementar** para implementar el proyecto de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="2bd9f-177">Right-click **BTAHL7 Project**, and click **Deploy** to deploy the BTAHL7 project.</span></span>  
  
 <span data-ttu-id="2bd9f-178">Continúe con [paso 14: publicar la orquestación como servicio Web](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="2bd9f-178">Proceed to [Step 14: Publish the Orchestration as a Web Service](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd9f-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bd9f-179">See Also</span></span>  
 [<span data-ttu-id="2bd9f-180">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="2bd9f-180">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)