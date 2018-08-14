---
title: Supervisar el rendimiento de SQL Server | Microsoft Docs
description: Supervisar las bases de datos de BizTalk Server mediante herramientas de rendimiento, Monitor de actividad y recopilación de datos
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 730896dc1cf0a465f68965f812da7311dd8664ab
ms.sourcegitcommit: ed9590dbcd97c12a1fe5ce2cdf8d826492cccdff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "39640120"
---
# <a name="monitor-sql-server-performance"></a>Supervisar el rendimiento de SQL Server
SQL Server proporciona varias herramientas para supervisar los eventos de SQL Server y para optimizar el diseño físico de la base de datos. [Herramientas para la supervisión de rendimiento y optimización](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools) describe estas herramientas. 
  
BizTalk Server es un proceso intensivo de la base de datos. al solucionar problemas de rendimiento de BizTalk Server, puede ser beneficioso comprobar también el rendimiento de SQL Server. Pueden ayudar las siguientes herramientas.  
  
## <a name="sql-server-activity-monitor"></a>Monitor de actividad SQL Server  
Monitor de actividad de SQL Server proporciona información sobre los procesos de SQL Server y cómo estos afectan a la instancia actual de SQL Server. Para obtener más información, consulte [Monitor de actividad](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), y [Cómo: abrir el Monitor de actividad (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio). 
  
## <a name="sql-serverdata-collection"></a>Colección de ServerData SQL  
SQL Server proporciona un recopilador de datos que puede usar para obtener y guardar datos recopilados de varios orígenes. El recopilador de datos permite usar contenedores de recopilación de datos, lo que le permite determinar el ámbito y la frecuencia de recopilación de datos en un equipo que ejecuta SQL Server. Consulte [la recopilación de datos](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento de la base de datos](../technical-guides/optimizing-database-performance.md)
