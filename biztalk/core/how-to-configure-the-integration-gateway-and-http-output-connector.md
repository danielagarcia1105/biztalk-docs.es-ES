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
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a>Cómo configurar la puerta de enlace de integración y el conector de salida HTTP
Para configurar la puerta de enlace de integración y el conector de salida HTTP, siga estos pasos.  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>Para crear y configurar un nuevo nodo de puerta de enlace  
  
1.  En un explorador Web, abra la aplicación PeopleSoft.  
  
2.  Busque **PeopleTools**, seleccione **Integration Broker**y, a continuación, seleccione **puertas de enlace**.  
  
3.  En el **Search By** , escriba `LOCAL`y, a continuación, haga clic en **búsqueda**.  
  
     ![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")  
  
4.  Escriba `machine-name/PSIGW/PeopleSoftListeningConnector` en el **dirección URL de la puerta de enlace** entrada.  
  
     ![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")  
  
5.  Haga clic en **actualizar**y, a continuación, haga clic en **guardar**.  
  
6.  Haga clic en el **propiedades** de vínculos para **HTTPTARGET** para ver la combinación de propiedades/valores para ese identificador.  
  
     La URL puede configurarla aquí o en la definición de nodo. Para este tema, establezca la URL en el nivel de nodo.  
  
     ![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")  
  
## <a name="see-also"></a>Vea también  
 [Crear un Host de HTTP de PeopleSoft y puerto](../core/creating-a-peoplesoft-http-host-and-port.md)