---
title: Segmento se repite menor que el mínimo permitido de veces | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8ca6c3d-f923-49bc-b5d9-65dc2d7adab1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee7aeb488fb2f8634fba73e7ddf3f44cd02a6529
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269940"
---
# <a name="segment-repeats-less-than-the-minimum-allowed-number-of-times"></a>El segmento se repite un número de veces inferior al mínimo permitido.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12SeSegmentRepeatsLessTimesDescription|  
|Texto del mensaje|El segmento se repite un número de veces inferior al mínimo permitido.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante, pues un segmento del intercambio no se repite el número mínimo de veces que requiere el esquema del documento.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del intercambio que repita el segmento de modo que se repita al menos el número mínimo de veces que requiere el esquema del documento y vuelva a enviar el intercambio.