---
title: 'De sesión único: Evento 10654 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca59040b340d033ab6c355c0440378f09d87000
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974485"
---
# <a name="single-sign-on-event-10654"></a>De sesión único: Evento 10654
## <a name="details"></a>Detalles  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10654                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N\D                             |
|  Nombre simbólico  |        SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED         |
|  Texto del mensaje   |    Acceso denegado al servidor de sincronización de contraseñas (para Windows).%r     |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que se envió un mensaje al servidor [nombre] pero se bloqueó la respuesta. Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el servidor.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con soporte técnico de Microsoft.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
