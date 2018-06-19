---
title: Interfaces para transaccional compatible con lotes del adaptador de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5289e8b8-4447-4196-9f7c-5e60c6598d8d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b51a67f63f3088ce64c9db35c368289ce156d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257580"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a>Interfaces de un adaptador de recepción transaccional compatible con lotes
Un adaptador de recepción crea y controla transacciones cuando se necesita un envío de mensajes transaccional.  
  
 Recepción transaccional adaptador crea y pasa un puntero a una transacción del Coordinador de transacciones distribuidas de Microsoft (MSDTC) en el **realiza** método de la **IBTTransportBatch** interfaz. Esto garantiza que todas las operaciones del lote se realicen en el ámbito de dicho objeto de transacción específico. Cuando se completa el envío del lote, el método de devolución de llamada del adaptador confirma o revierte la transacción. La acción que se realiza depende del estado devuelto desde el proxy de transporte y, probablemente, de otro trabajo relacionado con la transacción que realiza el adaptador y que no es visible para el proxy de transporte. El adaptador determina si la transacción es errónea o correcta. El adaptador informa del resultado de la transacción (confirma o revierte) al proxy de transporte mediante el uso de la **DTCCommitConfirm** método de la**IBTDTCCommitConfirm** interfaz. Pasa un valor en `true` para una transacción correcta o `false` para un error.  
  
 La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción transaccional compatible con lotes.  
  
 ![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")  
Flujo de trabajo de un adaptador de recepción que envía un lote de mensajes mediante transacciones DTC  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md)   
 [Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [Interfaces para un proceso en el adaptador de recepción](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [Adaptador de recepción de interfaces para un aislado](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [Adaptador de recepción de interfaces para un compatible con lotes](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [Adaptador de recepción de interfaces para una solicitud-respuesta sincrónico](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)