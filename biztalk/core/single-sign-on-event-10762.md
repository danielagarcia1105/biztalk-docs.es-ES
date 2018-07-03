---
title: 'De sesión único: Evento 10762 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 905c59062f8f4af397872f3f7d4434a67b19842e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996013"
---
# <a name="single-sign-on-event-10762"></a>De sesión único: Evento 10762
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                   Inicio de sesión único (SSO) empresarial                                                    |
| Versión del producto |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    Identificador del evento     |                                                             10762                                                              |
|  Origen del evento   |                                                             ENTSSO                                                             |
|    Componente    |                                                              N/D                                                               |
|  Nombre simbólico  |                                                     ENTSSO_E_WRONG_THREAD                                                      |
|  Texto del mensaje   | Se llamó al componente de cliente de SSO en el subproceso incorrecto. Actualmente, se encuentra bloqueado en un subproceso porque tiene una transacción. |
  
## <a name="explanation"></a>Explicación  
 Los componentes sólo pueden ser multiproceso cuando no tienen una transacción. Este componente tiene una transacción y, por lo tanto, está bloqueado en un subproceso.  
  
## <a name="user-action"></a>Acción del usuario  
 Configure la aplicación para que no llame a componentes de cliente de SSO en varios subprocesos cuando usa transacciones.