---
title: 'De sesión único: Evento 10848 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a324ff0a5de2ac6d2292692f2132c10aaabc5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991037"
---
# <a name="single-sign-on-event-10848"></a>De sesión único: Evento 10848
## <a name="details"></a>Detalles  
  
|                 |                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                 Inicio de sesión único (SSO) empresarial                                  |
| Versión del producto |                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    Identificador del evento     |                                           10848                                            |
|  Origen del evento   |                                           ENTSSO                                           |
|    Componente    |                                            N/D                                             |
|  Nombre simbólico  |                         ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS                         |
|  Texto del mensaje   | No se permite la sincronización directa de contraseñas de la aplicación porque sus campos son ambiguos. |
  
## <a name="explanation"></a>Explicación  
 Si existen dos campos, sólo uno de ellos debe marcarse para sincronización de contraseñas.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este problema, debe eliminar la aplicación y crearla nuevamente para que respete estas pautas.