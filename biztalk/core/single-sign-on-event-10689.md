---
title: 'De sesión único: Evento 10689 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79e4e31f-18e4-4f52-9466-18e58842942f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 277acc742cd49804559ba2c8e7aa157fb3c7092d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022811"
---
# <a name="single-sign-on-event-10689"></a>De sesión único: Evento 10689
## <a name="details"></a>Detalles  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  Nombre del producto   |                         Inicio de sesión único (SSO) empresarial                         |
| Versión del producto |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    Identificador del evento     |                                   10689                                   |
|  Origen del evento   |                                  ENTSSO                                   |
|    Componente    |                                    N\D                                    |
|  Nombre simbólico  |                 SSO_ERROR_REPLAY_INCORRECT_RECORD_VERSION                 |
|  Texto del mensaje   | El archivo de reproducción está dañado.%r<br /><br /> Archivo de reproducción: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que SSO restableció la comunicación con la base de datos de SSO, pero no pudo leer el archivo de reproducción porque está dañado. Si SSO no puede abrir un archivo de reproducción, continúa con el próximo archivo de reproducción (si existe).  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si los registros de eventos del sistema y de la aplicación presentan eventos asociados.  

- Elimine el archivo de reproducción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
