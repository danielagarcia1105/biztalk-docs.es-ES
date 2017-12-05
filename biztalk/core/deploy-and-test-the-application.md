---
title: "Implementar y probar la aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d93284823c2ce5d0c00a1601a5b9ae0aac4643c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="deploy-and-test-the-application"></a><span data-ttu-id="31624-102">Implementar y probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="31624-102">Deploy and test the application</span></span>
> [!NOTE]
>  <span data-ttu-id="31624-103">Este tutorial solo se aplica a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="31624-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="31624-104">En este tema, vamos a compilar, implementar, configurar y probar la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31624-104">In this topic, we build, deploy, configure, and test the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="build-and-deploy-the-application"></a><span data-ttu-id="31624-105">Compilar e implementar la aplicación</span><span class="sxs-lookup"><span data-stu-id="31624-105">Build and deploy the application</span></span>  
  
1.  <span data-ttu-id="31624-106">En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="31624-106">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="31624-107">En la página Propiedades, haga clic en la ficha Firma, active la casilla Firmar el ensamblado y, en la lista desplegable, elija la opción para crear un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="31624-107">On the Property page, click the Signing tab, select the Sign the assembly check box, and from the drop-down choose the option to create a new strong name key file.</span></span> <span data-ttu-id="31624-108">Siga las instrucciones que aparecen para crear el archivo.</span><span class="sxs-lookup"><span data-stu-id="31624-108">Follow the prompts to create the file.</span></span>  
  
3.  <span data-ttu-id="31624-109">Guarde los cambios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="31624-109">Save changes to the project.</span></span> <span data-ttu-id="31624-110">En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="31624-110">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="31624-111">Después de proyecto se compila correctamente, en el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="31624-111">After project builds successfully, in the Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="configure-the-application"></a><span data-ttu-id="31624-112">Configurar la aplicación</span><span class="sxs-lookup"><span data-stu-id="31624-112">Configure the application</span></span>  
 <span data-ttu-id="31624-113">Para configurar la aplicación, en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], cree los puertos de envío y recepción, y enlácelos con la orquestación y los puertos de envío y recepción lógicos creados como parte de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="31624-113">To configure the application, in [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], create the send and receive ports and then bind them to the orchestration and the logical send/receive ports created as part of the orchestration.</span></span>  
  
1.  <span data-ttu-id="31624-114">Cree un puerto de recepción por el que la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba un pedido de compra JSON.</span><span class="sxs-lookup"><span data-stu-id="31624-114">Create a receive port through which a JSON purchase order is received by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
    1.  <span data-ttu-id="31624-115">En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **BizTalk Application 1**, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="31624-115">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
    2.  <span data-ttu-id="31624-116">Proporcione un nombre para el puerto de recepción y, a continuación, en el panel izquierdo, haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="31624-116">Provide a name for the receive port, and then from the left pan, click **Receive Locations**.</span></span> <span data-ttu-id="31624-117">En el **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="31624-117">In the **Receive Locations** tab, click **New**.</span></span>  
  
    3.  <span data-ttu-id="31624-118">Especifique un nombre para la ubicación de recepción, seleccione el tipo de puerto como **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="31624-118">Specify a name for the receive location, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="31624-119">Proporcione la ubicación de carpeta de donde la ubicación de recepción tomará el pedido de compra JSON entrante.</span><span class="sxs-lookup"><span data-stu-id="31624-119">Provide the folder location from where the receive location will pick the incoming JSON purchase order.</span></span> <span data-ttu-id="31624-120">Especifique `*.json` como la máscara de archivo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31624-120">Specify `*.json` as the file mask and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="31624-121">Desde el **canalización de recepción** lista desplegable, seleccione **JSONToXml**.</span><span class="sxs-lookup"><span data-stu-id="31624-121">From the **Receive Pipeline** drop-down, select **JSONToXml**.</span></span> <span data-ttu-id="31624-122">Creó esta canalización de recepción personalizada en la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31624-122">You created this custom receive pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="31624-123">Haga clic en los puntos suspensivos **(...)**  botón junto a la canalización y, a continuación, en **fase 1 – componente descodificar**, proporcione los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="31624-123">Right-click the ellipsis **(…)** button next to the pipeline, and then under **Stage 1 – Deocde Component**, provide the following values:</span></span>  
  
        -   <span data-ttu-id="31624-124">RootNode-`ROOT`</span><span class="sxs-lookup"><span data-stu-id="31624-124">RootNode - `ROOT`</span></span>  
  
        -   <span data-ttu-id="31624-125">RootNodeNamespace:`http://BTSJSON`.</span><span class="sxs-lookup"><span data-stu-id="31624-125">RootNodeNamespace –`http://BTSJSON`.</span></span>  
  
         <span data-ttu-id="31624-126">Estos valores representan el espacio de nombres de destino y el nombre del nodo raíz del esquema del pedido de compra XML que se generó a partir del pedido de compra JSON con el asistente para esquemas JSON.</span><span class="sxs-lookup"><span data-stu-id="31624-126">These values represent the target namespace and the root node name of the XML purchase order schema that was generated from the JSON purchase order using the JSON schema wizard.</span></span>  
  
    6.  <span data-ttu-id="31624-127">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo abiertos.</span><span class="sxs-lookup"><span data-stu-id="31624-127">Click **OK** until you exit all open dialog boxes.</span></span>  
  
