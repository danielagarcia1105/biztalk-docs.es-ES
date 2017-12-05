---
title: "Cómo recuperar las alertas de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c477b4-4605-4763-b20a-3baf4529f13f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec36491dd7368e0e2fdbcd8fb5abab9d840c6b1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-recover-bam-alerts"></a>Cómo recuperar alertas SAE
Como parte de la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], si se usa Supervisión de la actividad económica (BAM), también será necesario recuperar las alertas de BAM.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a>Para recuperar las alertas de BAM (SQL Server 2008)  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.  
  
2.  En el símbolo del sistema, escriba:  
  
     **NSControl register - name BamAlerts-server***\<ServerName\>***-service - serviceusername "**  *\< ServiceUserName\>*  **"- servicepassword"**  *\<ServicePassword\>*  **"**   
  
     Esto habilita los servicios de notificación iniciar sesión en la base de datos correcta (esta información se mantiene en el registro del equipo del servicio NSControl).  
  
    > [!IMPORTANT]
    >  Recuerde que debe usar el nuevo servidor de bases de datos de servicios de notificación en el **-server** opción al volver a registrar el servicio. Además, el nombre de usuario que utilice en los nuevos servicios de notificación debería ser el mismo que el que utilizaba en los anteriores.  
  
3.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
4.  En el símbolo del sistema, escriba: **net start NS$ BamAlerts**.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)