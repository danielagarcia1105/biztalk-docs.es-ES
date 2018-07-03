---
title: Se encontró un elemento de fin al buscar el elemento de inicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e200f4ffd8d822a5c2bb1a0bad74a60e84a408a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992437"
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a>Se encontró un elemento de fin al buscar un elemento de inicio
## <a name="details"></a>Detalles  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  Nombre del producto   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| Versión del producto |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    Identificador del evento     |                                                 -                                                 |
|  Origen del evento   |      EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
|    Componente    |                                            Motor EDI                                             |
|  Nombre simbólico  |                             EndElementFoundWhenLookingForStartElement                             |
|  Texto del mensaje   | Un elemento EndElement con nombre {0} se encontró al buscar el elemento StartElement con nombre {1}, en profundidad {2} |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo procesar el mensaje XML entrante (después de analizar) o un mensaje XML saliente (antes de la serialización) debido a que no se pudo validar el mensaje XML. El mensaje XML no contenía una etiqueta de finalización para un encabezado o elemento de datos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, agregue la etiqueta de finalización o finalizador adecuados al mensaje XML y vuelva a enviar el mensaje.