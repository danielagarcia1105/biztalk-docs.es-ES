---
title: 'De sesión único: Evento 10662 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe707f23-ad54-4adb-a755-8d706a75efa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f33d106f7c272f74f99ef537e5083d9bdb015ecb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984709"
---
# <a name="single-sign-on-event-10662"></a>De sesión único: Evento 10662
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                             Inicio de sesión único (SSO) empresarial                                                                             |
| Versión del producto |                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    Identificador del evento     |                                                                                       10662                                                                                       |
|  Origen del evento   |                                                                                      ENTSSO                                                                                       |
|    Componente    |                                                                                        N\D                                                                                        |
|  Nombre simbólico  |                                                                     SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED                                                                     |
|  Texto del mensaje   | Se recibió un cambio de contraseña de Windows desde PCNS.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Datos adicionales: %3 %r<br /><br /> Usuario cliente: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que se recibió un cambio de contraseña de Windows proveniente del servicio de notificación de cambio de contraseña (PCNS).  

## <a name="user-action"></a>Acción del usuario  

-   No es necesario que el usuario realice ninguna acción.  

## <a name="more-info"></a>Más información

- [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
