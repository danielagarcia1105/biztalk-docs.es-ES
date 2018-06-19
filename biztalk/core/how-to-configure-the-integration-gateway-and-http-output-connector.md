---
title: Cómo configurar la puerta de enlace de integración y el conector de salida HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Integration Gateway
- gateway nodes, creating
- HTTP Output Connector
ms.assetid: a02ee533-07a8-42fa-a72a-7e5359b18f40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acfa52be85a664432af95af0ca292e9cc394c6ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247924"
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a><span data-ttu-id="6076d-102">Cómo configurar la puerta de enlace de integración y el conector de salida HTTP</span><span class="sxs-lookup"><span data-stu-id="6076d-102">How to Configure the Integration Gateway and HTTP Output Connector</span></span>
<span data-ttu-id="6076d-103">Para configurar la puerta de enlace de integración y el conector de salida HTTP, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6076d-103">Follow these steps to configure the Integration Gateway and HTTP Output Connector.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="6076d-104">Para crear y configurar un nuevo nodo de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="6076d-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="6076d-105">En un explorador Web, abra la aplicación PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="6076d-105">In a Web browser, open the PeopleSoft application.</span></span>  
  
2.  <span data-ttu-id="6076d-106">Busque **PeopleTools**, seleccione **Integration Broker**y, a continuación, seleccione **puertas de enlace**.</span><span class="sxs-lookup"><span data-stu-id="6076d-106">Locate **PeopleTools**, select **Integration Broker**, and then select **Gateways**.</span></span>  
  
3.  <span data-ttu-id="6076d-107">En el **Search By** , escriba `LOCAL`y, a continuación, haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="6076d-107">In the **Search By** field, type `LOCAL`, and then click **Search**.</span></span>  
  
     ![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")  
  
4.  <span data-ttu-id="6076d-108">Escriba `machine-name/PSIGW/PeopleSoftListeningConnector` en el **dirección URL de la puerta de enlace** entrada.</span><span class="sxs-lookup"><span data-stu-id="6076d-108">Enter `machine-name/PSIGW/PeopleSoftListeningConnector` into the **Gateway URL** entry.</span></span>  
  
     ![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")  
  
5.  <span data-ttu-id="6076d-109">Haga clic en **actualizar**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="6076d-109">Click **Refresh**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="6076d-110">Haga clic en el **propiedades** de vínculos para **HTTPTARGET** para ver la combinación de propiedades/valores para ese identificador.</span><span class="sxs-lookup"><span data-stu-id="6076d-110">Click the **Properties** link for **HTTPTARGET** to view the properties/value combination for that ID.</span></span>  
  
     <span data-ttu-id="6076d-111">La URL puede configurarla aquí o en la definición de nodo.</span><span class="sxs-lookup"><span data-stu-id="6076d-111">You can set the URL here, or at the Node Definition.</span></span> <span data-ttu-id="6076d-112">Para este tema, establezca la URL en el nivel de nodo.</span><span class="sxs-lookup"><span data-stu-id="6076d-112">For this discussion, set the URL at the Node level.</span></span>  
  
     ![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")  
  
## <a name="see-also"></a><span data-ttu-id="6076d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6076d-113">See Also</span></span>  
 [<span data-ttu-id="6076d-114">Crear un Host de HTTP de PeopleSoft y puerto</span><span class="sxs-lookup"><span data-stu-id="6076d-114">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)