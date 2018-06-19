---
title: 'Inicio de sesión único: Evento 10556 | Documentos de Microsoft'
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
ms.openlocfilehash: a8806898c853dd27bc3025e1ff16caf3c10dec86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271420"
---
# <a name="single-sign-on-event-10556"></a>Inicio de sesión único: Evento 10556
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10556|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_INVALID_GROUP_USER|  
|Texto del mensaje|Asignación no válida especificada para una aplicación de grupo. La asignación debe especificar una cuenta de usuarios de aplicación para esta aplicación.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Los usuarios de aplicación: %4|  
  
## <a name="explanation"></a>Explicación  
 La asignación no es válida.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si la asignación especifica una de las cuentas de usuario de aplicación para la aplicación.