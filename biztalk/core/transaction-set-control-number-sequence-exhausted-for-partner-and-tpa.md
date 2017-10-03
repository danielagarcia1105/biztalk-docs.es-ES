---
title: "Conjunto control número secuencia de transacciones agotada para el socio y TPA | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d87b1f2681bb07816721971cfbd17d2c3a0b91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a>Secuencia de número de control del conjunto de transacciones agotada para el socio y TPA
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EdiControlNumberExhaustedForParty|  
|Texto del mensaje|Secuencia conjunto de transacciones control número agotada para el socio '{1}' del TPA '{2}'. Restablezca la secuencia en {2} - propiedades de EDI mediante administración de BizTalk Server.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de Error, advertencia o información indica que BizTalk Server no se pueda procesar que el documento porque el intervalo de control del conjunto de transacciones se ha agotado para el acuerdo en {2}.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, active la casilla de verificación para restablecer el número de control para el acuerdo de {2} o aumentar el intervalo de números de control o pulse el botón Restablecer contra la especificación de intervalo de número de control en el acuerdo.