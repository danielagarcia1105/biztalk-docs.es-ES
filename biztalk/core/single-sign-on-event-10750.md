---
title: 'De sesión único: Evento 10750 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0fdaf2-d429-40b9-adc3-eb134687fb1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28526c6695cbf8f9c29e99621d6cb2f852fa7021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984373"
---
# <a name="single-sign-on-event-10750"></a>De sesión único: Evento 10750
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                    Inicio de sesión único (SSO) empresarial                                                                                                                     |
| Versión del producto |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    Identificador del evento     |                                                                                                                              10750                                                                                                                               |
|  Origen del evento   |                                                                                                                              ENTSSO                                                                                                                              |
|    Componente    |                                                                                                                               N\D                                                                                                                                |
|  Nombre simbólico  |                                                                                                                SSO_ERROR_PS_WRONG_USER_NAME_TYPE                                                                                                                 |
|  Texto del mensaje   | PasswordChangeNotify: Tipo de nombre de usuario incorrecto. El único valor aceptado es USER_NAME_TYPE_NT4.<br /><br /> La configuración del destino es incorrecta en Active Directory.%r<br /><br /> Tipo de nombre de usuario: %1 %r<br /><br /> Usuario cliente: %2 %r<br /><br /> Código de error: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que la sincronización de contraseñas recibió un cambio de contraseña proveniente del servicio de notificación de cambio de contraseña (PCNS), pero que dicha contraseña tenía un formato incorrecto.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe la configuración de PCNS. PCNS sólo puede ejecutarse en un controlador de dominio.  

- Configure el tipo de nombre de usuario en USER_NAME_TYPE_NT4 en Active Directory.  

  Para obtener más información, vea los recursos siguientes:  

- Para obtener más información sobre el procedimiento para especificar el tipo de nombre de usuario, consulte la documentación de Active Directory.  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
