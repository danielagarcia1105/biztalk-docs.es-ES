---
title: Uso de elementos de múltiples pedidos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, multiple calls
- JD Edwards OneWorld adapters, multi-order numbers
- multiple edit line calls [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multi-order numbers
- multi-order numbers [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multiple calls
ms.assetid: 207ea92c-03f7-4117-8414-eb174e659d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389e73ede2d1062c9907bd8640f38ce74ad6f316
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287260"
---
# <a name="using-multi-order-items"></a>Uso de elementos de múltiples pedidos
Debido a la estructura de la API de JD Edwards OneWorld, si desea usar números de varios pedidos con BizTalk Server, debe realizar varias llamadas a la línea de edición en su orquestación para agregar estos elementos de línea en una orquestación. Por ejemplo, un elemento de varios pedidos podría contener un encabezado con un único número de pedido, y detalles que incluyan varios pedidos de artículos (como Juguete 1EA, Guantes 2EA).  
  
 Para usar varias llamadas de línea de edición, es responsabilidad del programador de BizTalk Server su estructuración. El programador debe crear un bucle interno en la orquestación para realizar dichas llamadas.  
  
 El sistema JD Edwards OneWorld admite varias llamadas de línea de edición, pero no así la API. Si observa la estructura del método Editar línea, se trata de una estructura plana y no de una secuencia. Por lo tanto, debe llamar a la función cada vez que desee insertar un artículo de línea.  
  
## <a name="see-also"></a>Vea también  
 [Planeamiento y arquitectura](../core/planning-and-architecture17.md)