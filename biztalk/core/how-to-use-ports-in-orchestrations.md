---
title: Cómo usar puertos en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, adding ports
- Port Configuration Wizard [Orchestration Designer], configuring ports
- ports, operations
- operations, adding to ports
- configuring, ports
- ports, deleting
- deleting, ports
- ports, Port Configuration Wizard [Orchestration Designer]
- ports, adding to orchestrations
- ports, configuring
ms.assetid: da8665cd-ccde-4949-b5f5-01f9f8be5ce8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3edef29376d8724d93192040ee88951ced245ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257916"
---
# <a name="how-to-use-ports-in-orchestrations"></a><span data-ttu-id="5e101-102">Cómo usar puertos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="5e101-102">How to Use Ports in Orchestrations</span></span>
<span data-ttu-id="5e101-103">Los puertos se agregan a una orquestación de forma muy similar a como se agregan controles a un formulario Web Forms o Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5e101-103">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="5e101-104">También se pueden agregar puertos mediante la ventana Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="5e101-104">You can also add ports by using the Orchestration View window.</span></span>  
  
### <a name="to-add-a-new-port"></a><span data-ttu-id="5e101-105">Para agregar un puerto nuevo</span><span class="sxs-lookup"><span data-stu-id="5e101-105">To add a new port</span></span>  
  
-   <span data-ttu-id="5e101-106">Haga clic en un **superficie para el puerto** o un **vínculo de función**y, a continuación, haga clic en **nuevo puerto**.</span><span class="sxs-lookup"><span data-stu-id="5e101-106">Right-click a **Port Surface** or a **Role Link**, and then click **New Port**.</span></span>  
  
     <span data-ttu-id="5e101-107">: "O":</span><span class="sxs-lookup"><span data-stu-id="5e101-107">—Or—</span></span>  
  
     <span data-ttu-id="5e101-108">En la ventana Vista orquestación, haga clic en **puertos** y, a continuación, haga clic en **nuevo puerto**.</span><span class="sxs-lookup"><span data-stu-id="5e101-108">In the Orchestration View window, right-click **Ports** and then click **New Port**.</span></span>  
  
     <span data-ttu-id="5e101-109">Si un puerto aún no está completamente configurado, aparece una sugerencia de diseño sobre él.</span><span class="sxs-lookup"><span data-stu-id="5e101-109">A DesignTip appears on ports that are not yet fully configured.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="5e101-110">También puede arrastrar puertos hasta un **vínculo de función**.</span><span class="sxs-lookup"><span data-stu-id="5e101-110">You can also drag ports into a **Role Link**.</span></span>  
  
### <a name="to-add-and-configure-a-new-port"></a><span data-ttu-id="5e101-111">Para agregar y configurar un nuevo puerto</span><span class="sxs-lookup"><span data-stu-id="5e101-111">To add and configure a new port</span></span>  
  
1.  <span data-ttu-id="5e101-112">Desde el **orquestaciones de BizTalk** ficha del cuadro de herramientas, arrastre el **puerto** dar forma a un **superficie para el puerto** o un **vínculo de función**.</span><span class="sxs-lookup"><span data-stu-id="5e101-112">From the **BizTalk Orchestrations** tab of the Toolbox, drag the **Port** shape onto a **Port Surface** or a **Role Link**.</span></span>  
  
     <span data-ttu-id="5e101-113">: "O":</span><span class="sxs-lookup"><span data-stu-id="5e101-113">—Or—</span></span>  
  
     <span data-ttu-id="5e101-114">Haga clic en un **superficie para el puerto** o un **vínculo de función**y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="5e101-114">Right-click a **Port Surface** or a **Role Link**, and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="5e101-115">: "O":</span><span class="sxs-lookup"><span data-stu-id="5e101-115">—Or—</span></span>  
  
     <span data-ttu-id="5e101-116">En la ventana Vista orquestación, haga clic en **puertos** y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="5e101-116">In the Orchestration View window, right-click **Ports** and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="5e101-117">Aparecerá el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="5e101-117">The Port Configuration Wizard appears.</span></span>  
  
