---
title: Construir mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fa87c4f3400a80ce83df132747d0004232323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237820"
---
# <a name="constructing-messages"></a>Construir mensajes
Construya un mensaje en el momento en que escriba un mensaje en la orquestación, mediante la recepción o asignación de valores a una variable de mensaje. Cualquier mensaje que construya debe tener un tipo de mensaje, de modo que el motor de tiempo de ejecución tenga una descripción completa del objeto con el que se está trabajando. El tipo de mensajes de varias partes puede estar definido por el usuario; puede ser una clase .NET o un esquema. Puede construir mensajes de varias formas: puede invocar una clase .NET para crear un mensaje, asignar un mensaje a otro o usar una transformación para asignar determinados valores dentro de un mensaje a valores dentro de otro mensaje. Los mensajes también se construyen mediante una acción de recepción o cuando la orquestación acepta un mensaje como parámetro.  
  
> [!NOTE]
>  Un tipo de mensaje de varias partes no tiene por qué contener varias partes; puede que solo contenga una.  
  
> [!IMPORTANT]
>  Los mensajes son inmutables en BizTalk; es decir, una vez que lo haya construido, no puede modificar el original. Si es necesario realizar un cambio, debe construir una copia nueva del mensaje y asignarle valores de forma adecuada.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo configurar la forma construir mensaje](../core/how-to-configure-the-construct-message-shape.md)  
  
 [Cómo configurar la forma asignación de mensajes](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [Cómo configurar la forma transformación](../core/how-to-configure-the-transform-shape.md) 
  
 [Referencias de mensaje en la forma asignación de mensajes](../core/message-references-in-message-assignment-shape.md)  
  
 [Referencias de mensaje en el código de usuario](../core/message-references-in-user-code.md)  
  
 [Usar XPaths en las asignaciones de mensajes](../core/using-xpaths-in-message-assignments.md)  
  
 [Usar XPaths no canónicos en las asignaciones de mensajes](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [Construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md)  
  
 [Anexar nodos a mensajes en el código de usuario](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a>Vea también  
 [Usar mensajes en orquestaciones](../core/using-messages-in-orchestrations.md)