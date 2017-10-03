---
title: "La confirmación Edifact fue generada por el sistema. Sin embargo, le falta una propiedad de contexto para el conjunto de delimitadores. No se puede serializar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d7b1e62-3230-4cdc-830f-3267de1efd1c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d21ce485c2cd5c55bb941afdfc15d2ad545db61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-edifact-acknowledgement-was-generated-by-the-system-however-it-is-missing-a-context-property-for-delimiter-set-it-cannot-be-serialized"></a>La confirmación Edifact fue generada por el sistema. Sin embargo, le falta una propiedad de contexto para el conjunto de delimitadores. No se puede serializar.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|La confirmación Edifact fue generada por el sistema. Sin embargo, le falta una propiedad de contexto para el conjunto de delimitadores. No se puede serializar.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que BizTalk Server no puede serializar la confirmación EDIFACT y falta una propiedad de contexto para el conjunto de delimitadores del mensaje de BizTalk.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de escribir la propiedad de contexto Conjunto de delimitadores en el contexto del mensaje de BizTalk para confirmaciones EDIFACT.