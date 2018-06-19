---
title: 'Inicio de sesión único: Evento 11021 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70b987aa-8097-4243-a25b-f1cc12c5bc6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e246ac3d0bbab4e991b17c091567b4b59131b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278076"
---
# <a name="single-sign-on-event-11021"></a>Inicio de sesión único: Evento 11021
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11021|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED|  
|Texto del mensaje|El cambio de contraseña externa provocará el cambio de una cuenta externa diferente.%r<br /><br /> Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 %r<br /><br /> Cuenta externa 1: %4 %r<br /><br /> Cuenta externa 2: %5|  
  
## <a name="explanation"></a>Explicación  
 Este mensaje de información indica que el cambio de contraseña externa provocará el cambio de una cuenta externa diferente.  
  
## <a name="user-action"></a>Acción del usuario  
 Debe confirmar de inmediato que este cambio se efectuó con su conocimiento y autorización. Si es así, no se necesitan acciones. De lo contrario, averigüe dónde se inició el cambio y confirme que se trata de una ubicación segura del sistema.