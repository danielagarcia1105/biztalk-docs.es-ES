---
title: 'Inicio de sesión único: Evento 10551 | Documentos de Microsoft'
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
ms.openlocfilehash: 30c4b315744749d232c30f4cc28c4d297a0f5243
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270748"
---
# <a name="single-sign-on-event-10551"></a>Inicio de sesión único: Evento 10551
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10551|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_INVALID_USER|  
|Texto del mensaje|No se pudo crear la asignación porque el usuario especificado no es válido para la aplicación.%r<br /><br /> Nombre de dominio: %1 %r<br /><br /> Nombre de usuario: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Los usuarios de aplicación: %4|  
  
## <a name="explanation"></a>Explicación  
 El usuario especificado no es válido. Puede tratarse de un error de escritura.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe el nombre de usuario enumerado en la información de la advertencia, confirme que sea correcto y, a continuación, vuelva a crear la asignación.