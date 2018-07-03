---
title: Cómo hacer referencia a las bases de datos de importación principal de BAM adicionales | Microsoft Docs
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
ms.openlocfilehash: 54982491ca8ce2c7ca7acd9e176a7341b2642c78
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992317"
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a>Cómo agregar referencias a bases de datos de importación principal de BAM adicionales
Los administradores utilizan el **enable-reference** comando para hacer referencia a otras bases de datos de importación principal de BAM. La finalidad de agregar referencias a bases de datos de importación principales de BAM consiste en facilitar las actividades de BAM distribuidas.  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a>Para habilitar una referencia a una base de datos de importación principal de BAM adicional  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3. Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm enable-reference - TargetServer:\<TargetServer\> - TargetDatabase:\<base de datos de destino\>**, donde \< *TargetServer* \> se sustituye por el nombre de SQL server en el que la base de datos de importación principal de BAM de destino especificada por \<base de datos de destino\> reside. Presione ENTRAR.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)