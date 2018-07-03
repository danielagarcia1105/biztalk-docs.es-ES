---
title: 'De sesión único: Evento 10673 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fb923d1e137a00eed4ba87e65df71b226287aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975141"
---
# <a name="single-sign-on-event-10673"></a>De sesión único: Evento 10673
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                                                        Inicio de sesión único (SSO) empresarial                                                                                                                                                                         |
| Versión del producto |                                                                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    Identificador del evento     |                                                                                                                                                                                  10673                                                                                                                                                                                   |
|  Origen del evento   |                                                                                                                                                                                  ENTSSO                                                                                                                                                                                  |
|    Componente    |                                                                                                                                                                                   N\D                                                                                                                                                                                    |
|  Nombre simbólico  |                                                                                                                                                                SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED                                                                                                                                                                 |
|  Texto del mensaje   | El cambio de contraseña externa provocará cambios en varias cuentas de Windows.%r<br /><br /> Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 %r<br /><br /> Cuenta de Windows 1: %4 %r<br /><br /> Cuenta de Windows 2: %5 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que el cambio de contraseña externa provocará cambios en varias cuentas de Windows.  

## <a name="user-action"></a>Acción del usuario  

-   No es necesario que el usuario realice ninguna acción.  

## <a name="more-info"></a>Más información

- [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [Sincronización de contraseñas](../core/password-synchronization2.md)
