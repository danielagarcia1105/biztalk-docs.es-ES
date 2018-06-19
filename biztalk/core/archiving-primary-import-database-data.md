---
title: Archivar los datos de la base de datos de importación principal | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0fdfd55681fabd1b6cfc72f68b7e33150a121f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230420"
---
# <a name="archiving-primary-import-database-data"></a>Archivar datos de la base de datos de importación principal
Un administrador puede determinar la ventana de tiempo que se va a utilizar para archivar los datos de instancia de actividad en la base de datos de importación principal. Se utilizan las propiedades OnlineWindowTimeUnit y OnlineWindowTimeLength de la tabla BAM_Metadata_Activities en la base de datos BAMPrimaryImport.  
  
 Si los usuarios empresariales han implementado varias actividades, puede determinar una ventana de tiempo diferente para cada actividad. Para obtener información acerca de cómo implementar actividades, vea "Definir una actividad de negocio" en *Guía de usuario para trabajadores de información*.  
  
 En la tabla siguiente se describen los valores que puede utilizar para OnlineWindowTimeUnit y OnlineWindowTimeLength.  
  
|Propiedad|Valor|  
|--------------|-----------|  
|OnlineWindowTimeUnit|Esta propiedad puede ser: mes, día, hora o minuto. El valor predeterminado de esta propiedad es mes.|  
|OnlineWindowTimeLength|Esta propiedad debe ser un entero. El valor predeterminado de esta propiedad es 6.|  
  
 BAM extrae datos de la base de datos de importación principal mediante partición, cuando la partición es más antigua que la ventana en línea (hora actual – OnlineWindowTimeLength de OnlineWindowTimeUnit). Por ejemplo, se quitan las particiones anteriores a 5 días para OnlineWindowTimeLength = 5 y OnlineWindowTimeUnit = día.  
  
 BAM mueve datos de instancia de actividad a la base de datos de archivo de BAM. Durante la configuración de BAM para BizTalk se determina la base de datos de archivo de BAM. Para obtener información acerca de la configuración de BAM de BizTalk, consulte [esquema de configuración de BAM](../core/bam-configuration-schema.md).  
  
 BAM no archivará los datos de la instancia de actividad si no se ejecuta el paquete de Servicios de transformación de datos (DTS) de la actualización de cubos de BAM, que procesa los datos de la instancia en el cubo de actividad.  
  
 Para obtener información acerca de cómo ejecutar el paquete DTS de mantenimiento de datos BAM, consulte [paquetes DTS de SAE](../core/bam-dts-packages.md).  
  
 Con el tiempo, la base de datos BAMArchive aumenta de tamaño según se vayan agregando datos de instancia de actividad. Aunque no hay ningún modo sencillo de truncar una base de datos completa, puede truncar periódicamente el registro de transacciones de la base de datos para reducir los requisitos de almacenamiento y realizar una copia de seguridad periódica y archivar toda la base de datos BAMArchive. Vea “Truncar el registro de transacciones” en los Libros en pantalla de SQL Server para obtener más información.  
  
## <a name="see-also"></a>Vea también  
 [Definir el período de tiempo y las propiedades del período de tiempo](../core/defining-the-time-window-and-time-slice-properties.md)   
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)