2.  <span data-ttu-id="5e101-118">Siga los pasos del asistente para configurar el puerto.</span><span class="sxs-lookup"><span data-stu-id="5e101-118">Follow the steps in the wizard to configure the port.</span></span> <span data-ttu-id="5e101-119">Para obtener más información, consulte [cómo ejecutar el Asistente para configuración de puerto](../core/how-to-run-the-port-configuration-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5e101-119">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-remove-a-port"></a><span data-ttu-id="5e101-120">Para quitar un puerto</span><span class="sxs-lookup"><span data-stu-id="5e101-120">To remove a port</span></span>  
  
-   <span data-ttu-id="5e101-121">Haga clic en el puerto para quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5e101-121">Right-click the port to remove, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e101-122">Si elimina un puerto después de que se ha conectado a un **enviar** o **recepción** no se eliminará la forma de una orquestación que se ha compilado, las operaciones de puerto en la forma y recibirá errores cuando Intente compilar.</span><span class="sxs-lookup"><span data-stu-id="5e101-122">If you delete a port after it has been connected to a **Send** or **Receive** shape in an orchestration that has been compiled, the port operations on the shape will not be deleted, and you will receive errors when you try to compile.</span></span> <span data-ttu-id="5e101-123">Conecte la forma a otro puerto y vuelva a configurar las operaciones de éste.</span><span class="sxs-lookup"><span data-stu-id="5e101-123">Connect the shape to another port and reconfigure the port operations.</span></span>  
  
### <a name="to-configure-a-port-by-using-the-port-configuration-wizard"></a><span data-ttu-id="5e101-124">Para configurar un puerto empleando el Asistente para la configuración de puertos</span><span class="sxs-lookup"><span data-stu-id="5e101-124">To configure a port by using the Port Configuration Wizard</span></span>  
  
1.  <span data-ttu-id="5e101-125">Haga clic en el puerto para configurar y, a continuación, haga clic en **Configurar puerto**.</span><span class="sxs-lookup"><span data-stu-id="5e101-125">Right-click the port to configure, and then click **Configure Port**.</span></span>  
  
2.  <span data-ttu-id="5e101-126">Siga los pasos del Asistente para configurar el puerto.</span><span class="sxs-lookup"><span data-stu-id="5e101-126">Follow the steps in the Port Configuration Wizard to configure the port.</span></span> <span data-ttu-id="5e101-127">Para obtener más información, consulte [cómo ejecutar el Asistente para configuración de puerto](../core/how-to-run-the-port-configuration-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5e101-127">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-configure-a-port-manually-by-using-the-properties-window"></a><span data-ttu-id="5e101-128">Para configurar un puerto manualmente mediante la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="5e101-128">To configure a port manually by using the Properties window</span></span>  
  
1.  <span data-ttu-id="5e101-129">Seleccione el puerto que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="5e101-129">Select the port to configure.</span></span>  
  
2.  <span data-ttu-id="5e101-130">En la ventana Propiedades, especifique las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="5e101-130">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="5e101-131">Propiedad</span><span class="sxs-lookup"><span data-stu-id="5e101-131">Property</span></span>|<span data-ttu-id="5e101-132">Description</span><span class="sxs-lookup"><span data-stu-id="5e101-132">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="5e101-133">Tipo de puerto</span><span class="sxs-lookup"><span data-stu-id="5e101-133">Port Type</span></span>|<span data-ttu-id="5e101-134">Determina el patrón de comunicación, las operaciones y los tipos de mensaje de varias partes asociados con un puerto.</span><span class="sxs-lookup"><span data-stu-id="5e101-134">Determines the communication pattern, operations, and multi-part message types associated with a port.</span></span>|  
    |<span data-ttu-id="5e101-135">Dirección de comunicación</span><span class="sxs-lookup"><span data-stu-id="5e101-135">Communication Direction</span></span>|<span data-ttu-id="5e101-136">Determina si esta orquestación es la que envía esta comunicación o la que la recibe.</span><span class="sxs-lookup"><span data-stu-id="5e101-136">Determines whether this orchestration is the sender or the receiver for this communication.</span></span>|  
    |<span data-ttu-id="5e101-137">Patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="5e101-137">Communication Pattern</span></span>|<span data-ttu-id="5e101-138">Determina si este puerto se usa para comunicación de solicitud-respuesta o unidireccional.</span><span class="sxs-lookup"><span data-stu-id="5e101-138">Determines if this port is used for request-response or one-way communication.</span></span> <span data-ttu-id="5e101-139">(Esta propiedad está determinada por la **tipo de puerto** propiedad y es de solo lectura.)</span><span class="sxs-lookup"><span data-stu-id="5e101-139">(This property is determined by the **Port Type** property and is read-only.)</span></span>|  
    |<span data-ttu-id="5e101-140">Enlace</span><span class="sxs-lookup"><span data-stu-id="5e101-140">Binding</span></span>|<span data-ttu-id="5e101-141">Determina cómo llega a su destino un mensaje:</span><span class="sxs-lookup"><span data-stu-id="5e101-141">Determines how a message gets to its destination:</span></span><br /><br /> <span data-ttu-id="5e101-142">Directo: la comunicación es con otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="5e101-142">Direct—Communication is with another orchestration.</span></span><br /><br /> <span data-ttu-id="5e101-143">Dinámica: la comunicación es con un punto de conexión que se determina en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5e101-143">Dynamic—Communication is with an endpoint that is determined at run time.</span></span><br /><br /> <span data-ttu-id="5e101-144">Especificar más tarde, la comunicación es con un punto de conexión que se determina por un administrador en el tiempo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5e101-144">Specify later—Communication is with an endpoint that is determined by an administrator at configuration time.</span></span><br /><br /> <span data-ttu-id="5e101-145">Especificar ahora: la comunicación es con un punto de conexión que se conoce en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="5e101-145">Specify now—Communication is with an endpoint that is known at design time.</span></span>|  
    |<span data-ttu-id="5e101-146">Identificador</span><span class="sxs-lookup"><span data-stu-id="5e101-146">Identifier</span></span>|<span data-ttu-id="5e101-147">Nombre usado para este puerto en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="5e101-147">The name used for this port in the orchestration.</span></span>|  
    |<span data-ttu-id="5e101-148">Entrega ordenada</span><span class="sxs-lookup"><span data-stu-id="5e101-148">Ordered Delivery</span></span>|<span data-ttu-id="5e101-149">Para los puertos de recepción, garantiza que los mensajes publicados con un determinado orden en la base de datos de cuadro de mensajes se entreguen a los suscriptores correspondientes en ese mismo orden.</span><span class="sxs-lookup"><span data-stu-id="5e101-149">For receive ports, ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span> <span data-ttu-id="5e101-150">Para obtener más información, consulte [ordenada de mensajes de entrega](../core/ordered-delivery-of-messages.md).</span><span class="sxs-lookup"><span data-stu-id="5e101-150">For more information, see [Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md).</span></span>|  
    |<span data-ttu-id="5e101-151">Notificación de entrega</span><span class="sxs-lookup"><span data-stu-id="5e101-151">Delivery Notification</span></span>|<span data-ttu-id="5e101-152">Para los puertos de envío, determina si se recibe confirmación cuando un mensaje se envía correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e101-152">For send ports, determines whether want to receive an acknowledgment when a message is sent successfully.</span></span> <span data-ttu-id="5e101-153">Para obtener más información, consulte "Notificación de entrega" en [cómo configurar la forma envío](../core/how-to-configure-the-send-shape.md).</span><span class="sxs-lookup"><span data-stu-id="5e101-153">For more information, see "Delivery Notification" in [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span>|  
  
3.  <span data-ttu-id="5e101-154">Dependen de las propiedades restantes para especificar el **enlace** propiedad:</span><span class="sxs-lookup"><span data-stu-id="5e101-154">The remaining properties to specify are determined by the **Binding** property:</span></span>  
  
    -   <span data-ttu-id="5e101-155">Enlace directo: usar al comunicar directamente con otra orquestación.</span><span class="sxs-lookup"><span data-stu-id="5e101-155">Direct binding—Used when communicating directly with another orchestration.</span></span>  
  
        |<span data-ttu-id="5e101-156">Propiedad</span><span class="sxs-lookup"><span data-stu-id="5e101-156">Property</span></span>|<span data-ttu-id="5e101-157">Description</span><span class="sxs-lookup"><span data-stu-id="5e101-157">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="5e101-158">Puerto de orquestación de socio</span><span class="sxs-lookup"><span data-stu-id="5e101-158">Partner Orchestration Port</span></span>|<span data-ttu-id="5e101-159">Determina a qué puerto se enlazarán directamente las orquestaciones de socios.</span><span class="sxs-lookup"><span data-stu-id="5e101-159">Determines to which port the partner orchestrations will be directly bound.</span></span>|  
  
    -   <span data-ttu-id="5e101-160">Enlace dinámico: usar al comunicar con un punto de conexión que se determina en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5e101-160">Dynamic binding—Used when communicating with an endpoint that is determined at run time.</span></span>  
  
        |<span data-ttu-id="5e101-161">Propiedad</span><span class="sxs-lookup"><span data-stu-id="5e101-161">Property</span></span>|<span data-ttu-id="5e101-162">Description</span><span class="sxs-lookup"><span data-stu-id="5e101-162">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="5e101-163">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="5e101-163">Receive Pipeline</span></span>|<span data-ttu-id="5e101-164">Determina qué canalización se usará para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="5e101-164">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="5e101-165">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="5e101-165">Send Pipeline</span></span>|<span data-ttu-id="5e101-166">Determina qué canalización se usará para los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="5e101-166">Determines which pipeline to use for outgoing messages.</span></span>|  
  
    -   <span data-ttu-id="5e101-167">Especificar más tarde: usar al comunicar con un punto de conexión que está configurado por un administrador.</span><span class="sxs-lookup"><span data-stu-id="5e101-167">Specify later—Used when communicating with an endpoint that is configured by an administrator.</span></span>  
  
    -   <span data-ttu-id="5e101-168">Especificar ahora: usar al comunicar con un punto de conexión que se conoce en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="5e101-168">Specify now—Used when communicating with an endpoint that is known at design time.</span></span>  
  
        |<span data-ttu-id="5e101-169">Propiedad</span><span class="sxs-lookup"><span data-stu-id="5e101-169">Property</span></span>|<span data-ttu-id="5e101-170">Description</span><span class="sxs-lookup"><span data-stu-id="5e101-170">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="5e101-171">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="5e101-171">Receive Pipeline</span></span>|<span data-ttu-id="5e101-172">Determina qué canalización se usará para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="5e101-172">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="5e101-173">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="5e101-173">Send Pipeline</span></span>|<span data-ttu-id="5e101-174">Determina qué canalización se usará para los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="5e101-174">Determines which pipeline to use for outgoing messages.</span></span>|  
        |<span data-ttu-id="5e101-175">Transporte</span><span class="sxs-lookup"><span data-stu-id="5e101-175">Transport</span></span>|<span data-ttu-id="5e101-176">Determina qué transporte se usará para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e101-176">Determines which transport to use for sending messages.</span></span>|  
        |<span data-ttu-id="5e101-177">URI</span><span class="sxs-lookup"><span data-stu-id="5e101-177">URI</span></span>|<span data-ttu-id="5e101-178">Determina dónde se envían los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e101-178">Determines where to send messages.</span></span>|  
  
### <a name="to-add-a-port-operation"></a><span data-ttu-id="5e101-179">Para agregar una operación de puerto</span><span class="sxs-lookup"><span data-stu-id="5e101-179">To add a port operation</span></span>  
  
-   <span data-ttu-id="5e101-180">Haga clic en el puerto al que desea agregar una operación y, a continuación, haga clic en **nueva operación**.</span><span class="sxs-lookup"><span data-stu-id="5e101-180">Right-click the port to which you want to add an operation, and then click **New Operation**.</span></span>  
  
### <a name="to-remove-a-port-operation"></a><span data-ttu-id="5e101-181">Para quitar una operación de puerto</span><span class="sxs-lookup"><span data-stu-id="5e101-181">To remove a port operation</span></span>  
  
-   <span data-ttu-id="5e101-182">Haga clic en la operación de puerto para quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5e101-182">Right-click the port operation to remove, and then click **Delete**.</span></span>