---
title: Restaurar el grupo de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9bea20bacdd6b681d39e2bf3995d7626b9b1f63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021644"
---
# <a name="restoring-the-biztalk-group"></a>Restaurar el grupo de BizTalk
El grupo de BizTalk está representado por el conjunto de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de Analysis Services, paquetes SSIS y trabajos del Agente SQL. En esta sección se describe el proceso para restaurar el grupo de BizTalk.  
  
 En caso de que se requiere un cambio en el sistema de destino (sitio de recuperación ante desastres), deben completar los pasos siguientes:  
  
1. Restaurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y bases de datos de Analysis Services.  
  
2. Restaurar las aplicaciones y los servidores en tiempo de ejecución de BizTalk Server.  
  
   Tras la finalización de estos pasos, el grupo de BizTalk se estableció en el sitio de recuperación ante desastres, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden configurar los servidores en tiempo de ejecución y las aplicaciones pueden implementarse en el grupo de BizTalk. Los temas de esta sección explican los detalles de este proceso.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Detener el procesamiento de aplicaciones en el sistema de origen](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [Cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [Restauración de bases de datos que no se incluyen en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)