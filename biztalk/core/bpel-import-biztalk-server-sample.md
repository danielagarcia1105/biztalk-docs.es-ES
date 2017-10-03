---
title: Importar BPEL (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- examples, orchestrations
- examples, BPEL Import Wizard
- BPEL, examples
- BPEL Import Wizard, examples
- BPEL Import Wizard, orchestrations
ms.assetid: 3fc70608-ccd9-4249-b238-c09fc6551db1
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b76cead956ade8d16c5cbd26c55f94eabe15e1fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bpel-import-biztalk-server-sample"></a><span data-ttu-id="52c80-102">Importar BPEL (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="52c80-102">BPEL Import (BizTalk Server Sample)</span></span>
<span data-ttu-id="52c80-103">El ejemplo de Importar BPEL muestra cómo crear una orquestación a partir de una descripción de proceso de Lenguaje de ejecución de procesos empresariales (BPEL) y sus artefactos relacionados.</span><span class="sxs-lookup"><span data-stu-id="52c80-103">The BPEL Import sample demonstrates how to create an orchestration from a Business Process Execution Language (BPEL) process description and its related artifacts.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="52c80-104">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="52c80-104">What This Sample Does</span></span>  
 <span data-ttu-id="52c80-105">Wide World Importers es una empresa de transporte que ofrece servicios de envío automatizados a distribuidores.</span><span class="sxs-lookup"><span data-stu-id="52c80-105">Wide World Importers is a shipping company that provides automated shipping services to retailers.</span></span> <span data-ttu-id="52c80-106">En concreto, Wide World Importers permite a los distribuidores llevar a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="52c80-106">Specifically, Wide World Importers enables retailers to:</span></span>  
  
-   <span data-ttu-id="52c80-107">Solicitar envíos de pedidos</span><span class="sxs-lookup"><span data-stu-id="52c80-107">Request order shipments</span></span>  
  
-   <span data-ttu-id="52c80-108">Llevar a cabo un seguimiento de los envíos</span><span class="sxs-lookup"><span data-stu-id="52c80-108">Track shipments</span></span>  
  
-   <span data-ttu-id="52c80-109">Confirmar los envíos</span><span class="sxs-lookup"><span data-stu-id="52c80-109">Confirm shipments</span></span>  
  
-   <span data-ttu-id="52c80-110">Confirmar la facturación y los pagos de los envíos</span><span class="sxs-lookup"><span data-stu-id="52c80-110">Confirm invoicing and payment for shipments</span></span>  
  
 <span data-ttu-id="52c80-111">Mientras que la disponibilidad de estos servicios puede representarse mediante el uso de un documento de Lenguaje de descripción de servicios web (WSDL), un documento BPEL describe el modo en el que se espera que las compañías de productos llamen a los servicios y cómo deben esperar la respuesta de Wide World Importers.</span><span class="sxs-lookup"><span data-stu-id="52c80-111">While the availability of these services can be represented by using a Web Services Description Language (WSDL) document, a BPEL document describes the typical way in which the product companies are expected to call the services and how to expect responses from Wide World Importers.</span></span>  
  
 <span data-ttu-id="52c80-112">Cuando Northwind Traders contrata los servicios de Wide World Importers para que lleve a cabo su envío, se les entrega un archivo BPEL y algunos artefactos relacionados que describen la interacción.</span><span class="sxs-lookup"><span data-stu-id="52c80-112">When Northwind Traders hires Wide World Importers to handle their shipping, they are provided a BPEL file and some related artifacts that describe the entire interaction.</span></span> <span data-ttu-id="52c80-113">Mediante el archivo BPEL, Northwind Traders crea una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (BPELShipping) para procesar automáticamente los pedidos a través de Wide World Importers.</span><span class="sxs-lookup"><span data-stu-id="52c80-113">Using the BPEL file, Northwind Traders creates a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application (BPELShipping) to automatically process orders through Wide World Importers.</span></span>  
  
 <span data-ttu-id="52c80-114">Este ejemplo realiza un recorrido por este escenario en el que la aplicación BPELShipping:</span><span class="sxs-lookup"><span data-stu-id="52c80-114">This sample walks you through this scenario in which the BPELShipping application:</span></span>  
  
1.  <span data-ttu-id="52c80-115">Recibe un pedido del sistema de pedidos de cliente de Northwind Traders.</span><span class="sxs-lookup"><span data-stu-id="52c80-115">Receives an order from the Northwind Traders customer order system.</span></span>  
  
2.  <span data-ttu-id="52c80-116">Envía una solicitud de envío a Wide World Importers y solicita una confirmación.</span><span class="sxs-lookup"><span data-stu-id="52c80-116">Sends a shipping request to Wide World Importers and requests confirmation.</span></span>  
  
3.  <span data-ttu-id="52c80-117">Recibe una confirmación de la solicitud de envío de Wide World Importers.</span><span class="sxs-lookup"><span data-stu-id="52c80-117">Receives shipment request confirmation from Wide World Importers.</span></span>  
  
4.  <span data-ttu-id="52c80-118">Recibe una notificación de recogida de Wide World Importers.</span><span class="sxs-lookup"><span data-stu-id="52c80-118">Receives pickup notification from Wide World Importers.</span></span>  
  
5.  <span data-ttu-id="52c80-119">Recibe mensajes de estado del envío hasta el momento en el que el cliente ha recibido el envío.</span><span class="sxs-lookup"><span data-stu-id="52c80-119">Receives shipment status messages up to and including when the shipment has been received by the customer.</span></span>  
  
6.  <span data-ttu-id="52c80-120">Recibe una factura de Wide World Importers.</span><span class="sxs-lookup"><span data-stu-id="52c80-120">Receives an invoice from Wide World Importers.</span></span>  
  
7.  <span data-ttu-id="52c80-121">Responde a Wide World Importers con una confirmación de recepción de factura.</span><span class="sxs-lookup"><span data-stu-id="52c80-121">Responds to Wide World Importers with an invoice acknowledgment.</span></span>  
  
8.  <span data-ttu-id="52c80-122">Recibe una confirmación de pago de Wide World Importers.</span><span class="sxs-lookup"><span data-stu-id="52c80-122">Receives a payment confirmation from Wide World Importers.</span></span>  
  
9. <span data-ttu-id="52c80-123">Envía una confirmación de envío final al sistema de pedidos.</span><span class="sxs-lookup"><span data-stu-id="52c80-123">Sends a final shipping confirmation to the ordering system.</span></span>  
  
 <span data-ttu-id="52c80-124">Se utiliza una aplicación independiente de BizTalk (ShipperProcess) para simular la empresa Wide World Importers para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="52c80-124">A separate BizTalk application (ShipperProcess) is used to simulate Wide World Importers for this sample.</span></span> <span data-ttu-id="52c80-125">La aplicación BPELShipping se comunica con ShipperProcess mediante el transporte de archivos, que utiliza ubicaciones del sistema de archivos comunes para la comunicación.</span><span class="sxs-lookup"><span data-stu-id="52c80-125">The BPELShipping application communicates with ShipperProcess by using the FILE transport, which uses common file system locations for the communication.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="52c80-126">Cómo se ha diseñado este ejemplo y por qué</span><span class="sxs-lookup"><span data-stu-id="52c80-126">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="52c80-127">BPEL para servicios web es un lenguaje basado en XML que describe el proceso empresarial de forma que puedan compartirlo varias empresas distintas que desean hacer negocios entre sí mediante los servicios web.</span><span class="sxs-lookup"><span data-stu-id="52c80-127">BPEL for Web services is an XML-based language to describe the business process so that it can be easily shared across different companies who want to do business with each other using Web services.</span></span> <span data-ttu-id="52c80-128">BPEL describe cómo controlar el proceso empresarial en el nivel de protocolo empresarial, pero no describe el proceso interno de una empresa, como los pasos que la empresa realiza para procesar un pedido después de recibirlo de un socio comercial.</span><span class="sxs-lookup"><span data-stu-id="52c80-128">BPEL describes how to handle the business process at the business protocol level, but it does not describe the internal process in a company, such as the steps a company would take to process a purchase order after receiving it from a partner.</span></span> <span data-ttu-id="52c80-129">Este ejemplo está diseñado para mostrar cómo importar BPEL y los archivos WSDL correspondientes, convertirlos a una orquestación y, después, iniciar el proceso empresarial con el socio comercial.</span><span class="sxs-lookup"><span data-stu-id="52c80-129">This sample is designed to show you how to import BPEL and corresponding WSDL files, convert them into an orchestration, and then start to run the business process with the partner.</span></span>  
  
 <span data-ttu-id="52c80-130">A continuación, se muestra el procedimiento paso a paso que indica cómo importar los archivos BPEL y WSDL y convertirlos a una orquestación para que interactúe con una aplicación de BizTalk ya generada (ShipperProcess).</span><span class="sxs-lookup"><span data-stu-id="52c80-130">The following is the step-by-step procedure showing how to import the BPEL and WSDL files and convert them into an orchestration to interact with a prebuilt BizTalk application (ShipperProcess).</span></span> <span data-ttu-id="52c80-131">Si completa los pasos siguientes, no necesitará llevar a cabo los pasos descritos en "Generar e inicializar la aplicación BPELShipping".</span><span class="sxs-lookup"><span data-stu-id="52c80-131">If you complete the following steps, you do not need to perform the steps described in "To build and initialize the BPELShipping application".</span></span>  
  
#### <a name="to-import-from-bpel-and-build-a-working-solution"></a><span data-ttu-id="52c80-132">Para importar desde BPEL y generar una solución de trabajo</span><span class="sxs-lookup"><span data-stu-id="52c80-132">To import from BPEL and build a working solution</span></span>  
  
1.  <span data-ttu-id="52c80-133">En Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="52c80-133">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52c80-134">Antes de completar este procedimiento, deberá configurar la aplicación ShipperProcess para crear los proyectos de esquema y los procesos complementarios.</span><span class="sxs-lookup"><span data-stu-id="52c80-134">Before completing this procedure, you must set up the ShipperProcess application to create the supporting processes and schema projects.</span></span>  
  
2.  <span data-ttu-id="52c80-135">En el **nuevo proyecto** cuadro de diálogo, en el panel tipos de proyecto, seleccione **BizTalk (proyectos)**.</span><span class="sxs-lookup"><span data-stu-id="52c80-135">In the **New Project** dialog box, in the Project Types pane, select **BizTalk (Projects)**.</span></span> <span data-ttu-id="52c80-136">En el panel Plantillas, seleccione **proyecto de importación BPEL de servidor BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="52c80-136">In the Templates pane, select **BizTalk (Server) BPEL Import Project**.</span></span>  
  
3.  <span data-ttu-id="52c80-137">En el **nombre** cuadro, escriba **BPELShipping**.</span><span class="sxs-lookup"><span data-stu-id="52c80-137">In the **Name** box, enter **BPELShipping**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52c80-138">Si utiliza un nombre distinto, pueden producirse problemas con el paso de enlace final.</span><span class="sxs-lookup"><span data-stu-id="52c80-138">If you use a different name, you may experience problems with the final binding step.</span></span>  
  
4.  <span data-ttu-id="52c80-139">Seleccione una ubicación para el proyecto y, a continuación, haga clic en **Aceptar** para iniciar el Asistente para importar BPEL.</span><span class="sxs-lookup"><span data-stu-id="52c80-139">Select a location for the project, and then click **OK** to start the BPEL Import Wizard.</span></span>  
  
5.  <span data-ttu-id="52c80-140">En el **bienvenida** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52c80-140">On the **Welcome** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="52c80-141">En el **seleccione BPEL, WSDL y XSD archivos** página, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-141">On the **Select BPEL, WSDL, and XSD Files** page, click **Browse**.</span></span>  
  
7.  <span data-ttu-id="52c80-142">Seleccione todos los archivos de la \< *ruta de ejemplos*> \Orchestrations\BPELImport\BPELSource carpeta, haga clic en **abiertos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52c80-142">Select all the files from the \<*Samples Path*>\Orchestrations\BPELImport\BPELSource folder, click **Open**, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52c80-143">En este paso, seleccione los archivos BPEL y WSDL para describir el proceso empresarial y los archivos XSD para representar los esquemas de documentos empresariales.</span><span class="sxs-lookup"><span data-stu-id="52c80-143">In this step, you select the BPEL and WSDL files to describe the business process and the XSD files to represent the business document schemas.</span></span>  
  
8.  <span data-ttu-id="52c80-144">En el **seleccionar archivos WSDL para los WebServices invocados** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-144">On the **Select WSDL Files for Invoked WebServices** page, click **Finish**.</span></span>  
  
9. <span data-ttu-id="52c80-145">Cuando el Asistente para importar BPEL informe de que la importación se ha realizado correctamente, cierre el asistente.</span><span class="sxs-lookup"><span data-stu-id="52c80-145">After the BPEL Import Wizard reports a successful import, close the wizard.</span></span> <span data-ttu-id="52c80-146">Ya se ha creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="52c80-146">The project is now created.</span></span>  
  
10. <span data-ttu-id="52c80-147">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a la ubicación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="52c80-147">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the project location.</span></span>  
  
11. <span data-ttu-id="52c80-148">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="52c80-148">Run the following command:</span></span>  
  
     <span data-ttu-id="52c80-149">**sn – k BPELShipping.snk**</span><span class="sxs-lookup"><span data-stu-id="52c80-149">**sn –k BPELShipping.snk**</span></span>  
  
12. <span data-ttu-id="52c80-150">En el Explorador de soluciones, haga clic en el **BPELShipping** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="52c80-150">In Solution Explorer, right-click the **BPELShipping** project, and then click **Properties**.</span></span>  
  
13. <span data-ttu-id="52c80-151">En **comunes\ensamblado**, seleccione el archivo de clave de ensamblado **BPELShipping.snk** creado en el paso 11 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-151">Under **Common Properties\Assembly**, select the assembly key file **BPELShipping.snk** created in step 11, and then click **OK**.</span></span>  
  
14. <span data-ttu-id="52c80-152">En el Explorador de soluciones, seleccione todos los archivos .xsd y elimínelos.</span><span class="sxs-lookup"><span data-stu-id="52c80-152">In Solution Explorer, select all the .xsd files and delete them.</span></span>  
  
15. <span data-ttu-id="52c80-153">En el Explorador de soluciones, seleccione **Agregar referencia**y en el **proyectos** , haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-153">In Solution Explorer, select **Add Reference**, and on the **Projects** tab, click **Browse**.</span></span>  
  
16. <span data-ttu-id="52c80-154">Seleccione **ShippingSchemas.dll** desde la ubicación \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development y, a continuación, haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-154">Select **ShippingSchemas.dll** from the location \<*Samples Path*>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52c80-155">La sección "Generar e iniciar la aplicación ShipperProcess" contiene instrucciones acerca de cómo generarla.</span><span class="sxs-lookup"><span data-stu-id="52c80-155">The section "To build and initialize the ShipperProcess application" has instructions on how to build this.</span></span>  
  
17. <span data-ttu-id="52c80-156">En el Explorador de soluciones, haga doble clic en **OrderShippingProcess.bpel.odx**.</span><span class="sxs-lookup"><span data-stu-id="52c80-156">In Solution Explorer, double-click **OrderShippingProcess.bpel.odx**.</span></span>  
  
18. <span data-ttu-id="52c80-157">En el **vista** menú, seleccione **otras ventanas/Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="52c80-157">On the **View** menu, select **Other Windows/Orchestration View**.</span></span>  
  
19. <span data-ttu-id="52c80-158">En la ventana Vista orquestación, haga clic en **propiedades de orquestación** y, a continuación, haga clic en **ventana propiedades**.</span><span class="sxs-lookup"><span data-stu-id="52c80-158">In the Orchestration View window, right-click **Orchestration Properties** and then click **Properties Window**.</span></span>  
  
20. <span data-ttu-id="52c80-159">En la ventana Propiedades, establezca la **Exportable a orquestación** propiedad **False**.</span><span class="sxs-lookup"><span data-stu-id="52c80-159">In the Properties window, set the **Orchestration Exportable** property to **False**.</span></span>  
  
21. <span data-ttu-id="52c80-160">En el Explorador de soluciones, haga doble clic en **OrderShipping.wsdl.odx**.</span><span class="sxs-lookup"><span data-stu-id="52c80-160">In Solution Explorer, double-click **OrderShipping.wsdl.odx**.</span></span>  
  
22. <span data-ttu-id="52c80-161">En la ventana Vista orquestación, expanda **tipos de mensajes de tipos/Multipart**.</span><span class="sxs-lookup"><span data-stu-id="52c80-161">In the Orchestration View window, expand **Types/Multipart Message Types**.</span></span>  
  
23. <span data-ttu-id="52c80-162">Expanda **InvoiceAckMessageType** y, a continuación, haga clic en **InvoiceAckMessagePart**.</span><span class="sxs-lookup"><span data-stu-id="52c80-162">Expand **InvoiceAckMessageType** and then click **InvoiceAckMessagePart**.</span></span>  
  
24. <span data-ttu-id="52c80-163">En la ventana Propiedades, expanda el **tipo** campo y, a continuación, seleccione **esquemas/seleccionar del ensamblado mencionado**.</span><span class="sxs-lookup"><span data-stu-id="52c80-163">In the Properties window, expand the **Type** field, and select **Schemas/Select from referenced Assembly**.</span></span>  
  
25. <span data-ttu-id="52c80-164">En el **Seleccionar tipo de artefacto** cuadro de diálogo, haga clic en **ShippingSchemas**, seleccione la **Imported_InvoiceAckMessage** escriba y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-164">In the **Select Artifact Type** dialog box, click **ShippingSchemas**, select the **Imported_InvoiceAckMessage** type, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52c80-165">En los pasos del 23 al 25, reemplaza el tipo de mensaje de los servicios que participan en el proceso de BPEL con los tipos de mensajes correspondientes descritos en ShippingSchemas.</span><span class="sxs-lookup"><span data-stu-id="52c80-165">In steps 23 through 25, you replace the message type of the services that participate in the BPEL process to the corresponding message types described in the ShippingSchemas.</span></span>  
  
26. <span data-ttu-id="52c80-166">Repita los pasos del 23 al 25 para cada tipo de mensaje mediante los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="52c80-166">Repeat steps 23 through 25 for each message type using the following values.</span></span>  
  
    |<span data-ttu-id="52c80-167">Parte de mensaje</span><span class="sxs-lookup"><span data-stu-id="52c80-167">Message part</span></span>|<span data-ttu-id="52c80-168">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="52c80-168">Message type</span></span>|  
    |------------------|------------------|  
    |<span data-ttu-id="52c80-169">InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-169">InvoiceMessagePart</span></span>|<span data-ttu-id="52c80-170">ShippingSchemas.Imported_InvoiceMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-170">ShippingSchemas.Imported_InvoiceMessage</span></span>|  
    |<span data-ttu-id="52c80-171">OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-171">OrderAckMessagePart</span></span>|<span data-ttu-id="52c80-172">ShippingSchemas.Imported_OrderAckMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-172">ShippingSchemas.Imported_OrderAckMessage</span></span>|  
    |<span data-ttu-id="52c80-173">OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-173">OrderMessagePart</span></span>|<span data-ttu-id="52c80-174">ShippingSchemas.Imported_OrderMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-174">ShippingSchemas.Imported_OrderMessage</span></span>|  
    |<span data-ttu-id="52c80-175">PaymentConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-175">PaymentConfirmationMessagePart</span></span>|<span data-ttu-id="52c80-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span></span>|  
    |<span data-ttu-id="52c80-177">PickupNotificationMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-177">PickupNotificationMessagePart</span></span>|<span data-ttu-id="52c80-178">ShippingSchemas.Imported_PickupNotificationMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-178">ShippingSchemas.Imported_PickupNotificationMessage</span></span>|  
    |<span data-ttu-id="52c80-179">ShipConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-179">ShipConfirmationMessagePart</span></span>|<span data-ttu-id="52c80-180">ShippingSchemas.Imported_ShipConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-180">ShippingSchemas.Imported_ShipConfirmationMessage</span></span>|  
    |<span data-ttu-id="52c80-181">ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="52c80-181">ShippingHistoryPart</span></span>|<span data-ttu-id="52c80-182">ShippingSchemas.Imported_ShippingHistory</span><span class="sxs-lookup"><span data-stu-id="52c80-182">ShippingSchemas.Imported_ShippingHistory</span></span>|  
    |<span data-ttu-id="52c80-183">ShipRequestAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-183">ShipRequestAckMessagePart</span></span>|<span data-ttu-id="52c80-184">ShippingSchemas.Imported_ShipRequestAckMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-184">ShippingSchemas.Imported_ShipRequestAckMessage</span></span>|  
    |<span data-ttu-id="52c80-185">ShipRequestMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-185">ShipRequestMessagePart</span></span>|<span data-ttu-id="52c80-186">ShippingSchemas.Imported_ShipRequestMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-186">ShippingSchemas.Imported_ShipRequestMessage</span></span>|  
    |<span data-ttu-id="52c80-187">ShipStatusMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-187">ShipStatusMessagePart</span></span>|<span data-ttu-id="52c80-188">ShippingSchemas.Imported_ShipStatusMessage</span><span class="sxs-lookup"><span data-stu-id="52c80-188">ShippingSchemas.Imported_ShipStatusMessage</span></span>|  
  
27. <span data-ttu-id="52c80-189">En el Explorador de soluciones, haga clic en el **BPELShipping** , seleccione **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="52c80-189">In Solution Explorer, right-click the **BPELShipping** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
28. <span data-ttu-id="52c80-190">Seleccione todos los archivos .btm en la ubicación \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping.</span><span class="sxs-lookup"><span data-stu-id="52c80-190">Select all the .btm files from the location \<*Samples Path*>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping.</span></span>  
  
29. <span data-ttu-id="52c80-191">En la ventana Vista orquestación, busque el **asignación de mensajes** forma con el nombre MessageAssignment_1 en ConstructMessage1 y elimínela.</span><span class="sxs-lookup"><span data-stu-id="52c80-191">In the Orchestration View window, locate the **Message Assignment** shape named MessageAssignment_1 in ConstructMessage1 and delete it.</span></span>  
  
30. <span data-ttu-id="52c80-192">En el cuadro de herramientas, arrastre un **transformar** forma en la forma ConstructMessage1.</span><span class="sxs-lookup"><span data-stu-id="52c80-192">From the Toolbox, drag a **Transform** shape into the ConstructMessage1 shape.</span></span>  
  
31. <span data-ttu-id="52c80-193">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) y abra el **configuración de transformación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="52c80-193">In the Properties window, click the ellipsis button (**…**) and open the **Transform Configuration** dialog box.</span></span>  
  
