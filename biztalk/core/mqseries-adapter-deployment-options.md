---
title: Opciones de implementación del adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88fa674c38df8b31c1954234846fd3939ed8568
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263020"
---
# <a name="mqseries-adapter-deployment-options"></a>Opciones de implementación del adaptador de MQSeries
El adaptador de MQSeries le ofrece una gran flexibilidad a la hora de configurar su hardware. Al menos hay tres patrones principales de uso:  
  
-   BizTalk Server, el adaptador y MQSeries Server para Windows en el mismo equipo.  
  
-   BizTalk Server y el adaptador en un equipo, y MQSeries Server para Windows (incluido MQSAgent) en otro equipo que se conecta a uno o más equipos adicionales que ejecutan MQSeries Server.  
  
-   Varias instalaciones de BizTalk Server en un grupo y el adaptador, y MQSeries Server (que incluye MQSAgent) en otro equipo diferente.  
  
-   El adaptador funciona perfectamente si agrupa MQSeries Server y los administradores de colas de MQSeries.  
  
    > [!NOTE]
    >  En este caso, la aplicación MQSAgent COM+ no se debería agrupar. En su lugar, los nodos del clúster deberían tener instalada y configurada la aplicación MQSAgent COM+. En este escenario, si la aplicación MQSAgent COM+ se detiene, la siguiente llamada del cliente la reiniciará.  
  
## <a name="see-also"></a>Vea también  
 [Uso del adaptador de MQSeries](../core/using-the-mqseries-adapter.md)