---
title: Error al analizar. El X12 intercambio contenía los errores siguientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c1085d4-75ef-4f63-84c9-287a4a61274a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94b9907667a7f99c1ecf8c2dc326fe32e134abf3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240132"
---
# <a name="error-encountered-during-parsing-the-x12-interchange-had-the-following-errors"></a>Error al analizar. El intercambio X12 contenía los errores siguientes
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12InterchangeReceiveError|  
|Texto del mensaje|Error al analizar. El X12 intercambio con Id. '{0}' con el remitente Id. '{1}', Id. de destinatario '{2}' contenía los errores siguientes:|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI encontró un error al analizar un intercambio X12 entrante debido a los errores indicados en el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.