32. <span data-ttu-id="52c80-194">Seleccione **mapa existente**.</span><span class="sxs-lookup"><span data-stu-id="52c80-194">Select **Existing Map**.</span></span>  
  
33. <span data-ttu-id="52c80-195">Seleccione el nombre de asignación completo **BPELShipping.Order2ShipRequest**.</span><span class="sxs-lookup"><span data-stu-id="52c80-195">Select the fully qualified map name as **BPELShipping.Order2ShipRequest**.</span></span>  
  
34. <span data-ttu-id="52c80-196">Seleccione el origen como **orden. OrderMessagePart**.</span><span class="sxs-lookup"><span data-stu-id="52c80-196">Select the source as **order.OrderMessagePart**.</span></span>  
  
35. <span data-ttu-id="52c80-197">Seleccione el destino como **ship_request. ShipRequestMessagePart** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-197">Select the destination as **ship_request.ShipRequestMessagePart** and click **OK**.</span></span>  
  
36. <span data-ttu-id="52c80-198">Repita los pasos del 29 al 35 para cada uno de los **asignación de mensajes** formas y reemplácelas con **transformar** formas según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="52c80-198">Repeat steps 29 through 35 for each of the **Message Assignment** shapes and replace them with **Transform** shapes according to the following table.</span></span>  
  
    |<span data-ttu-id="52c80-199">Forma para reemplazar</span><span class="sxs-lookup"><span data-stu-id="52c80-199">Shape to replace</span></span>|<span data-ttu-id="52c80-200">Asignación para utilizarla</span><span class="sxs-lookup"><span data-stu-id="52c80-200">Map to use</span></span>|<span data-ttu-id="52c80-201">Documento de origen</span><span class="sxs-lookup"><span data-stu-id="52c80-201">Source document</span></span>|<span data-ttu-id="52c80-202">Documento de destino</span><span class="sxs-lookup"><span data-stu-id="52c80-202">Destination document</span></span>|  
    |----------------------|----------------|---------------------|--------------------------|  
    |<span data-ttu-id="52c80-203">MessageAssignment_2</span><span class="sxs-lookup"><span data-stu-id="52c80-203">MessageAssignment_2</span></span>|<span data-ttu-id="52c80-204">BPELShipping.Order2OrderAck</span><span class="sxs-lookup"><span data-stu-id="52c80-204">BPELShipping.Order2OrderAck</span></span>|<span data-ttu-id="52c80-205">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-205">order.OrderMessagePart</span></span>|<span data-ttu-id="52c80-206">order_ack.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-206">order_ack.OrderAckMessagePart</span></span>|  
    |<span data-ttu-id="52c80-207">MessageAssignment_3</span><span class="sxs-lookup"><span data-stu-id="52c80-207">MessageAssignment_3</span></span>|<span data-ttu-id="52c80-208">BPELShipping.Order2OrderNAck</span><span class="sxs-lookup"><span data-stu-id="52c80-208">BPELShipping.Order2OrderNAck</span></span>|<span data-ttu-id="52c80-209">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-209">order.OrderMessagePart</span></span>|<span data-ttu-id="52c80-210">order_ack.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-210">order_ack.OrderAckMessagePart</span></span>|  
    |<span data-ttu-id="52c80-211">MessageAssignment_4</span><span class="sxs-lookup"><span data-stu-id="52c80-211">MessageAssignment_4</span></span>|<span data-ttu-id="52c80-212">BPELShipping.Order2ShipHistory</span><span class="sxs-lookup"><span data-stu-id="52c80-212">BPELShipping.Order2ShipHistory</span></span>|<span data-ttu-id="52c80-213">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-213">order.OrderMessagePart</span></span>|<span data-ttu-id="52c80-214">ship_history.ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="52c80-214">ship_history.ShippingHistoryPart</span></span>|  
    |<span data-ttu-id="52c80-215">MessageAssignment_5</span><span class="sxs-lookup"><span data-stu-id="52c80-215">MessageAssignment_5</span></span>|<span data-ttu-id="52c80-216">BPELShipping.ShipHistory2Completed</span><span class="sxs-lookup"><span data-stu-id="52c80-216">BPELShipping.ShipHistory2Completed</span></span>|<span data-ttu-id="52c80-217">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-217">order.OrderMessagePart</span></span>|<span data-ttu-id="52c80-218">ship_history.ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="52c80-218">ship_history.ShippingHistoryPart</span></span>|  
    |<span data-ttu-id="52c80-219">MessageAssignment_6</span><span class="sxs-lookup"><span data-stu-id="52c80-219">MessageAssignment_6</span></span>|<span data-ttu-id="52c80-220">BPELShipping.Invoice2Ack</span><span class="sxs-lookup"><span data-stu-id="52c80-220">BPELShipping.Invoice2Ack</span></span>|<span data-ttu-id="52c80-221">invoice.InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-221">invoice.InvoiceMessagePart</span></span>|<span data-ttu-id="52c80-222">invoice_ack.InvoiceAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-222">invoice_ack.InvoiceAckMessagePart</span></span>|  
    |<span data-ttu-id="52c80-223">MessageAssignment_7</span><span class="sxs-lookup"><span data-stu-id="52c80-223">MessageAssignment_7</span></span>|<span data-ttu-id="52c80-224">BPELShipping.Order2FinalConfirmation</span><span class="sxs-lookup"><span data-stu-id="52c80-224">BPELShipping.Order2FinalConfirmation</span></span>|<span data-ttu-id="52c80-225">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-225">order.OrderMessagePart</span></span>|<span data-ttu-id="52c80-226">order_shipped.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="52c80-226">order_shipped.OrderAckMessagePart</span></span>|  
  
