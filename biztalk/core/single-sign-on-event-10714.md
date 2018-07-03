---
title: 'De sesión único: Evento 10714 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30523330ccaabddb94acf1ca1eba7d5c46c5fe0c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985301"
---
# <a name="single-sign-on-event-10714"></a>De sesión único: Evento 10714
## <a name="details"></a>Detalles  

|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                     Inicio de sesión único (SSO) empresarial                                     |
| Versión del producto |                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                     |
|    Identificador del evento     |                                               10714                                               |
|  Origen del evento   |                                              ENTSSO                                               |
|    Componente    |                                                N\D                                                |
|  Nombre simbólico  |                             SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED                              |
|  Texto del mensaje   | Los intentos caducaron; se descarta la notificación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que caducaron los intentos de notificación de la sincronización de contraseñas y que se ha descartado la notificación.  

 Cuando un cambio de contraseña (de Windows a un sistema externo) se envía a un adaptador de sincronización de contraseñas, éste confirma que ha procesado correctamente tal cambio. Si el cambio de contraseña no se realiza dentro del período especificado, o si se produce otro problema durante el cambio, el cambio de contraseña se envía nuevamente al adaptador de sincronización de contraseñas. Esto se lleva a cabo un número limitado de veces (reintentos máximos) y, después de este límite, se descarta la notificación de cambio de contraseña.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

  Para obtener más información, vea los recursos siguientes:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
