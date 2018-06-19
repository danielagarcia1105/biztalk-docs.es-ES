---
title: Configuración de SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, command line utilities
- configuring, SSO
- SSO, interfaces
- SSOConfig [SSO]
- SSO, configuring
- SSOClient [SSO]
- SSO, tools
- SSOManage [SSO]
ms.assetid: 6f755735-9b48-4771-beec-ced844f3d532
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d729633717d709a83c10e9b50c55791029902010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233044"
---
# <a name="configuring-sso"></a>Configuración de SSO
Puede configurar el inicio de sesión único empresarial con utilidades de la línea de comandos, herramientas de la interfaz de usuario o interfaces de COM o Microsoft .NET.  
  
## <a name="sso-command-line-utilities"></a>Utilidades de la línea de comandos de SSO  
 Dispone de tres utilidades de la línea de comandos para realizar tareas de inicio de sesión único empresarial:  
  
 **SSOConfig.** Habilita un administrador de SSO para configurar la base de datos de SSO y administrar el secreto principal.  
  
> [!NOTE]
>  El Asistente para configuración crea la base de datos de SSO y el servidor secreto principal.  
  
 **SSOManage.** Permite a los administradores SSO, administradores afiliados de SSO y administradores de la aplicación actualizar la base de datos SSO para agregar, eliminar y administrar aplicaciones, administrar asignaciones de usuarios y para establecer credenciales para la afiliada usuarios de la aplicación. Algunas operaciones las pueden llevar a cabo sólo los administradores de SSO o sólo los administradores de SSO y los administradores afiliados de SSO. Todas las operaciones que pueden realizar los administradores de aplicación las pueden realizar también los administradores de SSO y los administradores afiliados de SSO.  
  
 **SSOClient.** Permite a los usuarios de inicio de sesión único administrar sus propias asignaciones de usuario y establecer sus credenciales.  
  
 Para obtener más información acerca de las cuentas SSO, vea [grupos de usuarios de SSO](../core/sso-user-groups.md).  
  
## <a name="sso-ui-tools"></a>Herramientas de la interfaz de usuario de SSO  
 **Enterprise SSO complemento MMC.** Habilita a los administradores de SSO, administradores afiliados de SSO y administradores de aplicación para actualizar la base de datos de SSO con el fin de agregar, eliminar y administrar aplicaciones, administrar asignaciones de usuario y establecer credenciales para los usuarios de aplicaciones afiliadas. Algunas operaciones las pueden realizar únicamente los administradores de SSO, o sólo los administradores de SSO y los administradores afiliados de SSO. Todas las operaciones que se pueden realizar los administradores de aplicación también pueden realizarse por los administradores de SSO y administradores afiliados de SSO.  
  
 **Utilidad de cliente SSO.** Permite a los usuarios finales administrar sus propias asignaciones y establecer sus credenciales usando la herramienta de interfaz de usuario.  
  
## <a name="sso-com-and-net-interfaces"></a>Interfaces de COM y .NET de SSO  
 El inicio de sesión único empresarial proporciona interfaces de programación COM y .NET que permiten crear componentes personalizados y secuencias de comandos para facilitar la administración del sistema SSO.  
  
## <a name="see-also"></a>Vea también  
 [Componentes de SSO](../core/sso-components.md)