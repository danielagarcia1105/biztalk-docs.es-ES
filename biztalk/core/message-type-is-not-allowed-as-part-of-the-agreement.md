---
title: No se permite el tipo de mensaje como parte del acuerdo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979aa43d23d2fca95c244e10cb9d4768d76cf3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262740"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a>No se permite el tipo de mensaje como parte del acuerdo
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|TransactionSetNotAllowedDescription|  
|Texto del mensaje|Tipo de mensaje {0} no se permite como parte del acuerdo.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo procesar el documento porque el tipo de mensaje del documento no se permite como parte del acuerdo.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, mire los tipos de mensaje permitidos y no permitidos como parte del acuerdo.