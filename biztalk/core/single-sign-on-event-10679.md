---
title: 'De sesión único: Evento 10679 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbeb91e58582fcd37fca4c791b35a9edfc558c96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000357"
---
# <a name="single-sign-on-event-10679"></a>De sesión único: Evento 10679
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                           Inicio de sesión único (SSO) empresarial                                                                                                            |
| Versión del producto |                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                           |
|    Identificador del evento     |                                                                                                                     10679                                                                                                                      |
|  Origen del evento   |                                                                                                                     ENTSSO                                                                                                                     |
|    Componente    |                                                                                                                      N\D                                                                                                                       |
|  Nombre simbólico  |                                                                                                          SSO_WARN_PS_MAPPING_DISABLED                                                                                                          |
|  Texto del mensaje   | Cambio de contraseña externa. No se pudo cambiar la contraseña de la cuenta externa porque la asignación está deshabilitada.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se cambió la contraseña de la cuenta externa porque la asignación está deshabilitada.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, haga lo siguiente:  

-   Use las herramientas de administración de SSO para habilitar la asignación para este adaptador.  

## <a name="more-info"></a>Más información

- [Sincronización de contraseñas](../core/password-synchronization2.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