37. <span data-ttu-id="52c80-227">Guarde la orquestación.</span><span class="sxs-lookup"><span data-stu-id="52c80-227">Save the orchestration.</span></span>  
  
38. <span data-ttu-id="52c80-228">Haga doble clic en **Rule_1** en el **decidir** forma **Decision_1**.</span><span class="sxs-lookup"><span data-stu-id="52c80-228">Double-click **Rule_1** in the **Decide** shape **Decision_1**.</span></span>  
  
39. <span data-ttu-id="52c80-229">En el Editor de expresiones de BizTalk, reemplace</span><span class="sxs-lookup"><span data-stu-id="52c80-229">In BizTalk Expression Editor, replace</span></span>  
  
     <span data-ttu-id="52c80-230">ship_request_ack(BPELShipping.Ship_Acknowledged) == true</span><span class="sxs-lookup"><span data-stu-id="52c80-230">ship_request_ack(BPELShipping.Ship_Acknowledged) == true</span></span>  
  
     <span data-ttu-id="52c80-231">con</span><span class="sxs-lookup"><span data-stu-id="52c80-231">with</span></span>  
  
     <span data-ttu-id="52c80-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true</span><span class="sxs-lookup"><span data-stu-id="52c80-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true</span></span>  
  
40. <span data-ttu-id="52c80-233">Haga doble clic en el **bucle** forma denominada **Loop_1**.</span><span class="sxs-lookup"><span data-stu-id="52c80-233">Double-click the **Loop** shape named **Loop_1**.</span></span>  
  
