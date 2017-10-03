---
title: "Resolver problemas de inicio de sesión después de restaurar el sistema de destino | Documentos de Microsoft"
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
ms.openlocfilehash: e691e690552f6decb3eed5f55dd17295c21a4efd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a>Resolver problemas de inicio de sesión después de restaurar el sistema de destino
Dependiendo de cómo se ha configurado el sistema de origen durante la implementación, los usuarios "huérfanos" que necesite resolver. Un usuario huérfano de la base de datos es un usuario que no tiene una seguridad correspondiente inicio de sesión en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Crear inicios de sesión correspondientes para estos usuarios antes de poner el sistema en línea mediante el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (en **seguridad**, **inicios de sesión**). Puede crear estos inicios de sesión en cualquier momento, pero se recomienda que se crean cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura el trasvase de registros.  
  
 Los inicios de sesión que se crean deben corresponder a las cuentas de Windows y grupos que se usa cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura en el sistema de origen y los inicios de sesión que se crearon manualmente y se usa en ninguna [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-creó el rol. Si estos inicios de sesión corresponden a las cuentas de Windows locales o grupos, los grupos y cuentas deben crearse antes de que se puede agregar el inicio de sesión. Si no se cambia el nombre del equipo del servidor BizTalk Server, a continuación, resuelva los usuarios asociados con los inicios de sesión para los grupos y cuentas locales.  
  
 Al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros, siga los pasos descritos en Microsoft Knowledge Base artículo 918992 [cómo transferir los inicios de sesión y contraseñas entre instancias de SQL Server 2005 y SQL Server 2008](http://go.microsoft.com/fwlink/?LinkId=157143) (http:// ¿go.Microsoft.com/fwlink/? LinkId = 157143) para crear un script que se agregará a los inicios de sesión necesarios para el servidor de destino.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)