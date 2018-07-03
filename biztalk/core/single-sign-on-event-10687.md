---
title: 'De sesión único: Evento 10687 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e928e779d8b2d22a20cc502fb65fd321fb99668c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976477"
---
# <a name="single-sign-on-event-10687"></a>De sesión único: Evento 10687
## <a name="details"></a>Detalles  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                               Inicio de sesión único (SSO) empresarial                                               |
| Versión del producto |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    Identificador del evento     |                                                         10687                                                         |
|  Origen del evento   |                                                        ENTSSO                                                         |
|    Componente    |                                                          N\D                                                          |
|  Nombre simbólico  |                                               SSO_INFO_REPLAY_COMPLETE                                                |
|  Texto del mensaje   | Se completó la reproducción de cambios de contraseña externa almacenados.%r<br /><br /> Archivo de reproducción: %1 %r<br /><br /> Datos adicionales: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que SSO completó la reproducción del archivo de cambios de contraseña externa almacenados. La sincronización de contraseñas usa los archivos de reproducción cuando el servidor de ENTSSO no puede comunicarse con la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  

- No es necesario que el usuario realice ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