2.  <span data-ttu-id="31624-128">Cree un puerto de envío para enviar mensajes de factura JSON.</span><span class="sxs-lookup"><span data-stu-id="31624-128">Create a send port for sending out JSON invoice messages.</span></span>  
  
    1.  <span data-ttu-id="31624-129">En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **BizTalk Application 1**, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **enviar Puerto unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="31624-129">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="31624-130">Especifique un nombre para el puerto de envío, seleccione el tipo de puerto como **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="31624-130">Specify a name for the send port, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
    3.  <span data-ttu-id="31624-131">Proporcione la ubicación de carpeta donde el puerto de envío copia la factura JSON saliente.</span><span class="sxs-lookup"><span data-stu-id="31624-131">Provide the folder location where the send port copies the outgoing JSON invoice.</span></span> <span data-ttu-id="31624-132">Especifique `%MessageID%.json` como el nombre de archivo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31624-132">Specify `%MessageID%.json` as the file name and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="31624-133">Desde el **canalización de envío** lista desplegable, seleccione **XmlToJSON**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31624-133">From the **Send Pipeline** drop-down, select **XmlToJSON**, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="31624-134">Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo abiertos.</span><span class="sxs-lookup"><span data-stu-id="31624-134">Click **OK** until you exit all open dialog boxes.</span></span>  
  
3.  <span data-ttu-id="31624-135">Finalmente, enlace los puertos lógicos que creó como parte de la orquestación a los puertos físicos que ha creado ahora para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31624-135">Finally, bind the logical ports you created as part of the orchestration to the physical ports you created now to configure the application.</span></span>  
  
    1.  <span data-ttu-id="31624-136">Haga clic en **BizTalk Application 1**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="31624-136">Right-click **BizTalk Application 1**, and then click **Configure**.</span></span>  
  
    2.  <span data-ttu-id="31624-137">En el panel izquierdo, haga clic en **ProcessPO**.</span><span class="sxs-lookup"><span data-stu-id="31624-137">From the left pane, click **ProcessPO**.</span></span> <span data-ttu-id="31624-138">En el panel derecho, asocie un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hospedar, asigne los puertos lógicos a los puertos físicos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31624-138">From the right pane, associate a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host, map the logical ports to the physical ports, and then click **OK**.</span></span>  
  
    3.  <span data-ttu-id="31624-139">Haga clic en **BizTalk Application 1**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="31624-139">Right-click **BizTalk Application 1**, and then click **Start**.</span></span>  
  
## <a name="test-the-application"></a><span data-ttu-id="31624-140">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="31624-140">Test the application</span></span>  
  
1.  <span data-ttu-id="31624-141">Navegue al ejemplo que ha descargado y desde el **TestMessage** carpeta, copie **JsonPurchaseOrder.json**y péguelo en la carpeta asociada con la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="31624-141">Navigate to the sample you downloaded, and from the **TestMessage** folder, copy **JsonPurchaseOrder.json**, and paste it in the folder you associated with the receive location.</span></span> <span data-ttu-id="31624-142">Espere hasta que desaparezca el archivo.</span><span class="sxs-lookup"><span data-stu-id="31624-142">Wait till the file disappears.</span></span>  
  
2.  <span data-ttu-id="31624-143">Navegue a la carpeta que ha asociado al puerto de envío que había creado.</span><span class="sxs-lookup"><span data-stu-id="31624-143">Navigate to the folder that you associated with the send port you created.</span></span> <span data-ttu-id="31624-144">Tenga en cuenta que un   ***\<GUID\>*.json** archivo está disponible en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="31624-144">Notice that a ***\<GUID\>*.json** file is available in the folder.</span></span> <span data-ttu-id="31624-145">Abra el archivo y verifique que es el mensaje de factura.</span><span class="sxs-lookup"><span data-stu-id="31624-145">Open the file and verify that it’s the invoice message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31624-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="31624-146">See Also</span></span>  
 [<span data-ttu-id="31624-147">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="31624-147">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)