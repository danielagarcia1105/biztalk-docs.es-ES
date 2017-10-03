---
title: Uso de transacciones y controlar las excepciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions, orchestrations
- orchestrations, transactions
- orchestrations, errors
- transactions
- errors, orchestrations
- transactions, BizTalk Server Orchestration Engine
- errors, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], errors
- Scope shape [Orchestration Designer], transactions
ms.assetid: bb38f5eb-6641-4e7c-8e2a-c474fc739999
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab32729aa6b4f12aada623587f52728c6bd23240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-transactions-and-handling-exceptions"></a>Uso de transacciones y control de excepciones
Cuando designe una orquestación, debe considerar detenidamente dónde pueden producirse problemas y cuál es la mejor forma de procesarlos. Numerosas orquestaciones tienen varios puntos posibles de error. Los problemas pueden surgir por cualquier motivo; por ejemplo, puede que se desconecte el servidor o que el mensaje se formatee de forma incorrecta.  
  
 Es muy importante para una orquestación compleja o de larga ejecución realizar el seguimiento de su estado e informar de los errores en el momento en que se produzcan, para que los problemas se puedan solucionar con mayor precisión y un esfuerzo mínimo. Es de igual importancia para una orquestación mantener la integridad de un conjunto de acciones muy relacionadas, de modo que si parte de la transacción tiene lugar pero otra no, toda la transacción se puede deshacer como si nunca hubiese sucedido.  
  
 La orquestación de BizTalk permite garantizar la atomicidad del trabajo, es decir, la integridad de acciones relacionadas, incluso cuando los sistemas externos participan en transacciones. Proporcionan herramientas para controlar los errores, mantener el estado de una orquestación y solucionar problemas cuando se producen a través de transacciones, compensación y control de excepciones.  
  
 Un marco de trabajo para las transacciones y control de excepciones, el Diseñador de orquestaciones proporciona la **ámbito** forma. Un ámbito puede tener un tipo de transacción, una compensación y cualquier número de controladores de excepción.  
  
 Los pasos para configurar una transacción y el control de excepciones son:  
  
-   Crear un ámbito.  
  
-   Identificar el tipo de transacción necesario.  
  
-   Determinar lo que será necesario compensar.  
  
-   Identificar posibles errores.  
  
-   Agregar controladores de excepción y el código de compensación adecuados.  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a>Ejemplos de uso de transacciones, controladores de excepciones y compensaciones  
  
-   [Error de control (carpeta de ejemplos de BizTalk Server)](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [Compensación (ejemplo de BizTalk Server)](../core/compensation-biztalk-server-sample.md)  
  
-   Descargue el ejemplo SDK "Atomic Transactions con COM + realizando tareas de mantenimiento componentes in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
-   Descargue el ejemplo SDK "Utilizando el SQL adaptador con Atomic Transactions in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
-   Descargue el ejemplo SDK "Using Long-Running Transactions in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
-   Descargue el ejemplo SDK "Exception Handling in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Ámbitos](../core/scopes.md)  
  
-   [Cómo configurar la forma ámbito](../core/how-to-configure-the-scope-shape.md)  
  
-   [Realizar orquestaciones transaccionales](../core/making-orchestrations-transactional.md)  
  
-   [Excepciones](../core/exceptions.md)  
  
-   [Compensación](../core/compensation.md)  
  
## <a name="see-also"></a>Vea también  
 [Usar el motor de mensajería de BizTalk](../core/using-the-biztalk-messaging-engine.md)