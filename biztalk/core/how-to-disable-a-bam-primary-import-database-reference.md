---
title: "Cómo deshabilitar una referencia de base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc9afef7bdcfad84f105abda158c5ed5c6461619
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a>Cómo deshabilitar una referencia de base de datos de importación principal de BAM
Los administradores utilizan el **disable-reference** comando para deshabilitar una referencia a una base de datos de importación principal de BAM especificado.  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a>Para deshabilitar una referencia de una base de datos de importación principal de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm disable-reference - TargetServer:\<TargetServer\> - TargetDatabase:\<base de datos de destino\>[-Server:\<server\> ] [-Base de datos:\<base de datos\> ]**, donde  **\<**  *TargetServer*  **\>**  se sustituye por el nombre de SQL server en el que la base de datos de importación principal de BAM de destino especificado por \< *base de datos de destino* \> reside. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)