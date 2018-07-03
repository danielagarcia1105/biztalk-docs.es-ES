---
title: 'De sesión único: Evento 10677 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1fc5bfbb6df26f1b1125a0d5d8b06a75e441f15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022002"
---
# <a name="single-sign-on-event-10677"></a>De sesión único: Evento 10677
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                    Inicio de sesión único (SSO) empresarial                                                                                                                     |
| Versión del producto |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    Identificador del evento     |                                                                                                                              10677                                                                                                                               |
|  Origen del evento   |                                                                                                                              ENTSSO                                                                                                                              |
|    Componente    |                                                                                                                               N\D                                                                                                                                |
|  Nombre simbólico  |                                                                                                                  SSO_WARN_NO_EXISTING_PASSWORD                                                                                                                   |
|  Texto del mensaje   | Cambio de contraseña externa. No se puede comprobar la contraseña anterior porque no existen credenciales para la cuenta externa.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se puede realizar el cambio de contraseña externa porque la contraseña anterior no tiene credenciales existentes.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  

-   Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta externa. Debe establecer la contraseña externa (para la cuenta especificada) en todas esas aplicaciones.  

## <a name="more-info"></a>Más información

- [Sincronización de contraseñas](../core/password-synchronization2.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
