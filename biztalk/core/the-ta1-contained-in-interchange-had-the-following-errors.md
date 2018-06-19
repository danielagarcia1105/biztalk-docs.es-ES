---
title: El TA1 contenido en el intercambio contenía los errores siguientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bd7486d25e2c94fc809e6dc50c43359c152b70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278636"
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a>El TA1 contenido en el intercambio presentaba los errores siguientes
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12TA1Error|  
|Texto del mensaje|El {0} TA1 contenido en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes:|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar la confirmación TA1 entrante debido a la condición de error indicada. Esto puede indicar que la confirmación no se ajusta a TA1Schema.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente de la confirmación que resuelva el problema que presenta la confirmación, que se asegure de que ésta se ajusta a TA1Schema y que vuelva a enviar la confirmación.