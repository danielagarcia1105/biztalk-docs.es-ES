---
title: Restaurar el grupo de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12a1deff8fea6d769f138aa34bf6dab269a167f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-the-biztalk-group"></a>Restaurar el grupo de BizTalk
El grupo de BizTalk está representado por el conjunto de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las bases de datos de Analysis Services, paquetes SSIS y trabajos del Agente SQL. En esta sección se describe el proceso para restaurar el grupo de BizTalk.  
  
 En caso de que se requiere un cambio en el sistema de destino (sitio de recuperación ante desastres), deben completar los pasos siguientes:  
  
1.  Restaurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y bases de datos de Analysis Services.  
  
2.  Restaurar [!INCLUDE[prague](../includes/prague-md.md)] en tiempo de ejecución servidores y aplicaciones.  
  
 En la realización de estos pasos, el grupo de BizTalk se ha establecido en el sitio de recuperación ante desastres, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden configurar servidores de tiempo de ejecución y las aplicaciones pueden implementarse en el grupo de BizTalk. Los temas de esta sección tratan los detalles de este proceso.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Detener el proceso en el sistema de origen de la aplicación](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [Cómo restaurar las bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [Restaurar bases de datos que no se incluye en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)