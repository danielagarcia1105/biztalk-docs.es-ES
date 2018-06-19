---
title: Trasvase de registros de supervisión de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fae4ff40-7d86-4e9b-b1cc-4f00486ae4b9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eacec106823afc8203e7cce9679cb27cd29d0b78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298572"
---
# <a name="monitoring-biztalk-server-log-shipping"></a>Trasvase de registros de supervisión de BizTalk Server
Para determinar el último conjunto de copia de seguridad correcta de las bases de datos de BizTalk Server y los registros que se han restaurado, revise el contenido de la tabla Master.dbo.bts_LogShippingHistory en el destino [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias. Esta tabla se rellena con el trabajo de BizTalk Server trasvase obtener copia de seguridad historial de registro y se actualiza mediante el trabajo de restauración. Cuando una copia de seguridad se restaura correctamente, la columna de restauración se establece en un valor de 1 y RestoredDateTime se establece en la fecha y hora actuales.  
  
 Cuando todas las bases de datos que se restaura en el servidor de un determinado conjunto enumerado en la tabla Master.dbo.bts_LogShippingHistory de copia de seguridad se han restaurado correctamente, el identificador de conjunto de copia de seguridad se escribe en la tabla Master.dbo.bts_LogShippingLastRestoreSet. Esta tabla almacena los últimos conjuntos y es útil para determinar qué conjunto de copia de seguridad de registros se deben restaurar para poner en conexión el grupo de BizTalk de destino después de la aparición de un evento de recuperación ante desastres.  
  
## <a name="see-also"></a>Vea también  
 [Trasvase de registros de configuración de BizTalk Server](../technical-guides/configuring-biztalk-server-log-shipping.md)