---
title: "Actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema de estrella | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 319caa26-1292-4453-a316-efca4fbffdb6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184ab156770b0a62208a8e24c7870afa43d3a128
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a>Actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema en estrella
Si ha realizado una copia de seguridad de la base de datos de análisis de SAE, podrá restaurar la copia de seguridad en un equipo distinto y cambiar el nombre a esa copia de seguridad en el caso de que se produzca un error de datos o del sistema.  
  
 Para restaurar las bases de datos de análisis de BAM y el esquema de estrella, siga los pasos descritos en [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md). Además, debe actualizar la implementación de BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] paquetes de Integration Services (SSIS) con el nuevo nombre del servidor y el nombre de la base de datos.  
  
## <a name="how-to-update-references-to-bam-analysis-server-and-star-schema-database-names"></a>Cómo actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema de estrella  
 Para obtener instrucciones sobre cómo actualizar referencias a las bases de datos del servidor de análisis de BAM, consulte [actualizar referencias a la nueva base de datos de análisis de BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate). Para obtener instrucciones sobre cómo actualizar referencias a las bases de datos de esquema de estrella de BAM, consulte [actualizar referencias a la base de datos de esquema de estrella de BAM nueva](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate).