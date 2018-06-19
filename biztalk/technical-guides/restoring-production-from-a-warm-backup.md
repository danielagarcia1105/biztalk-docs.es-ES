---
title: Restauración de producción desde una copia de seguridad semiactiva | Documentos de Microsoft
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
ms.openlocfilehash: 8e590b4eccb6ee946a915ff1f3a0265bbfe977e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302092"
---
# <a name="restoring-production-from-a-warm-backup"></a>Restauración de producción desde una copia de seguridad semiactiva
Si el sistema de origen se convierte en no confiable, es posible restaurar las bases de datos de destino al origen. Realice el procedimiento siguiente para restaurar las bases de datos de destino al origen.  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a>Para restaurar las bases de datos de destino al origen siguen estos pasos  
  
1.  Deshabilitar todos los trabajos de copia de seguridad en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
2.  Espere a todos los trabajos que se complete en la recuperación de desastres (DR) de destino de restauración [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
3.  Deshabilitar todos los trabajos de restauración en el destino (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
4.  Restaurar todas las bases de datos con WITH STOPATMARK en el destino (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
5.  Todos los detenga [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios en todos los servidores BizTalk Server.  
  
6.  Quitar todas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionados con las bases de datos en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
7.  Realice una copia (completa) todas las bases de datos en el destino (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
8.  Restaurar (completa) todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de copia de seguridad en el paso 7 en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
9. Reinicie todos los servidores de BizTalk, incluido el servidor secreto principal.  
  
10. Quitar todas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionados con las bases de datos en el destino (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
11. Habilita los trabajos de copia de seguridad en el origen de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
12. Habilita los trabajos de restauración en el destino (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.  
  
## <a name="see-also"></a>Vea también  
 [Información avanzada acerca de la copia de seguridad y Restore2](../technical-guides/advanced-information-about-backup-and-restore2.md)