41. <span data-ttu-id="52c80-234">En el Editor de expresiones de BizTalk, reemplace</span><span class="sxs-lookup"><span data-stu-id="52c80-234">In BizTalk Expression Editor, replace</span></span>  
  
     <span data-ttu-id="52c80-235">ship_history(BPELShipping.Ship_Completed) == true</span><span class="sxs-lookup"><span data-stu-id="52c80-235">ship_history(BPELShipping.Ship_Completed) == true</span></span>  
  
     <span data-ttu-id="52c80-236">con</span><span class="sxs-lookup"><span data-stu-id="52c80-236">with</span></span>  
  
     <span data-ttu-id="52c80-237">ship_history(ShippingSchemas.Ship_Completed) == true</span><span class="sxs-lookup"><span data-stu-id="52c80-237">ship_history(ShippingSchemas.Ship_Completed) == true</span></span>  
  
42. <span data-ttu-id="52c80-238">Haga doble clic en **Rule_2** en el **decidir** forma **Decision_2**.</span><span class="sxs-lookup"><span data-stu-id="52c80-238">Double-click **Rule_2** in the **Decide** shape **Decision_2**.</span></span>  
  
43. <span data-ttu-id="52c80-239">En el Editor de expresiones de BizTalk, reemplace</span><span class="sxs-lookup"><span data-stu-id="52c80-239">In BizTalk Expression Editor, replace</span></span>  
  
     <span data-ttu-id="52c80-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="52c80-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span></span>  
  
     <span data-ttu-id="52c80-241">con</span><span class="sxs-lookup"><span data-stu-id="52c80-241">with</span></span>  
  
     <span data-ttu-id="52c80-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="52c80-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span></span>  
  
