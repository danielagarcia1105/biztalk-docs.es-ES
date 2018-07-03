---
title: 'De sesión único: Evento 10683 | Microsoft Docs'
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
ms.openlocfilehash: 5a8a769e9cf74a3d0119ca814d7201c1e14e7304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978309"
---
# <a name="single-sign-on-event-10683"></a>De sesión único: Evento 10683
## <a name="details"></a>Detalles  

|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
|  Nombre del producto   |                        Inicio de sesión único (SSO) empresarial                         |
| Versión del producto |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]        |
|    Identificador del evento     |                                  10683                                   |
|  Origen del evento   |                                  ENTSSO                                  |
|    Componente    |                                   N\D                                    |
|  Nombre simbólico  |                   SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD                   |
|  Texto del mensaje   | Se eliminó un archivo de reproducción porque era demasiado old.%r<br />Archivo de reproducción: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se eliminó el archivo de reproducción porque era demasiado antiguo. La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. En este caso, los cambios de contraseña se almacenan en un archivo cifrado temporal y se reproducen nuevamente en la base de datos de SSO cuando ésta vuelve a estar disponible. Si al momento de la reproducción de los archivos en esta base de datos se detecta un archivo demasiado antiguo, se lo descarta. Se descartan todos los cambios de contraseña antigua por el sistema de sincronización de contraseña de inicio de sesión único; el `password sync age` parámetro determina la edad máxima de contraseña de las solicitudes de cambio y que pueden controlarse mediante las herramientas de línea de comandos **ssoconfig – syncAge** o la MMC de administración de SSO.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
