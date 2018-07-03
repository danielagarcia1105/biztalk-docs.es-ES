---
title: Los paquetes DTS de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e49741a0fce6fd69e4e2ba5d8bb8dbd1956a0e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015853"
---
# <a name="bam-dts-packages"></a>Paquetes DTS de BAM
Un administrador puede actualizar parámetros para los siguientes paquetes DTS de BAM:  
  
- El **CubeUpdate** siempre se encuentra el paquete de servicios de transformación de datos (DTS) en el mismo servidor que la base de datos de esquema de estrella.  
  
- El **DataMaintenance** siempre se encuentra el paquete DTS en el mismo servidor que la base de datos de importación principal.  
  
  Los paquetes DTS utilizan los siguientes parámetros en el archivo BAMConfiguration.xml.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|ConnectionTimeOut|El valor de tiempo de espera (en segundos) de la conexión DTS es un entero. Si omite el parámetro ConnectionTimeOut, el archivo de configuración utilizará 60 segundos (el valor predeterminado).|  
|Cifrado|De forma predeterminada, los paquetes DTS no cifran los datos mientras los transforman (el valor Encryption es 0). Defina Encryption como 1 para cifrar los datos durante la transformación.|  
|OwnerPassword|Es la contraseña del propietario del paquete DTS. Los propietarios de paquetes DTS pueden abrir y modificar paquetes DTS. Para obtener información acerca de los propietarios de paquete DTS, consulte Libros en pantalla de SQL Server.|  
|UserPassword|Es la contraseña del usuario DTS. Los usuarios de paquetes DTS pueden ejecutar paquetes DTS. Para obtener información acerca de los usuarios de paquetes DTS, consulte Libros en pantalla de SQL Server.|  
  
 Los paquetes DTS utilizan las siguientes convenciones de nomenclatura en el archivo BAMConfiguration.xml.  
  
- **CubeUpdate** paquete DTS  
  
   **bam_AN_\<**  ***CubeName* \>**, donde CubeName es el nombre del cubo. El libro de trabajo de BAM genera el nombre de cubo a partir del nombre de vista. Si modifica el nombre del cubo en el documento XML de configuración de BAM, el nuevo nombre del cubo se usa en el nombre del paquete DTS.  
  
- **DataMaintenance** paquete DTS  
  
   **bam_DM_\<**  ***ActivityName* \>**, donde ActivityName es el nombre de la actividad.  
  
  El paquete DTS CubeUpdate se utiliza para añadir la agregación programada. En la sección siguiente, podrá especificar el período de tiempo para agregación de datos en tiempo real.  
  
## <a name="see-also"></a>Vea también  
 [Esquema de configuración de BAM](../core/bam-configuration-schema.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Administración de BAM](../core/managing-bam.md)