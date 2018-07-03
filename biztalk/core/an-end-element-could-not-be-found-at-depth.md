---
title: No se encontró un elemento de fin con profundidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1edb60a-122a-4fe9-8d73-96521fe7326b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c2727be39d3d2656e118d593b0347038657f61
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970189"
---
# <a name="an-end-element-could-not-be-found-at-depth"></a>No se encontró el elemento de fin con profundidad
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                               EndElementNotFoundAtDepth                                |
|  Texto del mensaje   |                     Elemento de fin con profundidad {0} no se pudo encontrar                     |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo procesar el intercambio saliente debido a que el mensaje XML no se pudo validar. El mensaje XML no contenía una etiqueta de finalización para un encabezado o elemento de datos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, agregue la etiqueta de finalización o finalizador adecuados al mensaje XML y vuelva a enviarlo.