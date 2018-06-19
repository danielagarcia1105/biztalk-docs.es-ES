---
title: Ejemplos de adaptadores de Oracle EBS | Documentos de Microsoft
description: Ejemplos de adaptadores de WCF de Enterprise Business Suite de Oracle que pueden usarse con BizTalk Server, el modelo de servicio WCF y el modelo del canal WCF
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12f19f13-3b01-40d6-b12c-811f99841040
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4069b7f5916291544ce76534e04b20af5680d69
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015347"
---
# <a name="samples-for-the-oracle-ebs-adapter"></a>Ejemplos para el adaptador de Oracle EBS
Ejemplos de [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] se clasifican en categorías:  
  
-   Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
-   Ejemplos de modelo de servicio WCF  
  
-   Ejemplos de modelo de canal WCF  
  
-   Ejemplos de Microsoft Office SharePoint Server  
  
 Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos de adaptadores de Oracle E-Business Suite](https://www.microsoft.com/download/details.aspx?id=6464). Las secuencias de comandos SQL para crear las tablas de interfaz, programas simultáneos, tablas y los paquetes que se utiliza en los ejemplos se incluyen. 
  
> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 En la lista siguiente describe los ejemplos. 
  
## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|InterfaceTableInsert|Muestra cómo insertar registros en una tabla de interfaz en Oracle E-Business Suite utilizando [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
|ConcurrentProgram|Muestra cómo invocar un programa simultáneo en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
|RequestSet|Muestra cómo invocar una solicitud establecida en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
|MsgContextProperty|Muestra cómo utilizar las propiedades de contexto de mensaje expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para establecer el contexto de la aplicación para realizar operaciones en artefactos en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
|OracleEBS_CompositeOperation|Muestra cómo realizar operaciones compuestas en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
|OracleNotifyIncremental|Muestra cómo recibir mensajes de notificación de consulta "incremental" de Oracle utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
|PollingUsingSelectStatement|Muestra cómo configurar una consulta de sondeo con una instrucción SELECT y recibir los resultados utilizando la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
|PollingUsingStoredProc|Muestra cómo configurar una consulta de sondeo con un procedimiento almacenado y recibir los resultados utilizando la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].|  
  
## <a name="wcf-service-model-sasamplesmples"></a>Modelo de servicio de WCF Sasamplesmples  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|ConcProgram_ServiceModel|Muestra cómo invocar programas simultáneos en Oracle E-Business Suite mediante el adaptador.|  
|ExecuteReader|Muestra cómo invocar una operación ExecuteReader en Oracle E-Business Suite mediante el adaptador.|  
|Interface_Table_Ops|Muestra cómo realizar operaciones en tablas de interfaz en Oracle E-Business Suite mediante el adaptador.|  
|LargeDataTypes_ServiceModel|Muestra cómo realizar operaciones en tablas con columnas de tipos de datos de gran tamaño en Oracle E-Business Suite mediante el adaptador.|  
|Notification_ServiceModel|Muestra cómo recibir notificaciones de las bases de datos subyacente mediante el adaptador de Oracle E-Business Suite.|  
|SelectPolling_ServiceModel|Muestra cómo utilizar una instrucción SELECT para sondear una tabla de interfaz en Oracle E-Business Suite mediante el adaptador.|  
|StoredProcPolling_ServiceModel|Muestra cómo utilizar un procedimiento almacenado de sondeo de tablas de Oracle E-Business Suite mediante el adaptador.|  
  
## <a name="wcf-channel-model-samples"></a>Ejemplos de modelo de canal de WCF  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|InsertOperation|Muestra cómo realizar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el adaptador.|  
|SelectPolling_ChannelModel|Muestra cómo utilizar una instrucción SELECT para sondear una tabla de interfaz en Oracle E-Business Suite mediante el adaptador.|  
  
## <a name="microsoft-office-sharepoint-server-samples"></a>Ejemplos de Microsoft Office SharePoint Server  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|MOSS_Sample|Muestra cómo utilizar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para crear un servicio de Windows Communication Foundation (WCF) a partir de artefactos de Oracle E-Business Suite y, a continuación, usar el servicio WCF para mostrar datos en Microsoft Office SharePoint Server con un elemento Web de lista de datos de negocio.|  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)