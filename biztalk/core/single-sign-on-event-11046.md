---
title: 'De sesión único: Evento 11046 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb82191b-2235-4efc-b254-59c2ff3f3080
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f00d7cbb50b29867771bfb236bbca417324186a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969485"
---
# <a name="single-sign-on-event-11046"></a>De sesión único: Evento 11046
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                        Inicio de sesión único (SSO) empresarial                                                                                        |
| Versión del producto |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    Identificador del evento     |                                                                                                  11046                                                                                                  |
|  Origen del evento   |                                                                                                 ENTSSO                                                                                                  |
|    Componente    |                                                                                                   N/D                                                                                                   |
|  Nombre simbólico  |                                                                                   SSO_WARN_EXISTING_MAPPING_EXTERNAL                                                                                    |
|  Texto del mensaje   | No se pudo crear la asignación porque ya existe una para la cuenta externa especificada.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Nombre de la aplicación: %2 %r<br /><br /> Cuenta externa: %3 |
  
## <a name="explanation"></a>Explicación  
 Ya existe una asignación para la cuenta externa especificada y no se permiten duplicados.  
  
## <a name="user-action"></a>Acción del usuario  
 No es necesario que el usuario realice ninguna acción.