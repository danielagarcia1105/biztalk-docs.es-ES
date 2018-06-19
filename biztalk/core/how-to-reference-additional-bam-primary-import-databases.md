---
title: Cómo hacer referencia a las bases de datos de importación principal de BAM adicionales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea80b32c-f2cb-4aca-89f4-d5b72e1ba021
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fca916339e48f6bce053753111f4467a4c9ae7d5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969978"
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a>Cómo agregar referencias a bases de datos de importación principal de BAM adicionales
Los administradores utilizan el **enable-reference** comando para hacer referencia a otras bases de datos de importación principal de BAM. La finalidad de agregar referencias a bases de datos de importación principales de BAM consiste en facilitar las actividades de BAM distribuidas.  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a>Para habilitar una referencia a una base de datos de importación principal de BAM adicional  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm enable-reference - TargetServer:\<TargetServer\> - TargetDatabase:\<base de datos de destino\>**, donde \< *TargetServer* \> se sustituye por el nombre de SQL server en el que la base de datos de importación principal de BAM de destino especificado por \<base de datos de destino\> reside. Presione ENTRAR.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)