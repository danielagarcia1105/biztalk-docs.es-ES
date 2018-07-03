---
title: Cómo definir agregaciones de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- aggregations [BAM], creating
- Excel add-in [BAM], security
- Excel add-in [BAM], creating aggregations
- managing [BAM], creating aggregations
ms.assetid: a5ef3a15-b1de-4099-8e94-64af4b5ec746
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57df4978f2b133794efd8fbdc99819bcedf144cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015909"
---
# <a name="how-to-define-bam-aggregations"></a>Cómo definir agregaciones de BAM
BAM admite dos tipos de agregación de datos:  
  
- Agregaciones de procesamiento analítico en línea (OLAP)  
  
- Agregaciones en tiempo real (ATR)  
  
  BAM usa Microsoft SQL Server Analysis para implementar agregaciones OLAP.  
  
  Debe configurar los desencadenadores de la base de datos de importación principal de BAM para definir las ATR.  
  
### <a name="to-define-olap-aggregations"></a>Para definir las agregaciones OLAP  
  
1.  En el libro de Excel de BAM, cree una vista, agregue al menos una dimensión y una medida al informe de tabla dinámica, desactive el botón ATR de la barra de herramientas y, por último, guarde el libro.  
  
    -   Para obtener información acerca de cómo abrir el libro BAM, crear una vista y agregar dimensiones y medidas, vea [definir una vista de BAM](../core/defining-a-bam-view.md).  
  
2.  Implemente el libro.  
  
    -   Para implementar el libro, siga las instrucciones de [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).  
  
3.  Un programador de soluciones utiliza el **DirectEventStream** clase para importar eventos a la base de datos de importación principal de BAM.  
  
    -   Para obtener información sobre la **DirectEventStream** de clases, vea [clase DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).  
  
4.  Ejecute el paquete de Servicios de transformación de datos (DTS) del cubo de actualización.  
  
    -   Para obtener información acerca de cómo ejecutar el paquete DTS del cubo de actualización, vea [paquetes DTS de BAM](../core/bam-dts-packages.md).  
  
5.  Abra la copia de datos activos más reciente del libro para ver las agregaciones OLAP.  
  
    > [!IMPORTANT]
    >  Por motivos de seguridad, BAM no elimina del libro las copias de datos activos existentes. En su lugar, BAM incrementa el nombre de archivo de la copia de datos activos.  
  
### <a name="to-define-the-rta"></a>Para definir la ATR  
  
1.  En el libro de Excel de BAM, cree una vista, agregue al menos una dimensión y una medida al informe de tabla dinámica, seleccione el botón ATR de la barra de herramientas y, a continuación, guarde el libro.  
  
    > [!WARNING]
    >  No defina varias ATR que usan la misma actividad de BAM . Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.  
  
    -   Para obtener información acerca de cómo abrir el libro BAM, crear una vista y agregar dimensiones y medidas, vea "Definir una vista de actividad económica" y "Definir agregaciones" en el *Guía de usuario de los trabajadores de información*.  
  
2.  Implemente el libro.  
  
    -   Para implementar el libro, siga las instrucciones de [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).  
  
3.  Un programador de soluciones utiliza el **DirectEventStream** clase para importar eventos a la base de datos de importación principal de BAM.  

  
4.  Abra la copia de datos activos más reciente del libro para ver las ATR.  
  
    > [!IMPORTANT]
    >  Por motivos de seguridad, BAM no elimina del libro las copias de datos activos existentes. En su lugar, BAM incrementa el nombre de archivo de la copia de datos activos.  
  
## <a name="see-also"></a>Vea también  
 [Paquetes DTS de BAM](../core/bam-dts-packages.md)   
 [Cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md)   
 [Actualización de OLAP y ATR propiedades de la cadena de conexión](../core/updating-olap-and-rta-connection-string-properties.md)   
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)