44. <span data-ttu-id="52c80-243">En la Vista orquestación, expanda **tipos/tipos de correlación** y haga clic en **_OrderCorrelationSet_Type\_**.</span><span class="sxs-lookup"><span data-stu-id="52c80-243">In the Orchestration View, expand **Types/Correlation Types** and click **_OrderCorrelationSet_Type\_**.</span></span>  
  
45. <span data-ttu-id="52c80-244">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) en **propiedades de correlación**.</span><span class="sxs-lookup"><span data-stu-id="52c80-244">In the Properties window, click the ellipsis button (**…**) on **Correlation Properties**.</span></span>  
  
46. <span data-ttu-id="52c80-245">En las propiedades de correlación en el panel, haga clic en **BPELShipping.OrderID**y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-245">In the Properties to correlate on pane, click **BPELShipping.OrderID**, and then click **Remove**.</span></span>  
  
47. <span data-ttu-id="52c80-246">En el panel de propiedades disponibles, expanda **esquemas de envío**, seleccione **Id. de pedido**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-246">In the Available Properties pane, expand **Shipping Schemas**, select **Order ID**, and then click **Add**.</span></span>  
  
48. <span data-ttu-id="52c80-247">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52c80-247">Click **OK**.</span></span>  
  
49. <span data-ttu-id="52c80-248">Guarde todos los archivos y genere la solución.</span><span class="sxs-lookup"><span data-stu-id="52c80-248">Save all the files and build the solution.</span></span>  
  
50. <span data-ttu-id="52c80-249">Implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="52c80-249">Deploy the solution.</span></span>  
  
