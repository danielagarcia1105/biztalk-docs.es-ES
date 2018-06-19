---
title: 'Inicio de sesión único: Evento 10714 | Documentos de Microsoft'
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
ms.openlocfilehash: ba63ab9197dcf9629f03f3d6c96f064345aaa46e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271380"
---
# <a name="single-sign-on-event-10714"></a>Inicio de sesión único: Evento 10714
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10714|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED|  
|Texto del mensaje|Los intentos caducaron; se descarta la notificación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que caducaron los intentos de notificación de la sincronización de contraseñas y que se ha descartado la notificación.  
  
 Cuando un cambio de contraseña (de Windows a un sistema externo) se envía a un adaptador de sincronización de contraseñas, éste confirma que ha procesado correctamente tal cambio. Si el cambio de contraseña no se realiza dentro del período especificado, o si se produce otro problema durante el cambio, el cambio de contraseña se envía nuevamente al adaptador de sincronización de contraseñas. Esto se lleva a cabo un número limitado de veces (reintentos máximos) y, después de este límite, se descarta la notificación de cambio de contraseña.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo configurar la sincronización de contraseña](../core/how-to-configure-password-synchronization.md)  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)