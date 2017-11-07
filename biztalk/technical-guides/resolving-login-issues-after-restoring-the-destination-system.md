---
title: "Resolver problemas de inicio de sesión después de restaurar el sistema de destino | Documentos de Microsoft"
description: "Incluir inicios de sesión de SQL Server para resolver usuarios huérfanos en BizTalk Server trasvase de registros"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9232ca3-dadb-4b3c-8ec4-4e307c32d2e5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 559302718c9fe504c9c264de92f6a4af161d91f9
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a>Resolver problemas de inicio de sesión después de restaurar el sistema de destino

## <a name="orphaned-users"></a>Usuarios huérfanos
Dependiendo de cómo se ha configurado el sistema de origen durante la implementación, los usuarios "huérfanos" que necesite resolver. Un usuario huérfano de la base de datos es un usuario que no tiene una seguridad correspondiente inicio de sesión en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Crear inicios de sesión correspondientes para estos usuarios antes de poner el sistema en línea mediante el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (en **seguridad**, **inicios de sesión**). Puede crear estos inicios de sesión en cualquier momento, pero se recomienda que se crean cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura el trasvase de registros.  
  
 Los inicios de sesión que se crean deben corresponder a las cuentas de Windows y grupos que se usa cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura en el sistema de origen y los inicios de sesión que se crearon manualmente y se usa en ninguna [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-creó el rol. Si estos inicios de sesión corresponden a las cuentas de Windows locales o grupos, los grupos y cuentas deben crearse antes de que se puede agregar el inicio de sesión. Si no se cambia el nombre del equipo del servidor BizTalk Server, a continuación, resuelva los usuarios asociados con los inicios de sesión para los grupos y cuentas locales.  
  
 Al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envío, de registro puede [KB 918992: transferir los inicios de sesión y contraseñas entre instancias de SQL Server](https://support.microsoft.com/help/918992/how-to-transfer-logins-and-passwords-between-instances-of-sql-server) para crear una secuencia de comandos que agrega los inicios de sesión necesarios para el servidor de destino.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)
