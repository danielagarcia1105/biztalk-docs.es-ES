---
title: Secuencia de número de control agotada de intercambio para el socio y TPA | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e77c0574-bc51-4690-a7f6-5702f6486f05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4744a8db00985db3e85c1cb8843f07b3488544b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257044"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a>Secuencia de número de control de intercambio agotada para el socio y TPA
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EdiControlNumberExhaustedForParty|  
|Texto del mensaje|Secuencia de número de control de intercambio agotado para el socio '{1}' del TPA '{2}'. Restablezca la secuencia en {2} - propiedades de EDI mediante administración de BizTalk Server.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de Error, advertencia o información indica que el servidor BizTalk Server no pudo procesar el documento porque se ha agotado el intervalo de control de intercambio para el acuerdo en {2}.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, active la casilla de verificación para restablecer el número de control para el acuerdo de {2} o aumentar el intervalo de números de control o pulse el botón Restablecer contra la especificación de intervalo de número de control en el acuerdo.