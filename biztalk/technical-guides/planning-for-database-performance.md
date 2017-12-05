---
title: Planear el rendimiento de la base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 11/29/2017
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
ms.openlocfilehash: 878320cf7c6a5762626087964033430afcf611cf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-database-performance"></a>Planear el rendimiento de la base de datos de

## <a name="overview"></a>Información general
Microsoft BizTalk Server es una muy base de datos intensivas aplicación que requieran la creación de hasta 13 bases de datos independientes en Microsoft SQL Server. Dada la naturaleza de uso intensivo de base de datos de BizTalk Server, resulta de importancia crítica que elija la versión adecuada y la edición de SQL Server que alojará las bases de datos de BizTalk Server. Para optimizar el rendimiento de los equipos que ejecutan SQL Server que alojan las bases de datos de BizTalk Server, siga las recomendaciones de este tema y en el [optimización de base de datos de BizTalk Server](optimizing-database-performance.md).
  

> [!NOTE]  
>  Aunque esta guía está escrita para otras versiones de BizTalk Server y SQL Server, probablemente pueda utilizar las mismas recomendaciones para las versiones más recientes.
  
## <a name="considerations-for-sql-server-editions"></a>Consideraciones para las ediciones de SQL Server  
 Las bases de datos de BizTalk Server deben configurarse para ejecutarse en una instancia dedicada de SQL Server siempre que sea posible. BizTalk Server es una aplicación de uso intensivo de bases de datos, así separación de los equipos de BizTalk Server y los equipos de SQL Server que alojan las bases de datos de BizTalk Server mejorarán el rendimiento y deben considerarse una práctica recomendada en un servidor BizTalk Server de producción entorno.  
  
 Distintas ediciones de SQL Server proporcionan características diferentes que pueden afectar al rendimiento de su entorno de BizTalk Server. Por ejemplo, en condiciones de carga elevada, puede ser supera el número de bloqueos disponibles de la base de datos que están disponibles para la versión de 32 bits de SQL Server, que es negativo en el rendimiento de la solución de BizTalk. Considere la posibilidad de alojamiento de la base de datos de cuadro de mensajes en una versión de 64 bits de SQL Server si se producen errores de "sin bloqueo" en el entorno de prueba. El número de bloqueos disponible es significativamente superior en la versión de 64 bits de SQL Server.  
  
 Tenga en cuenta la tabla siguiente al decidir el motor de base de datos características que necesitará para el entorno de BizTalk. Para las soluciones a pequeña escala, por ejemplo cuando ejecuta la edición para sucursales de BizTalk Server, SQL Server Workgroup Edition puede ser adecuada para albergar las bases de datos de BizTalk Server. Para gran escala, soluciones de nivel de empresa que requieren la agrupación en clústeres de soporte técnico, BizTalk registro envío compatibilidad ni la compatibilidad de Analysis Services, a continuación, se necesita SQL Server Enterprise Edition para hospedar las bases de datos.  
  
|Edición de SQL Server|Compatibilidad con 64 bits|Compatibilidad con varias instancias|Compatibilidad con clústeres|Analysis Services|  
|---|---|---|---|---|  
|SQL Server Enterprise Edition|Sí|Sí|Sí|Sí|  
|SQL Server Standard Edition|Sí|Sí|Sí (2 nodos)|Sí|  
|SQL Server Workgroup Edition|Sí|Sí|No|No|  
  
> [!NOTE]  
>  ATR de BAM requiere SQL Server Enterprise Edition.  
  
 Para obtener una lista completa de las características admitidas por las ediciones, vea [características compatibles con las ediciones de SQL Server](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016).