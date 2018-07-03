---
title: 'De sesión único: Evento 10708 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63675191-41cb-43fc-9355-e4ddc3f354c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b052e3545aa67b27bc94de579faedde782c0dec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003093"
---
# <a name="single-sign-on-event-10708"></a>De sesión único: Evento 10708
## <a name="details"></a>Detalles  

|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                   Inicio de sesión único (SSO) empresarial                                                    |
| Versión del producto |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    Identificador del evento     |                                                             10708                                                              |
|  Origen del evento   |                                                             ENTSSO                                                             |
|    Componente    |                                                              N\D                                                               |
|  Nombre simbólico  |                                                    SSO_WARN_PS_NO_WIN_SYNC                                                     |
|  Texto del mensaje   | No se permite la sincronización de contraseñas desde Windows. Compruebe los marcadores globales.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Usuario cliente: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que Windows solicita la sincronización de contraseñas pero no se establecieron los marcadores globales. Hay dos marcadores, uno que permite el envío de contraseñas a sistemas externos: (sso_flag_full_sync_from_windows_to_external) y otra que permite la recepción de contraseñas de sistemas externos (sso_flag_partial_sync_from_external_to_db).  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

-   Use el inicio de sesión único administrador complemento MMC, (sistema &#124; propiedades &#124; opciones) o la herramienta de línea de comandos `ssomanage –enable winsync/extsync` para habilitar los marcadores globales.  

## <a name="more-info"></a>Más información

- **Marcas de inicio de inicio de sesión único de Enterprise** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)
