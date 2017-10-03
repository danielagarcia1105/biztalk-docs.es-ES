---
title: "Cómo enumerar todas hace referencia a las bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69c6411378311892f85821a3e86d65a85f909d0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-all-referenced-databases"></a>Cómo enumerar todas las bases de datos a las que se hace referencia
Los administradores utilizan el **get-references** comando para enumerar todas las bases de datos de importación principal de BAM en otros servidores de BizTalk que han recibido referencias a la base de datos de importación principal de BAM local.  
  
### <a name="to-list-all-referenced-databases"></a>Para enumerar todas las bases de datos a las que se hace referencia  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm.exe get-references**. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)