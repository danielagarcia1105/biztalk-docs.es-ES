---
title: "Cómo configurar la función BTS_BACKUP_USERS para archivar y purgar datos de la base de datos de seguimiento de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, BTS_BACKUP_USERS role
- Tracking database, purging
- BTS_BACKUP_USERS role
- DTA Purge and Archive job
- archiving [Tracking database], BTS_BACKUP_USERS role
- archiving [Tracking database], DTA Purge and Archive job
- Tracking database, BTS_BACKUP_USERS role
- Tracking database, archiving
- purging, DTA Purge and Archive job
ms.assetid: c27aad2a-5788-4236-b5eb-ca730bf79851
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fb083f3755259ab2176541213d1637ce872c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>Cómo configurar el rol BTS_BACKUP_USERS para archivar y purgar datos de la base de datos de seguimiento de BizTalk
Por lo general, el trabajo DTA Purge and Archive (BizTAlkDTADb) se ejecuta utilizando las credenciales de usuario de la cuenta de servicio del Agente SQL Server. Para obtener una mayor seguridad, puede configurar el trabajo DTA Purge and Archive (BizTalkDTADb) para que se ejecute utilizando las credenciales de una cuenta que sea miembro de la función BTS_BACKUP_USERS. De esta forma, se evita la elevación de privilegios mediante la ejecución de trabajos del Agente SQL Server en cuentas con permisos básicos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>Procedimiento para configurar la función BTS_BACKUP_USERS para el archivo y depurado de datos de la base de datos de seguimiento de BizTalk  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **conectar** a conectar con el servidor SQL Server apropiado.  
  
3.  En **Microsoft SQL Server Management Studio**, haga doble clic en **BizTalkDTADb**, haga doble clic en **seguridad**, haga doble clic en **Roles**, y a continuación, haga doble clic en **Roles de base de datos**.  
  
4.  En el **detalles del explorador de objetos** panel, haga doble clic en **BTS_BACKUP_USERS**.  
  
5.  En el **propiedades del rol de base de datos – BTS_BACKUP_USERS** cuadro de diálogo **miembros de este rol**, haga clic en **agregar**.  
  
6.  En el **Seleccionar base de datos de usuario o rol** cuadro de diálogo, escriba una cuenta de usuario con credenciales de servicio del Agente SQL Server y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)