---
title: Grupos de usuarios de inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- groups, SSO
- user accounts, administrators
- service accounts, SSO
- SSO, user groups
- SSO, service accounts
- SSO, administrator accounts
ms.assetid: e279001e-c724-4a2d-8939-0ba9dd08a19c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cee8780b645cc6f58c0a75526a695e2148893023
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017292"
---
# <a name="sso-user-groups"></a>Grupos de usuarios de inicio de sesión único
Para configurar y administrar el sistema de inicio de sesión único (SSO) empresarial, deberá crear ciertas cuentas y grupos de Windows para cada una de estas funciones. Al configurar las cuentas de acceso en SSO empresarial, puede especificar más de una cuenta para cada una de estas funciones. En esta sección se describen las funciones.  
  
> [!IMPORTANT]
>  Se recomienda encarecidamente utilizar grupos de dominio al configurar el SSO.  
  
> [!NOTE]
>  Por motivos de seguridad, el sistema de SSO no admite las cuentas integradas.  
  
## <a name="single-sign-on-administrators"></a>Administradores de inicio de sesión único (SSO)  
 Los administradores de SSO tienen asignado el nivel más alto de derechos de usuario del sistema SSO. Pueden realizar las acciones siguientes:  
  
- Crear y administrar la base de datos de SSO.  
  
- Crear y administrar el secreto principal.  
  
- Habilitar y deshabilitar el sistema de SSO.  
  
- Crear adaptadores de sincronización de contraseñas.  
  
- Habilitar y deshabilitar la sincronización de contraseñas en el sistema de SSO.  
  
- Habilitar y deshabilitar el SSO iniciado por host.  
  
- Llevar a cabo todas las tareas administrativas.  
  
  La cuenta de administradores de SSO pueden ser una cuenta de grupo de Windows o una cuenta individual. La cuenta de administradores de SSO también puede ser una cuenta individual o de grupo local, o un dominio. Si se utiliza una cuenta individual, no se podrá cambiar esta cuenta por otra cuenta individual. Por tanto, se recomienda no utilizar una cuenta individual. Puede cambiar esta cuenta por una cuenta de grupo, siempre y cuando la cuenta original sea miembro de la nueva cuenta.  
  
> [!IMPORTANT]
>  La cuenta de servicio que ejecute el inicio de sesión único (SSO) empresarial deberá ser miembro de esta cuenta. Con el fin de proteger el entorno, asegúrese de que no existe otro servicio que utilice la misma cuenta de servicio.  
  
## <a name="single-sign-on-affiliate-administrators"></a>Administradores afiliados de inicio de sesión único (SSO)  
 El administrador afiliado de SSO define las aplicaciones afiliadas que contiene el sistema de SSO. Las aplicaciones afiliadas son entidades lógicas que representan el sistema de servidor con el que se conecta a través de SSO. Los administradores afiliados de SSO pueden llevar a cabo las siguientes acciones:  
  
- Crear, administrar y eliminar aplicaciones afiliadas.  
  
- Especificar la cuenta de administradores de aplicación de cada aplicación afiliada.  
  
- Realizar todas las tareas de administración que puedan realizar los administradores de aplicación y los usuarios de aplicación.  
  
  La cuenta de administradores afiliados de SSO puede ser una cuenta de grupo de Windows o una cuenta individual. La cuenta de administradores afiliados de SSO también puede ser un dominio, o una cuenta o grupo local.  
  
## <a name="application-administrators"></a>Administradores de aplicación  
 Hay un grupo de administradores de aplicación por cada aplicación afiliada.  
  
 Los miembros de este grupo pueden llevar a cabo las siguientes acciones:  
  
-   Cambiar la cuenta de grupo de usuarios de aplicación.  
  
-   Crear, eliminar y administrar asignaciones de credenciales para todos los usuarios de una aplicación afiliada concreta.  
  
-   Definir las credenciales de los usuarios pertenecientes a dicha cuenta de grupo de usuarios de aplicación afiliada.  
  
-   Realizar todas las tareas de administración que puedan realizar los usuarios de aplicación.  
  
## <a name="application-users"></a>Usuarios de aplicación  
 Hay una cuenta de grupo de usuarios de aplicación por cada aplicación afiliada. Esta cuenta contiene la lista de usuarios finales de un entorno de inicio de sesión único (SSO) empresarial. Los miembros de esta cuenta pueden llevar a cabo las siguientes acciones:  
  
-   Buscar sus credenciales en la aplicación afiliada.  
  
-   Administrar sus asignaciones de credenciales en la aplicación afiliada.  
  
> [!NOTE]
>  Tenga cuidado a la hora de asignar grupos. Por ejemplo, es posible utilizar un grupo de usuarios de seguridad de BizTalk Server para el grupo de usuarios de aplicación de SSO. Antes de hacerlo, asegúrese de que todos los usuarios necesitan todo el acceso que estará a su disposición.  
  
## <a name="see-also"></a>Vea también  
 [Cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md)   
 [Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Descripción de SSO](../core/understanding-sso.md)