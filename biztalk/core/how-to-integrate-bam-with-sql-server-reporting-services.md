---
title: Cómo integrar BAM con SQL Server Reporting Services | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a55d0fa09267cc23d54533427da326e5028d3f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970258"
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a>Integración de BAM con SQL Server 2005 Reporting Services
La creación de un informe basado en datos en la infraestructura de BAM emplea las tareas habituales asociadas a la creación de un informe para cualquier otro origen de datos de SQL Server. Para obtener más información acerca de cómo crear un informe con el Diseñador de informes, consulte [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe disponer de los permisos para obtener acceso a los datos necesarios para crear el informe.  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a>Cómo crear un informe en BAM mediante SQL Server Reporting Service  
  
1.  Seleccione el origen de datos desde el que se creará el informe.  
  
     BAM proporciona dos orígenes de datos que Reporting Services puede seleccionar.  
  
    |Origen de datos|Description|  
    |-----------------|-----------------|  
    |Base de datos de importación principal de BAM|Contiene vistas sobre instancias de actividad y agregaciones en tiempo real. Seleccione el tipo = "Microsoft SQL Server" y Connection String = "origen de datos =\<*nombre del servidor*\>; Catálogo inicial =\<*nombre de base de datos*\>", donde \< *nombre del servidor* \> y \< *base de datos nombre* \> son los nombres de servidor y base de datos de la base de datos de importación principal de Bam.|  
    |Base de datos de análisis de BAM|Contiene datos utilizados para consultar el cubo de análisis. Seleccione el tipo = "Microsoft SQL Server Analysis Server" y Connection String = "origen de datos =\<*nombre del servidor*\>; Catálogo inicial =\<*nombre de base de datos*\>", donde \< *nombre del servidor* \> y \< *base de datos nombre* \> son los nombres de servidor y base de datos de la base de datos de análisis de BAM.|  
  
2.  Diseñe la consulta. En el caso de la base de datos de importación principal de BAM, existen dos tipos de vistas:  
  
    |Nombre de vista|Description|  
    |---------------|-----------------|  
    |dbo.bam_\<*nombre de la vista*\>_\<*nombre de la actividad*\>View_View.|Esta vista contiene datos de la instancia.|  
    |dbo.bam_\<*nombre de la vista*\>_\<*nombre de tabla de dinámica de agregación en tiempo real*\>_RTAView|Esta vista contiene datos utilizados en las agregaciones en tiempo real.|  
  
    > [!NOTE]
    >  Puede escribir **seleccione \* de vista** devolver el resultado deseado establecido. Para la base de datos de análisis de BAM, haga clic en el generador de consultas y arrastre las dimensiones y medidas del cubo denominado \< *nombre de la vista* \> devolver el resultado deseado establecido.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Complete los pasos del Asistente para informes con el fin de especificar qué datos va a presentar y el modo de presentación.  
  
## <a name="see-also"></a>Vea también  
 [Administración de bases de datos de BAM](../core/managing-bam-databases.md)