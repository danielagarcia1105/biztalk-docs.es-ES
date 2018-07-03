---
title: Administrar la infraestructura dinámica de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, managing [BAM]
- managing [BAM], infrastructure
ms.assetid: af8a76b5-407a-484d-aff4-0d911f88313e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 861390d71c7cd16815ae7f3d446e956f0ae3bb74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004709"
---
# <a name="managing-the-bam-dynamic-infrastructure"></a>Administrar la infraestructura dinámica de BAM
Las características de Supervisión de la actividad económica (BAM) utilizan una infraestructura de generación dinámica de SQL y de procesamiento analítico en línea (OLAP). Los administradores usan la utilidad de administración de BAM para implementar el libro de definiciones de BAM o archivo XML, que se encargará de desarrollar el analista de negocios.  
  
 La infraestructura dinámica de BAM consiste en vistas de libro de BAM, implementaciones de BAM, paquetes de Servicios de transformación de datos (DTS) de BAM y bases de datos de BAM. Para obtener más información acerca de la infraestructura dinámica de BAM, consulte [infraestructura dinámica de BAM](../core/bam-dynamic-infrastructure.md).  
  
 BizTalk Server crea las siguientes bases de datos BAM al configurar BizTalk Server:  
  
- Base de datos de importación principal de BAM BAMPrimaryImport  
  
- Base de datos de esquema de estrella BAMStarSchema (opcional)  
  
- Base de datos de análisis de BAM BAMAnalysis (opcional)  
  
- Base de datos de archivo de BAM (BAMArchive)  
  
  Para obtener información acerca de las bases de datos BAM, consulte [administrar bases de datos de BAM](../core/managing-bam-databases.md).  
  
  En esta sección se describen las tareas que llevan a cabo los administradores para la administración de la infraestructura de BAM:  
  
- Implementar y anular la implementación de definiciones y vistas de BAM  
  
- Administrar el acceso de los usuarios a las vistas de BAM  
  
- Ejecutar los paquetes DTS de BAM  
  
- Realizar copias de seguridad de las bases de datos de BAM  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Administración de definiciones de BAM](../core/managing-bam-definitions.md)
  
-   [Administración de la seguridad de BAM](../core/managing-bam-security.md)  
  
-   [Administración de agregaciones](../core/managing-aggregations.md) 
  
-   [Administración de bases de datos de BAM](../core/managing-bam-databases.md)
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)