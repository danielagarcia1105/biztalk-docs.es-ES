---
title: 'De sesión único: Evento 10698 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aacd272480ddb58de38960ae8dc1a744815ced64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966477"
---
# <a name="single-sign-on-event-10698"></a>De sesión único: Evento 10698
## <a name="details"></a>Detalles  

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  Nombre del producto   |                      Inicio de sesión único (SSO) empresarial                       |
| Versión del producto |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    Identificador del evento     |                                10698                                 |
|  Origen del evento   |                                ENTSSO                                |
|    Componente    |                                 N\D                                  |
|  Nombre simbólico  |                     SSO_INFO_REPLAY_FILE_DELETED                     |
|  Texto del mensaje   | Se eliminó el archivo de reproducción o progreso.%r<br /><br /> Nombre de archivo: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que SSO eliminó un archivo de reproducción o progreso.  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
