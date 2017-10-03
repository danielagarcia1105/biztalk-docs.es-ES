---
title: "Restaurar los servicios de análisis y compatibilidad con bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da16bde7b69071b71b794c4c46407feab3ef4512
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-analysis-services-and-supporting-databases"></a>Restaurar los servicios de análisis y compatibilidad con bases de datos
Hay dos [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de Analysis Services que deben restaurarse en un escenario de recuperación ante desastres:  
  
-   Análisis de BAM (BAMAnalysis)  
  
-   Servidor de análisis de seguimiento (BizTalkAnalysisdb)  
  
 Implementación de BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] copia bases de datos pueden ser como parte del trabajo de copia de seguridad de BizTalk Server si BAM está habilitada pero no configurado.  
  
> [!NOTE]  
>  La base de datos de importación principal de BAM siempre se copia como parte del trabajo de copia de seguridad de BizTalk Server porque participa en transacciones DTC.  
  
 Las siguientes bases de datos BAM va a formar parte del trabajo de copia de seguridad de BizTalk Server si BAM está habilitada pero no configurado:  
  
-   BAMStarSchema  
  
-   BAMArchive  
  
 Siga los pasos de [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) restaurar estas bases de datos.  
  
 **En caso contrario,**  
 **Si BAM está habilitada y también se configura con BM.exe, el conjunto correcto de las bases de datos BAM debe restaurarse conjuntamente como un conjunto.** Para asegurarse de que se recuperará un conjunto completo de los datos archivados, la base de datos de archivo de BAM se copia después de la partición se copia en el archivo de BAM, pero antes de que la partición se elimina de la base de datos de importación principal de BAM. Esto se realiza mediante la modificación del paquete SSIS de mantenimiento de datos para cada actividad insertando un paso para realizar una copia de la base de datos de archivo de BAM antes de que el último paso "Finalizar archivo".  
  
 El procedimiento de restauración para las bases de datos BAM es: si se restaura la base de datos de importación principal de BAM con la última fecha de copia de seguridad de x, restaure las copias de las bases de datos de archivo de BAM y esquema de estrella de BAM que corresponden a la fecha más reciente, ¿cuándo fue el paquete SSIS de mantenimiento de datos ejecutar antes de la fecha de x.  
  
 Después de haber identificado el conjunto correcto de las bases de datos BAM, restaurar la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de Analysis Services mediante procedimientos estándares tal como se describe en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla para restaurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Bases de datos de analysis Services.  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad el análisis BAM y las bases de datos del servidor de análisis de seguimiento](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)