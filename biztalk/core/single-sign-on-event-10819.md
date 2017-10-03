---
title: "Inicio de sesión único: Evento 10819 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffa5e977-c8b9-4568-8963-0d4cf44b5637
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f2a98586d9c139674c64db6ca03aaa6abd6ba6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10819"></a>Inicio de sesión único: Evento 10819
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10819|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_MAPPING_CONFLICT|  
|Texto del mensaje|La cuenta externa no se actualizó debido a un conflicto de asignación.|  
  
## <a name="explanation"></a>Explicación  
 La cuenta externa no se actualizó debido a un conflicto de asignación.  
  
## <a name="user-action"></a>Acción del usuario  
 Si éste es el comportamiento esperado, no es necesario realizar ninguna acción. El mensaje es solamente informativo. Si se deben permitir conflictos de asignación, configure la aplicación adecuadamente.  
  
 Para obtener más información sobre los conflictos de asignación, consulte **propiedades de adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].