---
title: "Lista de comprobación: Archivar y purgar la base de datos de seguimiento de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22e97ac12e6b6b304318f57f309767ec7c63815f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a>Lista de comprobación: Archivar y purgar la base de datos de seguimiento de BizTalk
|Paso|Referencia|  
|----------|---------------|  
|Lea la información general de archivo y purga para familiarizarse con el proceso de archivo y purga de datos de seguimiento.|[Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|Aunque puede ejecutar el trabajo DTA Purge and Archive mediante sus credenciales de inicio de sesión, debería configurar el rol BTS_BACKUP_USERS con las credenciales del servidor SQL Server para ejecutar el trabajo DTA Purge and Archive. Esto ayuda a evitar elevación de privilegios.|[Cómo configurar la función BTS_BACKUP_USERS para archivar y purgar datos de la base de datos de seguimiento de BizTalk](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|Configure el trabajo DTA Purge and Archive.|[Cómo configurar el trabajo DTA Purge and Archive](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|Ejecute el trabajo DTA Purge and Archive, lo que archiva los datos en la base de datos de seguimiento de BizTalk (BizTalkDTADb) y purga los datos antiguos.|[Cómo purgar datos de la base de datos de seguimiento de BizTalk](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|Opcionalmente, puede purgar datos manualmente desde la base de datos de seguimiento de BizTalk (BizTalkDTADb) |[Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|Habilite la validación automática de los datos archivados desde la base de datos de seguimiento de BizTalk (BizTalkDTADb).|[Cómo habilitar la validación automática de archivos](../core/how-to-enable-automatic-archive-validation.md)|  
|Copie los mensajes sometidos a seguimiento en la base de datos de seguimiento BizTalk (BizTalkDTAdb). Esto resulta necesario para purgar datos mediante el trabajo DTA Purge and Archive.|[Cómo copiar mensajes controlados en la base de datos de seguimiento de BizTalk](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)