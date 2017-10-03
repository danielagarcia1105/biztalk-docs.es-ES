---
title: "Uno o más segmentos error | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 340c722bc96ec8efdf2f48e6b40260aa5323e675
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="one-or-more-segments-in-error"></a>Error en uno o más segmentos.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12TsOneOrMoreSegmentsInErrorDescription|  
|Texto del mensaje|Error en uno o más segmentos.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que uno o varios segmentos del intercambio no se ajustan al esquema que los controla.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, determine qué segmento tiene un error, abra el esquema que controla dicho segmento y determine a partir de dicho esquema por qué el segmento tiene un error.