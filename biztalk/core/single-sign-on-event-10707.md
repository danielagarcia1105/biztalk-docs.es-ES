---
title: 'Inicio de sesión único: Evento 10707 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81f4d484aa7a69f23cb66a921f1c630db9fcf790
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="single-sign-on-event-10707"></a>Inicio de sesión único: Evento 10707
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10707|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_NO_APP_SYNC|  
|Texto del mensaje|Los marcadores de sincronización de contraseñas de este adaptador deben permitir la sincronización de contraseñas y deben coincidir con los marcadores globales. Compruebe los marcadores de adaptador y los marcadores globales.%r<br /><br /> Adaptador: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que los marcadores de sincronización de contraseñas de este adaptador deben permitir la sincronización de contraseñas y deben coincidir con los marcadores globales.  
  
 La sincronización de contraseñas para un adaptador de sincronización de contraseñas se controla mediante dos marcadores, uno permite el envío de contraseñas a sistemas externos (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) y el otro permite la recepción de contraseñas de sistemas externos (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB). Para lograr una sincronización de contraseñas correcta, estos marcadores deben establecerse tanto para los "marcadores globales" como para los marcadores del adaptador específico. Este evento de advertencia se emite cuando un adaptador de sincronización de contraseñas necesita sincronización de contraseñas pero ninguno de estos marcadores está establecido para los "marcadores globales" y los marcadores del adaptador.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Use el complemento MMC del Administrador de SSO (sistema &#124; propiedades &#124; opciones) o la herramienta de línea de comandos `ssomanage –enable winsync/extsync` para habilitar los marcadores globales.  
  
## <a name="more-info"></a>Más información
  
-   **Marcas de inicio de sesión único de Enterprise** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)