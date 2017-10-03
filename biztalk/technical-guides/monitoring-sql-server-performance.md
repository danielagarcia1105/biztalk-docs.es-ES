---
title: "Supervisión del rendimiento de SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5abdc3054576e03f28967017767112cea652f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-performance"></a>Supervisión del rendimiento de SQL Server
[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]proporciona varias herramientas para supervisar los eventos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y para optimizar el diseño físico de la base de datos. Estas herramientas se describen en el tema [herramientas para la supervisión de rendimiento y optimización](http://go.microsoft.com/fwlink/?LinkId=146357) (http://go.microsoft.com/fwlink/?LinkId=146357) en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla. Información sobre herramientas específicas que se usan para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] a continuación se proporciona supervisión y optimización del rendimiento.  
  
## <a name="sql-server-performance-monitoring-tools"></a>Herramientas de supervisión de rendimiento de SQL Server  
 Dado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es tal un proceso intensivo de la base de datos, a menudo resulta útil echar un vistazo a lo que ocurre en SQL Server cuando solucione problemas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] problemas de rendimiento. El resto de este tema describe las herramientas disponibles para revisar los datos archivados y en tiempo real en de supervisión de rendimiento [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)].  
  
### <a name="sql-server-2008-r2-activity-monitor"></a>Monitor de actividad SQL Server 2008 R2  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Monitor de actividad proporciona información acerca de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] procesos y cómo estos procesos afectan a la instancia actual de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Para obtener más información acerca de [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Monitor de actividad, vea [Monitor de actividad](http://go.microsoft.com/fwlink/?LinkId=146355) (http://go.microsoft.com/fwlink/?LinkId=146355) en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla. Para obtener información acerca de cómo abrir el Monitor de actividad de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio, consulte [Cómo: abrir el Monitor de actividad (SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094) en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.  
  
### <a name="sql-server-2008-r2-data-collection"></a>Recopilación de datos SQL Server 2008 R2  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] proporciona un recopilador de datos que puede utilizar para obtener y guardar datos recopilados de varios orígenes. El recopilador de datos permite usar contenedores de recopilación de datos, que permiten determinar el ámbito y la frecuencia de recopilación de datos en un equipo que está ejecutando [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]. Para obtener más información acerca de cómo implementar [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] recopilación de datos, vea [la recopilación de datos](http://go.microsoft.com/fwlink/?LinkId=146356) (http://go.microsoft.com/fwlink/?LinkId=146356) en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de la base de datos](../technical-guides/optimizing-database-performance.md)