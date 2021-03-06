---
title: Las cuentas de usuario y funciones de trasvase | Microsoft Docs
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
ms.openlocfilehash: f3d82e9cd3f1ea942513319d0d68d528762ef35a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024490"
---
# <a name="log-shipping-user-accounts-and-roles"></a>Trasvase de registros Roles y cuentas de usuario
El trasvase de registros está controlado por un trabajo del Agente SQL Server para automatizar el proceso de restauración de copias de seguridad y los registros de BizTalk Server. Permisos incorrectos pueden hacer que las operaciones de restauración realizadas por BizTalk Server del trasvase de registros para conmutar por error. La cuenta de usuario configurada para restaurar las bases de datos debe tener acceso a la instancia de base de datos de producción que hospeda la base de datos de administración de BizTalk. En la mayoría de los casos esto significa que la cuenta de servicio para el trabajo del Agente SQL Server impulsando el trabajo de trasvase de registros del registro de BizTalk Server en la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia requiere un inicio de sesión y los permisos en la instancia de base de datos de producción que hospeda el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]base de datos de administración. Se supone que la cuenta de servicio del Agente SQL Server está configurada como el propietario del trabajo.  

 BizTalk Server incluye una función de SQL Server denominada BTS_BACKUP_USERS para que la cuenta de usuario configurada para restaurar las bases de datos no requiere permisos de administradores del sistema de SQL Server.  

 Al configurar la cuenta de usuario que se llevará a cabo operaciones de restauración de base de datos como parte de trasvase de registros de servidor BizTalk Server, compruebe lo siguiente:  

- Configurar el servicio Agente SQL Server para ejecutarse en una cuenta de dominio con un usuario asignado configurado en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio (en **seguridad**, **inicios de sesión**) en cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que la instancia hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos restauradas por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] iniciar trabajos de trasvase de registros.  

- Configurar un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] inicio de sesión de cuenta para este usuario y asigne este usuario al rol SQL BTS_BACKUP_USERS de BizTalk en cada servidor.  

- Asigne este usuario a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rol de administradores del sistema del equipo que ejecuta [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que aloja el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de administración.  

- La cuenta que realiza la copia de seguridad y restauración operaciones deben tener de lectura y acceso de escritura a la ruta UNC compartan donde se crean los archivos de copia de seguridad.
