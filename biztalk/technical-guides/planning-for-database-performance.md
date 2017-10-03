---
title: Planear el rendimiento de la base de datos de | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7212fa37-88e0-4b5f-af97-c72063357645
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1338088acc91a45572ae1b49131d99f6c58cb739
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-performance"></a>Planear el rendimiento de la base de datos de
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es una muy base de datos intensivas aplicación que requieran la creación de hasta 13 bases de datos independientes en Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Dada la naturaleza de uso intensivo de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], resulta de importancia crítica que elija la versión adecuada y la edición de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que hospedará el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Para optimizar el rendimiento de los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] esa casa el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, siga las recomendaciones de este tema y en el [optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=101578) notas del producto ([ http://go.Microsoft.com/fwlink/?LinkId=101578](http://go.microsoft.com/fwlink/?LinkID=101578)).  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]las bases de datos deben instalarse en cualquier [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] o [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)].  
  
> [!NOTE]  
>  Mientras estas notas del producto se escribe para otras versiones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], puede usar las mismas recomendaciones para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)].  
  
## <a name="considerations-for-sql-server-editions"></a>Consideraciones para las ediciones de SQL Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]las bases de datos deben configurarse para ejecutarse en una instancia dedicada de SQL Server siempre que sea posible. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]es una aplicación intensiva de base de datos, por lo que separación de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y los equipos de SQL Server que alojan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mejorará el rendimiento de bases de datos y debe considerarse como un procedimiento recomendado en uno de producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno .  
  
 Diferentes ediciones de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] proporcionan diversas características que pueden afectar al rendimiento de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Por ejemplo, en condiciones de carga elevada, el número de elementos disponibles de base de datos bloqueos que están disponibles para la versión de 32 bits de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] puede superarse, que es negativo en el rendimiento de la solución de BizTalk. Considere la posibilidad de alojamiento de la base de datos de cuadro de mensajes en una versión de 64 bits de SQL Server si se producen errores de "sin bloqueo" en el entorno de prueba. El número de bloqueos disponible es significativamente superior en la versión de 64 bits de SQL Server.  
  
 Tenga en cuenta la tabla siguiente al decidir el motor de base de datos características que necesitará para el entorno de BizTalk. Para las soluciones a pequeña escala, por ejemplo, cuando ejecuta [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] edición para sucursales, [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Workgroup Edition puede ser adecuada para el alojamiento del [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Para gran escala, compatibilidad con soluciones de nivel de empresa que requieren la agrupación en clústeres, soporte técnico, de trasvase de registros de BizTalk o Analysis Services admite y, a continuación, deberá [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Enterprise Edition para alojar el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos.  
  
|Versión y edición de SQL Server|Compatibilidad con 64 bits|Compatibilidad con varias instancias|Compatibilidad con clústeres|Analysis Services|  
|---------------------------------------|---------------------|-----------------------------|------------------------|-----------------------|  
|SQL Server 2008 SP1 / SQL Server 2008 R2 Enterprise Edition|Sí|Sí|Sí|Sí|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] / [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Edición Standard|Sí|Sí|Sí (2 nodos)|Sí|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] / [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Edición de grupo de trabajo|Sí|Sí|No|No|  
  
> [!NOTE]  
>  ATR de BAM requiere [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Enterprise Edition.  
  
 Para obtener una lista completa de las características admitidas por las ediciones de [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], consulte [características compatibles con las ediciones de SQL Server 2008 R2](http://go.microsoft.com/fwlink/?LinkId=151940) ([http://go.microsoft.com/fwlink/? LinkId = 151940](http://go.microsoft.com/fwlink/?LinkId=151940)) en el [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] documentación.