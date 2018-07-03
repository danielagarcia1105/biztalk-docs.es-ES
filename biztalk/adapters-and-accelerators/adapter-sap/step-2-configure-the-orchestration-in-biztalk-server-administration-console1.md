---
title: 'Paso 2: Configurar la orquestación en BizTalk Server Administration Consola1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration, configruing in BizTalk Server Administration console
- WCF-Custom port, creating
- migration
ms.assetid: fb057bce-5702-4ea0-8ed5-e299d3a78a11
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 696315b895ff778c0cc8f4f929cb62a4ba110846
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015061"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console"></a><span data-ttu-id="2be65-102">Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2be65-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console</span></span>
<span data-ttu-id="2be65-103">![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="2be65-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="2be65-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="2be65-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="2be65-105">**Objetivo:** en este paso, realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="2be65-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="2be65-106">Crear un WCF-Custom envío-puerto de recepción para enviar y recibir mensajes desde el sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2be65-106">Create a WCF-Custom send-receive port to send and receive messages from the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="2be65-107">Configurar este puerto para utilizar las asignaciones que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="2be65-107">Configure this port to use the maps that you created in the previous step.</span></span>  
  
- <span data-ttu-id="2be65-108">Configurar la orquestación ha implementado en el último paso para usar el puerto de WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="2be65-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="2be65-109">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="2be65-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="2be65-110">Implementar la orquestación de BizTalk para el que desea configurar el puerto de WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="2be65-110">Deploy the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="2be65-111">Para crear un puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="2be65-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="2be65-112">Al generar el esquema para una RFC con el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], un archivo de enlace también se agrega al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2be65-112">When you generate schema for an RFC using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="2be65-113">Puede importar este archivo de enlace en el BizTalk aplicación para crear un WCF-Custom envío-puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2be65-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="2be65-114">Para obtener instrucciones sobre cómo importar un archivo de enlace, consulte [importar enlaces](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf).</span><span class="sxs-lookup"><span data-stu-id="2be65-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf).</span></span>  
  
2. <span data-ttu-id="2be65-115">Después de importar el archivo de enlace, se crea un puerto de envío en el **puertos de envío** carpeta en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2be65-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3. <span data-ttu-id="2be65-116">Haga clic en el puerto de WCF-Custom y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2be65-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="2be65-117">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en el **General** ficha. En el panel derecho, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2be65-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="2be65-118">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y especificar las credenciales para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2be65-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
6. <span data-ttu-id="2be65-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2be65-119">Click **OK**.</span></span>  
  
7. <span data-ttu-id="2be65-120">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de entrada**.</span><span class="sxs-lookup"><span data-stu-id="2be65-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="2be65-121">En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **ResponseMap**.</span><span class="sxs-lookup"><span data-stu-id="2be65-121">From the right pane, click the field under the **Map** column, and from the drop-down, select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="2be65-122">![Configurar la asignación de entrada en el puerto WCF personalizado](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")</span><span class="sxs-lookup"><span data-stu-id="2be65-122">![Configure the inbound map on the WCF custom port](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")</span></span>  
  
8. <span data-ttu-id="2be65-123">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de salida.**</span><span class="sxs-lookup"><span data-stu-id="2be65-123">From the left pane of the send port properties dialog box, click **Outbound Maps.**</span></span> <span data-ttu-id="2be65-124">En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **RequestMap**.</span><span class="sxs-lookup"><span data-stu-id="2be65-124">From the right pane, click the field under the **Map** column, and from the drop-down, select **RequestMap**.</span></span>  
  
    <span data-ttu-id="2be65-125">![Configurar la asignación de salida en el puerto WCF personalizado](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")</span><span class="sxs-lookup"><span data-stu-id="2be65-125">![Configure the outbound map on the WCF custom port](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")</span></span>  
  
9. <span data-ttu-id="2be65-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2be65-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="2be65-127">Para configurar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2be65-127">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="2be65-128">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación de BizTalk donde se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2be65-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="2be65-129">Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2be65-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="2be65-130">En el panel izquierdo, haga clic en el que se va a configurar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2be65-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="2be65-131">En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2be65-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="2be65-132">En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2be65-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="2be65-133">Seleccione el puerto de archivo donde se colocará un mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2be65-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="2be65-134">La orquestación de BizTalk usarán el mensaje de solicitud y enviarlo al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2be65-134">The BizTalk orchestration will consume the request message and send it to the SAP system.</span></span>  
  
   2. <span data-ttu-id="2be65-135">Seleccione el puerto de archivo donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2be65-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the SAP system.</span></span>  
  
   3. <span data-ttu-id="2be65-136">Seleccione el puerto de envío WCF-custom que creó anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="2be65-136">Select the WCF-custom send port you created earlier in this topic.</span></span>  
  
   4. <span data-ttu-id="2be65-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2be65-137">Click **OK**.</span></span>  
  
      <span data-ttu-id="2be65-138">Para obtener más información acerca de cómo configurar una aplicación, consulte "Cómo configurar una aplicación" en [ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360).</span><span class="sxs-lookup"><span data-stu-id="2be65-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2be65-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2be65-139">Next Steps</span></span>  
 <span data-ttu-id="2be65-140">Ahora ha completado la migración de su proyecto de BizTalk vPrev para un proyecto de BizTalk que envía mensajes al sistema SAP mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2be65-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="2be65-141">Ahora debe probar la aplicación migrada de BizTalk mediante el envío de un mensaje de solicitud para invocar la RFC SD_RFC_CUSTOMER_GET, como se describe en [paso 3: probar la aplicación migrados](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md).</span><span class="sxs-lookup"><span data-stu-id="2be65-141">You must now test the migrated BizTalk application by sending a request message to invoke the SD_RFC_CUSTOMER_GET RFC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be65-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="2be65-142">See Also</span></span>  
 [<span data-ttu-id="2be65-143">Tutorial 2: Migración de un proyecto de BizTalk RFC de SAP</span><span class="sxs-lookup"><span data-stu-id="2be65-143">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)