---
title: La copia de seguridad de bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0524a8f0-15a3-4731-a7bd-c0c935fff6c8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b3d3e488c1bae99e343f5ff6d5a15b826138459
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980069"
---
# <a name="backing-up-databases"></a>Realizar copias de seguridad de bases de datos
Dado que[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza transacciones distribuidas entre varias bases de datos, el trabajo de copia de seguridad de BizTalk Server crea copias de seguridad sincronizadas de todas las [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Esto se logra mediante el uso de marcado las transacciones con el modelo de recuperación de base de datos "Full". Esto es necesario para las copias de seguridad sea transaccionalmente coherente entre bases de datos. Para obtener más información, consulte ["Copias de seguridad de registros, copias de seguridad completas y transacciones marcadas"](http://go.microsoft.com/fwlink/?LinkId=151565) (<http://go.microsoft.com/fwlink/?LinkId=151565>) en la documentación de BizTalk Server.  
  
## <a name="advantages-of-the-backup-biztalk-server-job"></a>Ventajas del trabajo de copia de seguridad de BizTalk Server  
 El trabajo de copia de seguridad de BizTalk Server es el único método admitido para copia de seguridad de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. El uso de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos de copia de seguridad el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se admite bases de datos en un entorno de producción.  
  
 Si la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se ejecuta el trabajo, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los registros de transacciones de base de datos crecerá sin límites. El trabajo de copia de seguridad trunca los registros de transacciones, lo que les impediría desmedidos. Si el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registros de transacciones de base de datos siguen creciendo, podrían en algún momento llenar el disco que se alojan en.  
  
> [!NOTE]
>  Utilizando tanto la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo y el trasvase de registros es actualmente la única completamente documentado y método admitido para llevar a cabo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copia de seguridad y restauración.  
  
## <a name="guidelines-for-the-backup-biztalk-server-job"></a>Directrices para el trabajo de copia de seguridad de BizTalk Server  
 Debe restaurar toda la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno de forma periódica. Esto incluye no solo los servidores SQL Server y el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, sino también para los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Debe documentar y practicar estos procedimientos antes de que realmente se produce un error.  
  
> [!NOTE]
>  La copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo no elimina los archivos de copia de seguridad anteriores. Debe definir y colocar los procesos para archivar los archivos de copia de seguridad antiguos y moverlos desde el directorio de copia de seguridad que usa el trabajo de copia de seguridad.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Vea los temas siguientes en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación:  
  
- Para obtener más información acerca de concreto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de copia de seguridad y restauración de las tareas, consulte ["Lista de comprobación: copia de seguridad y restauración"](http://go.microsoft.com/fwlink/?LinkId=154070) (<http://go.microsoft.com/fwlink/?LinkId=154070>).  
  
- Para obtener información general de copia de seguridad y restauración [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte ["Copia de seguridad y restauración de BizTalk servidor"](http://go.microsoft.com/fwlink/?LinkId=154071) (<http://go.microsoft.com/fwlink/?LinkId=154071>).  
  
- Para obtener más información acerca de cómo configurar el trabajo de copia de seguridad de BizTalk Server, consulte ["Cómo configurar el trabajo de servidor de BizTalk de copia de seguridad"](http://go.microsoft.com/fwlink/?LinkId=154072) (http://go.microsoft.com/fwlink/?LinkId=154072).  
  
## <a name="see-also"></a>Vea también  
 [Uso del trasvase de registros de BizTalk Server para la recuperación ante desastres](../technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)