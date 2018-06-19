---
title: 'Inicio de sesión único: Evento 10662 | Documentos de Microsoft'
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
ms.openlocfilehash: 8b941aa09b31f7e671625a7521843cd1059076da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270956"
---
# <a name="single-sign-on-event-10662"></a>Inicio de sesión único: Evento 10662
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10662|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED|  
|Texto del mensaje|Se recibió un cambio de contraseña de Windows desde PCNS.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Cuenta de Windows: %2 %r<br /><br /> Datos adicionales: %3 %r<br /><br /> Usuario cliente: %4|  
  
## <a name="explanation"></a>Explicación  
 Este evento de información indica que se recibió un cambio de contraseña de Windows proveniente del servicio de notificación de cambio de contraseña (PCNS).  
  
## <a name="user-action"></a>Acción del usuario  
  
-   No es necesario que el usuario realice ninguna acción.  
  
## <a name="more-info"></a>Más información
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)  
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]