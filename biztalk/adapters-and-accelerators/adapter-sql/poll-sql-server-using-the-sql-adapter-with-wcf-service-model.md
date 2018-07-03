---
title: Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef2e868-bd51-4393-b091-f67299b4759d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb3bbd42c732f3377c5823831b9507bbeb0c83bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022314"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a>Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio WCF
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir los mensajes basados en sondeos de cambio de datos de SQL Server. Puede especificar una instrucción de sondeo que se ejecuta el adaptador para sondear la base de datos. La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados. Según el tipo de mensaje de sondeo recibe, el adaptador expone las operaciones de sondeo diferentes:  
  
- **Sondeo**. Esta operación devuelve un conjunto de datos como parte del mensaje de sondeo.  
  
- **TypedPolling**. Esta operación devuelve un mensaje de sondeo fuertemente tipado.  
  
- **XmlPolling**. Esta operación devuelve el mensaje de sondeo como un mensaje XML. Debe usar esta operación si desea utilizar las instrucciones SELECT o procedimientos almacenados que utilizan la cláusula FOR XML para devolver los datos como los mensajes XML. [Cláusula FOR XML](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server) proporciona más información. 
  
  Para obtener más información acerca de estas operaciones de sondeo, consulte [sondeo en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).  
  
> [!NOTE]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes del adaptador tiene una sola aplicación con más de un sondeo o TypedPolling operaciones para la misma base de datos o tabla. Para admitir este escenario, el adaptador incluye un identificador único, **InboundID**: en el URI de conexión. Este identificador, cuando se agrega a la conexión URI, hace único, lo que permite varias operaciones de sondeo en una sola aplicación.  
  
 Los temas de esta sección proporcionan instrucciones sobre cómo usar las operaciones de sondeo y TypedPolling en una aplicación. NET.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Recibir mensajes basados en sondeos de cambio de datos de SQL Server mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [Recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde SQL Server mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)