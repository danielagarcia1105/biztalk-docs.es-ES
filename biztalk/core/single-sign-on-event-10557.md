---
title: 'Inicio de sesión único: Evento 10557 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc65dba8760c85ad9eb6552e56e52cc6b7dd3ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269772"
---
# <a name="single-sign-on-event-10557"></a>Inicio de sesión único: Evento 10557
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10557|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS|  
|Texto del mensaje|No se permite que los usuarios de aplicación controlen asignaciones para aplicaciones de grupo.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Usuario cliente: %4|  
  
## <a name="explanation"></a>Explicación  
 Un usuario de aplicación no tiene privilegios suficientes para crear o controlar asignaciones para aplicaciones de grupo.  
  
## <a name="user-action"></a>Acción del usuario  
 Esta actividad debe realizarla el administrador de aplicaciones.