---
title: Las cuentas de usuario y funciones de trasvase de registros | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b19a7d7c87289e07c7ac7a26bacd0c96f9090c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="log-shipping-user-accounts-and-roles"></a>Roles y cuentas de usuario de trasvase de registros
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]trasvase de registros está controlado por un trabajo del Agente SQL Server para automatizar el proceso de restauración de registros y copias de seguridad. Permisos incorrectos pueden hacer que las operaciones de restauración realizadas por [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] trasvase de registros para un error. La cuenta de usuario configurada para restaurar las bases de datos debe tener acceso a la instancia de base de datos de producción que hospeda la base de datos de administración de BizTalk. En la mayoría de los casos esto significa que la cuenta de servicio para el trabajo de agente SQL Server impulsar el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] trabajo de trasvase de registros en la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia requiere un inicio de sesión y permisos en la instancia de base de datos de producción que hospeda el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]base de datos de administración. Se supone que la cuenta de servicio del Agente SQL Server está configurada como el propietario del trabajo.  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]incluye una función de SQL Server denominada BTS_BACKUP_USERS para que la cuenta de usuario configurada para restaurar las bases de datos no requieren el permiso de los administradores del sistema de SQL Server.  
  
 Al configurar la cuenta de usuario que se llevará a cabo las operaciones de restauración de base de datos como parte de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] trasvase de registros, compruebe lo siguiente:  
  
-   Configurar el servicio Agente SQL Server para ejecutarse bajo una cuenta de dominio con un usuario asignado configurado en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio (en **seguridad**, **inicios de sesión**) en cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos restaurados la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos de trasvase de registro.  
  
-   Configurar un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] inicio de sesión de cuenta para este usuario y asignar al usuario a la función SQL BTS_BACKUP_USERS de BizTalk en cada servidor.  
  
-   Asigne este usuario a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rol de los administradores del sistema en el equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que aloja el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de administración.  
  
-   La cuenta que realiza la copia de seguridad y restauración de operaciones deben tener de lectura y acceso de escritura a la ruta UNC compartan donde se crean los archivos de copia de seguridad.