---
title: El segmento contiene errores de elementos de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469622e2-6500-4f55-ab53-f8d89ee0a978
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30b000f670e4329c68540b51f291097f5bbd4dc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998893"
---
# <a name="segment-has-data-element-errors"></a>El segmento contiene errores de elementos de datos
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                       X12SegmentHasDataElementErrorsDescription                        |
|  Texto del mensaje   |                            El segmento contiene errores de elementos de datos.                             |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio contenía segmentos que incluían elementos de datos que no se ajustaban al esquema del documento.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los elementos de datos del intercambio se ajustan al esquema del documento y vuelva a enviar el intercambio.