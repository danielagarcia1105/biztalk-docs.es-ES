---
title: "El procesamiento en la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, process management solutions
ms.assetid: 0b26447e-d8f1-4084-aa34-6e7f8ffccea5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 145dd8e616048f1caaa1a59ec41d099e93e47880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-business-process-management-solution"></a>Procesamiento en la solución de administración de procesos empresariales
Esta sección describe el funcionamiento de la solución de administración de procesos empresariales: cómo procesa los pedidos, se puede recuperar cómo hace uso de interrupciones y cómo controla las excepciones para que las acciones.  
  
 Procesamiento de pedidos se basa en dos orquestaciones principales, **OrderBroker** y **OrderManager**. El **OrderBroker** orquestación está escrita de modo que puede haber varias orquestaciones de administrador de pedidos, uno para cada tipo de orden. La solución incluye sólo un **OrderManager**. También es relativamente genérico para poder adaptarse a otros tipos de pedidos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [Lógica del Administrador de procesos](../core/process-manager-logic.md)  
  
-   [En las fases de procesamiento de orden de procesamiento](../core/processing-in-the-order-processing-stages.md)  
  
-   [Control de interrupciones en la solución de administración de procesos empresariales](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [Control de excepciones en la solución de administración de procesos empresariales](../core/exception-handling-in-the-business-process-management-solution.md)