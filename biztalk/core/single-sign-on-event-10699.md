---
title: 'De sesión único: Evento 10699 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3802f04d2adf7d95a6ff10ae208acabbc1acf8ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983373"
---
# <a name="single-sign-on-event-10699"></a>De sesión único: Evento 10699
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                       Inicio de sesión único (SSO) empresarial                                                                                                       |
| Versión del producto |                                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                       |
|    Identificador del evento     |                                                                                                                 10699                                                                                                                 |
|  Origen del evento   |                                                                                                                ENTSSO                                                                                                                 |
|    Componente    |                                                                                                                  N\D                                                                                                                  |
|  Nombre simbólico  |                                                                                           SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY                                                                                           |
|  Texto del mensaje   | Se recibió un cambio de contraseña externa desde un adaptador (del archivo de reproducción).%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 %r<br /><br /> Usuario cliente: %4 %r<br /><br /> Número de registro: %5 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que se recibió un cambio de contraseña externa desde un adaptador que estaba registrado para un archivo de reproducción. SSO está reproduciendo los cambios de contraseña externa almacenados desde el archivo de reproducción.  

 La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO. El archivo de progreso indica hasta qué punto SSO pudo leer el archivo de reproducción en caso de que se interrumpa nuevamente la comunicación con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
