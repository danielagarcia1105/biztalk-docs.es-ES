---
title: Los paquetes DTS de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 105d1b42848b73505d9a82df07693111708ce802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-dts-packages"></a>Paquetes DTS de BAM
Un administrador puede actualizar parámetros para los siguientes paquetes DTS de BAM:  
  
-   El **CubeUpdate** paquete de servicios de transformación de datos (DTS) siempre se encuentra en el mismo servidor que la base de datos de esquema de estrella.  
  
-   El **DataMaintenance** paquete DTS siempre se encuentra en el mismo servidor que la base de datos de importación principal.  
  
 Los paquetes DTS utilizan los siguientes parámetros en el archivo BAMConfiguration.xml.  
  
|Parámetro|Description|  
|---------------|-----------------|  
|ConnectionTimeOut|El valor de tiempo de espera (en segundos) de la conexión DTS es un entero. Si omite el parámetro ConnectionTimeOut, el archivo de configuración utilizará 60 segundos (el valor predeterminado).|  
|Cifrado|De forma predeterminada, los paquetes DTS no cifran los datos mientras los transforman (el valor Encryption es 0). Defina Encryption como 1 para cifrar los datos durante la transformación.|  
|OwnerPassword|Es la contraseña del propietario del paquete DTS. Los propietarios de paquetes DTS pueden abrir y modificar paquetes DTS. Para obtener información acerca de los propietarios de paquete DTS, consulte Libros en pantalla de SQL Server.|  
|UserPassword|Es la contraseña del usuario DTS. Los usuarios de paquetes DTS pueden ejecutar paquetes DTS. Para obtener información acerca de los usuarios de paquetes DTS, consulte Libros en pantalla de SQL Server.|  
  
 Los paquetes DTS utilizan las siguientes convenciones de nomenclatura en el archivo BAMConfiguration.xml.  
  
-   **CubeUpdate** paquete DTS  
  
     **bam_AN_\<**   
     ***CubeName* >**, donde CubeName es el nombre del cubo. El libro de trabajo de BAM genera el nombre de cubo a partir del nombre de vista. Si modifica el nombre del cubo en el documento XML de configuración de BAM, el nuevo nombre del cubo se usa en el nombre del paquete DTS.  
  
-   **DataMaintenance** paquete DTS  
  
     **bam_DM_\<**   
     ***ActivityName* >**, donde ActivityName es el nombre de la actividad.  
  
 El paquete DTS CubeUpdate se utiliza para añadir la agregación programada. En la sección siguiente, podrá especificar el período de tiempo para agregación de datos en tiempo real.  
  
## <a name="see-also"></a>Vea también  
 [Esquema de configuración de BAM](../core/bam-configuration-schema.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Administración de BAM](../core/managing-bam.md)