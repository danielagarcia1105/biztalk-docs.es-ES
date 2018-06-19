---
title: 'Paso 2: Configurar un unidireccionales de WCF-Custom puerto de recepción | Documentos de Microsoft'
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
ms.openlocfilehash: 6edf75f08bdf6a321188e484eb4f363366f8eb95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218556"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="a59d2-102">Paso 2: Configurar un unidireccionales de WCF-Custom puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="a59d2-102">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>
<span data-ttu-id="a59d2-103">![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="a59d2-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="a59d2-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="a59d2-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="a59d2-105">**Objetivo:** en este paso, configurará un puerto personalizado de WCF para recibir un IDOC de archivo sin formato de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a59d2-105">**Objective:** In this step, you configure a WCF-Custom port to receive a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="a59d2-106">Después de configurar el puerto, configurar BizTalk puerto de recepción de la aplicación para que use WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="a59d2-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a59d2-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a59d2-107">Prerequisites</span></span>  
 <span data-ttu-id="a59d2-108">Debe ha creado e implementado el proyecto de BizTalk vPrev para recibir IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a59d2-108">You must have built and deployed your vPrev BizTalk project to receive IDOCs from an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="a59d2-109">Para configurar el puerto de recepción de un unidireccionales de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="a59d2-109">To configure a WCF-Custom one-way receive port</span></span>  
  
1.  <span data-ttu-id="a59d2-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a59d2-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a59d2-111">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="a59d2-112">Expanda la aplicación en la que desea crear el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a59d2-112">Expand the application under which you want create the receive port.</span></span>  
  
4.  <span data-ttu-id="a59d2-113">Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-113">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="a59d2-114">En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a59d2-114">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="a59d2-115">En el **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-115">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="a59d2-116">El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a59d2-116">The **Receive Location Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="a59d2-117">En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a59d2-117">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="a59d2-118">Especifique un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="a59d2-118">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="a59d2-119">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-119">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="a59d2-120">En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a59d2-120">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="a59d2-121">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para recibir mensajes desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a59d2-121">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to receive messages from the SAP system.</span></span> <span data-ttu-id="a59d2-122">El URI para recibir mensajes desde el sistema SAP de conexión debe estar en el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="a59d2-122">The connection URI to receive messages from the SAP system must be in the following format:</span></span>  
  
        ```  
        sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
        ```  
  
         <span data-ttu-id="a59d2-123">En la siguiente ilustración muestra el cuadro de diálogo de propiedades de puerto con el URI especificado:</span><span class="sxs-lookup"><span data-stu-id="a59d2-123">The following figure shows the port properties dialog box with the URI specified:</span></span>  
  
         <span data-ttu-id="a59d2-124">![URI de conexión para recibir mensajes de SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span><span class="sxs-lookup"><span data-stu-id="a59d2-124">![Connection URI to receive messages from SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span></span>  
  
         <span data-ttu-id="a59d2-125">Para obtener más información sobre el URI de conexión, consulte [crear una conexión con el sistema SAP](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="a59d2-125">For more information about the connection URI, see [Create a  connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
    2.  <span data-ttu-id="a59d2-126">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="a59d2-127">Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a59d2-127">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        |<span data-ttu-id="a59d2-128">Propiedad de enlace</span><span class="sxs-lookup"><span data-stu-id="a59d2-128">Binding property</span></span>|<span data-ttu-id="a59d2-129">Establezca el valor a</span><span class="sxs-lookup"><span data-stu-id="a59d2-129">Set value to</span></span>|  
        |----------------------|------------------|  
        |<span data-ttu-id="a59d2-130">flatFileSegmentIndicator</span><span class="sxs-lookup"><span data-stu-id="a59d2-130">flatFileSegmentIndicator</span></span>|<span data-ttu-id="a59d2-131">**SegmentType**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-131">**SegmentType**.</span></span> <span data-ttu-id="a59d2-132">Esto indica que los archivos planos deben contener el tipo de segmento de cada segmento en el IDOC.</span><span class="sxs-lookup"><span data-stu-id="a59d2-132">This indicates that the flat files should contain the segment type for each segment in the IDOC.</span></span>|  
        |<span data-ttu-id="a59d2-133">padReceivedIdocWithSpaces</span><span class="sxs-lookup"><span data-stu-id="a59d2-133">padReceivedIdocWithSpaces</span></span>|<span data-ttu-id="a59d2-134">**True**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-134">**True**.</span></span> <span data-ttu-id="a59d2-135">Especifica si cada línea en el IDOC se rellena con espacios hasta la longitud correcta.</span><span class="sxs-lookup"><span data-stu-id="a59d2-135">Specifies whether each line in the IDOC is padded with spaces to the correct length.</span></span>|  
        |<span data-ttu-id="a59d2-136">receiveIDocFormat</span><span class="sxs-lookup"><span data-stu-id="a59d2-136">receiveIDocFormat</span></span>|<span data-ttu-id="a59d2-137">**Cadena**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-137">**String**.</span></span> <span data-ttu-id="a59d2-138">Esto especifica que el mensaje IDOC debe representarse como un campo de cadena único.</span><span class="sxs-lookup"><span data-stu-id="a59d2-138">This specifies that the IDOC message should be represented as a single string field.</span></span>|  
  
         <span data-ttu-id="a59d2-139">Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a59d2-139">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    3.  <span data-ttu-id="a59d2-140">Haga clic en el **otros** ficha y especifique las credenciales para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="a59d2-140">Click the **Others** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
    4.  <span data-ttu-id="a59d2-141">Haga clic en el **mensajes** ficha y en el **cuerpo del mensaje entrante de BizTalk** sección, elija el **ruta de acceso** opción.</span><span class="sxs-lookup"><span data-stu-id="a59d2-141">Click the **Messages** tab, and in the **Inbound BizTalk message body** section, choose the **Path** option.</span></span>  
  
    5.  <span data-ttu-id="a59d2-142">En el **expresión de ruta de acceso del cuerpo** texto, especifique la consulta XPath para extraer el IDOC de archivo sin formato del mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="a59d2-142">In the **Body path expression** text box, specify the XPath query to extract the flat-file IDOC from the XML message.</span></span> <span data-ttu-id="a59d2-143">Al hacerlo, el puerto de recepción extrae los datos de lo IDOC y recorta la etiqueta XML que forma parte de la **ReceiveIdoc** operación para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a59d2-143">By doing so, the receive port extracts the data from the IDOC and trims the XML tag that is part of the **ReceiveIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="a59d2-144">Para obtener más información acerca del esquema de mensaje para la **ReceiveIdoc** operación, vea [esquemas de mensaje para las operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a59d2-144">For more information about the message schema for the **ReceiveIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
         <span data-ttu-id="a59d2-145">![XPath de consulta para extraer el plano &#45; IDOC de archivo](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span><span class="sxs-lookup"><span data-stu-id="a59d2-145">![XPath query to extract the flat&#45;file IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span></span>  
  
         <span data-ttu-id="a59d2-146">Debe especificar la consulta XPath siguiente:</span><span class="sxs-lookup"><span data-stu-id="a59d2-146">You must specify the following XPath query:</span></span>  
  
        ```  
        /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
        ```  
  
    6.  <span data-ttu-id="a59d2-147">Desde el **codificación de nodo** lista desplegable, seleccione **cadena**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-147">From the **Node encoding** drop-down list, select **String**.</span></span>  
  
    7.  <span data-ttu-id="a59d2-148">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-148">Click **Apply**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="a59d2-149">En el cuadro de diálogo Propiedades de la ubicación de recepción, de la **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-149">In the Receive Location Properties dialog box, from the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="a59d2-150">Desde el **canalización de recepción** lista desplegable, seleccione **ConvertToXML**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-150">From the **Receive pipeline** drop-down list, select **ConvertToXML**.</span></span> <span data-ttu-id="a59d2-151">Esta canalización de desensamblador de archivos sin formato ya es una parte del proyecto de BizTalk vPrev para convertir un IDOC de archivo sin formato en un IDOC XML.</span><span class="sxs-lookup"><span data-stu-id="a59d2-151">This flat-file disassembler pipeline is already a part of the vPrev BizTalk project to convert a flat-file IDOC to an XML IDOC.</span></span>  
  
11. <span data-ttu-id="a59d2-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-152">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="a59d2-153">Para configurar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a59d2-153">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="a59d2-154">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda la aplicación de BizTalk donde se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="a59d2-154">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="a59d2-155">Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-155">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="a59d2-156">En el panel izquierdo, haga clic en la orquestación que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="a59d2-156">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="a59d2-157">En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a59d2-157">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="a59d2-158">En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a59d2-158">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="a59d2-159">Seleccione el WCF-Custom recibir puerto creado anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a59d2-159">Select the WCF-Custom receive port you created earlier in this topic.</span></span>  
  
    2.  <span data-ttu-id="a59d2-160">Seleccione un puerto de archivos donde recibirá el IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="a59d2-160">Select a file port where you will receive the flat-file IDOC.</span></span>  
  
    3.  <span data-ttu-id="a59d2-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a59d2-161">Click **OK**.</span></span>  
  
     <span data-ttu-id="a59d2-162">Para obtener más información acerca de cómo configurar una aplicación, consulte [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span><span class="sxs-lookup"><span data-stu-id="a59d2-162">For more information about configuring an application, see [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a59d2-163">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a59d2-163">Next Steps</span></span>  
 <span data-ttu-id="a59d2-164">Ahora ha completado la migración de su proyecto de BizTalk vPrev a un proyecto de BizTalk que recibe los IDOC desde un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a59d2-164">You have now completed migration of your vPrev BizTalk project to a BizTalk project that receives IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="a59d2-165">Ahora debe probar la aplicación migrada de BizTalk mediante la recepción de un IDOC de archivo sin formato, como se describe en [paso 3: probar la aplicación migran](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).</span><span class="sxs-lookup"><span data-stu-id="a59d2-165">You must now test the migrated BizTalk application by receiving a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59d2-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="a59d2-166">See Also</span></span>  
 [<span data-ttu-id="a59d2-167">Tutorial 4: Migrar una SAP recibir IDOC proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a59d2-167">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)