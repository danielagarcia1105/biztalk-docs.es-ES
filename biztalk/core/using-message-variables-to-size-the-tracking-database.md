---
title: Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message variables [Tracking database], CMsgs
- message variables [Tracking database], Events
- message variables [Tracking database], Properties
- Tracking database, database size
- message variables [Tracking database], Nserv
- message variables [Tracking database], Msgs
- message variables [Tracking database], PropSize
- message variables [Tracking database]
- message variables [Tracking database], MsgSize
- message variables [Tracking database], MsgNum
- Tracking database, messages
ms.assetid: 2d31ae25-3d16-4002-b5a5-dca25e764ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5418cdf79499302e6127db7fb66f108825a0d8c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287844"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a>Usar variables de mensaje para determinar el tamaño de la base de datos de seguimiento
En Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede utilizar una serie de variables para determinar el tamaño que alcanzará la base de datos de seguimiento de BizTalk (BizTalkDTADb) durante un determinado período de tiempo. Estas variables son:  
  
-   Número de canalizaciones utilizadas  
  
-   Número de orquestaciones empleadas  
  
-   Número de eventos generados  
  
-   Número de propiedades de mensaje sometidas a seguimiento  
  
-   Número de mensajes adicionales creados  
  
-   Estimación del número de mensajes recibidos en el margen de tiempo especificado  
  
 Aunque la ecuación que se utiliza para estimar el tamaño de la base de datos de seguimiento de BizTalk es sencilla, deberá aplicarla a todos los procesos de mensajes entrantes y salientes que utilicen la implementación de BizTalk Server. Es decir, tendrá que aplicar esta ecuación a cada escenario de mensajes distinto y sumar los resultados para obtener el tamaño de base de datos final estimado. En este documento, analizaremos dos escenarios. Estos escenarios son:  
  
1.  Recibir un mensaje, transformarlo y enviar el mensaje resultante.  
  
2.  Recibir un mensaje, ejecutar un proceso empresarial usando el mensaje y enviar el mensaje resultante.  
  
 Puede que ambos escenarios estén presentes en una misma instalación de BizTalk Server y que cada uno de ellos genere un volumen de datos de seguimiento diferente. El total de datos de seguimiento generados en la instalación de BizTalk Server es la suma de todos los escenarios.  
  
 Éstas son algunas de las variables que se utilizan en la ecuación:  
  
|Variable|Description|  
|--------------|-----------------|  
|**Nserv**|Número de servicios (número de canalizaciones + número de orquestaciones)|  
|**Eventos**|Número de eventos de mensaje generados|  
|**Propiedades**|Número de propiedades de mensaje sometidas a seguimiento|  
|**PropSize**|Tamaño (en bytes) de la propiedad promovida (campo)|  
|**CMsgs**|Número de mensajes adicionales creados por cada mensaje entrante|  
|**Mensajes**|Estimación del número de mensajes entrantes en un período determinado|  
|**MsgSize**|Tamaño del mensaje|  
|**MsgNum**|Número de mensajes sometidos a seguimiento por cada mensaje entrante|  
  
 La ecuación es la siguiente:  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 Esta ecuación calcula únicamente los datos de seguimiento que generan los mensajes, no incluye los que se generan para el Depurador de orquestaciones. Debe aplicar esta fórmula a cada proceso de mensaje para estimar el tamaño de la base de datos de seguimiento de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)