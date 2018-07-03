---
title: Restauración de la producción de una copia de seguridad semiactiva | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bda14b8-b3cc-4a5e-a353-fca5885fd594
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66177cd1f6f10e252a71d2875b4079e660125719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971365"
---
# <a name="restoring-production-from-a-warm-backup"></a>Restauración de la producción de una copia de seguridad semiactiva
Si se convierte en el sistema de origen no confiable, es posible restaurar las bases de datos del destino al origen. Realice el procedimiento siguiente para restaurar las bases de datos desde el destino al origen.  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a>Para restaurar las bases de datos del destino al origen siguen estos pasos  
  
1. Deshabilitar todos los trabajos de copia de seguridad en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
2. Espere a todos los trabajos de completa en la recuperación de desastres (DR) de destino de restauración [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
3. Deshabilitar todos los trabajos de restauración en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
4. Restaurar todas las bases de datos con STOPATMARK en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
5. Todos los detenga [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services en todos los servidores BizTalk Server.  
  
6. Todos los quitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionadas con bases de datos en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
7. Copia de seguridad (completa) todas las bases de datos en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
8. Restaurar (completa) todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de copia de seguridad en el paso 7 en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
9. Reinicie todos los servidores de BizTalk, incluido el servidor secreto principal.  
  
10. Todos los quitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionadas con bases de datos en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
11. Habilitar trabajos de copia de seguridad en el origen de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
12. Habilitar trabajos de restauración en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
## <a name="see-also"></a>Vea también  
 [Información avanzada acerca de la copia de seguridad y Restore2](../technical-guides/advanced-information-about-backup-and-restore2.md)