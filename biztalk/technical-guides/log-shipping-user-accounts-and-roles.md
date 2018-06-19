---
title: Las cuentas de usuario y funciones de trasvase de registros | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7dbec7cfa23c8a1e07e32cdf0c3ce7b044651ec
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010605"
---
# <a name="log-shipping-user-accounts-and-roles"></a>Roles y cuentas de usuario de trasvase de registros
Trasvase de registros está controlado por un trabajo del Agente SQL Server para automatizar el proceso de restauración de registros y copias de seguridad de BizTalk Server. Permisos incorrectos pueden hacer que las operaciones de restauración realizadas por el trasvase de registros de servidor BizTalk Server para producirá un error. La cuenta de usuario configurada para restaurar las bases de datos debe tener acceso a la instancia de base de datos de producción que hospeda la base de datos de administración de BizTalk. En la mayoría de los casos esto significa que la cuenta de servicio para el trabajo de agente SQL Server que se imponen el trabajo de trasvase de registros de servidor BizTalk Server en la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia requiere un inicio de sesión y permisos en la instancia de base de datos de producción que hospeda el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]base de datos de administración. Se supone que la cuenta de servicio del Agente SQL Server está configurada como el propietario del trabajo.  
  
 BizTalk Server incluye una función de SQL Server denominada BTS_BACKUP_USERS para que la cuenta de usuario configurada para restaurar las bases de datos no requieren el permiso de los administradores del sistema de SQL Server.  
  
 Al configurar la cuenta de usuario que se llevará a cabo las operaciones de restauración de base de datos como parte del trasvase de registros de servidor BizTalk Server, compruebe lo siguiente:  
  
-   Configurar el servicio Agente SQL Server para ejecutarse bajo una cuenta de dominio con un usuario asignado configurado en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio (en **seguridad**, **inicios de sesión**) en cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos restaurados la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos de trasvase de registro.  
  
-   Configurar un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] inicio de sesión de cuenta para este usuario y asignar al usuario a la función SQL BTS_BACKUP_USERS de BizTalk en cada servidor.  
  
-   Asigne este usuario a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rol de los administradores del sistema en el equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que aloja el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de administración.  
  
-   La cuenta que realiza la copia de seguridad y restauración de operaciones deben tener de lectura y acceso de escritura a la ruta UNC compartan donde se crean los archivos de copia de seguridad.