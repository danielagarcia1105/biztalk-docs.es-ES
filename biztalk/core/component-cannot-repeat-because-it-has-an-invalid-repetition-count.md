---
title: No se puede repetir el componente porque tiene un recuento de repetición no válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d535d72b5f265f07e6ae3fb468ed56efdc7975b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231684"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a>El componente no puede repetirse. Recuento de repetición no válido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|SchemaCode118EInvalidRepetition|  
|Texto del mensaje|El componente no puede repetirse. Recuento de repetición no válido de {0}.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un componente de elemento, elemento, segmento o bucle estaba repetido en el intercambio y el esquema no permite la repetición.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este error, asegúrese de que el componente de elemento, el elemento, el segmento o el bucle no se repita en el intercambio, según requiere el esquema, y vuelva a enviar el mensaje.