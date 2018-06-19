---
title: Control de acceso y seguridad de los datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access control, BizTalk Server Operator role
- databases, SQL roles
- access control, about access control
- BizTalk Server Administrator role
- databases, access control
- access control
- access control, BizTalk Server Administrator role
- access control, SQL roles
- user accounts, access control
- BizTalk Server Operator role
ms.assetid: f04fd4a3-0f8c-4170-934a-9cc77edd7f34
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11cb00eabf6110de78e2d194e0a25bfac6a3b6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225644"
---
# <a name="access-control-and-data-security"></a>Control de acceso y seguridad de los datos
BizTalk Server limita el acceso a sus procesos y bases de datos concediendo derechos de usuario mínimos; se pueden proteger datos importantes del sistema empleando características de Microsoft Windows Server. Por motivos de seguridad, los administradores de BizTalk Server y los hosts de BizTalk sólo deben tener los derechos de usuario necesarios para realizar sus tareas.  
  
 BizTalk controla el acceso administrativo a los datos mediante funciones SQL, con lo que controla el acceso a los datos tanto mediante herramientas como directamente por la base de datos. El acceso de host de BizTalk a los datos se controla mediante la utilización de cuentas y grupos de usuarios de host.  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], hay dos funciones administrativas: el Administrador de BizTalk Server y el operador de BizTalk Server. Cada vez que se crea una base de datos de BizTalk Server mediante instalación o mediante la consola de administración de BizTalk Server, éste crea automáticamente funciones SQL para ambas funciones administrativas en esa base de datos. BizTalk Server concede a cada función, así como a cualquier inicio de sesión de SQL Server asignado a ella, los derechos de usuario mínimos requeridos por los administradores de los objetos de SQL Server (tablas, vistas, procedimientos almacenados, etc.) para realizar tareas administrativas en esa base de datos.  
  
 El Administrador de BizTalk Server tiene una función de muchos privilegios, con acceso a los datos de configuración y de seguimiento. El Operador de BizTalk Server tiene una función de pocos privilegios, con acceso sólo para supervisar y solucionar problemas de acciones. Esta última función puede ver estados de servicio y flujos de mensajes, iniciar o detener aplicaciones y finalizar o reanudar instancias de servicio, pero no puede cambiar la configuración ni ver las propiedades ni el contenido de los mensajes.  
  
 Igualmente, BizTalk Server crea en cada base de datos una función SQL para el grupo de usuarios de cada host, y le concede los derechos de usuario mínimos para que el grupo de usuarios realice tareas para ese host.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cuentas de grupos y de usuario de Windows en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [Control de acceso para grupos y cuentas de servicio](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [Control de acceso para los Roles administrativos](../core/access-control-for-administrative-roles.md)  
  
-   [Control de acceso a información empresarial](../core/access-control-to-business-information.md)  
  
-   [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)