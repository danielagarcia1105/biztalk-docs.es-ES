---
title: Restauración de Analysis Services y bases de datos auxiliares | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf50a7ef1903d3839aaa9b810e145432b62b552
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020465"
---
# <a name="restoring-analysis-services-and-supporting-databases"></a>Restauración de Analysis Services y que admiten las bases de datos
Hay dos [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de Analysis Services que deben restaurarse en un escenario de recuperación ante desastres:  
  
- Análisis de BAM (BAMAnalysis)  
  
- Servidor de análisis de seguimiento (BizTalkAnalysisdb)  
  
  Implementación de BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos pueden ser una copia de seguridad como parte del trabajo de copia de seguridad de BizTalk Server si BAM está habilitado pero no configurado.  
  
> [!NOTE]  
>  La base de datos de importación principal de BAM siempre se copia como parte del trabajo de copia de seguridad de BizTalk Server porque participa en transacciones DTC.  
  
 Las siguientes bases de datos BAM será parte del trabajo de copia de seguridad de BizTalk Server si está habilitada pero no se ha configurado BAM:  
  
- BAMStarSchema  
  
- BAMArchive  
  
  Siga los pasos de [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) para restaurar estas bases de datos.  
  
  **En caso contrario,**  
  **Si BAM está habilitada y también se configura con BM.exe, el conjunto correcto de las bases de datos BAM debe restaurarse juntos como un conjunto.** Para asegurarse de que se recupera un conjunto completo de los datos archivados, la base de datos de archivo de BAM es una copia de seguridad después de la partición se copia en el archivo de BAM, pero antes de elimina la partición de la base de datos de importación principal de BAM. Esto se realiza modificando el paquete SSIS de mantenimiento de datos para cada actividad insertando un paso para realizar copias de seguridad de la base de datos de archivo de BAM antes de que el último paso "Finalizar archivo".  
  
  El procedimiento de restauración para las bases de datos BAM es: si se restaura la base de datos de importación principal de BAM con la última fecha de copia de seguridad de x, restaure las copias de las bases de datos de archivo de BAM y el esquema de estrella de BAM que corresponden a la fecha más reciente en el paquete SSIS de mantenimiento de datos se ejecutar antes de la fecha de x.  
  
  Después de haber identificado el conjunto correcto de las bases de datos BAM, restaure el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos de Analysis Services mediante procedimientos estándares, tal como se describe en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla para restaurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Bases de datos de analysis Services.  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad de las bases de datos de servidor de análisis de seguimiento y de análisis de BAM](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)