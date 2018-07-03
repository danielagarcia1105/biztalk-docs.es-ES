---
title: 'De sesión único: Evento 10806 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be61b0a48dde7b1c8de9ec716f4f9426c39fa0cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002701"
---
# <a name="single-sign-on-event-10806"></a>De sesión único: Evento 10806
## <a name="details"></a>Detalles  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  Nombre del producto   |                             Inicio de sesión único (SSO) empresarial                             |
| Versión del producto |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    Identificador del evento     |                                       10806                                       |
|  Origen del evento   |                                      ENTSSO                                       |
|    Componente    |                                        N/D                                        |
|  Nombre simbólico  |                         ENTSSO_E_APP_ASSIGNED_TO_ADAPTER                          |
|  Texto del mensaje   | No se puede eliminar la aplicación porque actualmente está asignada a un adaptador. |
  
## <a name="explanation"></a>Explicación  
 No se puede eliminar una aplicación si está asignada a un adaptador.  
  
## <a name="user-action"></a>Acción del usuario  
 Quite la asignación de la aplicación del adaptador y, a continuación, elimínela.