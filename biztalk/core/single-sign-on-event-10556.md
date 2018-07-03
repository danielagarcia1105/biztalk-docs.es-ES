---
title: 'De sesión único: Evento 10556 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66661a77-e8b0-4972-a3bc-4bb717967699
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79300dc2ff97fe3f410d0e8b06cdfbebd4782a48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011765"
---
# <a name="single-sign-on-event-10556"></a>De sesión único: Evento 10556
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                             Inicio de sesión único (SSO) empresarial                                                                                                                             |
| Versión del producto |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                             |
|    Identificador del evento     |                                                                                                                                       10556                                                                                                                                       |
|  Origen del evento   |                                                                                                                                      ENTSSO                                                                                                                                       |
|    Componente    |                                                                                                                                        N/D                                                                                                                                        |
|  Nombre simbólico  |                                                                                                                            SSO_WARN_INVALID_GROUP_USER                                                                                                                            |
|  Texto del mensaje   | Asignación no válida especificada para una aplicación de grupo. La asignación debe especificar una cuenta de usuarios de aplicación para esta aplicación.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Los usuarios de aplicación: %4 |
  
## <a name="explanation"></a>Explicación  
 La asignación no es válida.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si la asignación especifica una de las cuentas de usuario de aplicación para la aplicación.