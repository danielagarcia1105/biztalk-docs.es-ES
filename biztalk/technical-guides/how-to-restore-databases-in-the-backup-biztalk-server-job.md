---
title: Cómo restaurar las bases de datos en el trabajo de copia de seguridad de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bcac40f-ef0b-4ff0-8743-cf1614e14422
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fde33b46937118aa29aa8259225da2c4d2c0439
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992413"
---
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a>Cómo restaurar las bases de datos en el trabajo de copia de seguridad de BizTalk Server
En esta sección se describe los pasos para poner en línea las bases de datos en el grupo de BizTalk que estén respaldados por el trabajo de copia de seguridad de BizTalk Server. De forma predeterminada, se copian todas las bases de datos usando el trabajo de copia de seguridad de BizTalk Server, excepto las bases de datos BAM. Consulte [restauración de Analysis Services y bases de datos que admiten](../technical-guides/restoring-analysis-services-and-supporting-databases.md) para obtener más información acerca de la copia de seguridad y restauración de las bases de datos BAM. Es preciso efectuar una restauración de todas las bases de datos en la misma marca para garantizar que el estado transaccional sea coherente en todas las bases de datos. Para obtener más información, consulte [copias de seguridad de registros, copias de seguridad completas y transacciones marcadas](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).  
  
 Para obtener más información e instrucciones acerca de cómo restaurar bases de datos para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [cómo restaurar las bases de datos](http://go.microsoft.com/fwlink/?LinkId=151406) (<http://go.microsoft.com/fwlink/?LinkId=151406>).  
  
## <a name="see-also"></a>Vea también  
 [Restauración de bases de datos que no se incluyen en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)