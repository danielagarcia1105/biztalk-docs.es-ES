---
title: Resolver instancias de actividad incompletas | Documentos de Microsoft
description: Instancias de actividad BAM permanecen activas después de la copia de seguridad de la base de datos BAMPrimaryImport en BizTalk Server
ms.custom: ''
ms.date: 01/17/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 616ba096062da7ede8d78122e5a6faaca2befdc4
ms.sourcegitcommit: 20d33d8b74bf129a8d1a506ac4a1ad960184966d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2018
ms.locfileid: "27873420"
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a>Resolver instancias incompletas de actividad BAM - servidor BizTalk Server
BAM almacena datos de instancias de actividad incompletas en una clase especial *instancias activas* tabla en la base de datos BAMPrimaryImport.  
  
 Si algunos registros de instancia se inician antes de la última copia de seguridad de la base de datos de importación principal de BAM pero se completan después de realizar esa copia de seguridad, los registros de instancia se conservan en una tabla de instancias activas. Esto ocurre porque, después de restaurar la base de datos BAMPrimaryImport, se pierden los registros de finalización de estas instancias.  
  
 Aunque los registros de la tabla de instancias activas no impiden que SAE funcione correctamente, se recomienda marcarlos como "completados" y, seguidamente, moverlos a una ubicación externa a la tabla de instancias activas.  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión como miembro del grupo Administradores de BizTalk Server.  
  
## <a name="create-a-list-of-incomplete-activityids"></a>Crear una lista de elementos ActivityID incompletos 
  
1.  Ejecute la consulta siguiente en la base de datos BAMPrimaryImport:  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  Si hay datos de sistemas externos que indican que, efectivamente, la instancia de actividad se ha completado, ejecute la siguiente consulta para completar manualmente la instancia:  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  Puede seguir el mismo proceso para completar una actividad de continuación si se reemplaza `ActivityID` con `ContinuationID`.  
> 
>  Si el seguimiento principal tiene seguimientos de continuación activos, permanece activo hasta que éstos se completen.  

## <a name="remove-incomplete-instances"></a>Quitar instancias incompletas
También puede quitar instancias de actividad incompletas de la base de datos BAMPrimaryImport mediante un script SQL personalizado. Vea [quitar instancias de actividad incompletas](how-to-remove-incomplete-activity-instances.md) para obtener un ejemplo.

## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)
