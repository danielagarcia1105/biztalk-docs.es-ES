---
title: 'Paso 2: Configurar un puerto de envío unidireccional de WCF-Custom | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aab14799076d3f774130b357ab90c5ed5335f4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962794"
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="7763d-102">Paso 2: Configurar un puerto de envío unidireccional de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="7763d-102">Step 2: Configure a WCF-Custom One-way Send Port</span></span>
<span data-ttu-id="7763d-103">![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="7763d-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="7763d-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="7763d-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="7763d-105">**Objetivo:** en este paso, configurará un puerto personalizado de WCF para enviar el IDOC de archivo sin formato a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="7763d-105">**Objective:** In this step, you configure a WCF-Custom port to send the flat-file IDOC to an SAP system.</span></span> <span data-ttu-id="7763d-106">Después de configurar el puerto, configure la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="7763d-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7763d-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7763d-107">Prerequisites</span></span>  
 <span data-ttu-id="7763d-108">Debe ha creado e implementado el proyecto de BizTalk vPrev para enviar los IDOC a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="7763d-108">You must have built and deployed your vPrev BizTalk project to send IDOCs to an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="7763d-109">Para configurar un puerto de envío unidireccional de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="7763d-109">To configure a WCF-Custom one-way send port</span></span>  
  
1.  <span data-ttu-id="7763d-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="7763d-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7763d-111">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="7763d-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="7763d-112">Expanda la aplicación en la que desea crear el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7763d-112">Expand the application under which you want to create the send port.</span></span>  
  
4.  <span data-ttu-id="7763d-113">Haga clic en **puertos de envío**, seleccione **New**y haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="7763d-113">Right-click **Send Ports**, point to **New**, and click **Static One-way Send Port**.</span></span>  
  
5.  <span data-ttu-id="7763d-114">En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7763d-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="7763d-115">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7763d-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="7763d-116">En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7763d-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="7763d-117">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para enviar mensajes al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="7763d-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to send messages to the SAP system.</span></span> <span data-ttu-id="7763d-118">Para obtener más información sobre el URI de conexión, consulte [cree el URI de conexión del sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="7763d-118">For more information about the connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
         <span data-ttu-id="7763d-119">![URI de conexión especificado en el puerto de envío](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span><span class="sxs-lookup"><span data-stu-id="7763d-119">![Connection URI specified in the send port](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span></span>  
  
    2.  <span data-ttu-id="7763d-120">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="7763d-120">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="7763d-121">Para enviar un IDOC de archivo sin formato, debe usar el **SendIdoc** operación expuesta por basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7763d-121">To send a flat-file IDOC, you must use the **SendIdoc** operation exposed by the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7763d-122">**SendIdoc** operación permite a los clientes de adaptador enviar los IDOC que tengan un esquema débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="7763d-122">**SendIdoc** operation enables adapter clients to send IDOCs having a weakly-typed schema.</span></span> <span data-ttu-id="7763d-123">Para obtener más información, consulte [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="7763d-123">For more information, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span> <span data-ttu-id="7763d-124">La siguiente ilustración muestra la **acción** cuadro de texto con la acción para el **SendIdoc** operación.</span><span class="sxs-lookup"><span data-stu-id="7763d-124">The following figure shows the **Action** text box with the action for the **SendIdoc** operation.</span></span>  
  
         <span data-ttu-id="7763d-125">![Especificar la acción en el puerto de envío](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span><span class="sxs-lookup"><span data-stu-id="7763d-125">![Specify action in the send port](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span></span>  
  
    3.  <span data-ttu-id="7763d-126">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="7763d-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
    4.  <span data-ttu-id="7763d-127">Haga clic en el **credenciales** ficha y especifique las credenciales para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="7763d-127">Click the **Credentials** tab and specify the credentials to connect to an SAP system.</span></span>  
  
    5.  <span data-ttu-id="7763d-128">Haga clic en el **mensajes** ficha y en el **cuerpo del mensaje saliente de WCF** sección, elija el **plantilla** opción.</span><span class="sxs-lookup"><span data-stu-id="7763d-128">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
    6.  <span data-ttu-id="7763d-129">En el **XML** texto, especifique la plantilla que se usará para construir el mensaje WCF.</span><span class="sxs-lookup"><span data-stu-id="7763d-129">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="7763d-130">Al hacerlo, cree un mensaje que se ajusta a la **SendIdoc** operación para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7763d-130">By doing so, you create a message that conforms to the **SendIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7763d-131">Para obtener más información acerca de la estructura del mensaje para la **SendIdoc** operación, vea [esquemas de mensaje para las operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="7763d-131">For more information about the message structure for the **SendIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
         <span data-ttu-id="7763d-132">![Especificar plantilla para mensaje WCF saliente](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span><span class="sxs-lookup"><span data-stu-id="7763d-132">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span></span>  
  
         <span data-ttu-id="7763d-133">Para la operación SendIdoc, debe especificar la siguiente plantilla:</span><span class="sxs-lookup"><span data-stu-id="7763d-133">For the SendIdoc operation, you must specify the following template:</span></span>  
  
        ```  
        <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
        <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
        </SendIdoc>  
        ```  
  
         <span data-ttu-id="7763d-134">En la plantilla anterior, el `bts-msg-body` es puerto de recepción de XML IDOC que se crea utilizando el Desensamblador de archivos sin formato asociado al archivo.</span><span class="sxs-lookup"><span data-stu-id="7763d-134">In the preceding template, the `bts-msg-body` is XML IDOC that is created using the flat-file disassembler associated with the file receive port.</span></span> <span data-ttu-id="7763d-135">El XML IDOC se encapsula en el mensaje SendIdoc.</span><span class="sxs-lookup"><span data-stu-id="7763d-135">The XML IDOC is encapsulated in the SendIdoc message.</span></span>  
  
    7.  <span data-ttu-id="7763d-136">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7763d-136">Click **Apply**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="7763d-137">En el **propiedades de puerto de envío** cuadro de diálogo, desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="7763d-137">In the **Send Port Properties** dialog box, from the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="7763d-138">Desde el **canalización de envío** lista desplegable, seleccione **ConvertToFlatFile**.</span><span class="sxs-lookup"><span data-stu-id="7763d-138">From the **Send pipeline** drop-down list, select **ConvertToFlatFile**.</span></span> <span data-ttu-id="7763d-139">Esta canalización de ensamblador de archivo sin formato ya forma parte del proyecto de BizTalk vPrev y se utiliza para convertir un IDOC XML en un IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="7763d-139">This flat-file assembler pipeline is already a part of the vPrev BizTalk project and is used to convert an XML IDOC to a flat-file IDOC.</span></span>  
  
10. <span data-ttu-id="7763d-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7763d-140">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="7763d-141">Para configurar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7763d-141">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="7763d-142">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda la aplicación de BizTalk donde se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="7763d-142">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="7763d-143">Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7763d-143">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="7763d-144">En el panel izquierdo, haga clic en la orquestación que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="7763d-144">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="7763d-145">En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7763d-145">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="7763d-146">En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7763d-146">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="7763d-147">Seleccione el puerto de archivo donde se colocará el IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="7763d-147">Select the file port where you will drop the flat-file IDOC.</span></span>  
  
    2.  <span data-ttu-id="7763d-148">Seleccione el puerto de envío WCF-Custom que creó anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="7763d-148">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
    3.  <span data-ttu-id="7763d-149">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7763d-149">Click **OK**.</span></span>  
  
     <span data-ttu-id="7763d-150">Para obtener más información acerca de cómo configurar una aplicación, consulte "Cómo configurar una aplicación" en [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span><span class="sxs-lookup"><span data-stu-id="7763d-150">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7763d-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7763d-151">Next Steps</span></span>  
 <span data-ttu-id="7763d-152">Ahora ha completado la migración de su proyecto de BizTalk vPrev a un proyecto de BizTalk que envía el IDOC a un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7763d-152">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7763d-153">Ahora debe probar la aplicación migrada de BizTalk mediante el envío de un IDOC de archivo sin formato, como se describe en [paso 3: probar la aplicación migran](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md).</span><span class="sxs-lookup"><span data-stu-id="7763d-153">You must now test the migrated BizTalk application by sending a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7763d-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="7763d-154">See Also</span></span>  
 [<span data-ttu-id="7763d-155">Tutorial 3: Migración de un proyecto de BizTalk SAP IDOC de envío</span><span class="sxs-lookup"><span data-stu-id="7763d-155">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)