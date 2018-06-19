---
title: Cómo configurar la recepción y envío ubicaciones y puertos para la intercepción de WCF de BAM | Documentos de Microsoft
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
ms.openlocfilehash: aa77f39e8320c0d6598caaf5ea547592078774ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248444"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a><span data-ttu-id="ba5e0-102">Cómo configurar ubicaciones y puertos de recepción y de envío para la intercepción de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="ba5e0-102">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>
<span data-ttu-id="ba5e0-103">En este procedimiento puede configurar las ubicaciones de recepción y de envío en un escenario de enrutamiento por contenidos (CBR) para mostrar los conceptos clave de un modo sencillo.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-103">In this procedure you configure the receive and send locations in a content-based routing (CBR) scenario in order to demonstrate the key concepts in a straightforward manner.</span></span> <span data-ttu-id="ba5e0-104">Los conceptos mostrados aquí se pueden aplicar a una orquestación que se expone como servicio de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba5e0-104">The concepts demonstrated here can be applied to an orchestration that is exposed as a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ba5e0-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ba5e0-105">Prerequisites</span></span>  
 <span data-ttu-id="ba5e0-106">En este procedimiento se presupone que:</span><span class="sxs-lookup"><span data-stu-id="ba5e0-106">This procedure assumes that you have:</span></span>  
  
-   <span data-ttu-id="ba5e0-107">Modificar el archivo.config del equipo tal y como se muestra en [cómo agregar el comportamiento del Interceptor de BAM al archivo Machine.config](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="ba5e0-107">Modified your machince.config file as shown in [How to Add the BAM Interceptor Behavior to the Machine.config File](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).</span></span>  
  
-   <span data-ttu-id="ba5e0-108">Crea un adaptador de WCF para BizTalk Server como se muestra en [cómo crear un adaptador de WCF para BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba5e0-108">Created a WCF adapter for BizTalk Server as show in [How to Create a WCF Adapter for BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).</span></span>  
  
### <a name="to-configure-the-receive-and-send-locations"></a><span data-ttu-id="ba5e0-109">Para configurar las ubicaciones de recepción y de envío</span><span class="sxs-lookup"><span data-stu-id="ba5e0-109">To configure the receive and send locations</span></span>  
  
1.  <span data-ttu-id="ba5e0-110">Abra la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-110">Open the BizTalk Administration Console.</span></span> <span data-ttu-id="ba5e0-111">Para ello, haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-111">To do this, click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ba5e0-112">Expanda el árbol de la consola para ubicar el nodo Ubicaciones de recepción de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-112">Expand the console tree to locate the Receive Locations node for your BizTalk application.</span></span> <span data-ttu-id="ba5e0-113">Haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **aplicaciones**, haga clic en la aplicación que ha seleccionado en el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] cuadro de diálogo de tipo de servicio y, a continuación, haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-113">Click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], click **Applications**, click the application you selected in the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Type dialog box, and then click **Receive Locations**.</span></span> <span data-ttu-id="ba5e0-114">Existirá una nueva ubicación de recepción correspondiente a la que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-114">There will be a new receive location corresponding to the one you created.</span></span> <span data-ttu-id="ba5e0-115">Se encontrará en estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-115">It will be in disabled status.</span></span>  
  
3.  <span data-ttu-id="ba5e0-116">Haga doble clic en la ubicación de recepción para abrir el **propiedades de la ubicación de recepción** diálogo cuadro y, a continuación, elija WCF-Custom como tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-116">Double-click the receive location to open the **Receive Location Properties** dialog box, and then choose WCF-Custom as the transport type.</span></span>  
  
4.  <span data-ttu-id="ba5e0-117">Haga clic en el **configurar** para abrir el **propiedades de transporte de WCF-Custom** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-117">Click the **Configure** button to open the **WCF-Custom Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="ba5e0-118">Haga clic en el **enlace** pestaña y seleccione el enlace que desea usar.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-118">Click the **Binding** tab and select the binding you want to use.</span></span>  
  
6.  <span data-ttu-id="ba5e0-119">Haga clic en el **comportamiento** pestaña, haga clic en el **EndpointBehavior** nodo y, a continuación, seleccione **Agregar extensión**.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-119">Click the **Behavior** tab, right-click the **EndpointBehavior** node, and then select **Add Extension**.</span></span>  
  
7.  <span data-ttu-id="ba5e0-120">Seleccione el BAMEndPointExtension (ésta es la extensión que se ha agregado al archivo machine.config) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-120">Select the BAMEndPointExtension (this is the extension you added to the machine.config file), and then click **Ok**.</span></span>  
  
     <span data-ttu-id="ba5e0-121">![Pantalla de extensión de comportamiento seleccione](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span><span class="sxs-lookup"><span data-stu-id="ba5e0-121">![Select Behavior Extension screen](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span></span>  
  
8.  <span data-ttu-id="ba5e0-122">Seleccione la extensión que acaba de crear, escriba los valores siguientes y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="ba5e0-122">Select the extension you just created, enter the following values, and then click **OK**:</span></span>  
  
    |<span data-ttu-id="ba5e0-123">Propiedad</span><span class="sxs-lookup"><span data-stu-id="ba5e0-123">Property</span></span>|<span data-ttu-id="ba5e0-124">Valor</span><span class="sxs-lookup"><span data-stu-id="ba5e0-124">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ba5e0-125">PollingIntervalSec</span><span class="sxs-lookup"><span data-stu-id="ba5e0-125">PollingIntervalSec</span></span>|<span data-ttu-id="ba5e0-126">10</span><span class="sxs-lookup"><span data-stu-id="ba5e0-126">10</span></span>|  
    |<span data-ttu-id="ba5e0-127">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="ba5e0-127">ConnectionString</span></span>|<span data-ttu-id="ba5e0-128">ConnectionString: Integrated Security = SSPI; Persist Security Info = False; Initial Catalog = BAMPrimaryImport; origen de datos =</span><span class="sxs-lookup"><span data-stu-id="ba5e0-128">ConnectionString: Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=BAMPrimaryImport;Data Source=</span></span>|  
  
9. <span data-ttu-id="ba5e0-129">En el **propiedades de la ubicación de recepción** cuadro de diálogo, seleccione **PassThruReceive** desde el **canalización de recepción** lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-129">In the **Receive Location Properties** dialog box, select **PassThruReceive** from the **Receive pipeline** drop-down list, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="ba5e0-130">Habilite la ubicación de recepción y actualice la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-130">Enable the receive location and refresh the Administration console.</span></span> <span data-ttu-id="ba5e0-131">Un estado iniciado indica que la configuración se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba5e0-131">A started status indicates that the setup is successful.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba5e0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba5e0-132">See Also</span></span>  
 [<span data-ttu-id="ba5e0-133">Configurar el adaptador WCF para interceptar datos BAM</span><span class="sxs-lookup"><span data-stu-id="ba5e0-133">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)