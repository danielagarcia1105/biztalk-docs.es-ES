---
title: El segmento excede la descripción de uso máximo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1704a-5d49-4549-af50-d1a89a1e70f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62a52f7589dc42d3af6b07db6fcbeb926a3d5dbc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985325"
---
# <a name="segment-exceeds-maximum-use-description"></a>El segmento excede la descripción de uso máximo.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                         X12SegmentExceedsMaximumUseDescription                         |
|  Texto del mensaje   |                        El segmento excede la descripción de uso máximo.                         |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía más instancias de un segmento de lo que permitía el esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el intercambio no contiene más del número máximo permitido de segmentos y vuelva a enviar el intercambio.