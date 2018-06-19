---
title: 'Inicio de sesión único: Evento 10683 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c383a02400523686f00011c5eb6f71c9542ec5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271548"
---
# <a name="single-sign-on-event-10683"></a>Inicio de sesión único: Evento 10683
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10683|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD|  
|Texto del mensaje|Se eliminó un archivo de reproducción porque era demasiado old.%r<br />Archivo de reproducción: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se eliminó el archivo de reproducción porque era demasiado antiguo. La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. En este caso, los cambios de contraseña se almacenan en un archivo cifrado temporal y se reproducen nuevamente en la base de datos de SSO cuando ésta vuelve a estar disponible. Si al momento de la reproducción de los archivos en esta base de datos se detecta un archivo demasiado antiguo, se lo descarta. Se descartan todos los cambios de contraseña anterior por el sistema de sincronización de contraseña SSO; el `password sync age` parámetro determina la duración máxima de contraseña de las solicitudes de cambio y que puede controlarse mediante las herramientas de línea de comandos **ssoconfig – syncAge** o la MMC de administración de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
  
-   No es necesario que el usuario realice ninguna acción.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo configurar la sincronización de contraseña](../core/how-to-configure-password-synchronization.md)  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)