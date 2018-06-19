---
title: Consideraciones de seguridad para el Portal de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0f5220eba5b66daf41dffc7ab74f93df8bb509
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269388"
---
# <a name="security-considerations-for-the-bam-portal"></a>Consideraciones de seguridad para el portal de BAM
Con el principio de privilegios mínimos, las cuentas de usuario deben tener permisos restrictivos para realizar las tareas habituales en el portal de BAM. Tenga en cuenta las siguientes consideraciones cuando configure sus cuentas de usuario para BAM para equilibrar la seguridad con el acceso apropiado para usuarios.  
  
## <a name="user-accounts"></a>Cuentas de usuario  
 Cuentas de usuario con permisos mínimos no pueden usar el navigationfeature distribuida portal de BAM. Para poder utilizar esta característica, estas cuentas deben tener suficientes permisos para permitir el acceso a los servicios Web en el equipo remoto y en el local.  
  
 Es necesario que las cuentas de usuario para los servicios Web de BAM tengan permisos para obtener acceso a las bases de datos a las que se hace referencia y que sean miembro del rol BAM_ManagementWS de BAM en las bases de datos a las que se hace referencia.  
  
 Deben tenerse en cuenta estas consideraciones para los siguientes tipos de usuario.  
  
-   Los usuarios de dominio deben tener permisos de acceso a equipos remotos que alojan bases de datos de importación principal a las que se está obteniendo acceso.  
  
-   Los usuarios que tienen asignados un rol de usuario local no pueden utilizar la exploración distribuida.  
  
## <a name="administrator-accounts"></a>Cuentas de administrador  
 Los administradores tienen que ser miembros del grupo securityadmin o del sysadmin para conceder permisos a los usuarios de dominio.  
  
 Para ejecutar la utilidad de administración de BAM, debe ser, al menos, operador de base de datos para las bases de datos de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Portal de BAM](../core/bam-portal.md)