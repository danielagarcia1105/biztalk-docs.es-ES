---
title: Copia de seguridad de bases de datos | Documentos de Microsoft
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
ms.openlocfilehash: d6a4b40be0a9a7d4846dd965a4d9f934e69690e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300540"
---
# <a name="backing-up-databases"></a>Realizar copias de seguridad de bases de datos
Dado que[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza transacciones distribuidas a través de varias bases de datos, el trabajo de copia de seguridad de BizTalk Server crea copias de seguridad sincronizadas de todas las [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos. Esto se logra mediante el uso de marcado las transacciones con el modelo de recuperación de base de datos "Completa". Esto es necesario para las copias de seguridad para que sea transaccionalmente coherente entre las bases de datos. Para obtener más información, consulte ["Transacciones marcadas, copias de seguridad completas y las copias de seguridad del registro"](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565) en la documentación de BizTalk Server.  
  
## <a name="advantages-of-the-backup-biztalk-server-job"></a>Ventajas del trabajo de copia de seguridad de BizTalk Server  
 El trabajo de copia de seguridad de BizTalk Server es el único método admitido para la copia de seguridad de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos. El uso de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos para realizar una copia de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se admite bases de datos en un entorno de producción.  
  
 Si la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se ejecuta el trabajo, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registros de transacciones de base de datos crecerá sin enlazar. El trabajo de copia de seguridad trunca los registros de transacciones que mantenerlos crezca sin enlazar. Si el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registros de transacciones de base de datos siguen creciendo a, podría en algún momento llenar el disco que se alojan en.  
  
> [!NOTE]  
>  Mediante la copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo y el trasvase de registros es actualmente el único completamente documentado y el método admitido para llevar a cabo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copia de seguridad y restauración.  
  
## <a name="guidelines-for-the-backup-biztalk-server-job"></a>Directrices para el trabajo de copia de seguridad de BizTalk Server  
 Debe restaurar toda la matriz [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno de forma regular. Esto incluye no solo los servidores de SQL y el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, sino también los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Debe documentar y practicar estos procedimientos antes de que realmente se produce un error.  
  
> [!NOTE]  
>  La copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo no elimina los archivos de copia de seguridad anteriores. Debe definir e implementar procesos para archivar los archivos de copia de seguridad antiguos y moverlos desde el directorio de copia de seguridad que utiliza el trabajo de copia de seguridad.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Vea los temas siguientes en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación:  
  
-   Para obtener más información acerca de concreto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de copia de seguridad y restauración de las tareas, consulte ["Lista de comprobación: copia de seguridad y restauración"](http://go.microsoft.com/fwlink/?LinkId=154070) (http://go.microsoft.com/fwlink/?LinkId=154070).  
  
-   Para obtener información general de copia de seguridad y restauración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte ["Realizar una copia de seguridad y restauración de BizTalk Server"](http://go.microsoft.com/fwlink/?LinkId=154071) (http://go.microsoft.com/fwlink/?LinkId=154071).  
  
-   Para obtener más información acerca de cómo configurar el trabajo de copia de seguridad de BizTalk Server, vea ["Cómo configurar el trabajo de servidor de BizTalk de copia de seguridad"](http://go.microsoft.com/fwlink/?LinkId=154072) (http://go.microsoft.com/fwlink/?LinkId=154072).  
  
## <a name="see-also"></a>Vea también  
 [Uso de recuperación ante desastres de trasvase de registros de servidor BizTalk Server](../technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)