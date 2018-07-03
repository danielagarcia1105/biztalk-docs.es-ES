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
# <a name="how-to-create-a-new-gateway-node"></a>Cómo crear un nodo de puerta de enlace nuevo
Siga los pasos que se detallan a continuación y configure un nodo de puerta de enlace nuevo en PeopleSoft Enterprise.  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>Para crear y configurar un nuevo nodo de puerta de enlace  
  
1. En PeopleSoft, en el panel izquierdo, haga clic en el **Node Definitions** vínculo.  
  
2. Haga clic en el **agregar un nuevo valor** ficha.  
  
3. En el **nombre de nodo** , introduzca `MSEXTERNAL`y, a continuación, haga clic en **agregar**.  
  
4. Haga clic en el **nodo** pestaña y escriba la siguiente información:  
  
   1. **Descripción:** escriba una descripción para el nodo.  
  
   2. **Tipo de nodo:** seleccione **externo**.  
  
   3. **Tipo de enrutamiento:** seleccione **implícita**.  
  
      ![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")  
  
5. Haga clic en el **conectores** pestaña y escriba la siguiente información:  
  
   1. **Id. de puerta de enlace:** escriba `LOCAL`.  
  
   2. **Id. de conector:** escriba `HTTPTARGET`.  
  
      ![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")  
  
6. Haga clic en el **búsqueda** icono.  
  
7. En **Id. de conector**, haga clic en el **HTTPTARGET** vínculo.  
  
    ![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")  
  
8. En el **propiedades** , escriba la siguiente información:  
  
   1.  **Encabezado:** escriba `Y`.  
  
   2.  **HTTPPROPERTY:** escriba `POST`.  
  
   3.  **PrimaryURL:** escriba la dirección IP y puerto del equipo de destino (el equipo de desarrollo).  
  
   > [!NOTE]
   >  El **puerto de recepción** se configuró anteriormente.  
  
    ![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")  
  
## <a name="see-also"></a>Vea también  
 [Creación de puertos y hosts HTTP de PeopleSoft](../core/creating-a-peoplesoft-http-host-and-port.md)