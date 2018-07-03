---
title: Mover bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a0d09a1-90a5-4a5d-a783-b979724e101b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15562fc1fb642a4766190dabe912e81b38bb1ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972421"
---
# <a name="moving-databases"></a>Mover bases de datos
El método recomendado para mover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos (excepto las bases de datos de supervisión de la actividad económica (BAM)) consiste en configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros como se describe en la sección [recuperación ante desastres](../technical-guides/disaster-recovery.md). A excepción de las bases de datos usa BAM, todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos pueden realizar copias de seguridad utilizando la **Backup BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajo del agente. Para obtener más información acerca de este trabajo, consulte [cómo programar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154674) (<http://go.microsoft.com/fwlink/?LinkId=154674>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 Esta sección describe cómo mover las bases de datos relacionadas con BAM y cómo mover los restantes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos sin configurar primero [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros. Este enfoque puede resultar útil cuando se actualiza el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o en otros escenarios que no están relacionadas con la recuperación ante desastres.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Mover bases de datos de BAM](../technical-guides/moving-bam-databases.md)  
  
-   [Mover bases de datos que no son de BAM](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a>Vea también  
 [Administración de BizTalk Server2](../technical-guides/managing-biztalk-server2.md)