51. <span data-ttu-id="52c80-250">Vaya a la ubicación \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\BPELShipping y haga doble clic en **BindAndStartOnly.bat** para enlazar e iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="52c80-250">Browse to the location \<*Samples Path*>\Orchestrations\BPELImport\Solution\BPELShipping and double-click **BindAndStartOnly.bat** to bind and start the orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="52c80-251">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="52c80-251">Where to Find This Sample</span></span>  
 <span data-ttu-id="52c80-252">*\<Ejemplos de ruta de acceso >*\Orchestrations\BPELImport</span><span class="sxs-lookup"><span data-stu-id="52c80-252">*\<Samples Path>*\Orchestrations\BPELImport</span></span>  
  
 <span data-ttu-id="52c80-253">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="52c80-253">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="52c80-254">Archivos</span><span class="sxs-lookup"><span data-stu-id="52c80-254">File(s)</span></span>|<span data-ttu-id="52c80-255">Description</span><span class="sxs-lookup"><span data-stu-id="52c80-255">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52c80-256">BPELSource\InvoiceAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-256">BPELSource\InvoiceAckMessage.xsd</span></span>|<span data-ttu-id="52c80-257">Esquema de confirmación de factura.</span><span class="sxs-lookup"><span data-stu-id="52c80-257">Invoice acknowledgment schema.</span></span>|  
