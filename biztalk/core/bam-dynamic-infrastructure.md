---
title: Infraestructura dinámica de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, BAM
- BAM, infrastructure
ms.assetid: 88f39438-3213-4f0d-8b8d-e6426c266138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3660eeb6f85fb21ff78b7b833b21adbb3af87385
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230452"
---
# <a name="bam-dynamic-infrastructure"></a>Infraestructura dinámica de BAM
La infraestructura de BAM consta de tablas de SQL Server, vistas de BAM, procedimientos almacenados y paquetes de servicios de transformación de datos (DTS) en las bases de datos BAM (importación principal, archivo, esquema de estrella y análisis) como configurado y administrado mediante incremental implementaciones de definiciones de BAM. La infraestructura es donde, en tiempo de ejecución eventos se correlacionan, agregan y, a continuación, están disponibles para consultar los usuarios.  
  
 En esta sección se describen algunos de estos procesos de infraestructura. Por ejemplo, una vez que extraiga los datos de interés de sus aplicaciones (la definición de BAM), los puede almacenar para que estén disponibles para consultas. Asimismo, puede mantener ciertas agregaciones creadas previamente de los datos para realizar consultas agregadas más rápidamente.  
  
 Normalmente, dicha funcionalidad se logra mediante un gran esfuerzo de desarrollo para implementar un almacén de datos. Sin embargo, BAM en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] simplifica este proceso en gran medida al generar de forma automática la infraestructura de SQL y OLAP basada en sus definiciones de actividad y vista.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Qué es una definición de BAM?](../core/what-is-a-bam-definition.md)  
  
-   [¿Qué es un esquema de definición de BAM?](../core/what-is-a-bam-definition-schema.md)  
  
-   [Almacenamiento de datos de actividad](../core/activity-data-storage.md)  
  
-   [¿Qué es una agregación?](../core/what-is-an-aggregation.md)  
  
-   [Consultar datos de BAM](../core/querying-bam-data.md)  
  
-   [Limitaciones de la infraestructura BAM](../core/bam-infrastructure-limitations.md)  
  
-   [Cómo definir alertas fuera de intervalo numérico dimensión en instalaciones que no sean en inglés](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)