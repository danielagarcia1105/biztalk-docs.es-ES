---
title: Error durante la serialización. El X12 grupo funcional contenía los errores siguientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c6b74d713f0d182a07cc6a509cd7d06fc34b82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290060"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a>Error durante la serialización. El grupo funcional X12 contenía los errores siguientes
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12FunctionalGroupSendError|  
|Texto del mensaje|Error durante la serialización. El X12 funcional de grupo receptor con el identificador '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. '{3}' contenía los errores siguientes:|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio X12 saliente debido a los errores indicados con el grupo funcional identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el grupo funcional y, a continuación, determine la resolución del problema en la ayuda del producto.