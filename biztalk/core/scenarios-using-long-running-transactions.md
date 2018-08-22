---
title: Escenarios de uso de transacciones de larga ejecución | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions, long-running
- long-running transactions, timeouts
- transactions, examples
- long-running transactions, examples
- long-running compensations
- examples, long-running transactions
- examples, custom compensations
ms.assetid: 76b3e0f8-44dc-419e-a73a-c2908b1d8795
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ac14bc6e333f963dda7cb9b33d1ebf371c0546
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269924"
---
# <a name="scenarios-using-long-running-transactions"></a>Escenarios que usan transacciones de larga ejecución
En los escenarios siguientes se describe el uso de transacciones de larga ejecución.  
  
## <a name="scenario-1-using-long-running-transactions-with-timeouts"></a>Escenario 1: Uso de transacciones de larga ejecución con tiempos de espera  
 Ámbitos de larga ejecución se puede asociar con un tiempo de espera, que es el tiempo lógico en el que se debe completar el trabajo de ejecución prolongada. Si el ámbito no se completa dentro del tiempo especificado, una excepción predefinida del sistema **TimeoutException** se genera.  
  
 Puede crear procesos de larga ejecución si marca la orquestación completa como de larga ejecución, o bien tiene un ámbito de larga ejecución externo anidado a cualquier otro ámbito. En el primer escenario, se ejecuta un controlador de excepción proporcionado por el sistema, mientras que en el último se pueden asociar controladores de excepción específicos al ámbito externo. El controlador de excepción predeterminado proporcionado por el sistema ejecutará el controlador de compensación de los ámbitos transaccionales anidados y completados de forma correcta, si hay alguno, en orden inverso a la finalización. Puede conseguir el mismo resultado mediante la auto compensación si usa la forma Compensar en el controlador de excepción para una transacción de larga ejecución.  
  
 La siguiente orquestación es una representación de cómo asociar tiempos de espera a transacciones de larga ejecución.  
  
 **Transacciones de ejecución larga con tiempos de espera**  
  
 ![Transacciones de larga ejecución con tiempos de espera](../core/media/bts-trans-orch-fig7.gif "BTS_Trans_Orch_Fig7")  
  
 Algunas veces, puede ser necesario establecer una conexión con sistemas heredados que funcionan en forma de lotes. Este escenario muestra un pedido que se ha recibido y enviado al sistema heredado. El sistema heredado procesa el pedido y devuelve una confirmación de pedido. La operación de envío inicializa un conjunto de correlaciones mediante el número de pedido y la operación de recepción sigue a ese conjunto de correlaciones. La operación de recepción se encuentra también en un ámbito de larga ejecución con un valor de tiempo de espera.  
  
 El motor de orquestaciones deshidratará la instancia de orquestación que espera la recepción. La correlación asegurará que se invoca la misma instancia de orquestación cuando se recibe el mensaje. Si la confirmación de pedido de compra no llega en el intervalo de tiempo especificado por los valores de tiempo de espera, una **TimeoutException** se iniciará.  
  
## <a name="scenario-2-using-long-running-transactions-with-custom-compensation"></a>Escenario 2: Uso de transacciones de larga ejecución con compensación personalizada  
 Las siguientes orquestaciones demuestran cómo asociar e invocar compensaciones personalizadas asociadas a orquestaciones completas. Este escenario inserta un cliente nuevo y los detalles del pedido para el cliente. La lógica de la orquestación indica que si se produce un error en la inserción del pedido, debería deshacer la inserción del cliente. La inserción del cliente puede hacerla un sistema heredado y, por lo tanto, mostrarse en una orquestación a la que se puede llamar diferente. La orquestación de llamada tiene el **personalizado** propiedad establecida de la compensación, que proporciona una hoja independiente para realizar el proceso de compensación. La compensación consiste en eliminar el cliente que se acaba de insertar.  
  
 La orquestación de llamada tiene un ámbito de larga ejecución para realizar la inserción del pedido. Este ámbito se anida en un ámbito de larga ejecución externo. El ámbito externo tiene un controlador de excepción asociado para detectar cualquier excepción. El controlador usa la forma Compensar para invocar la excepción personalizada asociada a la orquestación de llamada y deshacer, de este modo, cualquier cambio que se pueda haber producido en la llamada a la orquestación.  
  
 **Transacciones de larga ejecución con compensación personalizada**  
  
 ![Transacciones de larga ejecución con compensación personalizada](../core/media/bts-trans-orch-fig8.gif "BTS_Trans_Orch_Fig8")  
  
 **Orquestación llamada (principal)**  
  
 ![Llamado orquestación & #40; main & #41; ](../core/media/bts-trans-orch-fig9.gif "BTS_Trans_Orch_Fig9")  
  
 **Orquestación llamada (compensación)**  
  
 ![Llamado orquestación & #40; compensación & #41; ](../core/media/bts-trans-orch-fig10.gif "BTS_Trans_Orch_Fig10")