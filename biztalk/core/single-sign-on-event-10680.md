---
title: 'De sesión único: Evento 10680 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ce2871618722af1fce4175be715c8ac1fa55a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974901"
---
# <a name="single-sign-on-event-10680"></a>De sesión único: Evento 10680
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                        Inicio de sesión único (SSO) empresarial                                                                                                                                        |
| Versión del producto |                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                        |
|    Identificador del evento     |                                                                                                                                                  10680                                                                                                                                                  |
|  Origen del evento   |                                                                                                                                                 ENTSSO                                                                                                                                                  |
|    Componente    |                                                                                                                                                   N\D                                                                                                                                                   |
|  Nombre simbólico  |                                                                                                                                      SSO_WARN_PS_GET_CREDS_FAILED                                                                                                                                       |
|  Texto del mensaje   | No se cambió la contraseña de la cuenta externa porque no se pudieron obtener las credenciales externas existentes de la base de datos de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4 %r<br /><br /> Código de error: %5 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se cambió la contraseña de la cuenta externa porque no se pudieron obtener las credenciales externas existentes de la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

-   Compruebe las credenciales externas.  

-   Si las credenciales externas no son válidas, use las herramientas de administración de SSO para establecerlas para esta cuenta externa. Debe establecer la contraseña externa (para la cuenta especificada) en todas las aplicaciones asociadas.  

## <a name="more-info"></a>Más información

- [Sincronización de contraseñas](../core/password-synchronization2.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
