---
title: 'Paso 2: Configurar un unidireccionales de WCF-Custom puerto de recepción | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way receive port, configuring
- migration
ms.assetid: e2a8f074-64d5-4e6c-84d0-318fb606c0ba
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d3320e7a2e6b948309087f2b33def57db9db0c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990301"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="20f87-102">Paso 2: Configurar un unidireccionales de WCF-Custom puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="20f87-102">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>
<span data-ttu-id="20f87-103">![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="20f87-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="20f87-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="20f87-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="20f87-105">**Objetivo:** en este paso, configurará un puerto personalizado de WCF para recibir un IDOC de archivo sin formato de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="20f87-105">**Objective:** In this step, you configure a WCF-Custom port to receive a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="20f87-106">Después de configurar el puerto, configura BizTalk puerto de recepción de la aplicación para que use el WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="20f87-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20f87-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="20f87-107">Prerequisites</span></span>  
 <span data-ttu-id="20f87-108">Debe ha creado e implementado el proyecto de BizTalk vPrev para recibir los IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="20f87-108">You must have built and deployed your vPrev BizTalk project to receive IDOCs from an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="20f87-109">Para configurar el puerto de recepción de un unidireccionales de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="20f87-109">To configure a WCF-Custom one-way receive port</span></span>  
  
1. <span data-ttu-id="20f87-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="20f87-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="20f87-111">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="20f87-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="20f87-112">Expanda la aplicación bajo el cual desea crear el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="20f87-112">Expand the application under which you want create the receive port.</span></span>  
  
4. <span data-ttu-id="20f87-113">Haga clic en **puertos de recepción**, apunte a **New**y haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="20f87-113">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port**.</span></span>  
  
5. <span data-ttu-id="20f87-114">En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="20f87-114">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6. <span data-ttu-id="20f87-115">En el **ubicaciones de recepción** , haga clic **New**.</span><span class="sxs-lookup"><span data-stu-id="20f87-115">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="20f87-116">El **propiedades de ubicación de recepción** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="20f87-116">The **Receive Location Properties** dialog box appears.</span></span>  
  
7. <span data-ttu-id="20f87-117">En el **propiedades de ubicación de recepción** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20f87-117">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="20f87-118">Especifique un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="20f87-118">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="20f87-119">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="20f87-119">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="20f87-120">En el **propiedades de transporte WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20f87-120">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="20f87-121">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para recibir mensajes desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="20f87-121">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to receive messages from the SAP system.</span></span> <span data-ttu-id="20f87-122">El URI de conexión para recibir mensajes desde el sistema SAP debe estar en el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="20f87-122">The connection URI to receive messages from the SAP system must be in the following format:</span></span>  
  
      ```  
      sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
      ```  
  
       <span data-ttu-id="20f87-123">En la siguiente ilustración se muestra el cuadro de diálogo de propiedades de puerto con el URI especificado:</span><span class="sxs-lookup"><span data-stu-id="20f87-123">The following figure shows the port properties dialog box with the URI specified:</span></span>  
  
       <span data-ttu-id="20f87-124">![URI de conexión para recibir mensajes de SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span><span class="sxs-lookup"><span data-stu-id="20f87-124">![Connection URI to receive messages from SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span></span>  
  
       <span data-ttu-id="20f87-125">Para obtener más información sobre el URI de conexión, consulte [crear una conexión al sistema SAP](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="20f87-125">For more information about the connection URI, see [Create a  connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
   2. <span data-ttu-id="20f87-126">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="20f87-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="20f87-127">Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="20f87-127">Make sure you specify the following binding properties for the receive port.</span></span>  
  
      |<span data-ttu-id="20f87-128">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="20f87-128">Binding property</span></span>|<span data-ttu-id="20f87-129">Establecer valor en</span><span class="sxs-lookup"><span data-stu-id="20f87-129">Set value to</span></span>|  
      |----------------------|------------------|  
      |<span data-ttu-id="20f87-130">FlatFileSegmentIndicator</span><span class="sxs-lookup"><span data-stu-id="20f87-130">flatFileSegmentIndicator</span></span>|<span data-ttu-id="20f87-131">**SegmentType**.</span><span class="sxs-lookup"><span data-stu-id="20f87-131">**SegmentType**.</span></span> <span data-ttu-id="20f87-132">Esto indica que los archivos planos deben contener el tipo de segmento para cada segmento en el IDOC.</span><span class="sxs-lookup"><span data-stu-id="20f87-132">This indicates that the flat files should contain the segment type for each segment in the IDOC.</span></span>|  
      |<span data-ttu-id="20f87-133">PadReceivedIdocWithSpaces</span><span class="sxs-lookup"><span data-stu-id="20f87-133">padReceivedIdocWithSpaces</span></span>|<span data-ttu-id="20f87-134">**True**.</span><span class="sxs-lookup"><span data-stu-id="20f87-134">**True**.</span></span> <span data-ttu-id="20f87-135">Especifica si cada línea en el IDOC se rellena con espacios en la longitud correcta.</span><span class="sxs-lookup"><span data-stu-id="20f87-135">Specifies whether each line in the IDOC is padded with spaces to the correct length.</span></span>|  
      |<span data-ttu-id="20f87-136">ReceiveIDocFormat</span><span class="sxs-lookup"><span data-stu-id="20f87-136">receiveIDocFormat</span></span>|<span data-ttu-id="20f87-137">**Cadena**.</span><span class="sxs-lookup"><span data-stu-id="20f87-137">**String**.</span></span> <span data-ttu-id="20f87-138">Esto especifica que el mensaje IDOC debe representarse como un campo de cadena único.</span><span class="sxs-lookup"><span data-stu-id="20f87-138">This specifies that the IDOC message should be represented as a single string field.</span></span>|  
  
       <span data-ttu-id="20f87-139">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="20f87-139">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   3. <span data-ttu-id="20f87-140">Haga clic en el **otros** pestaña y especificar las credenciales para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="20f87-140">Click the **Others** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
   4. <span data-ttu-id="20f87-141">Haga clic en el **mensajes** ficha y en el **cuerpo del mensaje entrante de BizTalk** sección, elija el **ruta** opción.</span><span class="sxs-lookup"><span data-stu-id="20f87-141">Click the **Messages** tab, and in the **Inbound BizTalk message body** section, choose the **Path** option.</span></span>  
  
   5. <span data-ttu-id="20f87-142">En el **expresión de ruta de cuerpo** texto, especifique la consulta XPath para extraer el IDOC de archivo sin formato del mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="20f87-142">In the **Body path expression** text box, specify the XPath query to extract the flat-file IDOC from the XML message.</span></span> <span data-ttu-id="20f87-143">Al hacerlo, el puerto de recepción extrae los datos del IDOC y recorta la etiqueta XML que forma parte de la **ReceiveIdoc** operación basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20f87-143">By doing so, the receive port extracts the data from the IDOC and trims the XML tag that is part of the **ReceiveIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="20f87-144">Para obtener más información acerca del esquema de mensaje para el **ReceiveIdoc** operación, vea [esquemas de mensaje para operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="20f87-144">For more information about the message schema for the **ReceiveIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
       <span data-ttu-id="20f87-145">![Consulta XPath para extraer el plano&#45;IDOC de archivo](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span><span class="sxs-lookup"><span data-stu-id="20f87-145">![XPath query to extract the flat&#45;file IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span></span>  
  
       <span data-ttu-id="20f87-146">Debe especificar la consulta XPath siguiente:</span><span class="sxs-lookup"><span data-stu-id="20f87-146">You must specify the following XPath query:</span></span>  
  
      ```  
      /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
      ```  
  
   6. <span data-ttu-id="20f87-147">Desde el **codificación de nodo** lista desplegable, seleccione **cadena**.</span><span class="sxs-lookup"><span data-stu-id="20f87-147">From the **Node encoding** drop-down list, select **String**.</span></span>  
  
   7. <span data-ttu-id="20f87-148">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20f87-148">Click **Apply**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="20f87-149">En el cuadro de diálogo Propiedades de ubicación de recepción desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="20f87-149">In the Receive Location Properties dialog box, from the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="20f87-150">Desde el **canalización de recepción** lista desplegable, seleccione **ConvertToXML**.</span><span class="sxs-lookup"><span data-stu-id="20f87-150">From the **Receive pipeline** drop-down list, select **ConvertToXML**.</span></span> <span data-ttu-id="20f87-151">Esta canalización de desensamblador de archivo sin formato ya es una parte del proyecto de BizTalk vPrev para convertir un IDOC de archivo sin formato en un IDOC de XML.</span><span class="sxs-lookup"><span data-stu-id="20f87-151">This flat-file disassembler pipeline is already a part of the vPrev BizTalk project to convert a flat-file IDOC to an XML IDOC.</span></span>  
  
11. <span data-ttu-id="20f87-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20f87-152">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="20f87-153">Para configurar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="20f87-153">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="20f87-154">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda la aplicación de BizTalk donde se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="20f87-154">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="20f87-155">Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="20f87-155">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="20f87-156">En el panel izquierdo, haga clic en el que se va a configurar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="20f87-156">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="20f87-157">En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="20f87-157">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="20f87-158">En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="20f87-158">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="20f87-159">Seleccione el WCF-Custom recibir el puerto que creó anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="20f87-159">Select the WCF-Custom receive port you created earlier in this topic.</span></span>  
  
   2. <span data-ttu-id="20f87-160">Seleccione un puerto de archivos donde recibirá el IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="20f87-160">Select a file port where you will receive the flat-file IDOC.</span></span>  
  
   3. <span data-ttu-id="20f87-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20f87-161">Click **OK**.</span></span>  
  
      <span data-ttu-id="20f87-162">Para obtener más información acerca de cómo configurar una aplicación, consulte [ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360).</span><span class="sxs-lookup"><span data-stu-id="20f87-162">For more information about configuring an application, see [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="20f87-163">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="20f87-163">Next Steps</span></span>  
 <span data-ttu-id="20f87-164">Ahora ha completado la migración de su proyecto de BizTalk vPrev para un proyecto de BizTalk que recibe los IDOC desde un sistema SAP mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20f87-164">You have now completed migration of your vPrev BizTalk project to a BizTalk project that receives IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="20f87-165">Ahora debe probar la aplicación de BizTalk migrada al recibir un IDOC de archivo sin formato, como se describe en [paso 3: probar la aplicación migrados](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).</span><span class="sxs-lookup"><span data-stu-id="20f87-165">You must now test the migrated BizTalk application by receiving a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f87-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="20f87-166">See Also</span></span>  
 [<span data-ttu-id="20f87-167">Tutorial 4: Migración de un proyecto de BizTalk IDOC de SAP de recepción</span><span class="sxs-lookup"><span data-stu-id="20f87-167">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)