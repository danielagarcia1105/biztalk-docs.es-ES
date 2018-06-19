---
title: Definir el período de tiempo y las propiedades del período de tiempo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- managing [BAM], real-time data
- Primary Import database [BAM], time properties
- aggregations [BAM], managing
- Primary Import database [BAM], real-time data
- BAMConfiguration.xml file
- aggregations [BAM], real-time data
ms.assetid: 7f07b179-da10-4702-baf7-69516c8f16a6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d846b03866196e0a31facbbff68db50ec6a00a5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239060"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a>Definir las propiedades del período de tiempo y de la ventana de tiempo
Los administradores utilizan las propiedades TimeWindow y TimeSlice en el archivo BAMConfiguration.xml para determinar la actividad de los datos de las tablas de agregación en tiempo real de la base de datos de importación principal de BAM.  
  
> [!NOTE]
>  Para aprobar los cambios realizados en el archivo de configuración de BAM, los administradores deberán anular la implementación de la configuración de BAM actual, y después implementar el archivo BAMConfiguration.xml actualizado.  
  
 Para obtener información acerca de cómo anular la implementación de una definición de BAM, consulte [cómo quitar definiciones de BAM](../core/how-to-remove-bam-definitions.md). Para obtener información acerca de cómo implementar una definición de BAM, consulte [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).  
  
 Si desea cambiar los valores TimeWindow y TimeSlice sin anular la implementación de la infraestructura de BAM, modifique las columnas de la tabla BAM_Metadata_Activities en la base de datos de importación principal.  
  
## <a name="timeslice"></a>TimeSlice  
 La propiedad TimeSlice se utiliza para agrupar datos de instancias completas de BAM. La propiedad TimeSlice utiliza el tiempo en el que se escriben los datos como datos de la instancia del grupo de BAM en la base de datos de importación principal de BAM.  
  
 Por ejemplo, la instancia A se haya completado y se mantiene en la base de datos de importación principal de BAM en 1/1/2000 1:02 a.m. La instancia B se haya completado y se mantiene en la base de datos de importación principal de BAM en 1/1/2000 1:04 a.m. Si establece el valor de la propiedad TimeSlice en cinco minutos, la instancia A y B de la instancia se agrupan juntos.  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a>Para cambiar el valor TimeSlice en el archivo de configuración de BAM  
  
-   Cambie el valor en esta línea del archivo de configuración de BAM:  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a>Para cambiar el valor TimeSlice en la tabla BAM_Metadata_Activities  
  
-   Modifique los valores RTATimeSlic que se encuentran en la tabla bam_Metadata_Activities de la base de datos BAMPrimaryImport. Si implementa varias agregaciones en tiempo real (ATR) para una o más actividades, puede especificar una ventana de tiempo diferente para cada ATR.  
  
    > [!NOTE]
    >  El valor de la ventana ATR debe ser un número entero, mientras que la unidad de tiempo siempre son minutos.  
  
## <a name="timewindow"></a>TimeWindow  
 Cuando ejecuta el paquete DTS de CubeUpdate, el paquete transporta datos desde la base de datos de importación principal de BAM a los cubos de BAM. El paquete transporta datos de agregación en tiempo real como instancias de datos de BAM siempre que todos los datos del grupo tengan una antigüedad superior a la determinada en la propiedad de la ventana ATR.  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a>Para cambiar el valor TimeWindow en el archivo de configuración de BAM  
  
-   Cambie el valor en esta línea del archivo de configuración de BAM:  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a>Para cambiar el valor TimeWindow en la tabla BAM_Metadata_Activities  
  
-   Modifique los valores RTAWindow que se encuentran en la tabla bam_Metadata_Activities de la base de datos BAMPrimaryImport. Si implementa varias agregaciones en tiempo real (ATR) para una o más actividades, puede especificar una ventana de tiempo diferente para cada ATR.  
  
    > [!NOTE]
    >  El valor de la ventana ATR debe ser un número entero, mientras que la unidad de tiempo siempre son minutos.  
  
## <a name="see-also"></a>Vea también  
 [Esquema de configuración de BAM](../core/bam-configuration-schema.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)