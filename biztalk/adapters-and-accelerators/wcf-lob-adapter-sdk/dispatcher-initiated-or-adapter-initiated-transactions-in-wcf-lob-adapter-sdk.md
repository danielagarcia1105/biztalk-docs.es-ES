---
title: Configurar las transacciones iniciadas por el distribuidor o iniciada por el adaptador con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85b9ef8d-3922-4838-a41a-32db5e005dc0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa8105b4b6f8eb77d68471faf9b702419f6a1f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a>Configurar las transacciones iniciadas por el distribuidor o iniciada por el adaptador con el SDK de adaptador LOB de WCF
## <a name="inbound-transactions"></a>Transacciones entrantes  
 Hay dos métodos para implementar las transacciones con las operaciones de entrada: iniciadas por el distribuidor o iniciada por el adaptador. Los requisitos del adaptador indican qué método se debe utilizar. El valor de la `SupportsTransactedInbound` propiedad indica qué tipo de transacción que implementará el adaptador.  
  
 En la tabla siguiente compara iniciadas por el distribuidor con las transacciones iniciadas por el adaptador.  
  
|SupportsTransactedInbound|Comportamiento transaccional|  
|-------------------------------|----------------------------|  
|True (iniciadas por el distribuidor)|-TryReceive siempre se llamará en el contexto de una transacción.<br />-La transacción se confirmará después de que el mensaje se devuelve a la implementación del servicio.<br />-Se creará una transacción nueva para cada llamada IInputChannel.Receive. La expansión de una transacción entre varios recibe depende en el host de servicio y no el desarrollador de adaptadores. **Nota:** si el host no está usando el distribuidor WCF (host de servicio) y en su lugar usará la programación de nivel de canal, el host debe respetar el **TransactedReceiveEnabled** propiedad del enlace de WCF y debe realizar todas las llamadas a IInputChannel.Receive dentro de una transacción. **Nota:** si el adaptador utiliza transacciones iniciadas por el distribuidor y se usa con Biztalk Server, establezca la `SupportedInboundChannels` propiedad `SupportedInboundChannels.IInputChannel` para indicar que el adaptador sólo es compatible con canales unidireccionales. Si no se establece, BizTalk Server intentará usar canales bidireccionales.|  
|False (iniciadas por el adaptador)|-El desarrollador de adaptadores debe implementar la lógica de transacción en el adaptador.<br />-Adaptador-iniciar transacciones sólo pueden trabajar con un modelo (canal de respuesta) mensajería bidireccional.<br />-Una transacción puede abarcar varios mensajes, ya que se pueden crear clones dependientes para cada mensaje por el distribuidor.|  
  
### <a name="dispatcher-initiated-transactions"></a>Transacciones iniciadas por el distribuidor  
 Cuando se establece SupportsTransactedInbound en **true**, el distribuidor WCF, a continuación, creará automáticamente una transacción al llamar a la **TryReceive** método del adaptador y confirmará la transacción Después de que el mensaje se devuelve a la implementación del servicio. Esto no exige las implementaciones específicas de código transaccional en el adaptador aparte de establecer el `SupportsTransactedInbound` propiedad **true**. Sin embargo, esto depende del adaptador se hospeda dentro de un host de servicio que utiliza el distribuidor WCF y no se producirá si usa la programación de nivel de canal. Cuando se usa la programación de nivel de canal, el host debe respetar el `TransactedReceiveEnabled` propiedad del enlace de WCF y efectuar todas las llamadas a la recepción dentro de una transacción.  
  
 A continuación muestra a un cliente crear una transacción y, a continuación, llamar al adaptador mediante programación de nivel de canal.  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a>Transacciones iniciadas por el adaptador  
 Cuando el `SupportsTransactedInbound` propiedad está establecida en **false**, compatibilidad con transacciones debe implementarse en el código del adaptador mediante la creación de una nueva transacción. Antes de devolver un mensaje de **TryReceive**, la transacción debe asociarse al mensaje mediante una llamada a la **establecer** método de la **TransactionMessageProperty** clase. Esta implementación requiere compatibilidad con transacciones explícitas en el código del adaptador y proporciona mayor control sobre el comportamiento transaccional del adaptador.  
  
 A continuación, muestra cómo crear una transacción dependiente y asociar esto al mensaje antes de que se devuelva al cliente.  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a>Vea también  
 [Actividades de desarrollo](../../esb-toolkit/development-activities.md)