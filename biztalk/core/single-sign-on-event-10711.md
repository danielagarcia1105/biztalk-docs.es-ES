---
title: 'De sesión único: Evento 10711 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40722fe1-4be9-40d3-b5c5-a740a4b59f45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9966cd2f588d34c3be60282bc7acfa54cd1f42b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982581"
---
# <a name="single-sign-on-event-10711"></a>De sesión único: Evento 10711
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                             Inicio de sesión único (SSO) empresarial                                                                                                             |
| Versión del producto |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    Identificador del evento     |                                                                                                                       10711                                                                                                                       |
|  Origen del evento   |                                                                                                                      ENTSSO                                                                                                                       |
|    Componente    |                                                                                                                        N\D                                                                                                                        |
|  Nombre simbólico  |                                                                                                         SSO_WARN_PS_MISSING_INITIAL_CREDS                                                                                                         |
|  Texto del mensaje   | Cambio de contraseña externa. Algunos campos de credenciales externas faltantes de esta asignación se han establecido en los valores predeterminados.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se recibió un cambio de contraseña externa con credenciales faltantes. En esos campos se usaron los valores predeterminados.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Si es necesario, establezca las credenciales para que coincidan.  

  Para obtener más información, vea los recursos siguientes:  

- [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
