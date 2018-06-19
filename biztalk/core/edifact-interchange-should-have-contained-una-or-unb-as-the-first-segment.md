---
title: El intercambio EDIFACT debía contener UNA o UNB como primer segmento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673df728dea00852e9713aed12f8ced902a4fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240036"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a>El intercambio Edifact debía contener UNA o UNB como primer segmento
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|El intercambio Edifact debía contener UNA o UNB como primer segmento. En su lugar, se encontró {0}.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de Error, advertencia o información indica que la recepción EDI canalización no pudo procesar el intercambio EDIFACT entrante porque el primer segmento no era ni UNA ni un segmento UNB. El segmento UNA es opcional; el segmento UNB, obligatorio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el remitente del intercambio incluye un segmento UNA o UNB como primer segmento del intercambio y vuelva a enviar el intercambio.