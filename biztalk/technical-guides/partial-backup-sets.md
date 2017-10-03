---
title: Conjuntos de copia de seguridad parciales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9740cb0f45d6bb46c13a95e50e4717ef142b164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="partial-backup-sets"></a>Conjuntos de copia de seguridad parciales
Al hacer una copia de seguridad de las bases de datos en el sistema de origen, pueden producirse problemas que den como resultado un conjunto de copia de seguridad parcial. Cuando esto ocurre, la tabla Master.dbo.bts_LogShippingHistory contendrá un 0 en la **SetComplete** columna para todos los registros en el conjunto.  
  
 No se puede restaurar estos conjuntos. Como resultado, la cadena de copia de seguridad de registros se interrumpe. Se debe omitir el conjunto, como el registro de todos los conjuntos de copia de seguridad después de él, hasta el siguiente conjunto de copia de seguridad completa. El trabajo de restauración buscará automáticamente el siguiente conjunto de copia de seguridad completa válido. Si no lo encuentra, se produce un error y restaura establezca para reparar el entorno de destino.  
  
 En la mayoría de los casos el sistema de origen detectará que un conjunto de copia de seguridad parcial se ha producido y generará automáticamente un conjunto de copia de seguridad completa la próxima vez que se ejecuta si se configura para ello.  
  
> [!NOTE]  
>  La causa más común de este problema es suficiente espacio en disco para los grupos de archivos del sistema de destino.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)