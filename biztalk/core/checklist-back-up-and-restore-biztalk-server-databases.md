---
title: 'Lista de comprobación: Copia de seguridad y restaurar bases de datos de servidor BizTalk Server | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- restoring, checklists
- maintaining, restoring
- maintaining, checklists
- restoring, BizTalk Server
- maintaining, backing up
- checklists, backing up
- backing up, checklists
- BizTalk Server, backing up
- checklists, restoring
- BizTalk Server, restoring
ms.assetid: 12f7e02e-57b1-4e55-8e44-7fe2d7920f5a
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3c8c68eb62273562b0f703ae79c0db76ec837c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232708"
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a>Lista de comprobación: Copia de seguridad y restaurar bases de datos de servidor BizTalk Server
Antes de intentar realizar una copia de seguridad de BizTalk Server o de efectuar su restauración, asegúrese de familiarizarse con los procesos que entran en juego.  
  
## <a name="backing-up-biztalk-server"></a>Realizar una copia de seguridad de BizTalk Server  
  
|Paso|Referencia|  
|----------|---------------|  
|Aprenda cómo realizar una copia de seguridad de BizTalk Server y cómo efectuar su restauración.|[Prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|Asegúrese de contar con los permisos apropiados para realizar una copia de seguridad de BizTalk Server y efectuar su restauración.|[Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)|  
|Configure el trabajo de copia de seguridad de BizTalk Server.|[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|Configure el servidor en el que se almacenarán las copias de seguridad.|[Cómo configurar el sistema de destino de trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|Si está utilizando Supervisión de la actividad económica (SAE), realice una copia de seguridad de la base de datos de SAE.|[Copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)|  
|Si está utilizando el inicio de sesión único empresarial, realice una copia de seguridad del secreto principal.|[Administrar el secreto principal](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a>Restaurar BizTalk Server  
  
|Paso|Referencia|  
|----------|---------------|  
|Restaure las bases de datos.|[Cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)|  
|Actualice las referencias a los nombres de base de datos de SAE.|[Cómo realizar una copia del análisis de seguimiento y análisis de BAM bases de datos de servidor](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [Cómo actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema en estrella](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [Cómo actualizar referencias al nombre de base de datos de archivo BAM](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [Cómo actualizar referencias a la cadena de conexión y el nombre de base de datos de importación principal de BAM](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [Cómo actualizar referencias a la notificación de BAM de servicios de bases de datos](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [Cómo resolver instancias de actividad incompletas](../core/how-to-resolve-incomplete-activity-instances.md)|  
|Si está utilizando el inicio de sesión único empresarial, restaure el secreto principal.|[Administrar el secreto principal](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md)