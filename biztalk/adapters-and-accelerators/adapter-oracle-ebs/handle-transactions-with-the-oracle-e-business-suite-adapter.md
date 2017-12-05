---
title: Controlar las transacciones con el adaptador de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b443be9d-a93d-4836-8717-5ee9dad4442f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d3d9946db7ea9ec1e9d035aa34081c1a11c113e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="handle-transactions-with-the-oracle-e-business-suite-adapter"></a>Controlar las transacciones con el adaptador de Oracle E-Business Suite
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]no se inicia una transacción al realizar una operación en Oracle E-Business Suite. En su lugar, el adaptador realiza las operaciones mediante el contexto de transacción proporcionado por los clientes de adaptador. Para poder realizar operaciones en una transacción usando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe:  
  
-   Habilitar transacciones en los clientes de adaptador. Por ejemplo, para habilitar las transacciones en el servidor BizTalk Server, debe seleccionar la **Use Transaction** casilla de verificación en la **transacciones** área no cliente de la **mensajes** pestaña para un WCF-Custom o Puerto de WCF-OracleEBS.  
  
-   Establezca el valor de la **UseAmbientTransaction** enlazar la propiedad a **True** en el adaptador. Para obtener más información acerca de la propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
> [!IMPORTANT]
>  Para usar el adaptador para realizar transacciones en Oracle E-Business Suite, debe tener instalado el **Oracle Services para Microsoft Transaction Server** componente, al instalar el cliente de Oracle, en el equipo que ejecuta el adaptador cliente.  
  
## <a name="transactions-in-the-outbound-operations"></a>Transacciones en las operaciones de salida  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] realiza una operación de salida en una sola transacción. Para operaciones compuestas, todas las operaciones se realizan en una única transacción, pero con diferentes conexiones de ODP.NET. Para obtener más información acerca de las operaciones de salida obtenidas por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [¿cómo los metadatos de adaptador de superficie de Oracle E-Business Suite?](https://msdn.microsoft.com/library/dd788431.aspx).  
  
## <a name="transactions-in-the-inbound-operations"></a>Transacciones en las operaciones de entrada  
 La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone las dos operaciones de entrada siguientes:  
  
-   **Sondeo**: la instrucción de sondeo y la instrucción de sondeo posterior (si se especifica) se ejecutan en una transacción, mientras que se ejecuta la instrucción de disponibilidad de los datos obtenidos en una transacción diferente. De forma similar, la instrucción de sondeo y la instrucción de sondeo posterior a la se ejecutan con la misma conexión ODP.NET, mientras que se ejecuta la instrucción disponibles de los datos obtenidos mediante una conexión de ODP.NET diferentes.  
  
-   **Notificación**: la operación de notificación se realiza en una transacción mediante una única conexión ODP.NET.  
  
 Para obtener más información acerca de las operaciones de entrada obtenidas por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [¿cómo los metadatos de adaptador de superficie de Oracle E-Business Suite?](https://msdn.microsoft.com/library/dd788431.aspx).  
  
## <a name="see-also"></a>Vea también  
[El adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)