|<span data-ttu-id="52c80-258">BPELSource\InvoiceMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-258">BPELSource\InvoiceMessage.xsd</span></span>|<span data-ttu-id="52c80-259">Esquema de factura.</span><span class="sxs-lookup"><span data-stu-id="52c80-259">Invoice schema.</span></span>|  
|<span data-ttu-id="52c80-260">BPELSource\OrderAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-260">BPELSource\OrderAckMessage.xsd</span></span>|<span data-ttu-id="52c80-261">Esquema de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="52c80-261">Order acknowledgment schema.</span></span>|  
|<span data-ttu-id="52c80-262">BPELSource\OrderHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-262">BPELSource\OrderHeader.xsd</span></span>|<span data-ttu-id="52c80-263">Esquema de encabezado de pedido.</span><span class="sxs-lookup"><span data-stu-id="52c80-263">Order header schema.</span></span>|  
|<span data-ttu-id="52c80-264">BPELSource\OrderMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-264">BPELSource\OrderMessage.xsd</span></span>|<span data-ttu-id="52c80-265">Esquema de mensajes de pedido.</span><span class="sxs-lookup"><span data-stu-id="52c80-265">Order message schema.</span></span>|  
|<span data-ttu-id="52c80-266">BPELSource\OrderShipping.wsdl</span><span class="sxs-lookup"><span data-stu-id="52c80-266">BPELSource\OrderShipping.wsdl</span></span>|<span data-ttu-id="52c80-267">Archivo WSDL al que hace referencia BPEL.</span><span class="sxs-lookup"><span data-stu-id="52c80-267">WSDL file referred to by BPEL.</span></span>|  
|<span data-ttu-id="52c80-268">BPELSource\OrderShippingProcess.bpel</span><span class="sxs-lookup"><span data-stu-id="52c80-268">BPELSource\OrderShippingProcess.bpel</span></span>|<span data-ttu-id="52c80-269">Flujo de proceso BPEL.</span><span class="sxs-lookup"><span data-stu-id="52c80-269">BPEL process flow.</span></span>|  
|<span data-ttu-id="52c80-270">BPELSource\PaymentConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-270">BPELSource\PaymentConfirmationMessage.xsd</span></span>|<span data-ttu-id="52c80-271">Mensaje de confirmación de pago.</span><span class="sxs-lookup"><span data-stu-id="52c80-271">Payment confirmation message.</span></span>|  
|<span data-ttu-id="52c80-272">BPELSource\PickupNotificationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-272">BPELSource\PickupNotificationMessage.xsd</span></span>|<span data-ttu-id="52c80-273">Mensaje de notificación de recogida.</span><span class="sxs-lookup"><span data-stu-id="52c80-273">Pickup notification message.</span></span>|  
|<span data-ttu-id="52c80-274">BPELSource\ShipConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-274">BPELSource\ShipConfirmationMessage.xsd</span></span>|<span data-ttu-id="52c80-275">Mensaje de confirmación de envío.</span><span class="sxs-lookup"><span data-stu-id="52c80-275">Shipment confirmation message.</span></span>|  
|<span data-ttu-id="52c80-276">BPELSource\ShippingHistory.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-276">BPELSource\ShippingHistory.xsd</span></span>|<span data-ttu-id="52c80-277">Documento de historial de envío.</span><span class="sxs-lookup"><span data-stu-id="52c80-277">Shipping history document.</span></span>|  
|<span data-ttu-id="52c80-278">BPELSource\ShipRequestAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-278">BPELSource\ShipRequestAckMessage.xsd</span></span>|<span data-ttu-id="52c80-279">Enviar confirmación de solicitud.</span><span class="sxs-lookup"><span data-stu-id="52c80-279">Ship request acknowledgment.</span></span>|  
|<span data-ttu-id="52c80-280">BPELSource\ShipRequestMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-280">BPELSource\ShipRequestMessage.xsd</span></span>|<span data-ttu-id="52c80-281">Enviar mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="52c80-281">Ship request message.</span></span>|  
|<span data-ttu-id="52c80-282">BPELSource\ShipStatusMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="52c80-282">BPELSource\ShipStatusMessage.xsd</span></span>|<span data-ttu-id="52c80-283">Enviar mensaje de estado.</span><span class="sxs-lookup"><span data-stu-id="52c80-283">Ship status message.</span></span>|  
|<span data-ttu-id="52c80-284">Solution\bindings\BPELBindings.xml</span><span class="sxs-lookup"><span data-stu-id="52c80-284">Solution\bindings\BPELBindings.xml</span></span>|<span data-ttu-id="52c80-285">Archivo de enlace que especifica los enlaces de puertos de la orquestación BPELShipping.</span><span class="sxs-lookup"><span data-stu-id="52c80-285">Binding file specifying port bindings for the BPELShipping orchestration.</span></span>|  
|<span data-ttu-id="52c80-286">Solution\bindings\ShipperBindings.xml</span><span class="sxs-lookup"><span data-stu-id="52c80-286">Solution\bindings\ShipperBindings.xml</span></span>|<span data-ttu-id="52c80-287">Archivo de enlace que especifica los enlaces de puertos de la orquestación ShipperProcess.</span><span class="sxs-lookup"><span data-stu-id="52c80-287">Binding file specifying port bindings for the ShipperProcess orchestration.</span></span>|  
|<span data-ttu-id="52c80-288">Solution\BPELShipping\BindAndStartOnly.bat</span><span class="sxs-lookup"><span data-stu-id="52c80-288">Solution\BPELShipping\BindAndStartOnly.bat</span></span>|<span data-ttu-id="52c80-289">Archivo por lotes que se utiliza para enlazar e iniciar la orquestación BPELImport después de que se haya generado manualmente e implementado.</span><span class="sxs-lookup"><span data-stu-id="52c80-289">Batch file to use for binding and starting the BPELImport orchestration after it has been built manually and deployed.</span></span>|  
|<span data-ttu-id="52c80-290">Solution\BPELShipping\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="52c80-290">Solution\BPELShipping\cleanup.bat</span></span>|<span data-ttu-id="52c80-291">Archivo por lotes que se utiliza para quitar el proceso BPELShipping.</span><span class="sxs-lookup"><span data-stu-id="52c80-291">Batch file to use to remove the BPELShipping process.</span></span>|  
|<span data-ttu-id="52c80-292">Solution\BPELShipping\Setup.bat</span><span class="sxs-lookup"><span data-stu-id="52c80-292">Solution\BPELShipping\Setup.bat</span></span>|<span data-ttu-id="52c80-293">Archivo por lotes que se utiliza para instalar e iniciar el ejemplo BPELShipping proporcionado.</span><span class="sxs-lookup"><span data-stu-id="52c80-293">Batch file to use to install and start the provided BPELShipping sample.</span></span>|  
|<span data-ttu-id="52c80-294">Solution\BPELShipping\BPELShipping.sln</span><span class="sxs-lookup"><span data-stu-id="52c80-294">Solution\BPELShipping\BPELShipping.sln</span></span>|<span data-ttu-id="52c80-295">El ejemplo BPELShipping ya generado.</span><span class="sxs-lookup"><span data-stu-id="52c80-295">The prebuilt BPELShipping sample.</span></span>|  
<span data-ttu-id="52c80-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span><span class="sxs-lookup"><span data-stu-id="52c80-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span></span>|<span data-ttu-id="52c80-297">Factura para facturar la asignación de confirmación.</span><span class="sxs-lookup"><span data-stu-id="52c80-297">Invoice to invoice acknowledgment map.</span></span>|  
|<span data-ttu-id="52c80-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span><span class="sxs-lookup"><span data-stu-id="52c80-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span></span>|<span data-ttu-id="52c80-299">Asignación para convertir el Mensaje de pedido a la confirmación de envío final.</span><span class="sxs-lookup"><span data-stu-id="52c80-299">Map to convert from Order message to final shipment confirmation.</span></span>|  
|<span data-ttu-id="52c80-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span><span class="sxs-lookup"><span data-stu-id="52c80-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span></span>|<span data-ttu-id="52c80-301">Asignación para convertir el Mensaje de pedido a la confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="52c80-301">Map to convert from Order message to order acknowledgment.</span></span>|  
|<span data-ttu-id="52c80-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span><span class="sxs-lookup"><span data-stu-id="52c80-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span></span>|<span data-ttu-id="52c80-303">Asignación para convertir de Mensaje de pedido a confirmación negativa de pedido.</span><span class="sxs-lookup"><span data-stu-id="52c80-303">Map to convert from Order message to order negative acknowledgment.</span></span>|  
|<span data-ttu-id="52c80-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span><span class="sxs-lookup"><span data-stu-id="52c80-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span></span>|<span data-ttu-id="52c80-305">Asignación para convertir de Mensaje de pedido a Documento de historial de envío.</span><span class="sxs-lookup"><span data-stu-id="52c80-305">Map to convert from Order message to Shipping history document.</span></span>|  
|<span data-ttu-id="52c80-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span><span class="sxs-lookup"><span data-stu-id="52c80-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span></span>|<span data-ttu-id="52c80-307">Asignación para convertir el Mensaje de pedido a la Solicitud de envío.</span><span class="sxs-lookup"><span data-stu-id="52c80-307">Map to convert from Order message to order Shipping request.</span></span>|  
|<span data-ttu-id="52c80-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span><span class="sxs-lookup"><span data-stu-id="52c80-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span></span>|<span data-ttu-id="52c80-309">Asignación para definir el Historial de envío como completado.</span><span class="sxs-lookup"><span data-stu-id="52c80-309">Map to set the Shipping history to completed.</span></span>|  
|<span data-ttu-id="52c80-310">Solution\ShipperProcess\setup.bat</span><span class="sxs-lookup"><span data-stu-id="52c80-310">Solution\ShipperProcess\setup.bat</span></span>|<span data-ttu-id="52c80-311">El archivo por lotes que se va a generar, implementar, enlazar e iniciar la orquestación de la aplicación auxiliar ShipperProcess y sus puertos.</span><span class="sxs-lookup"><span data-stu-id="52c80-311">Batch file to build, deploy, bind, and start the ShipperProcess helper orchestration and its ports.</span></span>|  
|<span data-ttu-id="52c80-312">Solution\ShipperProcess\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="52c80-312">Solution\ShipperProcess\cleanup.bat</span></span>|<span data-ttu-id="52c80-313">Archivo por lotes para detener, dar de baja y anular la implementación de la orquestación de la aplicación auxiliar ShipperProcess y sus puertos.</span><span class="sxs-lookup"><span data-stu-id="52c80-313">Batch file to stop, unenlist, and undeploy the ShipperProcess helper orchestration and its ports.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="52c80-314">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="52c80-314">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="52c80-315">El primer paso consiste en generar e iniciar la aplicación ShipperProcess utilizada para simular Wide World Importers.</span><span class="sxs-lookup"><span data-stu-id="52c80-315">The first step is to build and initialize the ShipperProcess application used to simulate Wide World Importers.</span></span>  
  
#### <a name="to-build-and-initialize-the-shipperprocess-application"></a><span data-ttu-id="52c80-316">Para generar e iniciar la aplicación ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="52c80-316">To build and initialize the ShipperProcess application</span></span>  
  
1.  <span data-ttu-id="52c80-317">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="52c80-317">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="52c80-318">Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="52c80-318">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="52c80-319">*\<Ejemplos de ruta de acceso >*\Orchestrations\BPELImport\Solution\ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="52c80-319">*\<Samples Path>*\Orchestrations\BPELImport\Solution\ShipperProcess</span></span>  
  
