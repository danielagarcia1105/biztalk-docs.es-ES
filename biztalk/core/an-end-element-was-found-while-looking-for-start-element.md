---
title: "Se encontró un elemento de fin al buscar el elemento de inicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dacaa096b15a6f2969ed56b5bac2138876a6095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a>Se encontró un elemento de fin al buscar un elemento de inicio
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EndElementFoundWhenLookingForStartElement|  
|Texto del mensaje|Se encontró un elemento EndElement con nombre {0}, al buscar el elemento StartElement con {1} del nombre, en profundidad {{2}|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo procesar el mensaje XML entrante (después de analizar) o un mensaje XML saliente (antes de la serialización) debido a que no se pudo validar el mensaje XML. El mensaje XML no contenía una etiqueta de finalización para un encabezado o elemento de datos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, agregue la etiqueta de finalización o finalizador adecuados al mensaje XML y vuelva a enviar el mensaje.