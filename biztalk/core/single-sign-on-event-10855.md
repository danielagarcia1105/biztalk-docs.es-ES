---
title: 'De sesión único: Evento 10855 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba244f8e-bc61-475f-913c-475ebf1c69ee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d5914cc119a68c109b883c888b3898bc7db07e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986453"
---
# <a name="single-sign-on-event-10855"></a>De sesión único: Evento 10855

|                 |                                                                        |
|-----------------|------------------------------------------------------------------------|
|  Nombre del producto   |                       Inicio de sesión único (SSO) empresarial                        |
| Versión del producto |       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    Identificador del evento     |                                 10855                                  |
|  Origen del evento   |                                 ENTSSO                                 |
|    Componente    |                                  N/D                                   |
|  Nombre simbólico  |                    ENTSSO_E_PASSWORD_FILTER_FAILED                     |
|  Texto del mensaje   | No se pueden devolver las credenciales debido a un error de filtro de contraseña. |

## <a name="explanation"></a>Explicación  
 El filtro de contraseña no es válido. La causa más probable de ello es que el filtro se creó manualmente (no recomendado).  

## <a name="user-action"></a>Acción del usuario  
 Vuelva a crear el filtro de contraseña a través del Asistente para crear filtros.