---
title: 'Inicio de sesión único: Evento 10731 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 605e77f0-61f2-4a97-9ea0-bdc56344e8d9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10960489638aa565a11ecc32c70fc3a8fc6d477b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270692"
---
# <a name="single-sign-on-event-10731"></a>Inicio de sesión único: Evento 10731
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10731|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_INVALID_USER_NOT_IN_GROUP|  
|Texto del mensaje|No se pudo crear la asignación porque el usuario especificado no es miembro de la cuenta de usuarios de aplicación.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Usuarios de aplicación: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se pudo crear la asignación porque el usuario especificado no es miembro de la cuenta de usuarios de aplicación.%r  
  
 Existe una cuenta de grupo de usuarios de aplicación para cada aplicación afiliada. Los miembros de esta cuenta pueden comprobar sus credenciales en la aplicación afiliada y, también, pueden administrar sus asignaciones de credenciales en ella.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Agregue el usuario especificado al grupo de usuarios de aplicación para la aplicación afiliada especificada.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Grupos de usuarios SSO](../core/sso-user-groups.md)  
  
-   [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)