---
title: 'De sesión único: Evento 10671 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f321a971f89c535da26604c3e03a2b62ebf060e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000077"
---
# <a name="single-sign-on-event-10671"></a>De sesión único: Evento 10671
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                                                                  Inicio de sesión único (SSO) empresarial                                                                                                                                                                                  |
| Versión del producto |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    Identificador del evento     |                                                                                                                                                                                            10671                                                                                                                                                                                            |
|  Origen del evento   |                                                                                                                                                                                           ENTSSO                                                                                                                                                                                            |
|    Componente    |                                                                                                                                                                                             N\D                                                                                                                                                                                             |
|  Nombre simbólico  |                                                                                                                                                                         SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED                                                                                                                                                                          |
|  Texto del mensaje   | El cambio de contraseña de Windows provocará cambios en varias cuentas en el mismo sistema externo.%r<br /><br /> Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 %r<br /><br /> Cuenta externa 1: %4 %r<br /><br /> Cuenta externa 2: %5 |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que el cambio de contraseña de Windows provocará cambios en varias cuentas en el mismo sistema externo.  

## <a name="user-action"></a>Acción del usuario  

-   No es necesario que el usuario realice ninguna acción.  

## <a name="more-info"></a>Más información

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [Sincronización de contraseñas](../core/password-synchronization2.md)
