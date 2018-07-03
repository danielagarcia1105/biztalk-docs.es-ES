---
title: 'De sesión único: Evento 10739 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a08c0b5194b3c6cb2a75966a33d7215fd0b7b499
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969453"
---
# <a name="single-sign-on-event-10739"></a>De sesión único: Evento 10739
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                               Inicio de sesión único (SSO) empresarial                                                                               |
| Versión del producto |                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                               |
|    Identificador del evento     |                                                                                         10739                                                                                         |
|  Origen del evento   |                                                                                        ENTSSO                                                                                         |
|    Componente    |                                                                                          N\D                                                                                          |
|  Nombre simbólico  |                                                                       SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER                                                                        |
|  Texto del mensaje   | No se pudo actualizar la contraseña de Windows en la base de datos de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3\\%4 %r<br /><br /> Código de error: %5 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que SSO no pudo actualizar la contraseña de Windows en la base de datos de SSO. El mensaje de advertencia indica que existen varias causas posibles para el error. En algunos casos, esta advertencia podría indicar un problema de configuración; en otros casos, es posible que se haya eliminado la asignación mientras el cambio de contraseña estaba en curso.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Intente cambiar la contraseña nuevamente.  

- Si los intentos adicionales generan error, cambie la contraseña manualmente mediante las herramientas de línea de comandos o de la interfaz de usuario.  

  Para obtener más información, vea los recursos siguientes:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
