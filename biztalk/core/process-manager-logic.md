---
title: "Administrador de procesos lógica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e562362fec8e13589f1860e74024ffe70dad1c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="process-manager-logic"></a>Lógica del Administrador de procesos
Esta sección se describe cómo el Administrador de procesos, el **OrderManager** orquestación, procesa pedidos. Describe campos fundamentales en los distintos mensajes de pedido y realiza un seguimiento de los pedidos nuevos y actualizados a través de la orquestación.  
  
 El **OrderManager** orquestación coordina orquestaciones subordinadas para procesar el pedido. Puede agregar, eliminar o modificar estas fases sin tener que cambiar la **OrderManager**. El **OrderManager** realiza gran parte de la coordinación mediante mensajes personalizados definidos por las clases. NET. Para obtener una lista de todos los mensajes en la solución, vea [referencia de mensaje para la solución de administración de procesos empresariales](../core/message-reference-for-the-business-process-management-solution.md). Para obtener información acerca de cómo definir tipos de mensajes con las clases. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
> [!NOTE]
>  Debido al tamaño y ámbito de **OrderManager**, puede que desee leer estas secciones, especialmente la segunda, con la orquestación abierta en Microsoft Visual Studio.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Campos y los mensajes de teclado](../core/key-messages-and-fields.md)  
  
-   [Flujo de pedidos a través del Administrador de proceso](../core/order-flow-through-the-process-manager.md)