---
title: Compatibilidad con Operations2 compuesto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724d5bc41686abc3928716a0e08801107df25055
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979389"
---
# <a name="support-for-composite-operations"></a>Compatibilidad para operaciones compuestas
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes del adaptador realizar operaciones compuestas que pueden incluir cualquier número de las siguientes operaciones y en cualquier orden:  
  
- Seleccionar, insertar, actualizar y eliminar operaciones en una tabla de interfaz y base de datos.  
  
- Seleccione la operación en una vista de interfaz y la vista de base de datos.  
  
- Procedimientos almacenados, funciones y procedimientos de los paquetes que se exponen como operaciones en el adaptador.  
  
  Pueden dirigirse a las operaciones en una operación compuesta de tablas y vistas de la misma base de datos o bases de datos diferentes. Sin embargo, los datos no se comparten o reutilizar en distintas operaciones en una operación compuesta. Por ejemplo, en una operación compuesta, el conjunto de resultados de una operación Select no se puede usar como parámetro de entrada para un procedimiento almacenado.  
  
  Cada operación en una operación compuesta se realiza mediante una conexión independiente. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consume tantas conexiones de la agrupación de conexiones ODP.NET como el número de operaciones en una operación compuesta y, a continuación, libera las conexiones que se ejecutan las operaciones. Sin embargo, si una operación en la operación de composición devuelve un conjunto de resultados, la conexión se libera solo después de que se consume el mensaje.  
  
> [!IMPORTANT]
>  Si experimenta problemas de tiempo de espera mientras se ejecuta una operación compuesta podría ser porque el número de conexiones es menor que el número de operaciones en una operación compuesta que implican:  
> 
> - Procedimientos almacenados que contengan BFILE, BLOB, CLOB, NCLOB y REF CURSOR como OUT o IN OUT parámetros.  
>   -   Operación de selección.  
> 
>   Para resolver este problema, debe asegurarse de que, si hay un número de "n" de estas operaciones en una operación compuesta, el valor especificado para el **MinPoolSize** enlaza la propiedad es "n + 1" o superior. Para obtener más información sobre la **MinPoolSize** enlaza la propiedad, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
 Para obtener información acerca de:  
  
- Cómo realizar operaciones compuestas en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones compuestas en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).  
  
- Los esquemas para la operación compuesta de mensajes, vea [esquemas de mensaje para la operación compuesta](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md).  
  
> [!NOTE]
>  También puede establecer el contexto de las aplicaciones para operaciones compuestas en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Es obligatorio para establecer el contexto de las aplicaciones para las operaciones compuestas si alguna de las operaciones en una operación compuesta se realiza en una vista de tabla o la interfaz de la interfaz. Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="see-also"></a>Vea también  
 [Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)