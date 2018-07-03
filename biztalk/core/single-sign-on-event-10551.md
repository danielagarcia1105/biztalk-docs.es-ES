---
title: 'De sesión único: Evento 10551 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a014d9fa9adec99a05eba3f4a0f17047e2e1175
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973493"
---
# <a name="single-sign-on-event-10551"></a>De sesión único: Evento 10551
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                   Inicio de sesión único (SSO) empresarial                                                                                                   |
| Versión del producto |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    Identificador del evento     |                                                                                                             10551                                                                                                             |
|  Origen del evento   |                                                                                                            ENTSSO                                                                                                             |
|    Componente    |                                                                                                              N/D                                                                                                              |
|  Nombre simbólico  |                                                                                                     SSO_WARN_INVALID_USER                                                                                                     |
|  Texto del mensaje   | No se pudo crear la asignación porque el usuario especificado no es válido para la aplicación.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Los usuarios de aplicación: %4 |
  
## <a name="explanation"></a>Explicación  
 El usuario especificado no es válido. Puede tratarse de un error de escritura.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe el nombre de usuario enumerado en la información de la advertencia, confirme que sea correcto y, a continuación, vuelva a crear la asignación.