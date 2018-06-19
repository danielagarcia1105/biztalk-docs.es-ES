---
title: Cómo crear un nuevo nodo de puerta de enlace | Documentos de Microsoft
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
ms.openlocfilehash: b371243d58389415349d5a88c05b7bf312e70ef9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249388"
---
# <a name="how-to-create-a-new-gateway-node"></a><span data-ttu-id="404a6-102">Cómo crear un nodo de puerta de enlace nuevo</span><span class="sxs-lookup"><span data-stu-id="404a6-102">How to Create a New Gateway Node</span></span>
<span data-ttu-id="404a6-103">Siga los pasos que se detallan a continuación y configure un nodo de puerta de enlace nuevo en PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="404a6-103">Follow these steps to create and configure a new Gateway node in PeopleSoft Enterprise.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="404a6-104">Para crear y configurar un nuevo nodo de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="404a6-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="404a6-105">En PeopleSoft, en el panel izquierdo, haga clic en el **definiciones del nodo** vínculo.</span><span class="sxs-lookup"><span data-stu-id="404a6-105">In PeopleSoft, on the left panel, click the **Node Definitions** link.</span></span>  
  
2.  <span data-ttu-id="404a6-106">Haga clic en el **agregar un nuevo valor** ficha.</span><span class="sxs-lookup"><span data-stu-id="404a6-106">Click the **Add a New Value** tab.</span></span>  
  
3.  <span data-ttu-id="404a6-107">En el **nombre de nodo** , escriba `MSEXTERNAL`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="404a6-107">In the **Node Name** field, enter `MSEXTERNAL`, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="404a6-108">Haga clic en el **nodo** pestaña y escriba la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="404a6-108">Click the **Node** tab, and enter the following information:</span></span>  
  
    1.  <span data-ttu-id="404a6-109">**Descripción:** escriba una descripción para el nodo.</span><span class="sxs-lookup"><span data-stu-id="404a6-109">**Description:** Enter a description for the node.</span></span>  
  
    2.  <span data-ttu-id="404a6-110">**Tipo de nodo:** seleccione **externo**.</span><span class="sxs-lookup"><span data-stu-id="404a6-110">**Node Type:** Select **External**.</span></span>  
  
    3.  <span data-ttu-id="404a6-111">**Tipo de enrutamiento:** seleccione **implícita**.</span><span class="sxs-lookup"><span data-stu-id="404a6-111">**Routing Type:** Select **Implicit**.</span></span>  
  
     ![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")  
  
5.  <span data-ttu-id="404a6-112">Haga clic en el **conectores** pestaña y escriba la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="404a6-112">Click the **Connectors** tab, and enter the following information:</span></span>  
  
    1.  <span data-ttu-id="404a6-113">**Id. de puerta de enlace:** escriba `LOCAL`.</span><span class="sxs-lookup"><span data-stu-id="404a6-113">**Gateway ID:** Enter `LOCAL`.</span></span>  
  
    2.  <span data-ttu-id="404a6-114">**Id. de conector:** escriba `HTTPTARGET`.</span><span class="sxs-lookup"><span data-stu-id="404a6-114">**Connector ID:** Enter `HTTPTARGET`.</span></span>  
  
     ![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")  
  
6.  <span data-ttu-id="404a6-115">Haga clic en el **búsqueda** icono.</span><span class="sxs-lookup"><span data-stu-id="404a6-115">Click the **Lookup** icon.</span></span>  
  
7.  <span data-ttu-id="404a6-116">En **Id. del conector**, haga clic en el **HTTPTARGET** vínculo.</span><span class="sxs-lookup"><span data-stu-id="404a6-116">Under **Connector ID**, click the **HTTPTARGET** link.</span></span>  
  
     ![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")  
  
8.  <span data-ttu-id="404a6-117">En el **propiedades** ficha, escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="404a6-117">On the **Properties** tab, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="404a6-118">**Encabezado:** escriba `Y`.</span><span class="sxs-lookup"><span data-stu-id="404a6-118">**Header:** Enter `Y`.</span></span>  
  
    2.  <span data-ttu-id="404a6-119">**HTTPPROPERTY:** escriba `POST`.</span><span class="sxs-lookup"><span data-stu-id="404a6-119">**HTTPPROPERTY:** Enter `POST`.</span></span>  
  
    3.  <span data-ttu-id="404a6-120">**PrimaryURL:** escriba la dirección IP y el puerto del equipo de destino (el equipo de desarrollo).</span><span class="sxs-lookup"><span data-stu-id="404a6-120">**PrimaryURL:** Enter the IP address and port of the target computer (the development computer).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="404a6-121">El **puerto de recepción** se ha establecido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="404a6-121">The **Receive Port** was previously set.</span></span>  
  
     ![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")  
  
## <a name="see-also"></a><span data-ttu-id="404a6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="404a6-122">See Also</span></span>  
 [<span data-ttu-id="404a6-123">Crear un Host de HTTP de PeopleSoft y puerto</span><span class="sxs-lookup"><span data-stu-id="404a6-123">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)