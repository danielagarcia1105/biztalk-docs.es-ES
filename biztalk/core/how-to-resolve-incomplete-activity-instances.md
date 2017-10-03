---
title: "Cómo resolver instancias de actividad incompletas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- instances, incomplete [BAM]
- restoring, BAM
- Primary Import database [BAM], incomplete instances
- restoring [BAM], Primary Import database
- Primary Import database [BAM], restoring
- BAM, restoring
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81df9ee8b004a2dbd4a672eecb4f34894421a432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-incomplete-activity-instances"></a>Cómo resolver instancias de actividad incompletas
BAM almacena datos de instancias de actividad incompletas en una clase especial *instancias activas* tabla en la base de datos BAMPrimaryImport.  
  
 Si algunos registros de instancia se inician antes de la última copia de seguridad de la base de datos de importación principal de BAM pero se completan después de realizar esa copia de seguridad, los registros de instancia se conservan en una tabla de instancias activas. Esto ocurre porque, después de restaurar la base de datos BAMPrimaryImport, se pierden los registros de finalización de estas instancias.  
  
 Aunque los registros de la tabla de instancias activas no impiden que SAE funcione correctamente, se recomienda marcarlos como "completados" y, seguidamente, moverlos a una ubicación externa a la tabla de instancias activas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-generate-a-list-of-incomplete-activityids-for-an-activity"></a>Para generar una lista de elementos ActivityID incompletos para una actividad  
  
1.  Ejecute la consulta siguiente en la base de datos BAMPrimaryImport:  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  Si hay datos de sistemas externos que indican que, efectivamente, la instancia de actividad se ha completado, ejecute la siguiente consulta para completar manualmente la instancia:  
  
    ```  
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    ```  
  
> [!NOTE]
>  Puede seguir el mismo proceso para completar una actividad de continuación mediante la sustitución de ActivityID con ContinuationID.  
  
> [!NOTE]
>  Si el seguimiento principal tiene seguimientos de continuación activos, permanece activo hasta que éstos se completen.  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)