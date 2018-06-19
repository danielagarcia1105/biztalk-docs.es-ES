---
title: Directrices de ajuste de tamaño de la base de datos de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, performance
- Tracking database, size
- Tracking Analysis Server database [BAM]
- performance, Tracking database
ms.assetid: 2188bee5-c0dd-4448-bd4a-4ffb2a0c79f1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c0293ff0a03583e51ee447ec1bd6283f1b02164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279700"
---
# <a name="tracking-database-sizing-guidelines"></a>Instrucciones para ajustar el tamaño de la base de datos de seguimiento
Esta sección describen las consideraciones de tamaño de la base de datos de seguimiento de BizTalk (BizTalkDTADb) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Explica cómo utilizar ecuaciones y variables de mensaje para determinar el tamaño que alcanzará la base de datos de seguimiento de BizTalk durante un determinado período de tiempo y proporciona ejemplos específicos sobre cómo aplicar las ecuaciones. Esto proporciona la correlación aproximada entre los mensajes de BizTalk, la configuración de seguimiento y el tamaño de la base de datos de seguimiento. No tiene en cuenta otros factores del servidor SQL Server como el tamaño del índice en las tablas de seguimiento; considere la posibilidad de utilizar multiplicadores razonables para contabilizar dichos factores.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a>Vea también  
 [Tamaño del registro en las bases de datos de seguimiento](../core/record-size-in-tracking-databases.md)   
 [Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)