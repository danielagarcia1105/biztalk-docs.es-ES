---
title: 'De sesión único: Evento 10569 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e051a84-51c1-4e63-be55-6278a1d17c5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25665947921bb316a4d931228016eaf917b4a685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987205"
---
# <a name="single-sign-on-event-10569"></a>De sesión único: Evento 10569
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                       Inicio de sesión único (SSO) empresarial                                                                                        |
| Versión del producto |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    Identificador del evento     |                                                                                                 10569                                                                                                  |
|  Origen del evento   |                                                                                                 ENTSSO                                                                                                 |
|    Componente    |                                                                                                  N/D                                                                                                   |
|  Nombre simbólico  |                                                                                    SSO_WARN_NO_UPDATE_BY_APP_ADMIN                                                                                     |
|  Texto del mensaje   | El administrador de aplicación no puede cambiar la cuenta de administradores de aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Administradores de aplicación: %2 %r<br /><br /> Código de error: %3 |
  
## <a name="explanation"></a>Explicación  
 El administrador de aplicación no puede cambiar la cuenta de administradores de aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para cambiar la cuenta de administradores de aplicación, debe ser un administrador de aplicación afiliado de SSO o superior.