---
title: 'De sesión único: Evento 10592 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fdf7259de2217c2e6cd616f58b3b1118bf991c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017260"
---
# <a name="single-sign-on-event-10592"></a>De sesión único: Evento 10592
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                             Inicio de sesión único (SSO) empresarial                                                              |
| Versión del producto |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    Identificador del evento     |                                                                       10592                                                                        |
|  Origen del evento   |                                                                       ENTSSO                                                                       |
|    Componente    |                                                                        N/D                                                                         |
|  Nombre simbólico  |                                                           SSO_WARN_TICKET_DECRYPT_FAILED                                                           |
|  Texto del mensaje   | No se puede descifrar el vale. El vale no es válido o puede haber caducado.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Código de error: %2 |
  
## <a name="explanation"></a>Explicación  
 El vale no es válido o puede haber caducado.  
  
## <a name="user-action"></a>Acción del usuario  
 Confirme si el vale que desea usar es válido y si no ha caducado.