---
title: Escenarios de uso de transacciones atómicas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e73cfea7a99e2fafbf115a367dbf0840de3369c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270948"
---
# <a name="scenarios-using-atomic-transactions"></a>Escenarios que usan transacciones atómicas
En los escenarios siguientes se describe el uso de transacciones atómicas.  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a>Escenario 1: Una transacción atómica con ServicedComponent de COM +  
 La siguiente orquestación muestra cómo utilizar el **RetryTransactionException** con transacciones atómicas. Aunque los controladores de excepción se pueden incluir directamente para un ámbito atómico, el ámbito puede incluir un ámbito no transaccional que puede tener un controlador de excepción. El **ServicedComponent** da de alta en la misma transacción DTC y cualquier excepción producida por el componente es detectada y reenviada como **RetryTransactionException**. (Se supone que la **vuelva a intentar** propiedad está establecida en **True** para el ámbito atómico).  
  
 Tenga en cuenta que la orquestación se habría suspendida y se habría revierte la acción en la forma asignación de mensajes incluso si la **RetryTransactionException** no se produce. No obstante, este patrón permite aportar estabilidad a la aplicación donde se producen reintentos automáticamente.  
  
 **Una transacción atómica con ServicedComponent de COM +**  
  
 ![Una transacción atómica con COM &#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a>Escenario 2: Usar adaptadores de transacción con transacciones atómicas  
 La siguiente orquestación muestra cómo usar transacciones atómicas con el adaptador de SQL. Toda la orquestación está marcada como de larga ejecución con transacciones atómicas individuales para los dos elementos de trabajo lógicos: insertar un nuevo cliente y un orden de inserción de detalles para el cliente.  
  
 Si, por cualquier motivo, se produce un error en la inserción del pedido, debería deshacer la inserción del cliente. En el ejemplo se usa el adaptador de SQL para hacer el trabajo de base de datos. Tal y como se mencionó anteriormente, el ámbito asociado con una transacción atómica se completa cuando se envía el mensaje a la base de datos de cuadro de mensajes. Esto implica que, una vez que el motor ha enviado correctamente el mensaje en los ámbitos Scope_InsertCustomer y Scope_InsertOrder, se confirma cada uno de los ámbitos. El adaptador de SQL crea una nueva transacción para la inserción real del cliente o el orden.  
  
 Los puertos tienen una propiedad “Notificación de entrega” para validar que el mensaje se ha enviado correctamente a través del puerto de envío. Si la propiedad Notificación de entrega está establecida en “Transmitted”, se coloca una suscripción de recepción antes del punto de confirmación transaccional de la operación de envío. No obstante, en el caso de ámbitos atómicos, la suscripción de recepción se coloca en el ámbito primario envolvente.  
  
 En el escenario donde la transacción SQL InsertOrder produce un error, se devolverá un mensaje de confirmación negativa y se confirma “Scope_InsertOrder”. Una vez que el puerto de envío agota los reintentos configurados, se genera una excepción DeliveryFailureException. El controlador de excepción predeterminado detectará esta excepción, que ejecutará el proceso de compensación predeterminado. Esto invocará a los controladores de compensación asociados a Scope_InsertCustomer y Scope_InsertOrder, lo que provocará la operación deshacer para la inserción de la información de cliente.  
  
> [!NOTE]
>  La anidación de los dos ámbitos en un ámbito de larga ejecución y la invocación de la forma Compensar (dirigida a la transacción de larga ejecución) desde el controlador de excepción para el ámbito de larga ejecución producirá el mismo comportamiento descrito más arriba. La orquestación completa no se podría marcar como atómica puesto que las transacciones atómicas no permiten transacciones anidadas.  
  
 **Adaptadores de transacción con transacciones atómicas**  
  
 ![Adaptadores con transacciones atómicas con transacciones](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")