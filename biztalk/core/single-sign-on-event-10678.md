---
title: 'De sesión único: Evento 10678 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fa3cde1cb26023ab4115f5538b8a3081eaaf1bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977437"
---
# <a name="single-sign-on-event-10678"></a>De sesión único: Evento 10678
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                    Inicio de sesión único (SSO) empresarial                                                                                                                    |
| Versión del producto |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    Identificador del evento     |                                                                                                                              10678                                                                                                                              |
|  Origen del evento   |                                                                                                                             ENTSSO                                                                                                                              |
|    Componente    |                                                                                                                               N\D                                                                                                                               |
|  Nombre simbólico  |                                                                                                                   SSO_WARN_PASSWORD_MISMATCH                                                                                                                    |
|  Texto del mensaje   | Cambio de contraseña externa. La contraseña anterior proporcionada por el adaptador no coincide con la contraseña existente para la cuenta externa.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia incida que la contraseña anterior proporcionada por el adaptador no coincide con la contraseña existente para la cuenta externa.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, haga lo siguiente:  

-   Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta externa. Debe establecer la contraseña externa (para la cuenta especificada) en todas esas aplicaciones.  

## <a name="more-info"></a>Más información

- [Sincronización de contraseñas](../core/password-synchronization2.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
