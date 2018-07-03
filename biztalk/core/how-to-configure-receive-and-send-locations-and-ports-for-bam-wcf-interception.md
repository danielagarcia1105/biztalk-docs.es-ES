---
title: Configuración de recepción y envío puertos y ubicaciones para la intercepción de WCF de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501194dc-427a-4910-88c9-19cf47daeaad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d6fb5a58efe721f3000dddefb0354bd7834d46c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991653"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a><span data-ttu-id="4b2ef-102">Cómo configurar ubicaciones y puertos de recepción y de envío para la intercepción de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="4b2ef-102">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>
<span data-ttu-id="4b2ef-103">En este procedimiento puede configurar las ubicaciones de recepción y de envío en un escenario de enrutamiento por contenidos (CBR) para mostrar los conceptos clave de un modo sencillo.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-103">In this procedure you configure the receive and send locations in a content-based routing (CBR) scenario in order to demonstrate the key concepts in a straightforward manner.</span></span> <span data-ttu-id="4b2ef-104">Los conceptos mostrados aquí se pueden aplicar a una orquestación que se expone como servicio de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b2ef-104">The concepts demonstrated here can be applied to an orchestration that is exposed as a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] service.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="4b2ef-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4b2ef-105">Prerequisites</span></span>  
 <span data-ttu-id="4b2ef-106">En este procedimiento se presupone que:</span><span class="sxs-lookup"><span data-stu-id="4b2ef-106">This procedure assumes that you have:</span></span>  

-   <span data-ttu-id="4b2ef-107">Puede modificar el archivo.config del equipo como se muestra en [cómo agregar el comportamiento del Interceptor de BAM al archivo Machine.config](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="4b2ef-107">Modified your machince.config file as shown in [How to Add the BAM Interceptor Behavior to the Machine.config File](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).</span></span>  

-   <span data-ttu-id="4b2ef-108">Crea un adaptador de WCF para BizTalk Server como se muestra en [cómo crear un adaptador de WCF para BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="4b2ef-108">Created a WCF adapter for BizTalk Server as show in [How to Create a WCF Adapter for BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).</span></span>  

### <a name="to-configure-the-receive-and-send-locations"></a><span data-ttu-id="4b2ef-109">Para configurar las ubicaciones de recepción y de envío</span><span class="sxs-lookup"><span data-stu-id="4b2ef-109">To configure the receive and send locations</span></span>  

1. <span data-ttu-id="4b2ef-110">Abra la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-110">Open the BizTalk Administration Console.</span></span> <span data-ttu-id="4b2ef-111">Para ello, haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-111">To do this, click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="4b2ef-112">Expanda el árbol de la consola para ubicar el nodo Ubicaciones de recepción de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-112">Expand the console tree to locate the Receive Locations node for your BizTalk application.</span></span> <span data-ttu-id="4b2ef-113">Haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **aplicaciones**, haga clic en la aplicación que ha seleccionado en el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] cuadro de diálogo de tipo de servicio y, a continuación, haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-113">Click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], click **Applications**, click the application you selected in the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Type dialog box, and then click **Receive Locations**.</span></span> <span data-ttu-id="4b2ef-114">Existirá una nueva ubicación de recepción correspondiente a la que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-114">There will be a new receive location corresponding to the one you created.</span></span> <span data-ttu-id="4b2ef-115">Se encontrará en estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-115">It will be in disabled status.</span></span>  

3. <span data-ttu-id="4b2ef-116">Haga doble clic en la ubicación de recepción para abrir el **propiedades de ubicación de recepción** diálogo cuadro y, a continuación, elija WCF-Custom como tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-116">Double-click the receive location to open the **Receive Location Properties** dialog box, and then choose WCF-Custom as the transport type.</span></span>  

4. <span data-ttu-id="4b2ef-117">Haga clic en el **configurar** botón para abrir el **propiedades de transporte WCF-Custom** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-117">Click the **Configure** button to open the **WCF-Custom Transport Properties** dialog box.</span></span>  

5. <span data-ttu-id="4b2ef-118">Haga clic en el **enlace** pestaña y seleccione el enlace que desea usar.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-118">Click the **Binding** tab and select the binding you want to use.</span></span>  

6. <span data-ttu-id="4b2ef-119">Haga clic en el **comportamiento** pestaña, haga clic en el **EndpointBehavior** nodo y, a continuación, seleccione **Agregar extensión**.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-119">Click the **Behavior** tab, right-click the **EndpointBehavior** node, and then select **Add Extension**.</span></span>  

7. <span data-ttu-id="4b2ef-120">Seleccione el BAMEndPointExtension (ésta es la extensión que agregó al archivo machine.config) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-120">Select the BAMEndPointExtension (this is the extension you added to the machine.config file), and then click **Ok**.</span></span>  

    <span data-ttu-id="4b2ef-121">![Pantalla de extensión de comportamiento de SELECT](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span><span class="sxs-lookup"><span data-stu-id="4b2ef-121">![Select Behavior Extension screen](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span></span>  

8. <span data-ttu-id="4b2ef-122">Seleccione la extensión que acaba de crear, escriba los valores siguientes y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="4b2ef-122">Select the extension you just created, enter the following values, and then click **OK**:</span></span>  


   |      <span data-ttu-id="4b2ef-123">Property</span><span class="sxs-lookup"><span data-stu-id="4b2ef-123">Property</span></span>      |                                                        <span data-ttu-id="4b2ef-124">Valor</span><span class="sxs-lookup"><span data-stu-id="4b2ef-124">Value</span></span>                                                         |
   |--------------------|----------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="4b2ef-125">PollingIntervalSec</span><span class="sxs-lookup"><span data-stu-id="4b2ef-125">PollingIntervalSec</span></span> |                                                          <span data-ttu-id="4b2ef-126">10</span><span class="sxs-lookup"><span data-stu-id="4b2ef-126">10</span></span>                                                          |
   |  <span data-ttu-id="4b2ef-127">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="4b2ef-127">ConnectionString</span></span>  | <span data-ttu-id="4b2ef-128">ConnectionString: Integrated Security = SSPI; Persist Security Info = False; Initial Catalog = BAMPrimaryImport; origen de datos =</span><span class="sxs-lookup"><span data-stu-id="4b2ef-128">ConnectionString: Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=BAMPrimaryImport;Data Source=</span></span> |


9. <span data-ttu-id="4b2ef-129">En el **propiedades de ubicación de recepción** cuadro de diálogo, seleccione **PassThruReceive** desde el **canalización de recepción** lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-129">In the **Receive Location Properties** dialog box, select **PassThruReceive** from the **Receive pipeline** drop-down list, and then click **OK**.</span></span>  

10. <span data-ttu-id="4b2ef-130">Habilite la ubicación de recepción y actualice la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-130">Enable the receive location and refresh the Administration console.</span></span> <span data-ttu-id="4b2ef-131">Un estado iniciado indica que la configuración se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-131">A started status indicates that the setup is successful.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4b2ef-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b2ef-132">See Also</span></span>  
 [<span data-ttu-id="4b2ef-133">Configuración del adaptador de WCF para interceptar datos de BAM</span><span class="sxs-lookup"><span data-stu-id="4b2ef-133">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)