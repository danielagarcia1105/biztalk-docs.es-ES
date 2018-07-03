---
title: 'De sesión único: Evento 10709 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b114b8afb55c41171ef537a9dfc56d341943a226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014253"
---
# <a name="single-sign-on-event-10709"></a>De sesión único: Evento 10709
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                  Inicio de sesión único (SSO) empresarial                                                                                                                   |
| Versión del producto |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    Identificador del evento     |                                                                                                                            10709                                                                                                                             |
|  Origen del evento   |                                                                                                                            ENTSSO                                                                                                                            |
|    Componente    |                                                                                                                             N\D                                                                                                                              |
|  Nombre simbólico  |                                                                                                                SSO_WARN_PS_PCNS_ACCESS_DENIED                                                                                                                |
|  Texto del mensaje   | Los cambios de contraseña de Windows desde PCNS sólo se aceptarán si provienen de controladores de dominio del dominio de acceso.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Usuario cliente: %2 %r<br /><br /> Dominio de acceso: %3 %r<br /><br /> Sid de acceso: %4 %r<br /><br /> Código de error: %5 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se recibió un cambio de contraseña de Windows proveniente del servicio de notificación de cambio de contraseña (PCNS) en un servidor fuera del dominio del servidor de ENTSSO. Los cambios de contraseña de Windows sólo se aceptarán si provienen de controladores de dominio en el mismo dominio como el servidor de ENTSSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Configure un servidor de ENTSSO en el mismo dominio que PCNS.  

  Para obtener más información, vea los recursos siguientes:  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
