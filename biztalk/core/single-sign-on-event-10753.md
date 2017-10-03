---
title: "Inicio de sesión único: Evento 10753 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc43f8ffba195b7a0156a9004d140f1e3c585db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10753"></a>Inicio de sesión único: Evento 10753
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10753|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|ENTSSO_E_MAPPING_EXISTS|  
|Texto del mensaje|La asignación ya existe.|  
  
## <a name="explanation"></a>Explicación  
 La asignación ya existe en la cuenta de Windows que se encuentra en uso o en la cuenta externa.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe las asignaciones existentes y la asignación que intenta crear. Si la asignación que desea ya existe, use ésta y elimine la nueva. De lo contrario, elimine la asignación nueva y vuelva a crearla.