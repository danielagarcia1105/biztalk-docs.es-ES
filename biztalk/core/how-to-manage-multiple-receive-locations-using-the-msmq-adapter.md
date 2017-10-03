---
title: "Cómo administrar varias ubicaciones de recepción mediante el adaptador de MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72438551d2ecab09b918808d43e7d7de6d600677
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a>Cómo administrar varias ubicaciones de recepción mediante el adaptador de MSMQ
Para aumentar su rendimiento, el adaptador de MSMQ es multiproceso. Cuando se han definido muchas ubicaciones de recepción, puede que no haya suficientes subprocesos disponibles para todas estas ubicaciones. Esto impide que algunas de las ubicaciones de recepción recojan mensajes. Existen tres formas de solucionar este problema:  
  
-   Agregar hosts de BizTalk a su equipo y distribuir las ubicaciones de recepción entre los hosts. La adición de hosts resulta en más subprocesos disponibles para las ubicaciones de recepción.  
  
-   Establecer el **procesamiento en serie** propiedad `True` en cada ubicación de recepción. Cuando esta propiedad se define como `True`, se asigna un solo subproceso a cada ubicación de recepción. Esto deja más subprocesos disponibles en el grupo. No obstante, también esto puede provocar una disminución del rendimiento.  
  
-   Modificar el Registro para aumentar el número de subprocesos disponibles para el host del controlador de recepción del adaptador de MSMQ. Para obtener más información, consulte el **modificar los valores de subprocesos que alojan CLR para el host** sección de [parámetros de configuración que afectan al rendimiento del adaptador](../core/configuration-parameters-that-affect-adapter-performance.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador MSMQ](../core/configuring-the-msmq-adapter.md)