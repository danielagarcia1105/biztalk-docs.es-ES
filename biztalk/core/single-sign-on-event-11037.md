---
title: 'De sesión único: Evento 11037 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceec837a53d4cad3c236373a907497795efbd12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998901"
---
# <a name="single-sign-on-event-11037"></a>De sesión único: Evento 11037
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                               Inicio de sesión único (SSO) empresarial                                                                                                               |
| Versión del producto |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    Identificador del evento     |                                                                                                                         11037                                                                                                                         |
|  Origen del evento   |                                                                                                                        ENTSSO                                                                                                                         |
|    Componente    |                                                                                                                          N/D                                                                                                                          |
|  Nombre simbólico  |                                                                                                              SSO_INFO_PS_MAPPING_INVALID                                                                                                              |
|  Texto del mensaje   | Cambio de contraseña externa. No se cambió la contraseña de la cuenta externa porque la asignación ya no es válida.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Cuenta externa: %4 |
  
## <a name="explanation"></a>Explicación  
 La asignación ya no forma parte del grupo de usuarios de aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 El mensaje enumera el nombre de la cuenta externa y la aplicación. Puede usar esta información para averiguar por qué la asignación ya no es válida.