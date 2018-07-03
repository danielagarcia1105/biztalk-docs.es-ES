---
title: 'De sesión único: Evento 10681 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d2b400db062dc76b32d071032ee75c55ef48046
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011669"
---
# <a name="single-sign-on-event-10681"></a>De sesión único: Evento 10681
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                              Inicio de sesión único (SSO) empresarial                                                                                               |
| Versión del producto |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    Identificador del evento     |                                                                                                        10681                                                                                                         |
|  Origen del evento   |                                                                                                        ENTSSO                                                                                                        |
|    Componente    |                                                                                                         N\D                                                                                                          |
|  Nombre simbólico  |                                                                                         SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE                                                                                          |
|  Texto del mensaje   | Cambio de contraseña externa. No se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se cambió la contraseña de Windows porque uno o varios cambios de cuenta externa tienen error.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  

-   Compruebe los registros del sistema y eventos de aplicación para los eventos asociados.  

-   Compruebe la configuración del adaptador mediante las herramientas de administración de SSO.  

-   Compruebe los sistemas externos.  

## <a name="more-info"></a>Más información

- [Sincronización de contraseñas](../core/password-synchronization2.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
