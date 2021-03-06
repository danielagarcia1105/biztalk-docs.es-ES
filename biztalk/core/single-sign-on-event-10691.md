---
title: 'De sesión único: Evento 10691 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fcefb49-c068-41e9-850d-99864c0899bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69acc99acd002f23d3d6e02430d58fb88f9651a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009901"
---
# <a name="single-sign-on-event-10691"></a>De sesión único: Evento 10691
## <a name="details"></a>Detalles  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                          Inicio de sesión único (SSO) empresarial                                          |
| Versión del producto |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    Identificador del evento     |                                                    10691                                                    |
|  Origen del evento   |                                                   ENTSSO                                                    |
|    Componente    |                                                     N\D                                                     |
|  Nombre simbólico  |                                       SSO_ERROR_REPLAY_FILE_MISMATCH                                        |
|  Texto del mensaje   | El archivo de reproducción está dañado.%r<br /><br /> Archivo de reproducción: %1 %r<br /><br /> Datos adicionales: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo abrir el archivo de reproducción porque no coincide con el archivo de progreso correspondiente. Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

- Elimine el archivo de reproducción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
