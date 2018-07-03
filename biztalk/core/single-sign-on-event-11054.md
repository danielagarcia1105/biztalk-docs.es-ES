---
title: 'De sesión único: Evento 11054 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59dc801d-fc78-4561-8a26-9d815c86d842
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0225123b40abd32280a240daf1d3c072dc4d969a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999437"
---
# <a name="single-sign-on-event-11054"></a>De sesión único: Evento 11054
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                                                           Inicio de sesión único (SSO) empresarial                                                                                                                                                                           |
| Versión del producto |                                                                                                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                           |
|    Identificador del evento     |                                                                                                                                                                                     11054                                                                                                                                                                                     |
|  Origen del evento   |                                                                                                                                                                                    ENTSSO                                                                                                                                                                                     |
|    Componente    |                                                                                                                                                                                      N/D                                                                                                                                                                                      |
|  Nombre simbólico  |                                                                                                                                                                         SSO_WARN_APP_USERS_NOT_GROUP                                                                                                                                                                          |
|  Texto del mensaje   | La cuenta de usuarios de aplicación contiene una o varias cuentas individuales (no de grupo). Si estas cuentas individuales se eliminan de Active Directory o del equipo local, deberán quitarse de inmediato del sistema SSO; de lo contrario, se considerarán un riesgo de seguridad.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Usuarios de aplicación: %2 %r<br /><br /> Las cuentas individuales: %3 |
  
## <a name="explanation"></a>Explicación  
 La eliminación de una cuenta individual en el equipo local o de Active Directory no elimina automáticamente esa cuenta en el sistema SSO. Es decir, si se eliminó la cuenta USER1 localmente, y después otro usuario (por ejemplo, un empleado nuevo) se incorpora al sistema con ese mismo nombre, el sistema SSO le concede al nuevo USER1 todos los derechos de seguridad correspondientes al USER1 original. Esto presenta un riesgo de seguridad.  
  
 Como procedimiento recomendado, las cuentas de administración de SSO deben usar cuentas de grupo (no individuales) de Active Directory.  
  
## <a name="user-action"></a>Acción del usuario  
 No es necesario que el usuario realice ninguna acción hasta que se elimine una cuenta individual en el equipo local o de Active Directory. Cuando esto suceda, el usuario deberá eliminar la cuenta individual en el sistema SSO tan pronto como sea posible.