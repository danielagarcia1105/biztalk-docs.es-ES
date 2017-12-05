---
title: "Archivos de configuración de servicios de Script de línea de comandos de BAM para la notificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b22607193ed7c345388a6435e2d58c16b8986370
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a>Secuencia de comandos de línea de comandos de BAM para archivos de configuración de servicios de notificación
Los administradores utilizan la secuencia de comandos ProcessBamNSFiles.vbs para personalizar el comportamiento de los servicios de notificación de SQL Server para alertas BAM. Puede utilizar la secuencia de comandos para obtener el archivo de definición de la aplicación (ADF) de servicios de notificación y el archivo de configuración de servicios de notificación. Estos archivos se pueden modificar y, a continuación, se puede utilizar la secuencia de comandos para aplicar los cambios.  
  
 La secuencia de comandos se ejecuta desde un símbolo del sistema de servicios de notificación y no desde un símbolo de sistema común. Si se ejecuta la secuencia de comandos desde un símbolo de sistema común, la secuencia de comandos se ejecutará incorrectamente. Cuando se ejecuta la secuencia de comandos, todos los parámetros son obligatorios.  
  
## <a name="get-command"></a>Get (comando)  
 **Uso**  
  
 **cscript ProcessBamNSFiles-Get \<ruta de acceso de archivo de configuración\> \<ruta del archivo ADF\>\<servidor de importación principal\> \<base de datos de importación principal  \>**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|ruta del archivo de configuración|Especifica el nombre y la ubicación en la que se va a almacenar el archivo de configuración.|  
|ruta del archivo ADF|Especifica el nombre y la ubicación en la que se va a almacenar el archivo ADF.|  
|servidor de importación principal|Nombre del equipo en el que se almacena la base de datos de importación principal de BAM.|  
|base de datos de importación principal|Nombre de la base de datos de importación principal de BAM.|  
  
 Recupera los archivos de definición de la aplicación y de configuración de servicios de notificación de la base de datos de importación principal de BAM y los guarda en las rutas especificadas.  
  
## <a name="update-command"></a>Update (comando)  
 **Uso**  
  
 **cscript ProcessBamNSFiles-Update \<configfilepath\> \<adffilepath\>\<primaryimport server\> \<base de datos de importación principal  \>**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|ruta del archivo de configuración|Especifica el nombre y la ubicación desde la que se va a actualizar la información de configuración de servicios de notificación.|  
|ruta del archivo ADF|Especifica el nombre y la ubicación desde la que se va a actualizar la información de ADF.|  
|servidor de importación principal|Nombre del equipo en el que se almacena la base de datos de importación principal de BAM.|  
|base de datos de importación principal|Nombre de la base de datos de importación principal de BAM.|  
  
 Llama a servicios de notificación y actualiza la configuración con la información de los archivos especificados. Los archivos ADF y los de configuración se almacenan en la base de datos de importación principal de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas de línea de comandos de BAM](../core/bam-command-line-tools.md)