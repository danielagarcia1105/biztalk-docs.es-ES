---
title: Controlar las transacciones con el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971c2fba-640c-4ae5-9ab3-2d8227c1627d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94914c2f0f7bde91ea55032048e30232af60d02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970709"
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a>Controlar las transacciones con el adaptador de base de datos de Oracle
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] no se inicia una transacción mientras se realiza una operación en la base de datos de Oracle. En su lugar, el adaptador realiza las operaciones mediante el contexto de transacción proporcionado por los clientes del adaptador. Para poder realizar operaciones en una transacción utilizando el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe:  
  
-   Habilitar transacciones en los clientes del adaptador. Por ejemplo, para habilitar las transacciones de BizTalk Server, debe seleccionar la **Use Transaction** casilla de verificación en la **transacciones** área de la **mensajes** pestaña para un WCF-Custom o Puerto de WCF-OracleDB.  
  
-   Establezca el valor de la **UseAmbientTransaction** enlazar la propiedad a **True** en el adaptador. Para obtener más información acerca de la propiedad de enlace, consulte [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
> [!IMPORTANT]
>  Para usar el adaptador para realizar transacciones en la base de datos de Oracle, debe tener instalado el **Oracle Services para Microsoft Transaction Server** , componente, al instalar el cliente de Oracle, en el equipo que ejecuta el adaptador cliente.  
  
## <a name="transactions-in-the-outbound-operations"></a>Transacciones en las operaciones de salida  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] realiza una operación de salida en una sola transacción. Para operaciones compuestas, todas las operaciones se realizan en una única transacción, pero con diferentes conexiones ODP.NET. Para obtener más información acerca de las operaciones salientes obtenidas por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [¿cómo los metadatos de adaptador de superficie de Oracle?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).  
  
## <a name="transactions-in-the-inbound-operations"></a>Transacciones en las operaciones de entrada  
 La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone las dos operaciones de entrada siguientes:  
  
- **Sondeo**: la instrucción de sondeo y la instrucción de sondeo posterior (si se especifica) se ejecutan en una transacción, mientras que se ejecuta la instrucción disponibles de los datos obtenidos en una transacción diferente. De forma similar, la instrucción de sondeo y la instrucción de sondeo posterior a la se ejecutan con la misma conexión ODP.NET, mientras que se ejecuta la instrucción disponibles de los datos obtenidos con otra conexión ODP.NET.  
  
- **Notificación**: la operación de notificación se realiza en una transacción con una sola conexión ODP.NET.  
  
  Para obtener más información acerca de las operaciones de entrada obtenidas por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [¿cómo los metadatos de adaptador de superficie de Oracle?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)