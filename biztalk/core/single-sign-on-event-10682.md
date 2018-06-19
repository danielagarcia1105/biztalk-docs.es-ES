---
title: 'Inicio de sesión único: Evento 10682 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46f0f425-3946-4bac-a412-488c4afe460d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79aeff556fbbbbbbbcf41f63a37ab3b47311d697
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271412"
---
# <a name="single-sign-on-event-10682"></a>Inicio de sesión único: Evento 10682
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10682|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_REPLAY_INVALID_DIR_FOUND|  
|Texto del mensaje|Se encontró un directorio en el directorio de archivos de reproducción - será ignored.%r<br />Directorio: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se encontró un directorio en el directorio de archivos de reproducción. La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. En este caso, los cambios de contraseña se almacenan en un archivo cifrado temporal y se reproducen en la base de datos SSO cuando vuelva a estar disponible. El directorio de archivos de reproducción debe contener archivos de reproducción solamente. Este error se emite si se encuentra un directorio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Use la herramienta de línea de comandos "ssoconfig -replayFiles" para cambiar el directorio de reproducción.  
  
-   Elimine el directorio con error si no se encuentra en uso.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo configurar la sincronización de contraseña](../core/how-to-configure-password-synchronization.md)  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)