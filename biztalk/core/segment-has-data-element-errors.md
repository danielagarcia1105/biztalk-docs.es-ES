---
title: Segmento contiene errores de elementos de datos | Documentos de Microsoft
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
ms.openlocfilehash: 27c8c9e43bfe0a733a3e95b7812195a0b7f3990c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269428"
---
# <a name="segment-has-data-element-errors"></a>El segmento contiene errores de elementos de datos
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12SegmentHasDataElementErrorsDescription|  
|Texto del mensaje|El segmento contiene errores de elementos de datos.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio contenía segmentos que incluían elementos de datos que no se ajustaban al esquema del documento.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los elementos de datos del intercambio se ajustan al esquema del documento y vuelva a enviar el intercambio.