---
title: No se cambie la configuración de SQL Server | Microsoft Docs
description: Max Degree of Parallelism, de creación automática de estadísticas de actualización automática de estadísticas y volver a generar índices en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b383bfb-c3d9-47d4-b294-f6be94302734
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60479097dc9e56c2bc0c525d0de7d7a33afccaa5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978269"
---
# <a name="sql-server-settings-that-should-not-be-changed"></a>Configuración de SQL Server que no se debe cambiar
Al configurar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] durante los procedimientos de preparación operativa para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], no debe realizar cambios a la siguiente configuración.  
  
## <a name="sql-server-max-degree-of-parallelism"></a>Grado máximo de paralelismo de SQL Server  
 Max Degree de paralelismo (MDOP) se establece en "1" durante la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias que hospedan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes. Se trata de un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] configuración de nivel de instancia. Esta configuración no debe cambiarse el valor de "1". Cambio a algo distinto de "1" puede tener un efecto negativo importante en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procedimientos almacenados y rendimiento. Si se cambia la configuración de paralelismo para una instancia de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tendrá un efecto adverso en otras aplicaciones de base de datos que se ejecutan en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia, debe crear una instancia independiente de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] dedicados a hospedar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
 Las consultas en paralelo generalmente son más adecuadas para el procesamiento por lotes y las cargas de trabajo de decisión. Normalmente no son deseables en un entorno de procesamiento de transacciones donde haya muchas consultas cortas y rápidas que se ejecutan en paralelo. Además, cambiar la configuración a veces hace que el plan de consulta va a cambiar, de MDOP que conduce a bajo rendimiento de consultas o incluso interbloqueos con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las consultas.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procedimientos almacenados proporcionan las combinaciones correctas y las sugerencias de bloqueo siempre que sea posible para intentar evitar que el optimizador de consultas hace mucho trabajo y cambiar el plan. Estos procedimientos almacenados proporcionan las ejecuciones de consulta coherente mediante la creación de las consultas de modo que el optimizador de consultas se saca de la imagen tanto como sea posible.  
  
 Para obtener más información, consulte [899000 KB: configuración de paralelismo para la instancia de SQL Server usado por BizTalk Server](https://support.microsoft.com/help/899000/the-parallelism-setting-for-the-instance-of-sql-server-when-you-config).  
  
## <a name="sql-server-statistics-on-the-messagebox-database"></a>Estadísticas de SQL Server en la base de datos de cuadro de mensajes  
 Las siguientes opciones están desactivadas de forma predeterminada en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes cuando se crea:  
  
- Crear estadísticas automáticamente  
  
- Actualizar estadísticas automáticamente  
  
  No habilite estas opciones en las bases de datos de cuadro de mensajes. Habilitación de la "crear estadísticas automáticamente" y "auto update statistics" opciones pueden provocar retrasos de ejecución de consulta no deseados, especialmente en un entorno high-load.  
  
  Además, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los procedimientos almacenados tienen las combinaciones exactas y sugerencias de bloqueo especificadas en las consultas. Esto se hace para garantizar que el plan de consulta óptimo se usa por la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consultas en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Las distribuciones y los resultados esperados para las consultas se conocen; se conoce el número aproximado de filas devueltas. Por lo general no son necesarias las estadísticas.  
  
  Para obtener más información, vea los siguientes artículos de Microsoft Knowledge Base:  
  
- **912262**:["las opciones Actualizar estadísticas, la creación automática de opción de estadísticas y la configuración de paralelismo se ha desactivado en la instancia de base de datos SQL Server que hospeda la base de datos BizTalkMsgBoxDB de BizTalk Server"](https://support.microsoft.com/help/912262/the-auto-update-statistics-option-the-auto-create-statistics-option-an) .  
  
- **917845**:["experimenta el bloqueo, condiciones, u otros problemas SQL Server de interbloqueo al intentar conectarse a la base de datos BizTalkMsgBoxDb de BizTalk Server"](https://support.microsoft.com/help/917845/you-experience-blocking--deadlock-conditions--or-other-sql-server-issu).  
  
## <a name="changes-to-the-messagebox-database"></a>Cambios realizados en la base de datos de cuadro de mensajes  
 La base de datos de cuadro de mensajes se debe tratar como código fuente de aplicación que no sean de Microsoft. Es decir, se debe no introducir algunos "retoques" la base de datos de cuadro de mensajes a través de los cambios realizados en tablas, índices, procedimientos almacenados y la mayoría configuración de base de datos de SQL Server. Para obtener más información, en el blog del motor principal de BizTalk, consulte [qué puede y no se puede hacer con el servidor de base de datos de cuadro de mensajes](http://go.microsoft.com/fwlink/p/?LinkId=101577).  
  
## <a name="default-settings-for-the-database-index-rebuilds-and-defragmentation"></a>Los valores predeterminados para las recompilaciones de índice de base de datos y la desfragmentación  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no admite la desfragmentación de índices. "DBCC INDEXDEFRAG" y "ALTER INDEX... REORGANIZAR..." no se admiten ya que utilizan la página de bloqueo, que puede causar bloqueos e interbloqueos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] índice de base de datos de soporte técnico hace vuelve a generar ("DBCC DBREINDEX" y "ALTER INDEX... REBUILD..."), pero solo deben realizarse durante ventanas de mantenimiento cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no está procesando datos. Recompilaciones de índices mientras [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está procesando datos no se admiten.  
  
 Para obtener más información, consulte [917845 KB: experiencia de bloqueo, condiciones, u otros problemas de SQL Server de interbloqueo al intentar conectarse a la base de datos BizTalkMsgBoxDb de BizTalk Server "](https://support.microsoft.com/help/917845/you-experience-blocking--deadlock-conditions--or-other-sql-server-issu).  
  
 Fragmentación del índice no es parte de un problema de rendimiento para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como se haría para un sistema DSS o un sistema OLTP que realiza exploraciones de índice. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza consultas muy selectivas y las actualizaciones y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procedimientos almacenados no deberían causar la tabla o índice examina.  
  
 
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: configuración de SQL Server](~/technical-guides/checklist-configuring-sql-server.md)
