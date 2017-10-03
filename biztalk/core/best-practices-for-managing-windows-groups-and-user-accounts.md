---
title: Procedimientos recomendados para administrar las cuentas de usuario y grupos de Windows | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, Windows groups
- authenticating, best practices
- Windows groups, security
- best practices, user accounts
- best practices, security
- security, best practices
- user accounts, security
- authenticating, security
- Windows groups, best practices
- best practices, authenticating
- user accounts, best practices
- hosts, security
- hosts, best practices
- best practices, hosts
ms.assetid: 0c4a141e-97ce-434a-8e45-a56c634bbd6c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f7560e3867bf290f20e0f2f49a740d7298131b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a>Prácticas recomendadas para administrar grupos de Windows y cuentas de usuario
En esta sección, se detallan prácticas recomendadas y sugerencias para administrar la seguridad de grupos de Windows y de cuentas de usuario.  
  
-   **Utilice las cuentas de servicio con privilegios mínimos necesarios para las instancias de host**  
  
     Para garantizar la seguridad del entorno de BizTalk Server, se recomienda utilizar cuentas de servicio con los privilegios mínimos necesarios para ejecutar instancias de host. Para obtener más información acerca de los privilegios mínimos requeridos por las cuentas de servicio, consulte [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md).  
  
-   **Use grupos de usuarios diferentes para la autenticación de confianza y hosts que no son de confianza**  
  
     Para garantizar que los hosts con autenticación que no es de confianza tengan menos privilegios que los hosts con autenticación de confianza, se deben utilizar cuentas de servicio distintas para cada host.  
  
-   **Usar un grupo de usuario diferente para cada Host de BizTalk**  
  
     Para maximizar el límite de seguridad entre hosts, se recomienda utilizar un grupo de usuarios de Windows diferente para cada uno de los hosts de BizTalk del grupo de BizTalk.  
  
-   **Quite el usuario de instalación desde el grupo de administradores de BizTalk Server**  
  
     Al instalar BizTalk Server en un equipo único con grupos locales, el usuario que lleva a cabo una instalación interactiva de BizTalk Server se agrega automáticamente al grupo de administradores de BizTalk Server. Con ello, se permite al usuario configurar BizTalk Server con el administrador de configuración.  
  
     Si el usuario que instala BizTalk Server no va a encargarse de su administración, se recomienda quitar a este usuario del grupo de administradores de BizTalk Server una vez configurada la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la seguridad de servidor BizTalk Server](../core/managing-biztalk-server-security.md)