---
title: El intercambio contenía un error estructural. La parte situada después del error se ha suspendido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a028608e9843ee40c26bc7e8b158d97552a58163
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241300"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a>El intercambio contenía un error estructural. La parte situada después del error se ha suspendido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EfactInterchangeStructuralError|  
|Texto del mensaje|El intercambio con el identificador '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural. La parte situada después del error se está suspendiendo. Consulte Cola de suspensión para obtener información detallada.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque ha tenido lugar un error estructural en el intercambio. Esto se ha producido con un intercambio que se estaba conservando, con conjuntos de transacciones suspendidos debido al error. Como resultado de este error, el o los conjuntos de transacciones que incluían el error se han suspendido, pero el resto de los conjuntos de transacciones se han procesado como parte del lote conservado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del intercambio que corrija el error estructural y vuelva a enviar el intercambio.