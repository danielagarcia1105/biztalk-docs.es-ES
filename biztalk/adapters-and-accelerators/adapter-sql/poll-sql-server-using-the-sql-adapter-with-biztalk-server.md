---
title: Sondear el servidor de SQL con el adaptador de SQL BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eef9a4b4-552d-4552-b318-1deab506bad9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e631a966ffee632e6c866a962c4fe47b2f1025
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a>Sondear el servidor de SQL con el adaptador de SQL BizTalk Server
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de cambio de datos basado en sondeo de SQL Server. Puede especificar una instrucción de sondeo que el adaptador se ejecuta para sondear la base de datos. La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados. Según el tipo de mensaje de sondeo recibido, el adaptador expone tres formas diferentes de sondeo:  
  
-   **Sondeo**. Esta operación devuelve un conjunto de datos como parte del mensaje de sondeo. En tiempo de diseño, el esquema del objeto de base de datos se sondean, no está disponible. En su lugar, el esquema está disponible como parte del mensaje de sondeo durante el tiempo de ejecución.  
  
-   **TypedPolling**. Esta operación devuelve un mensaje de sondeo fuertemente tipado. En tiempo de diseño, el esquema del objeto de base de datos también está disponible. Debe usar esta operación para el sondeo si desea asignar determinados elementos del mensaje de sondeo a otro esquema, lo que sería para otra operación.  
  
-   **XmlPolling**. Esta operación devuelve el mensaje de sondeo como un mensaje XML. Debe usar esta operación si desea utilizar las instrucciones SELECT o procedimientos almacenados que utilizan la cláusula FOR XML para devolver los datos como mensajes XML. Para obtener más información acerca de la cláusula FOR XML, vea [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx). 
  
 Para obtener más información acerca de estas operaciones de sondeo, consulte [soporte técnico para el sondeo](https://msdn.microsoft.com/library/dd788416.aspx).  
  
> [!NOTE]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador tiene una única aplicación de BizTalk con operaciones de más de un sondeo o TypedPolling para la misma base de datos o tabla. Para admitir este escenario, el adaptador incluye un identificador único, **InboundID**: en el URI de conexión. Este Id., cuando se agrega a la conexión URI, hace único, lo que permite varias operaciones de sondeo en una sola aplicación de BizTalk.  
  
 Los temas de esta sección proporcionan instrucciones sobre cómo utilizar el sondeo, TypedPolling y XmlPolling en una aplicación de BizTalk. Esta sección también proporciona información sobre cómo usar el **InboundID** propiedad de conexión.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el uso de BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [Recibir fuertemente tipado mensajes de cambio de datos basado en sondeo desde SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [Recepción de sondeo mensajes utilizando instrucciones SELECT con la cláusula FOR XML de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [Recepción de sondeo mensajes a través de varios puertos de recepción de SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)