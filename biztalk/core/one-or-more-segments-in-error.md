---
title: Error en uno o más segmentos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c364af2691767ac55a52afb52b77f09d39ef6d2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005076"
---
# <a name="one-or-more-segments-in-error"></a>Error en uno o más segmentos.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                        X12TsOneOrMoreSegmentsInErrorDescription                        |
|  Texto del mensaje   |                             Error en uno o más segmentos.                              |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que uno o varios segmentos del intercambio no se ajustan al esquema que los controla.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, determine qué segmento tiene un error, abra el esquema que controla dicho segmento y determine a partir de dicho esquema por qué el segmento tiene un error.