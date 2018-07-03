---
title: Ejemplos del adaptador de Oracle EBS | Microsoft Docs
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
ms.openlocfilehash: a4fdffd6d24ce18c38c45a086ea0f6376241d21d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000893"
---
# <a name="samples-for-the-oracle-ebs-adapter"></a>Ejemplos para el adaptador de Oracle EBS
Ejemplos para [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] se clasifican en categorías:  
  
- Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
- Ejemplos de modelo de servicio WCF  
  
- Ejemplos de modelo de canal WCF  
  
- Ejemplos de Microsoft Office SharePoint Server  
  
  Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos del adaptador de Oracle E-Business Suite](https://www.microsoft.com/download/details.aspx?id=6464). Los scripts SQL para crear las tablas de interfaz, programas simultáneos, tablas y paquetes que se usan en los ejemplos se incluyen. 
  
> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 En la lista siguiente describe los ejemplos. 
  
## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server  
  
|    Nombre del directorio de ejemplo     |                                                                                                                                                                        Descripción                                                                                                                                                                        |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     InterfaceTableInsert     |                                                                                   Muestra cómo insertar registros en una tabla de interfaz en Oracle E-Business Suite utilizando [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                                    |
|      ConcurrentProgram       |                                                                                       Se muestra cómo invocar un programa simultáneo en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                                       |
|          RequestSet          |                                                                                          Se muestra cómo invocar una solicitud que se establezca en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                                           |
|      MsgContextProperty      | Muestra cómo usar las propiedades de contexto de mensaje expuestas por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para establecer el contexto de la aplicación para realizar operaciones en los artefactos en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. |
| OracleEBS_CompositeOperation |                                                                                      Muestra cómo realizar operaciones compuestas en Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                                       |
|   OracleNotifyIncremental    |                                                                                   Muestra cómo recibir mensajes de notificación de consulta "incremental" desde Oracle mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                                    |
| PollingUsingSelectStatement  |                                                                            Muestra cómo configurar una consulta de sondeo mediante una instrucción SELECT y recibir los resultados mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                            |
|    PollingUsingStoredProc    |                                                                            Muestra cómo configurar una consulta de sondeo mediante un procedimiento almacenado y recibir los resultados mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                            |
  
## <a name="wcf-service-model-sasamplesmples"></a>Modelo de servicio WCF Sasamplesmples  
  
|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|ConcProgram_ServiceModel|Muestra cómo invocar programas simultáneos en Oracle E-Business Suite mediante el adaptador.|  
|ExecuteReader|Muestra cómo invocar una operación ExecuteReader en Oracle E-Business Suite mediante el adaptador.|  
|Interface_Table_Ops|Muestra cómo realizar operaciones en tablas de interfaz en Oracle E-Business Suite mediante el adaptador.|  
|LargeDataTypes_ServiceModel|Muestra cómo realizar operaciones en tablas con columnas de tipos de datos de gran tamaño en Oracle E-Business Suite mediante el adaptador.|  
|Notification_ServiceModel|Muestra cómo recibir notificaciones de las bases de datos subyacente mediante el adaptador de Oracle E-Business Suite.|  
|SelectPolling_ServiceModel|Muestra cómo usar una instrucción SELECT para sondear una tabla de interfaz en Oracle E-Business Suite mediante el adaptador.|  
|StoredProcPolling_ServiceModel|Muestra cómo usar un procedimiento almacenado para sondear las tablas de Oracle E-Business Suite mediante el adaptador.|  
  
## <a name="wcf-channel-model-samples"></a>Ejemplos de modelo de canal de WCF  
  
|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|InsertOperation|Muestra cómo realizar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el adaptador.|  
|SelectPolling_ChannelModel|Muestra cómo usar una instrucción SELECT para sondear una tabla de interfaz en Oracle E-Business Suite mediante el adaptador.|  
  
## <a name="microsoft-office-sharepoint-server-samples"></a>Ejemplos de Microsoft Office SharePoint Server  
  
| Nombre del directorio de ejemplo |                                                                                                                                                                  Descripción                                                                                                                                                                   |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      MOSS_Sample      | Muestra cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para crear un servicio de Windows Communication Foundation (WCF) de los artefactos de Oracle E-Business Suite y, a continuación, usar el servicio WCF para mostrar los datos en Microsoft Office SharePoint Server mediante un elemento Web de lista de datos de Business. |
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)