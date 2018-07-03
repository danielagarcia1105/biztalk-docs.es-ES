---
title: 'De sesión único: Evento 10653 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0d85aca-20d9-4d65-8834-b31eacf143c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9f0edb3ce5fa7f8fb59c4b65914a9c8b6640adc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969461"
---
# <a name="single-sign-on-event-10653"></a>De sesión único: Evento 10653
## <a name="details"></a>Detalles  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10653                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N\D                             |
|  Nombre simbólico  |        SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED         |
|  Texto del mensaje   |    Acceso denegado al servidor de sincronización de contraseñas (para adaptadores).%r    |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que un cliente intentó comunicarse con el servidor pero se rechazó la llamada. Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con soporte técnico de Microsoft.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
