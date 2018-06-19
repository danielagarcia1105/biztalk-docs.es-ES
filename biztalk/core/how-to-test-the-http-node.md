---
title: Cómo probar el nodo HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP node, testing
- testing HTTP node
ms.assetid: f6881e8f-9f92-4312-bb5e-06bbfb9fe0bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2790a4e3fa0ff1ed9a9b9b0c2018108c9cbb1282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255532"
---
# <a name="how-to-test-the-http-node"></a>Cómo probar el nodo HTTP
Para probar el nodo HTTP, siga estos pasos:  
  
### <a name="to-test-the-http-node"></a>Para probar el nodo HTTP  
  
1.  En PeopleSoft Enterprise, vaya a **PeopleTools**, **Integration Broker**, **Monitor**, **Monitor Message**.  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  Haga clic en el **estado del nodo** ficha.  
  
3.  En el **Message Node Name** , escriba `MSEXTERNAL`y, a continuación, haga clic en el **búsqueda** icono.  
  
4.  En **Message Node Name**, seleccione **MSEXTERNAL**.  
  
     Aparecerá un mensaje que indica que PeopleSoft se está comunicando a través de HTTP.  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     Si no recibe el mensaje, compruebe que:  
  
    1.  Los puertos y las direcciones IP coinciden con el puerto de recepción y el nodo.  
  
    2.  BizTalk Server se está ejecutando.  
  
## <a name="see-also"></a>Vea también  
 [Crear un Host de HTTP de PeopleSoft y puerto](../core/creating-a-peoplesoft-http-host-and-port.md)