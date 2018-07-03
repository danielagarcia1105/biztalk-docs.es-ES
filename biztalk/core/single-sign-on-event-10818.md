---
title: 'De sesión único: Evento 10818 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 328e4286ed024923ab66e147e806ef5db5065b77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972437"
---
# <a name="single-sign-on-event-10818"></a>De sesión único: Evento 10818
## <a name="details"></a>Detalles  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  Nombre del producto   |                            Inicio de sesión único (SSO) empresarial                            |
| Versión del producto |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    Identificador del evento     |                                      10818                                      |
|  Origen del evento   |                                     ENTSSO                                      |
|    Componente    |                                       N/D                                       |
|  Nombre simbólico  |                         ENTSSO_E_AMBIGUOUS_SYNC_FIELDS                          |
|  Texto del mensaje   | La aplicación debe tener dos campo o se debe marcar un solo campo para sincronización. |
  
## <a name="explanation"></a>Explicación  
 Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.