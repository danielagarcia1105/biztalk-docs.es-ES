---
title: Supervisar el rendimiento de SQL Server | Documentos de Microsoft
description: "Supervisar las bases de datos de BizTalk Server mediante herramientas de rendimiento, Monitor de actividad y la recopilación de datos"
ms.custom: 
ms.date: 11/29/2017
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
ms.openlocfilehash: 1e4f9db738298ec2a242350faae3ba5bc9da1c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="monitor-sql-server-performance"></a>Supervisar el rendimiento de SQL Server
SQL Server proporciona varias herramientas para supervisar los eventos de SQL Server y para optimizar el diseño físico de la base de datos. [Herramientas para la supervisión de rendimiento y optimización](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools) describe estas herramientas. 
  
BizTalk Server es un proceso intensivo de la base de datos. al solucionar problemas de rendimiento de BizTalk Server, puede ser beneficioso comprobar el rendimiento de SQL Server. Pueden ayudar las herramientas siguientes.  
  
## <a name="sql-server-activity-monitor"></a>Monitor de actividad SQL Server  
Monitor de actividad de SQL Server proporciona información acerca de los procesos de SQL Server y cómo estos procesos afectan a la instancia actual de SQL Server. Para obtener más información, consulte [Monitor de actividad](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), y [Cómo: abrir el Monitor de actividad (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio). 
  
## <a name="sql-serverdata-collection"></a>Colección de registrando ServerData SQL  
SQL Server proporciona un recopilador de datos que puede usar para obtener y guardar los datos recopilados de varios orígenes. El recopilador de datos permite usar contenedores de recopilación de datos, lo que permite determinar el ámbito y la frecuencia de recopilación de datos en un equipo que ejecuta SQL Server. Vea [la recopilación de datos](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento de la base de datos](../technical-guides/optimizing-database-performance.md)