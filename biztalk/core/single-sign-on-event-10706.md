---
title: 'Inicio de sesión único: Evento 10706 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5703c81d87376349561f644da558b8594cd51b79
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22271564"
---
# <a name="single-sign-on-event-10706"></a>Inicio de sesión único: Evento 10706
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10706|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_PS_NO_GLOBAL_SYNC|  
|Texto del mensaje|Los adaptadores de grupo requieren que los marcadores globales permitan la sincronización de contraseñas. Compruebe los marcadores globales.%r<br /><br /> Adaptador: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que un adaptador de sincronización de contraseñas externas solicita la sincronización de contraseñas pero ninguno de los marcadores globales está establecido. Existen dos marcadores, que permite el envío de contraseñas a sistemas externos: (sso_flag_full_sync_from_windows_to_external) y otra que permite la recepción de contraseñas de sistemas externos (sso_flag_partial_sync_from_external_to_db).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  
  
-   Usar el SSO administrador complemento MMC, (sistema &#124; propiedades &#124; opciones) o la herramienta de línea de comandos `ssomanage –enable winsync/extsync` para habilitar los marcadores globales.  
  
## <a name="more-info"></a>Más información
  
-   **Marcas de inicio de sesión único de Enterprise** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)