---
title: Marcar transacciones en progreso como completadas en SAE | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data recovery
- data recovery, BAM
- BAM, data loss
- data loss, BAM
ms.assetid: 8f734953-483a-481a-9ded-b48923859199
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 508001fcc1023acfd54b7d28bea7f246cb6a1a2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262372"
---
# <a name="marking-in-progress-transactions-as-complete-in-bam"></a>Marcar transacciones en progreso como completadas en SAE
Supervisión de la actividad económica (SAE) conserva datos de instancias de seguimiento sin completar en una tabla especial de instancias activas. Si algunos registros de instancia se inician antes de la última copia de seguridad pero se completan después de realizar esta última, los registros se conservan en una tabla de instancias activas. Aunque esto no impide que funcione el sistema, puede marcar estos registros de forma manual como completados para que puedan moverse a una ubicación externa a la tabla de instancias activas.  
  
 Se puede determinar una lista de elementos ActivityID incompletos para una actividad dada efectuando la siguiente consulta en la base de datos de importación principal de SAE:  
  
```  
Select ActivityID from bam_<ActivityName> where IsComplete = 0  
```  
  
 Si hay datos de sistemas externos que indican que la instancia de actividad se ha completado, puede utilizar la siguiente consulta para completar manualmente la instancia:  
  
```  
exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
```  
  
## <a name="see-also"></a>Vea también  
 [Resolver la pérdida de datos](../core/resolving-data-loss.md)