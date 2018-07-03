---
title: Cómo crear un nuevo nodo de puerta de enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- gateway nodes, creating
ms.assetid: e7c5f9a7-a58e-4661-9cb5-2414e31a57a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c26dd33fcdc4bd8ad43f03ef3fff6d006480a1c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976165"
---
# <a name="how-to-create-a-new-gateway-node"></a><span data-ttu-id="0bc9f-102">Cómo crear un nodo de puerta de enlace nuevo</span><span class="sxs-lookup"><span data-stu-id="0bc9f-102">How to Create a New Gateway Node</span></span>
<span data-ttu-id="0bc9f-103">Siga los pasos que se detallan a continuación y configure un nodo de puerta de enlace nuevo en PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-103">Follow these steps to create and configure a new Gateway node in PeopleSoft Enterprise.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="0bc9f-104">Para crear y configurar un nuevo nodo de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="0bc9f-104">To create and configure a new gateway node</span></span>  
  
1. <span data-ttu-id="0bc9f-105">En PeopleSoft, en el panel izquierdo, haga clic en el **Node Definitions** vínculo.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-105">In PeopleSoft, on the left panel, click the **Node Definitions** link.</span></span>  
  
2. <span data-ttu-id="0bc9f-106">Haga clic en el **agregar un nuevo valor** ficha.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-106">Click the **Add a New Value** tab.</span></span>  
  
3. <span data-ttu-id="0bc9f-107">En el **nombre de nodo** , introduzca `MSEXTERNAL`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-107">In the **Node Name** field, enter `MSEXTERNAL`, and then click **Add**.</span></span>  
  
4. <span data-ttu-id="0bc9f-108">Haga clic en el **nodo** pestaña y escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="0bc9f-108">Click the **Node** tab, and enter the following information:</span></span>  
  
   1. <span data-ttu-id="0bc9f-109">**Descripción:** escriba una descripción para el nodo.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-109">**Description:** Enter a description for the node.</span></span>  
  
   2. <span data-ttu-id="0bc9f-110">**Tipo de nodo:** seleccione **externo**.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-110">**Node Type:** Select **External**.</span></span>  
  
   3. <span data-ttu-id="0bc9f-111">**Tipo de enrutamiento:** seleccione **implícita**.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-111">**Routing Type:** Select **Implicit**.</span></span>  
  
      <span data-ttu-id="0bc9f-112">![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")</span><span class="sxs-lookup"><span data-stu-id="0bc9f-112">![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")</span></span>  
  
5. <span data-ttu-id="0bc9f-113">Haga clic en el **conectores** pestaña y escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="0bc9f-113">Click the **Connectors** tab, and enter the following information:</span></span>  
  
   1. <span data-ttu-id="0bc9f-114">**Id. de puerta de enlace:** escriba `LOCAL`.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-114">**Gateway ID:** Enter `LOCAL`.</span></span>  
  
   2. <span data-ttu-id="0bc9f-115">**Id. de conector:** escriba `HTTPTARGET`.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-115">**Connector ID:** Enter `HTTPTARGET`.</span></span>  
  
      <span data-ttu-id="0bc9f-116">![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")</span><span class="sxs-lookup"><span data-stu-id="0bc9f-116">![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")</span></span>  
  
6. <span data-ttu-id="0bc9f-117">Haga clic en el **búsqueda** icono.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-117">Click the **Lookup** icon.</span></span>  
  
7. <span data-ttu-id="0bc9f-118">En **Id. de conector**, haga clic en el **HTTPTARGET** vínculo.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-118">Under **Connector ID**, click the **HTTPTARGET** link.</span></span>  
  
    <span data-ttu-id="0bc9f-119">![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")</span><span class="sxs-lookup"><span data-stu-id="0bc9f-119">![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")</span></span>  
  
8. <span data-ttu-id="0bc9f-120">En el **propiedades** , escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="0bc9f-120">On the **Properties** tab, enter the following information:</span></span>  
  
   1.  <span data-ttu-id="0bc9f-121">**Encabezado:** escriba `Y`.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-121">**Header:** Enter `Y`.</span></span>  
  
   2.  <span data-ttu-id="0bc9f-122">**HTTPPROPERTY:** escriba `POST`.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-122">**HTTPPROPERTY:** Enter `POST`.</span></span>  
  
   3.  <span data-ttu-id="0bc9f-123">**PrimaryURL:** escriba la dirección IP y puerto del equipo de destino (el equipo de desarrollo).</span><span class="sxs-lookup"><span data-stu-id="0bc9f-123">**PrimaryURL:** Enter the IP address and port of the target computer (the development computer).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0bc9f-124">El **puerto de recepción** se configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0bc9f-124">The **Receive Port** was previously set.</span></span>  
  
    <span data-ttu-id="0bc9f-125">![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")</span><span class="sxs-lookup"><span data-stu-id="0bc9f-125">![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc9f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bc9f-126">See Also</span></span>  
 [<span data-ttu-id="0bc9f-127">Creación de puertos y hosts HTTP de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="0bc9f-127">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)