---
title: El esquema del conjunto de transacciones contiene uno o más de control de los segmentos ISA, IEA, GS, GE | Microsoft Docs
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
ms.openlocfilehash: 4f0ab50802cbb872d7ba884a8256824426fbe098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008207"
---
# <a name="transaction-set-schema-contains-one-or-more-of-control-segments-isa-iea-gs-ge"></a>El esquema de conjunto de transacciones contiene uno o más segmentos de control ISA, IEA, GS, GE.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                       SchemaCode114EOtherControlSegmentsPresent                        |
|  Texto del mensaje   |    El esquema de conjunto de transacciones contiene uno o más segmentos de control ISA, IEA, GS, GE.    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia, información indica que la canalización de recepción no pudo procesar el conjunto de transacciones entrantes o que la canalización de envío no pudo procesar el conjunto de transacciones salientes porque el esquema del documento para el conjunto de transacciones definió al menos un segmento ISA, IEA, GS o GE.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, anule la implementación del esquema del documento, quite el segmento ISA, IEA, GS o GE del esquema y vuelva a implementar el esquema.