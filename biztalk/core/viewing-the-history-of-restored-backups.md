---
title: Ver el historial de restaura las copias de seguridad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring, history
- backing up, history
ms.assetid: 8852befa-b8e7-469d-b014-75c881907442
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa5a7fbe2b0e731920880570b0555402ba162c7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288156"
---
# <a name="viewing-the-history-of-restored-backups"></a>Ver el historial de las copias de seguridad restauradas
Para determinar el último conjunto de copias de seguridad restaurado correctamente, revise el contenido de la tabla Master.dbo.bts_LogShippingHistory. El trabajo Obtener historial de copias de seguridad rellena esta tabla, mientras que el trabajo Restaurar bases de datos efectúa su actualización. Cuando una copia de seguridad se restaura correctamente, la columna de restauración se establece como 1, y RestoredDateTime se define con la hora y fecha actuales.  
  
 Cuando todas las bases de datos que se están restaurando en el servidor a partir de un conjunto particular de copias de seguridad culminan correctamente el proceso de restauración, se escribe el Id. del conjunto de copias de seguridad en la tabla Master.dbo.bts_LogShippingLastRestoreSet.  
  
## <a name="gaps-in-the-restore-process"></a>Desapariciones en el proceso de restauración  
 Al revisar los registros de la tabla Master.dbo.bts_LogShippingHistory, es posible que se haya producido alguna desaparición en los conjuntos restaurados. Esto puede ocurrir por varios motivos. No obstante, aunque hayan desaparecido elementos, aún podrá recuperar la estabilidad del sistema de destino (es decir, de los equipos de copia de seguridad). Para reparar el sistema de destino, es preciso restaurar un conjunto completo de copias de seguridad después de que se produzca la desaparición. De lo contrario, el entorno de destino no será estable.  
  
> [!NOTE]
>  Las copias de seguridad completas tan sólo se restauran para crear inicialmente la base de datos y para reparar problemas en la cadena de copias de seguridad del historial de registros. En la mayoría de casos, no se restauran conjuntos completos de copias de seguridad, puesto que no forman parte de la cadena de copias de seguridad de registros.  
  
## <a name="see-also"></a>Vea también  
 [Información avanzada sobre la copia de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)