3.  <span data-ttu-id="52c80-320">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="52c80-320">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="52c80-321">Genera el proyecto ShippingSchemas, que contiene los esquemas utilizados en ShipperProcess y en el proceso de BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-321">Builds the ShippingSchemas project, which contains the schemas used in the ShipperProcess and the BPELShipping process</span></span>  
  
    -   <span data-ttu-id="52c80-322">Genera el ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="52c80-322">Builds the ShipperProcess</span></span>  
  
    -   <span data-ttu-id="52c80-323">Implementa los proyectos ShippingSchemas y ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="52c80-323">Deploys the ShippingSchemas and ShipperProcess projects</span></span>  
  
    -   <span data-ttu-id="52c80-324">Crea y enlaza los puertos de envío y recepción utilizados por ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="52c80-324">Creates and binds the send and receive ports used by ShipperProcess</span></span>  
  
    -   <span data-ttu-id="52c80-325">Se inician los puertos utilizados por ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="52c80-325">Starts the ports used by ShipperProcess</span></span>  
  
    -   <span data-ttu-id="52c80-326">Da de alta e inicia la orquestación ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="52c80-326">Enlists and starts the ShipperProcess orchestration</span></span>  
  
 <span data-ttu-id="52c80-327">Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="52c80-327">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="52c80-328">Puede aparecer una o más de las advertencias siguientes; puede pasarlas por alto.</span><span class="sxs-lookup"><span data-stu-id="52c80-328">One or more of the following warnings may be displayed; you can ignore these.</span></span>  
  
```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  
  
> [!NOTE]
>  <span data-ttu-id="52c80-329">No será necesario llevar a cabo los pasos siguientes si se han completado los que se describen en "Para importar desde BPEL y generar una solución de trabajo".</span><span class="sxs-lookup"><span data-stu-id="52c80-329">You do not need to perform the following steps if you completed the steps described in "To import from BPEL and build a working solution."</span></span>  
  
#### <a name="to-build-and-initialize-the-bpelshipping-application"></a><span data-ttu-id="52c80-330">Para generar e iniciar la aplicación BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-330">To build and initialize the BPELShipping application</span></span>  
  
1.  > [!WARNING]
    >  <span data-ttu-id="52c80-331">Antes de ejecutar estos pasos, debe completar los pasos anteriores titulados "Para generar e iniciar la aplicación ShipperProcess".</span><span class="sxs-lookup"><span data-stu-id="52c80-331">Before executing these steps, you must complete the steps above entitled “To build and initialize the ShipperProcess application”.</span></span>  
  
     <span data-ttu-id="52c80-332">Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="52c80-332">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="52c80-333">*\<Ejemplos de ruta de acceso >*\Orchestrations\BPELImport\Solution\BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-333">*\<Samples Path>*\Orchestrations\BPELImport\Solution\BPELShipping</span></span>  
  
2.  <span data-ttu-id="52c80-334">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="52c80-334">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="52c80-335">Genera el proyecto BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-335">Builds the BPELShipping project</span></span>  
  
    -   <span data-ttu-id="52c80-336">Implementa el proyecto BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-336">Deploys the BPELShipping project</span></span>  
  
    -   <span data-ttu-id="52c80-337">Crea y enlaza los puertos de envío y recepción utilizados por el proceso BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-337">Creates and binds the send and receive ports used by the BPELShipping process</span></span>  
  
    -   <span data-ttu-id="52c80-338">Inicia los puertos utilizados por el proceso BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-338">Starts the ports used by the BPELShipping process</span></span>  
  
    -   <span data-ttu-id="52c80-339">Da de alta e inicia la orquestación BPELShipping</span><span class="sxs-lookup"><span data-stu-id="52c80-339">Enlists and starts the BPELShipping orchestration</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="52c80-340">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="52c80-340">Running This Sample</span></span>  
  
#### <a name="to-run-the-bpel-import-sample"></a><span data-ttu-id="52c80-341">Para ejecutar el ejemplo de Importación BPEL</span><span class="sxs-lookup"><span data-stu-id="52c80-341">To run the BPEL Import sample</span></span>  
  
1.  <span data-ttu-id="52c80-342">Copia la **Order.xml** de archivos desde el  *\<ruta de ejemplos >*\Orchestrations\BPELImport\Solution en la carpeta a la \< *ruta de ejemplos >*\ Carpeta Orchestrations\BPELImport\Solution\Ports\ReceiveOrder.</span><span class="sxs-lookup"><span data-stu-id="52c80-342">Copy the **Order.xml** file from the *\<Samples Path>*\Orchestrations\BPELImport\Solution folder to the \<*Samples Path>*\Orchestrations\BPELImport\Solution\Ports\ReceiveOrder folder.</span></span>  
  
2.  <span data-ttu-id="52c80-343">El BPELShipping orquestación recoge este archivo como un pedido en el sistema de procesamiento de pedidos de cliente, se ejecuta en el proceso de envío, y crea un archivo cada uno de los \< *ruta de ejemplos*> \Orchestrations\ Carpeta BPELImport\Solution\Ports\SendOrder y \< *ruta de ejemplos*> \Orchestrations\BPELImport\Solution\Ports\FinalConfirmation carpeta.</span><span class="sxs-lookup"><span data-stu-id="52c80-343">The BPELShipping orchestration picks up this file as an order from the customer order processing system, runs through the shipping process, and produces one file each in the \<*Samples Path*>\Orchestrations\BPELImport\Solution\Ports\SendOrder folder and the \<*Samples Path*>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation folder.</span></span> <span data-ttu-id="52c80-344">El formato del nombre de estos archivos es \< *MessageID*> .xml, donde  *\<MessageID >* es el GUID generado para identificar de forma exclusiva el mensaje.</span><span class="sxs-lookup"><span data-stu-id="52c80-344">The format of the name of these files is \<*MessageID*>.xml, where *\<MessageID>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="52c80-345">Desinstalar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="52c80-345">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-bpel-import-sample"></a><span data-ttu-id="52c80-346">Para desinstalar el ejemplo Importación BPEL</span><span class="sxs-lookup"><span data-stu-id="52c80-346">To uninstall the BPEL Import sample</span></span>  
  
1.  <span data-ttu-id="52c80-347">En un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a \< *ruta de ejemplos*> \Orchestrations\BPELImport\BPELShipping.</span><span class="sxs-lookup"><span data-stu-id="52c80-347">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*>\Orchestrations\BPELImport\BPELShipping.</span></span>  
  
2.  <span data-ttu-id="52c80-348">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="52c80-348">Run Cleanup.bat.</span></span>  
  
3.  <span data-ttu-id="52c80-349">Vaya a \< *ejemplos de ruta de acceso*> \Orchestrations\BPELImport\ShipperProcess.</span><span class="sxs-lookup"><span data-stu-id="52c80-349">Browse to \<*Samples Path*>\Orchestrations\BPELImport\ShipperProcess.</span></span>  
  
4.  <span data-ttu-id="52c80-350">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="52c80-350">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c80-351">Vea también</span><span class="sxs-lookup"><span data-stu-id="52c80-351">See Also</span></span>  
 [<span data-ttu-id="52c80-352">Orquestaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="52c80-352">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)