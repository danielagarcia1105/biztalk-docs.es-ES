---
title: Mover las bases de datos de BizTalk Server | Microsoft Docs
description: Pasos para mover las bases de datos de BizTalk Server a un nuevo servidor, como detener servicios y el uso de trabajos del Agente SQL Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec302e6d-c89d-4fe7-849f-97b5566e8ba4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a3509a6a0297b0f58a16cfd3eff1dc29420232b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978909"
---
# <a name="how-to-move-the-biztalk-server-databases"></a>Movimiento de bases de datos de BizTalk Server

## <a name="overview"></a>Información general
Este procedimiento se puede usar para mover las bases de datos principales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a otro servidor así como para mover las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] local a un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] remoto o a un clúster de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  

## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rol de servidor fijo sysadmin para realizar este procedimiento.  
  
## <a name="move-steps"></a>Mover los pasos
  
1. Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [reiniciar servicios de BizTalk Server y apagar el servidor BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).
  
   > [!IMPORTANT]
   >  Es importante asegurarse de que todos los servicios y trabajos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se han detenido antes de mover las bases de datos.  
  
2. Detenga el servicio IIS.  
  
3. Detenga el servicio del Agente SQL Server.  
  
4. Copia de seguridad de las bases de datos de BizTalk siguiendo los procedimientos de copia de seguridad de base de datos, como se describe en [copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md).  
  
5. Los procedimientos de restauración de las bases de datos de BizTalk en el nuevo servidor de la base de datos de restauración [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md).  
  
6. Los trabajos del Agente SQL Server se enumeran a continuación para la transferencia al nuevo servidor, como se describe en el script [cómo hacer copia de seguridad y restaurar trabajos del Agente SQL](../core/how-to-back-up-and-restore-sql-agent-jobs.md).  Ejecute cada uno de los scripts en el servidor nuevo para volver a crear los trabajos.  
  
    Ejecute cada uno de los scripts en el servidor nuevo para volver a crear los trabajos. Determinados trabajos, como el **Backup BizTalk Server (BizTalkMsgBoxDb)** del trabajo, tendrá que volver a configurar a menos que las nuevas rutas de acceso de archivo de servidor y el nombre del servidor son idénticas para el servidor anterior.  
  
   > [!NOTE]
   >  También puede usar SSIS/DTS **transferir trabajos** de tareas para mover los trabajos al nuevo servidor, pero la mayoría de los usuarios probablemente resultará más fácil para generar un script los trabajos mediante SQL Management Studio.  
  
7. Además de scripting de trabajos del Agente SQL Server como se describe en el paso anterior, también debe script inicios de sesión como se describe en [cómo hacer copia de seguridad y restaurar inicios de sesión de servidor de SQL](../core/how-to-back-up-and-restore-sql-server-logins.md). Estos inicios de sesión deben restaurarse en el servidor de destino.  
  
8. Restaurar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos siguiendo los pasos del 9 al 22 de [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md). En este procedimiento se explica cómo actualizar el Registro y la base de datos de administración de BizTalk (BizTalkMgmtDb) con la nueva ubicación de bases de datos de BizTalk.  
  
   > [!NOTE]
   >  En el **SampleUpdateInfo.xml** archivo comentario todas las bases de datos excepto a los que han movido al nuevo servidor.  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos de BizTalk Server](../core/moving-biztalk-server-databases.md)