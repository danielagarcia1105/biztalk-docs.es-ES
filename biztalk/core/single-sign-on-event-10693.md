---
title: 'De sesión único: Evento 10693 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 672bac7d-0ccc-4a42-a49d-57e387f4cf3a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f9dd254fd81d54f0c60a2ea8b0a143e94ddd516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009485"
---
# <a name="single-sign-on-event-10693"></a>De sesión único: Evento 10693
## <a name="details"></a>Detalles  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                       Inicio de sesión único (SSO) empresarial                                        |
| Versión del producto |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    Identificador del evento     |                                                 10693                                                  |
|  Origen del evento   |                                                 ENTSSO                                                 |
|    Componente    |                                                  N\D                                                   |
|  Nombre simbólico  |                                    SSO_WARNING_REPLAY_CANNOT_CREATE                                    |
|  Texto del mensaje   | No se pudo crear el archivo de reproducción o progreso.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> Código de error: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que SSO no pudo crear un archivo de reproducción o progreso cuando se interrumpió la conexión con la base de datos de SSO.  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
