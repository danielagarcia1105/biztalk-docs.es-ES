---
title: Compatibilidad con Operations2 compuesto | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5766adec70c1a1fe7eaabe4ffaf07499e33d210c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-composite-operations"></a>Compatibilidad con operaciones compuestas
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes de adaptador realizar operaciones compuestas que pueden incluir cualquier número de las siguientes operaciones y en cualquier orden:  
  
-   SELECT, Insert, Update y Delete operaciones en una tabla de interfaz y la tabla de base de datos.  
  
-   Operación SELECT en una vista de la interfaz y la vista de base de datos.  
  
-   Los procedimientos almacenados, funciones y procedimientos de los paquetes que aparecen como operaciones en el adaptador.  
  
 Las operaciones en una operación compuesta pueden tener como destino tablas y vistas de la misma base de datos o bases de datos diferentes. Sin embargo, los datos no se comparten o volver a usar en operaciones diferentes en una operación compuesta. Por ejemplo, en una operación compuesta, el conjunto de resultados de una operación de selección no puede utilizarse como parámetro de entrada para un procedimiento almacenado.  
  
 Cada operación en una operación compuesta se realiza mediante una conexión independiente. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consume tantas conexiones de la agrupación de conexiones ODP.NET como el número de operaciones en una operación compuesta y, a continuación, libera las conexiones que se ejecutan las operaciones. Sin embargo, si una operación en la operación compuesta devuelve un conjunto de resultados, se libera la conexión solo después de que se consume el mensaje.  
  
> [!IMPORTANT]
>  Si tiene problemas de tiempo de espera mientras se ejecuta una operación compuesta, a continuación, podría deberse a que el número de conexiones es menor que el número de operaciones en una operación compuesta que implican:  
>   
>  -   Procedimientos almacenados que contengan BFILE, BLOB, CLOB, NCLOB y REF CURSOR como OUT o IN a parámetros.  
> -   Seleccione la operación.  
>   
>  Para resolver este problema, debe asegurarse de que si hay "n" número de tales operaciones en una operación compuesta, el valor especificado para la **MinPoolSize** enlaza la propiedad es "n + 1" o superior. Para obtener más información sobre la **MinPoolSize** enlace de propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
 Para obtener información acerca de:  
  
-   Cómo realizar operaciones compuestas en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones compuestas en la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).  
  
-   Esquemas para la operación compuesta de mensajes, vea [esquemas de mensaje para la operación compuesta](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md).  
  
> [!NOTE]
>  También puede establecer el contexto de las aplicaciones para operaciones compuestas en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Es obligatorio para establecer el contexto de las aplicaciones para las operaciones compuestas si cualquiera de las operaciones en una operación compuesta se realiza en una vista de tabla o la interfaz de la interfaz. Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo, vea [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="see-also"></a>Vea también  
 [Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)