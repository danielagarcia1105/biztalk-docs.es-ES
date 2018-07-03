---
title: Control de acceso para los Roles administrativos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- roles, administrative
- administrator accounts, administrative roles
- administrative roles
- access control, administrative roles
ms.assetid: 328e049b-921d-4057-85f0-7d008ec308bb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7999230f3ec0545d8cd15b66e1407148f080bb26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990317"
---
# <a name="access-control-for-administrative-roles"></a>Control de acceso para los Roles administrativos
Cuando un usuario abre cualquiera de las herramientas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que requieren acceso a las bases de datos o los recursos de Windows, el usuario interactivo de la herramienta debe disponer de los derechos de usuario de SQL Server y Windows adecuados para realizar las diversas tareas correspondientes.  
  
 Una o varias de las herramientas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] obtienen acceso a las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por tanto, el servidor BizTalk Server debe conceder cierto nivel de acceso a cada base de datos a los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por otro lado, la preservación de la seguridad requiere que los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tengan solo los derechos de usuario necesarios para realizar sus tareas. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cumple ambos requisitos mediante los roles de base de datos de SQL Server. Siempre que cree un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos a través de la instalación o la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea automáticamente roles de base de datos de SQL Server para ambas funciones administrativas en esa base de datos. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] concede cada rol y cualquier inicio de sesión de SQL Server asignado al rol, los derechos de usuario mínimos necesarios para los administradores en los objetos (tablas, vistas, procedimientos almacenados, etcetera) para realizar tareas administrativas en esa base de datos de SQL Server.  
  
> [!NOTE]
>  Hay ciertas tareas administrativas para las que los administradores de BizTalk deben tener más permisos que los que reciben a través de los roles de SQL Server: por ejemplo, la creación de instancias de host. Para obtener más información acerca de estos permisos adicionales, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], hay dos Roles administrativos: el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrador y el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operador. El administrador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es un rol con muchos privilegios que proporciona acceso a los datos de configuración y de seguimiento. El operador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es un rol de pocos privilegios que proporciona acceso solo para supervisar y solucionar problemas de acciones. La grupo Operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- Es un rol administrativo de pocos privilegios, sin acceso a los datos de los mensajes.  
  
- Permite a los miembros supervisar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para detectar errores, realizar consultas para detectar instancias o mensajes suspendidos y ver la configuración.  
  
- Impide que los miembros cambien la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por ejemplo, los operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no pueden cambiar puertos de envío, ubicaciones de recepción ni filtros de puertos, ni tampoco implementar artefactos nuevos.  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea el rol predeterminado de administrador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuando se instala el producto por primera vez. De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le asigna el nombre Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], aunque puede elegir un nombre diferente.  
  
  Igualmente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea en cada base de datos un rol de base de datos de SQL Server para el grupo de usuarios de cada host, y le concede los derechos de usuario mínimos para que el grupo de usuarios realice tareas para ese host. Debe agregar los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] al grupo de administradores afiliados de inicio de sesión único. Para obtener más información acerca de Enterprise Single Sign-On, vea [SSO utilizando](../core/using-sso.md).  
  
> [!CAUTION]
>  Los administradores de BizTalk deben tener plena confianza en el origen del ensamblado que implementarán en el sistema. Si implementan ensamblados con código del que no están seguros, pueden exponer el entorno de BizTalk a ataques potenciales. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se aplica ninguna restricción en las acciones que los componentes de código personalizado pueden realizar cuando el motor de BizTalk los invoca.  
  
## <a name="see-also"></a>Vea también  
 [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md)   
 [Cuentas de grupos y de usuario de Windows en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)