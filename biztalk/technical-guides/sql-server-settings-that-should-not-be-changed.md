---
title: "Configuración de SQL Server que no debe cambiarse | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b383bfb-c3d9-47d4-b294-f6be94302734
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fb6e2553c005d3ba8651c860ff844e8cc74106
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-settings-that-should-not-be-changed"></a>Configuración de SQL Server que no se debe cambiar
Al configurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] durante los procedimientos de preparación operativa para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], no debe realizar cambios en las configuraciones siguientes.  
  
## <a name="sql-server-max-degree-of-parallelism"></a>Grado máximo de paralelismo de SQL Server  
 Max Degree de paralelismo (MDOP) se establece en "1" durante la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s) que hospedan la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes. Se trata de un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] configuración de nivel de instancia. Esta configuración no se debe cambiar el valor de "1". Cambiar esto a algo distinto de "1" puede tener un efecto negativo importante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los procedimientos almacenados y rendimiento. Si se cambia el valor de paralelismo para una instancia de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tendrá un efecto adverso en otras aplicaciones de base de datos que se están ejecutando en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia, debe crear una instancia independiente de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] dedicados a hospedar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
 Las consultas en paralelo generalmente son más adecuadas para el procesamiento por lotes y las cargas de trabajo de compatibilidad de decisión. Normalmente no son deseables en un entorno de procesamiento de transacciones que tienen muchas consultas cortos y rápidas ejecutar en paralelo. Además, cambiar el MDOP establecer a veces, se produce el plan de consulta puede cambiar, lo que conduce a bajo rendimiento de consultas o incluso interbloqueos con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consultas.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los procedimientos almacenados proporcionan las combinaciones correctas y sugerencias de bloqueo siempre que sea posible con el fin de tratar de impedir que el optimizador de consultas realiza mucho trabajo y cambiar el plan. Estos procedimientos almacenados proporcionan las ejecuciones de consulta coherente mediante la creación de las consultas de modo que el optimizador de consultas se saca la imagen tanto como sea posible.  
  
 Para obtener más información, vea el artículo de Microsoft Knowledge Base 899000, ["El valor de configuración de paralelismo para la instancia de SQL Server al configurar BizTalk Server"](http://go.microsoft.com/fwlink/?LinkId=153432) (http://go.microsoft.com/fwlink/?LinkId=153432).  
  
## <a name="sql-server-statistics-on-the-messagebox-database"></a>Estadísticas de SQL Server en la base de datos de cuadro de mensajes  
 Las siguientes opciones están desactivadas de forma predeterminada en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes cuando se crea:  
  
-   Creación automática de estadísticas  
  
-   Actualizar estadísticas automáticamente  
  
 No habilite estas opciones en las bases de datos de cuadro de mensajes. Habilitar la "crear estadísticas automáticamente" y "actualizará las estadísticas automáticamente" opciones pueden provocar retrasos de ejecución de consulta no deseables, especialmente en un entorno de alta carga.  
  
 Además, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los procedimientos almacenados tienen las combinaciones parciales y sugerencias de bloqueo especificadas en las consultas. Esto se hace para garantizar que el plan de consulta óptimo se utiliza la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consultas en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Se conocen las distribuciones y los resultados esperados para las consultas; se conoce el número aproximado de filas devueltas. Por lo general no son necesarias las estadísticas.  
  
 Para obtener más información, vea los siguientes artículos de Microsoft Knowledge Base:  
  
-   **912262**:["la opción de estadísticas de actualización automática, la creación automática de opción de estadísticas y la configuración de paralelismo están desactivados en la instancia de base de datos SQL Server que hospeda la base de datos BizTalkMsgBoxDB de BizTalk Server"](http://go.microsoft.com/fwlink/?LinkId=153430) (http://go.microsoft.com/fwlink/?LinkId=153430).  
  
-   **917845**:["Experimentas bloqueo, deadlock condiciones u otros problemas SQL Server al intentar conectarse a la base de datos BizTalkMsgBoxDb de BizTalk Server"](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/?LinkId=153429).  
  
## <a name="changes-to-the-messagebox-database"></a>Cambios en la base de datos de cuadro de mensajes  
 La base de datos de cuadro de mensajes se debe tratar como código fuente de aplicación no de Microsoft. Es decir, debe no "ajustar" la base de datos de cuadro de mensajes a través de los cambios en tablas, índices, procedimientos almacenados y la mayoría configuración de base de datos de SQL Server. Para obtener más información, en el blog del motor principal de BizTalk, consulte la entrada ["¿qué puede y no puede realizar con el servidor de base de datos de cuadro de mensajes"](http://go.microsoft.com/fwlink/?LinkId=101577) (http://go.microsoft.com/fwlink/?LinkId=101577).  
  
## <a name="default-settings-for-the-database-index-rebuilds-and-defragmentation"></a>Los valores predeterminados para los vuelve a generar el índice de base de datos y la desfragmentación  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]no se admite la desfragmentación de índices. "DBCC INDEXDEFRAG" y "ALTER INDEX... REORGANIZAR..." no se admiten puesto que utilizan la página de bloqueo, que puede causar bloqueos y los interbloqueos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]índice de base de datos de soporte técnico de modo vuelve a generar ("DBCC DBREINDEX" y "ALTER INDEX... REBUILD..."), pero solo deben realizarse durante las ventanas de mantenimiento cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no está procesando datos. Regeneraciones de índice al [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está procesando datos no se admiten.  
  
 Para obtener más información, vea el artículo de Microsoft Knowledge Base 917845 ["Experimentas bloqueo, deadlock condiciones u otros problemas SQL Server al intentar conectarse a la base de datos BizTalkMsgBoxDb de BizTalk Server"](http://go.microsoft.com/fwlink/?LinkId=153429) (http:// ¿go.Microsoft.com/fwlink/? LinkId = 153429).  
  
 Fragmentación del índice no es de un problema de rendimiento para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como se haría para un sistema DSS o un sistema OLTP que realiza exploraciones de índice. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]¿las consultas muy selectivas y las actualizaciones y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los procedimientos almacenados no deben suponer un tabla o recorridos de índice.  
  
 Para obtener más información acerca de los tipos de cargas de trabajo y fragmentación de índice, vea ["Microsoft SQL Server 2000 índice prácticas recomendadas de desfragmentación"](http://go.microsoft.com/fwlink/?LinkId=101580) (http://go.microsoft.com/fwlink/?LinkId=101580). Una oferta del artículo:  
  
 "Tal y como se muestra en la figura 1, hay pocas diferencias entre el rendimiento de los procedimientos almacenados antes y después de la desfragmentación. Dado que las consultas subyacentes emitidas por estos procedimientos almacenados se actúa sobre partes muy selectivas de los datos, rendimiento de cargas de trabajo no afecta negativamente afectado por índices fragmentados."  
  
> [!NOTE]  
>  El contenido del artículo también se aplica a [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] y [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configurar SQL Server](~/technical-guides/checklist-configuring-sql-server.md)