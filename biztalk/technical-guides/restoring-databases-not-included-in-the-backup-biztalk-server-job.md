---
title: Restaurar bases de datos no incluidos en el trabajo de copia de seguridad de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7141980-d4a6-4409-be9b-c94a7f733376
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b24b0815c5948bac86dc3c614d05eb87d0684bdb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999253"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a>Restaurar bases de datos que no se incluye en el trabajo de copia de seguridad de BizTalk Server
En esta sección se describe cómo restaurar las bases de datos que forman parte de la solución de BizTalk general pero que no estén respaldados por el trabajo de copia de seguridad de BizTalk Server. Todas las bases de datos que forman parte de una solución de BizTalk se hará copia usando el trabajo de copia de seguridad de BizTalk Server, excepto los siguientes:  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Bases de datos de Analysis Services  
  
- Bases de datos BAM cuando BAM está habilitada y configurada mediante BM.exe  
  
  En esta sección también describe cómo actualizar referencias de base de datos después de restaurar las bases de datos enumerados anteriormente y se incluye información acerca de cómo resolver instancias de actividad incompletas de BAM.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Restauración de Analysis Services y bases de datos auxiliares](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [Actualización de referencias de base de datos](../technical-guides/updating-database-references.md)  
  
-   [Cómo resolver instancias de actividad incompletas de BAM](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)