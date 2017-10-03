---
title: "Cómo configurar el envío del adaptador de MQSeries y controladores de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive handlers, MQSeries adapters
- configuring [MQSeries adapters], receive handlers
- MQSeries adapters, send handlers
- MQSeries adapters, receive handlers
- send handlers, MQSeries adapters
- configuring [MQSeries adapters], send handlers
ms.assetid: e1cfc415-50d2-440b-9301-ad69da28ad3e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a1e933f62adaf4e17fae5334e65f50610fb6f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a><span data-ttu-id="6f6ba-102">Controladores de recepción y envío de cómo configurar el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="6f6ba-102">How to Configure MQSeries Adapter Send and Receive Handlers</span></span>
<span data-ttu-id="6f6ba-103">Puede configurar algunas propiedades para los controladores de recepción y envío del adaptador de MQSeries mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-103">You can configure some properties for the send and receive handlers for the MQSeries adapter through the BizTalk Server Administration console.</span></span> <span data-ttu-id="6f6ba-104">El proceso se describe en [cómo configurar ubicaciones de recepción de MQSeries adaptador y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) establece los valores para la mayoría de las propiedades del controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-104">The process described in [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) establishes the values for the majority of send handler properties.</span></span>  
  
## <a name="to-configure-the-send-and-receive-handlers"></a><span data-ttu-id="6f6ba-105">Para configurar los controladores de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="6f6ba-105">To configure the send and receive handlers</span></span>  
 <span data-ttu-id="6f6ba-106">Siga estos pasos para configurar controladores de envío y recepción para el adaptador de MQSeries:</span><span class="sxs-lookup"><span data-stu-id="6f6ba-106">Follow these steps to configure send and receive handlers for the MSQeries adapter:</span></span>  
  
1.  <span data-ttu-id="6f6ba-107">Haga clic en **iniciar**, seleccione **programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-107">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6f6ba-108">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, haga clic para expandir **configuración de plataforma**y, a continuación, haga clic en Expanda **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-108">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, click to expand **Platform Settings**, and then click to expand **Adapters**.</span></span>  
  
3.  <span data-ttu-id="6f6ba-109">En la lista de adaptadores expandida, seleccione **MQSeries**.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-109">In the expanded adapter list, select **MQSeries**.</span></span> <span data-ttu-id="6f6ba-110">La lista de controladores de envío y recepción enlazados al adaptador de MQSeries aparece en el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-110">The list of send and receive handlers that are bound to the MQSeries adapter appear in the right pane.</span></span>  
  
4.  <span data-ttu-id="6f6ba-111">En el panel derecho, haga doble clic en un controlador de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-111">In the right pane, double-click a send or receive handler in the right pane.</span></span>  
  
5.  <span data-ttu-id="6f6ba-112">En el **propiedades de controlador de adaptador** cuadro de diálogo, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-112">In the **Adapter Handler Properties** dialog box, click **Properties**.</span></span>  
  
6.  <span data-ttu-id="6f6ba-113">En el **propiedades de transporte MQSeries** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f6ba-113">In the **MQSeries Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6f6ba-114">Use</span><span class="sxs-lookup"><span data-stu-id="6f6ba-114">Use this</span></span>|<span data-ttu-id="6f6ba-115">Para</span><span class="sxs-lookup"><span data-stu-id="6f6ba-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6f6ba-116">**Número máximo de mensajes en lote**</span><span class="sxs-lookup"><span data-stu-id="6f6ba-116">**Maximum Messages in Batch**</span></span>|<span data-ttu-id="6f6ba-117">Definir el número máximo de mensajes en un lote.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-117">Set the maximum number of messages in a batch.</span></span> <span data-ttu-id="6f6ba-118">Sólo se aplica al controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-118">Applies only to the send handler.</span></span>|  
    |<span data-ttu-id="6f6ba-119">**Server**</span><span class="sxs-lookup"><span data-stu-id="6f6ba-119">**Server**</span></span>|<span data-ttu-id="6f6ba-120">Nombre del equipo que ejecuta MQSeries Server para Windows.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-120">The name of the computer that is running MQSeries Server for Windows.</span></span>|  
  
7.  <span data-ttu-id="6f6ba-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-121">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f6ba-122">Las propiedades de puerto de envío y ubicación de recepción invalidan los valores de los controladores de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-122">The Receive Location and Send Port properties override the Receive Handler and Send Handler values.</span></span> <span data-ttu-id="6f6ba-123">Si las propiedades del puerto de envío y la ubicación de recepción no tienen valores, el adaptador utiliza los valores del controlador de envío y recepción respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-123">If there is no value for the Receive Location or Send Port properties, the adapter uses the Receive Handler and Send Handler values respectively.</span></span>  
  
8.  <span data-ttu-id="6f6ba-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f6ba-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f6ba-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f6ba-125">See Also</span></span>  
 <span data-ttu-id="6f6ba-126">[Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="6f6ba-126">[How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span></span>  
 [<span data-ttu-id="6f6ba-127">Configurar el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="6f6ba-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)