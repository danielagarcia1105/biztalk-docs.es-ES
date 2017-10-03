---
title: "Las transacciones de larga ejecución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- long-running transactions, about long-running transactions
- atomic transactions, long-running transactions
- long-running transactions, orchestrations
- long-running transactions, nesting
- scopes, examples
- orchestrations, transactions
- compensations, long-running transactions
- compensations, customizing
- transactions, long-running
- transactions, compensation blocks
- long-running transactions
- long-running transactions, timeouts
- compensations, examples
- fault tolerance, long-running transactions
- transactions, examples
- orchestrations, long-running transactions
- transactions, atomic
- transactions, fault tolerance
- scopes, long-running transactions
- long-running transactions, fault tolerance
- transactions, nesting
- examples, scopes
ms.assetid: 4bf4d0c8-903a-411f-963b-bd4cfdfc2958
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c419c79b9de6287a0361dfe4e2e6b9dc555153
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="long-running-transactions"></a>Transacciones de larga ejecución
Las transacciones de larga ejecución son construcciones importantes y utilizadas frecuentemente en orquestaciones de BizTalk. Proporcionan funciones para la compensación personalizada y el control de excepciones personalizado basados en el ámbito, así como la capacidad para anidar transacciones; todo ello ofrece una gran flexibilidad a la hora de diseñar una arquitectura de transacciones sólida.  
  
 Las transacciones de larga ejecución se utilizan cuando es posible que la transacción deba ejecutarse durante un período prolongado y no son necesarias las propiedades ACID completas (es decir, no es necesario garantizar el aislamiento de los datos procedentes de otras transacciones). Una transacción de larga ejecución puede tener largos períodos de inactividad que suelen deberse a la espera de la llegada de mensajes externos.  
  
 Las transacciones de larga ejecución poseen coherencia y durabilidad, pero no atomicidad ni aislamiento. Los datos dentro de una transacción de larga ejecución no están bloqueados; otros procesos o aplicaciones pueden modificarlos. La propiedad de aislamiento para actualizaciones de estado no se conserva porque no se pueden mantener los bloqueos durante un período prolongado.  
  
 La confirmación de una transacción de larga ejecución es distinta de la confirmación de una transacción atómica. No hay ningún supuesto implícito de coordinación distribuida en lo que respecta al resultado (una transacción de larga ejecución existe únicamente dentro de una sola instancia de orquestación). En su lugar, una transacción de larga ejecución se considera confirmada cuando se ha completado la última instrucción contenida en ella. No se produce ninguna reversión automática del estado en caso de la anulación de una transacción. Esto se puede conseguir mediante la programación de los controladores de excepción y compensación.  
  
 Un ámbito puede definir su propio estado mediante la declaración de variables, mensajes y componentes .NET. Una transacción de larga ejecución tiene acceso a la información de estado de su propio ámbito, a cualquier ámbito que la contenga y a cualquier información de estado que esté definida globalmente dentro de la orquestación. Sin embargo, no dispone de acceso a la información de estado de ningún ámbito que no la contenga.  
  
## <a name="nesting"></a>Anidación  
 Las transacciones de larga ejecución pueden contener transacciones atómicas u otras transacciones de larga ejecución. Se pueden anidar en niveles de profundidad arbitrarios. Por ejemplo, la transacción podría contener otras dos transacciones de larga ejecución, cada una de las cuales podría contener transacciones atómicas.  
  
 La anidación resulta especialmente útil cuando uno o más componentes de la transacción global tienen que ser atómicos, mientras que la transacción global tiene que ser de larga ejecución. Considere el ejemplo de recepción y cumplimentación de un pedido. El pedido puede llegar en cualquier momento y los distintos pasos para cumplimentarlo pueden tardar en producirse, pero aún así desea tratar todo el proceso como una transacción. En este caso, la transacción global tiene que ser obviamente una de larga ejecución, aunque uno de los pasos, como la confirmación de un pago, tenga que ser atómico.  
  
> [!NOTE]
>  No se puede anidar un ámbito transaccional dentro de un ámbito o una orquestación que no lo sea. Una orquestación o un ámbito de inclusión que no sea transaccional no administrará el estado, ya que debe controlar debidamente la administración de estado de cualquier ámbito que contenga.  
  
> [!NOTE]
>  Una transacción sincronizada no puede incluir ninguna otra transacción ni ámbitos sincronizados.  
  
## <a name="compensation"></a>Compensación  
 Una transacción de larga ejecución puede especificar un bloque de compensación al que se llamará para compensar las actividades de la transacción una vez se confirme. Podría bastar con deshacer la transacción donde sea factible o realizar alguna otra función, como la notificación, que ayude a paliar en cierta medida los efectos de la transacción. Si no agrega su propio código de compensación, el motor de tiempo de ejecución llamará de forma predeterminada a los bloques de compensación de las transacciones internas, tanto de larga ejecución como atómicas, en orden inverso, comenzando por la última transacción confirmada y terminando por la primera.  
  
> [!NOTE]
>  La compensación solo puede realizarse en una transacción que se haya confirmado correctamente.  
  
## <a name="fault-tolerance"></a>Tolerancia a errores  
 Las transacciones admiten la tolerancia a errores para la recuperación tanto de errores internos (como averías del equipo y errores de software) como de errores externos (como mensajes de cancelación). Cuando se produce un error en una transacción, las actualizaciones parciales dentro de transacciones de larga ejecución no se deshacen automáticamente ya que están en transacciones ACID.  
  
 Si se produce un error, se llama al bloque de código de excepción correspondiente a la transacción de larga ejecución. El bloque de código de excepción contiene un conjunto de controladores de errores que se escriben para tratar cualquiera de los errores que puedan surgir durante la ejecución de la transacción. Para controlar el error, puede basarse en el último estado conocido de mensajes, variables y objetos.  
  
 Normalmente, deseará que el controlador de excepción evalúe el estado de la orquestación en el momento en que se produce la excepción, lleve a cabo cualquier acción necesaria basada en dicho estado y llame a las compensaciones de las transacciones anidadas.  
  
 Cuando se produce un error, se interrumpe la ejecución de las transacciones de larga ejecución. Una vez que se produce un error, no se puede reanudar.  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de uso de transacciones de larga ejecución](../core/scenarios-using-long-running-transactions.md)   
 [Transacciones atómicas](../core/atomic-transactions.md)   
 [Uso de transacciones y control de excepciones](../core/using-transactions-and-handling-exceptions.md)