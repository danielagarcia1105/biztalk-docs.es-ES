---
title: 'De sesión único: Evento 10682 | Microsoft Docs'
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
ms.openlocfilehash: 5c7ed830c44404e0365505b7dc0f3a5c6fec8a85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999717"
---
# <a name="single-sign-on-event-10682"></a>De sesión único: Evento 10682
## <a name="details"></a>Detalles  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                   Inicio de sesión único (SSO) empresarial                                    |
| Versión del producto |                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    Identificador del evento     |                                             10682                                              |
|  Origen del evento   |                                             ENTSSO                                             |
|    Componente    |                                              N\D                                               |
|  Nombre simbólico  |                               SSO_WARN_REPLAY_INVALID_DIR_FOUND                                |
|  Texto del mensaje   | Se encontró un directorio en el directorio de archivos de reproducción - será ignored.%r<br />Directorio: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se encontró un directorio en el directorio de archivos de reproducción. La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. En este caso, los cambios de contraseña se almacenan en un archivo cifrado temporal y se reproducen nuevamente en la base de datos SSO cuando vuelva a estar disponible. El directorio de archivos de reproducción debe contener archivos de reproducción solamente. Este error se emite si se encuentra un directorio.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  

- Use la herramienta de línea de comandos "ssoconfig -replayFiles" para cambiar el directorio de reproducción.  

- Elimine el directorio con error si no se encuentra en uso.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
