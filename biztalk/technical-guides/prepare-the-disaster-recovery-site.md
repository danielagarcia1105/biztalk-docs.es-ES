---
title: "Preparar el sitio de recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a60be6d04d0f73013f67c5fe8e5b0144357fd1f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="prepare-the-disaster-recovery-site"></a>Preparar el sitio de recuperación ante desastres
Registro de BizTalk Server envío tiene dos escenarios admitidos. Uno es donde inician sesión envío para todas las bases de datos en todas las instancias de producción de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se aplica a una instancia de la recuperación ante desastres única de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. El otro escenario es donde trasvase de registros de las bases de datos para cada instancia de producción de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se aplica a una instancia correspondiente de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en el sitio de recuperación ante desastres. Tenga en cuenta que es totalmente compatible para que tenga el mismo número de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias en el sitio de recuperación ante desastres de bases de datos porque hay en producción, pero en menos servidores físicos. Esta sección proporciona instrucciones sobre estos preparativos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Preparación de los servidores SQL Server de recuperación ante desastres](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [Realizar una copia de seguridad de las bases de datos de servidor de análisis de seguimiento y de análisis de BAM](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [Preparación de los servidores de BizTalk de recuperación ante desastres](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [Preparación de las aplicaciones para la recuperación ante desastres](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [Cómo restaurar el servidor de secreto maestro](../technical-guides/how-to-restore-the-master-secret-server.md)