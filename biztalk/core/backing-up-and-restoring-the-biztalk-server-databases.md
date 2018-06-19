---
title: Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44bbb9316f1d036551acba5441424bcce65c2549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230372"
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a>Realizar una copia de seguridad y restaurar las bases de datos de BizTalk Server
En esta sección se proporciona información acerca de cómo realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server. Debería seguir los procedimientos de esta sección para garantizar la posibilidad de restaurar un entorno de BizTalk Server coherente en el caso de que se produzca un error de hardware. BizTalk Server lleva a cabo transacciones distribuidas en las bases de datos, de modo que resulta extremadamente importante realizar una copia de seguridad y una restauración ulterior de todas las bases de datos.  
  
 BizTalk Server requiere un proceso de copia de seguridad personalizado que utiliza copias de seguridad de registros y de bases de datos completas junto con marcas de registros de carácter transaccional. Para obtener información acerca de este proceso, consulte [transacciones marcadas y copias de seguridad completas, copias de seguridad del registro](../core/marked-transactions-full-backups-and-log-backups.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Lista de comprobación: Copia de seguridad y restaurar bases de datos de servidor BizTalk Server](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [Prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [Copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)  
  
-   [Resolver la pérdida de datos](../core/resolving-data-loss.md)  
  
-   [Información avanzada sobre la copia de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)