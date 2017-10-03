---
title: "Actualizar las referencias a la base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3da3b545-0d81-491b-bc37-0a980a7814b6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba37a32c82967e84b61bb46c58c62af9bf23b1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update-references-to-the-bam-primary-import-database"></a>Actualizar las referencias a la base de datos de importación principal de BAM
Si ha realizado una copia de seguridad de la base de datos de importación principal de SAE, en el caso de que se produzca un error de datos o del sistema podrá restaurar la copia de seguridad en un equipo distinto y cambiar el nombre a esa copia de seguridad.  
  
 El servicio de bus de sucesos SAE mueve los datos de sucesos desde la base de datos de cuadro de mensajes a la base de datos de importación principal de SAE. El servicio de bus de eventos de SAE incluye una lógica de tolerancia a errores que le permite recuperarse y reiniciarse a partir de un error inesperado sin pérdida alguna de datos. Para obtener más información sobre el servicio de Bus de sucesos SAE, vea el tema [administrar el servicio de Bus de eventos BAM](http://go.microsoft.com/fwlink/?LinkID=154194) (http://go.microsoft.com/fwlink/?LinkID=154194).  
  
 Para restaurar la base de datos de importación principal de BAM, siga los pasos descritos en [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md). Además, debe actualizar los paquetes SSIS de BAM con el nuevo nombre del servidor y el nombre de la base de datos.  
  
## <a name="how-to-update-references-to-bam-primary-import-database"></a>Cómo actualizar referencias a la base de datos de importación principal de BAM  
 Para obtener instrucciones sobre cómo actualizar referencias a la base de datos de importación principal de BAM, [actualizar referencias a la base de importación principal de BAM nueva](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef).  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad el análisis BAM y las bases de datos del servidor de análisis de seguimiento](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)