---
title: 'De sesión único: Evento 10694 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75faca65-48d9-45f6-b079-2b612ef3de76
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45d5bcd178020e6aee2b16e3cd3fbababd6b8498
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981653"
---
# <a name="single-sign-on-event-10694"></a>De sesión único: Evento 10694
## <a name="details"></a>Detalles  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  Nombre del producto   |                              Inicio de sesión único (SSO) empresarial                              |
| Versión del producto |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    Identificador del evento     |                                        10694                                        |
|  Origen del evento   |                                       ENTSSO                                        |
|    Componente    |                                         N\D                                         |
|  Nombre simbólico  |                         SSO_ERROR_REPLAY_INCORRECT_VERSION                          |
|  Texto del mensaje   | El archivo de reproducción o progreso está dañado.%r<br /><br /> Nombre de archivo: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de reproducción porque está dañado. Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
