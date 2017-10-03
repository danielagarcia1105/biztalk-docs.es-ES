---
title: "Paso 3B: enlazar la orquestación con el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb973066-8797-4f51-a89e-3845f2811605
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10111de1080aacd532be96f501be1d20acda1dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>Paso 3B: enlazar la orquestación con el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 3A: crear una orquestación para el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md).  
  
### <a name="to-add-a-file-receive-location"></a>Para agregar una ubicación de recepción de archivos  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, en el panel izquierdo, expanda Administración de BizTalk Server, **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **instancias de Host** . Compruebe que el estado de la **BizTalkServerApplication** hospedar la instancia y la instancia de FileActhost es **ejecutando**. Si no es así, haga clic en las instancias de host y haga clic en **iniciar**.  
  
3.  En el panel izquierdo, expanda aplicaciones y, a continuación, expanda BizTalk Application 1. Haga clic en orquestaciones.  
  
4.  Haga clic en **DynamicSendOrchestration** y haga clic en **propiedades**.  
  
5.  En el **propiedades de orquestación** cuadro de diálogo, en el panel izquierdo, haga clic en **enlaces** y realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Host**|En la lista desplegable, seleccione **aplicación de servidor BizTalk Server**.|  
    |**Extracción dinámica**|En la lista desplegable, seleccione **Tutorial_FA_DynamicSendPort**.|  
    |**SendPullResponseToSender**|En la lista desplegable, seleccione **Tutorial_FA_SendPullResponsetoReceiver**.|  
  
## <a name="see-also"></a>Vea también  
 [Paso 3A: crear una orquestación para el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)