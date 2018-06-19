---
title: Ejecutar operaciones compuestas en SQL Server mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36a1ff6e4b2c7d4d56855ce1531f99cd490a2a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223332"
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a>Ejecutar operaciones compuestas en SQL Server mediante el adaptador de SQL
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] permite a los clientes de adaptador realizar operaciones compuestas en la base de datos de SQL Server. Una operación compuesta puede incluir cualquier número de las siguientes operaciones y en cualquier orden:  
  
-   Las operaciones Insert, Update y Delete en las tablas y vistas.  
  
-   Procedimientos almacenados que aparecen como operaciones en el adaptador.  
  
 Las operaciones en una operación compuesta *debe* tablas y vistas en una sola base de datos de destino.  
  
 Para obtener información acerca de:  
  
-   Cómo realizar operaciones compuestas en [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones compuestas en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md).  
  
-   Esquemas para la operación compuesta de mensajes, vea [esquemas de mensaje para operaciones compuestas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).  
  
> [!IMPORTANT]
>  Si no hay "n" número de operaciones en una operación compuesta que devuelven un número de conjunto, a continuación, "n+1" resultado de las conexiones es necesario para la operación compuesta que se ejecute. Por lo tanto, debe asegurarse de que el valor especificado para la **MaxConnectionPoolSize** propiedad de enlace es n + 1 o mayor. Para obtener más información sobre la **MaxConnectionPoolSize** enlace de propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)