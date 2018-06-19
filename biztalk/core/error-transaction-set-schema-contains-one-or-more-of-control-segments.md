---
title: Esquema del conjunto de transacciones contiene uno o varios de control segmentos ISA, IEA, GS, GE | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7589d8f0-c727-47df-afbc-77b0f190f3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff90a7ea80208f0a69ee8aca5c7593c7b6253c53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241828"
---
# <a name="transaction-set-schema-contains-one-or-more-of-control-segments-isa-iea-gs-ge"></a>El esquema de conjunto de transacciones contiene uno o más segmentos de control ISA, IEA, GS, GE.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|SchemaCode114EOtherControlSegmentsPresent|  
|Texto del mensaje|El esquema de conjunto de transacciones contiene uno o más segmentos de control ISA, IEA, GS, GE.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia, información indica que la canalización de recepción no pudo procesar el conjunto de transacciones entrantes o que la canalización de envío no pudo procesar el conjunto de transacciones salientes porque el esquema del documento para el conjunto de transacciones definió al menos un segmento ISA, IEA, GS o GE.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, anule la implementación del esquema del documento, quite el segmento ISA, IEA, GS o GE del esquema y vuelva a implementar el esquema.