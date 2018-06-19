---
title: 'Inicio de sesión único: Evento 11020 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa6a0d72-ece6-4094-9263-dbf69bb068c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 444a61beec74a9d7141df79d05d8863cc10d6dc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277380"
---
# <a name="single-sign-on-event-11020"></a>Inicio de sesión único: Evento 11020
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11020|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED|  
|Texto del mensaje|El cambio de contraseña de Windows provocará el cambio de una cuenta de Windows diferente.%r<br /><br /> Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 %r<br /><br /> Cuenta de Windows 1: %4 %r<br /><br /> Cuenta de Windows 2: %5|  
  
## <a name="explanation"></a>Explicación  
 Este mensaje de información indica que el cambio de contraseña de Windows provocará el cambio de una cuenta de Windows diferente.  
  
## <a name="user-action"></a>Acción del usuario  
 Debe confirmar de inmediato que este cambio se efectuó con su conocimiento y autorización. Si es así, no se necesitan acciones. De lo contrario, averigüe dónde se inició el cambio y confirme que se trata de una ubicación segura del sistema.