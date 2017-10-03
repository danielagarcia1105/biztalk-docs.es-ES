---
title: Restaurar bases de datos no incluidos en el trabajo de copia de seguridad de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7141980-d4a6-4409-be9b-c94a7f733376
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3277886207e04a30fec8bb61f29b5fe8c5ec3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a>Restaurar bases de datos que no se incluye en el trabajo de copia de seguridad de BizTalk Server
En esta sección se describe cómo restaurar las bases de datos que forman parte de la solución general de BizTalk, pero no están respaldados por el trabajo de copia de seguridad de BizTalk Server. Se copiarán todas las bases de datos que forman parte de una solución de BizTalk con el trabajo de copia de seguridad de BizTalk Server excepto los siguientes:  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Bases de datos de Analysis Services  
  
-   Bases de datos BAM cuando BAM está habilitada y configurada mediante BM.exe  
  
 Esta sección también describe cómo actualizar referencias de base de datos después de restaurar las bases de datos enumerados anteriormente e incluye información acerca de cómo resolver instancias incompletas de actividad BAM.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Restaurar los servicios de análisis y compatibilidad con bases de datos](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [Actualizar referencias de base de datos](../technical-guides/updating-database-references.md)  
  
-   [Cómo resolver instancias de actividad BAM incompleta](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)