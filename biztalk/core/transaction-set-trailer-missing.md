---
title: Falta el finalizador del conjunto de transacciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07753300-fe47-47a6-a947-6abec10c1c90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f1c153aa0bb62b6c62f4eeebf9d1fb9bea004b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279292"
---
# <a name="transaction-set-trailer-missing"></a>Falta el finalizador del conjunto de transacciones.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12TsTrailerMissingDescription|  
|Texto del mensaje|Falta el finalizador del conjunto de transacciones.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el conjunto de transacciones entrantes o que la canalización de envío no pudo procesar el conjunto de transacciones salientes porque el conjunto de transacciones no incluyó el finalizador del conjunto de transacciones SE (para conjuntos de transacciones X12) o el finalizador de mensaje UNT (para conjuntos de transacciones EDIFACT).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del conjunto de transacciones que agregue a este un finalizador del conjunto de transacciones SE (para conjuntos de transacciones X12) o el finalizador de mensaje UNT (para conjuntos de transacciones EDIFACT) y, a continuación, vuelva a enviar el conjunto de transacciones.