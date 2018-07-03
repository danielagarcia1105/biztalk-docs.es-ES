---
title: 'De sesión único: Evento 10655 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bb6a8dd-35e4-40a6-8900-450a9b6de249
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ce0442b02667ce9796d9418dae4b1700dd757d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013013"
---
# <a name="single-sign-on-event-10655"></a>De sesión único: Evento 10655
## <a name="details"></a>Detalles  

|                 |                                                                              |
|-----------------|------------------------------------------------------------------------------|
|  Nombre del producto   |                          Inicio de sesión único (SSO) empresarial                           |
| Versión del producto |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]          |
|    Identificador del evento     |                                    10655                                     |
|  Origen del evento   |                                    ENTSSO                                    |
|    Componente    |                                     N\D                                      |
|  Nombre simbólico  |                   SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED                   |
|  Texto del mensaje   | Acceso denegado al servidor de sincronización de contraseñas (para ping).%r<br /><br /> Usuario cliente: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que se envió un mensaje al servidor [nombre] pero se bloqueó la respuesta. Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el servidor.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con soporte técnico de Microsoft.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
