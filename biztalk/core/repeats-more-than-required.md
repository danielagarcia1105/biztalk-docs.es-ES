---
title: Se repite más de necesario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cb8f9e324c9d09e09649719c98e3f684b0d81f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268228"
---
# <a name="repeats-more-than-required"></a>Más repeticiones de las necesarias.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12FeRepeatsMoreThanRequiredDescription|  
|Texto del mensaje|Más repeticiones de las necesarias.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que los segmentos de un intercambio X12 entrante que se encuentran dentro o fuera de un bucle se repiten más veces que las que requiere el esquema del documento.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los segmentos que se encuentran dentro o fuera de un bucle del intercambio se repiten el número de veces especificado en el esquema y reenvíe el intercambio.