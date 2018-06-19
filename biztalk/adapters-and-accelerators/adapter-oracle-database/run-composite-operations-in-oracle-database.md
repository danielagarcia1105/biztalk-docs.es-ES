---
title: Ejecutar operaciones compuestas en base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b877d8e3-2016-40e8-888f-6b768021d6b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5595823fab4f25948e3d88db759ae525f62130
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215124"
---
# <a name="run-composite-operations-in-oracle-database"></a>Ejecutar operaciones compuestas en base de datos de Oracle
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes de adaptador realizar operaciones compuestas que pueden incluir cualquier número de las siguientes operaciones y en cualquier orden:  
  
-   SELECT, Insert, Update y Delete operaciones en tablas y vistas.  
  
-   Procedimientos almacenados, funciones, procedimientos o funciones de los paquetes que aparecen como operaciones en el adaptador.  
  
 Las operaciones en una operación compuesta pueden tener como destino tablas y vistas de la misma base de datos o bases de datos diferentes. Sin embargo, los datos no se comparten o volver a usar en operaciones diferentes en una operación compuesta. Por ejemplo, en una operación compuesta, el conjunto de resultados de una operación de selección no puede utilizarse como parámetro de entrada para un procedimiento almacenado.  
  
 Cada operación en una operación compuesta se realiza mediante una conexión independiente. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume tantas conexiones de la agrupación de conexiones ODP.NET como el número de operaciones en una operación compuesta y, a continuación, libera las conexiones que se ejecutan las operaciones. Sin embargo, si una operación en la operación compuesta devuelve un conjunto de resultados, se libera la conexión solo después de que se consume el mensaje.  
  
> [!IMPORTANT]
>  Si tiene problemas de tiempo de espera mientras se ejecuta una operación compuesta, a continuación, podría deberse a que el número de conexiones es menor que el número de operaciones en una operación compuesta que implican:  
>   
>  -   Procedimientos almacenados que contengan BFILE, BLOB, CLOB, NCLOB y REF CURSOR como OUT o IN a parámetros.  
> -   Seleccione la operación.  
>   
>  Para resolver este problema, debe asegurarse de que si hay "n" número de tales operaciones en una operación compuesta, el valor especificado para la **MinPoolSize** enlaza la propiedad es "n + 1" o superior. Para obtener más información sobre la **MinPoolSize** enlace de propiedad, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
 Para obtener información acerca de:  
  
-   Cómo realizar operaciones compuestas en [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones compuestas en la base de datos Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).  
  
-   Esquemas para la operación compuesta de mensajes, vea [esquemas de mensaje para la operación compuesta](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)