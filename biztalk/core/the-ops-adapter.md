---
title: El adaptador Ops | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67463adf4e1e960ab6608e67595a679804aa223e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-ops-adapter"></a>El adaptador Ops
El diseño de la solución tiene como finalidad pasar, siempre que sea posible, mensajes problemáticos y errores a sistemas de operaciones que tomen una decisión respecto a si corregir el error o finalizar el pedido. El adaptador Ops, combinado con la característica de elaboración de informes de errores nueva, controla muchos de estos casos.  
  
 La solución utiliza el adaptador en un puerto configurado para utilizar la característica de elaboración de informes de errores nueva. Cuando recibe un error, el adaptador llama a dos métodos, **inicializar** y **Execute**, en una clase en un ensamblado especificado. En la solución, estos métodos envían el error al grupo de operaciones correcto.  
  
 La solución incluye un controlador de ejemplos, aunque puede escribir fácilmente uno propio y usar el adaptador en otras soluciones. Para obtener información general sobre la nueva característica informes de errores, vea [enrutamiento de mensajes de error utilizando](../core/using-failed-message-routing.md).  
  
> [!NOTE]
>  El adaptador Ops se genera con el Marco de trabajo de adaptadores. Para obtener información sobre la creación de adaptadores con el marco de trabajo, consulte [desarrollar adaptadores Custom](../core/developing-custom-adapters.md).  
  
 En esta sección se explica cómo funciona el adaptador y cómo se configura. Asimismo, se suministran los detalles acerca de los ensamblados controladores de errores. La sección concluye con los datos de implementación que podrían resultar útiles a los usuarios que deseen modificar el adaptador o utilizarlo en otras aplicaciones.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Usar el adaptador Ops](../core/using-the-ops-adapter.md)  
  
-   [El controlador de errores de las operaciones de ejemplo](../core/the-sample-operations-error-handler.md)  
  
-   [Detalles de implementación del adaptador OPS](../core/ops-adapter-implementation-details.md)