---
title: Controlar las transacciones con el adaptador de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b443be9d-a93d-4836-8717-5ee9dad4442f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9d5bc59cdce4b78a01dc867e12a84eac3b3469d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010917"
---
# <a name="handle-transactions-with-the-oracle-e-business-suite-adapter"></a>Controlar las transacciones con el adaptador de Oracle E-Business Suite
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] no se inicia una transacción mientras se realiza una operación en Oracle E-Business Suite. En su lugar, el adaptador realiza las operaciones mediante el contexto de transacción proporcionado por los clientes del adaptador. Para poder realizar operaciones en una transacción utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe:  
  
-   Habilitar transacciones en los clientes del adaptador. Por ejemplo, para habilitar las transacciones de BizTalk Server, debe seleccionar la **Use Transaction** casilla de verificación en la **transacciones** área de la **mensajes** pestaña para un WCF-Custom o Puerto de WCF-OracleEBS.  
  
-   Establezca el valor de la **UseAmbientTransaction** enlazar la propiedad a **True** en el adaptador. Para obtener más información acerca de la propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
> [!IMPORTANT]
>  Para usar el adaptador para realizar transacciones en Oracle E-Business Suite, debe tener instalado el **Oracle Services para Microsoft Transaction Server** , componente, al instalar el cliente de Oracle, en el equipo que ejecuta el adaptador cliente.  
  
## <a name="transactions-in-the-outbound-operations"></a>Transacciones en las operaciones de salida  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] realiza una operación de salida en una sola transacción. Para operaciones compuestas, todas las operaciones se realizan en una única transacción, pero con diferentes conexiones ODP.NET. Para obtener más información acerca de las operaciones salientes obtenidas por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [¿cómo los metadatos de adaptador de superficie de Oracle E-Business Suite?](https://msdn.microsoft.com/library/dd788431.aspx).  
  
## <a name="transactions-in-the-inbound-operations"></a>Transacciones en las operaciones de entrada  
 La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone las dos operaciones de entrada siguientes:  
  
- **Sondeo**: la instrucción de sondeo y la instrucción de sondeo posterior (si se especifica) se ejecutan en una transacción, mientras que se ejecuta la instrucción disponibles de los datos obtenidos en una transacción diferente. De forma similar, la instrucción de sondeo y la instrucción de sondeo posterior a la se ejecutan con la misma conexión ODP.NET, mientras que se ejecuta la instrucción disponibles de los datos obtenidos con otra conexión ODP.NET.  
  
- **Notificación**: la operación de notificación se realiza en una transacción con una sola conexión ODP.NET.  
  
  Para obtener más información acerca de las operaciones de entrada obtenidas por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [¿cómo los metadatos de adaptador de superficie de Oracle E-Business Suite?](https://msdn.microsoft.com/library/dd788431.aspx).  
  
## <a name="see-also"></a>Vea también  
[El adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)