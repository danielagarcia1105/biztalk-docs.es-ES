---
title: 'De sesión único: Evento 10746 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3f4fa77909ba53e16d3dffd31073ff93e233ed5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998869"
---
# <a name="single-sign-on-event-10746"></a>De sesión único: Evento 10746
## <a name="details"></a>Detalles  

|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                           Inicio de sesión único (SSO) empresarial                                                           |
| Versión del producto |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                           |
|    Identificador del evento     |                                                                     10746                                                                     |
|  Origen del evento   |                                                                    ENTSSO                                                                     |
|    Componente    |                                                                      N\D                                                                      |
|  Nombre simbólico  |                                                           SSO_WARN_PASSWORD_EXPIRED                                                           |
|  Texto del mensaje   | La contraseña de la cuenta externa caducó.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que caducó la contraseña de la cuenta externa.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, compruebe los registros de eventos de aplicación y del sistema para los errores asociados.    

## <a name="more-info"></a>Más información
Para obtener más información, vea los recursos siguientes:  

- **Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
