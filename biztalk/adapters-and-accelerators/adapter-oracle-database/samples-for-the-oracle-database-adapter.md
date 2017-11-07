---
title: Ejemplos de adaptadores de base de datos de Oracle | Documentos de Microsoft
description: Ejemplos de adaptadores de WCF de la base de datos de Oracle que pueden usarse con BizTalk Server, el modelo de servicio WCF y el modelo del canal WCF
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bfef9fcfce65d8aede1cd905a53469c565977f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-oracle-database-adapter"></a>Ejemplos para el adaptador de la base de datos de Oracle
Ejemplos de [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] se clasifican en categorías:  
  
-   Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
-   Ejemplos de modelo de servicio WCF  
  
-   Ejemplos de modelo de canal WCF  

  
Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos de adaptadores de base de datos de Oracle](https://www.microsoft.com/download/details.aspx?id=4675). Las secuencias de comandos SQL para crear las tablas y los paquetes utilizados en los ejemplos se incluyen. 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
En la lista siguiente describe los ejemplos.
  
## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|Func_RecordTypes|Muestra cómo usar parámetros de tipo de registro y valores devueltos en funciones y procedimientos con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|Func_RefCursor|Muestra cómo utilizar los parámetros REF CURSOR en funciones y procedimientos con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|InvokeFunction|Muestra cómo invocar una función de base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|InvokeOverloadedProc|Muestra cómo invocar con las funciones sobrecargadas y los procedimientos de la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|Operate_BFILE|Muestra cómo utilizar tipos BFILE de Oracle en los procedimientos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|Operate_LOB|Muestra cómo realizar operaciones de ReadLOB y UpdateLOB en tablas con tipos de datos LOB mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|PollingQuery|Muestra cómo configurar una consulta de sondeo y recibir los resultados utilizando la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|SelectAccTable|Muestra cómo realizar una consulta select en una tabla de base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|SqlExec|Muestra cómo realizar consultas con parámetros mediante la operación SQLEXECUTE en una base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
  
## <a name="wcf-service-model-samples"></a>Ejemplos de modelo de servicio WCF  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|OracleBfileTypeSM|Muestra cómo utilizar tipos BFILE de Oracle en las operaciones básicas de SQL que aparecen para las tablas de Oracle y como parámetros a procedimientos de Oracle.|  
|OracleOverloadsSM|Muestra cómo invocar las funciones sobrecargadas y los procedimientos de un paquete.|  
|OraclePollingSM|Muestra cómo configurar una consulta de sondeo y recibir los resultados.|  
|OracleRecordTypesSM|Muestra cómo usar parámetros de tipo de registro y valores devueltos en funciones y procedimientos.|  
|OracleRefCursorsSM|Muestra cómo utilizar los parámetros REF CURSOR en funciones y procedimientos|  
|OracleTransactedDmlSM|Muestra cómo realizar operaciones en la base de datos de Oracle en una transacción utilizando el modelo de servicio WCF.|  
  
## <a name="wcf-channel-model-samples"></a>Ejemplos de modelo de canal WCF  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|OraclePollingCM|Muestra cómo configurar una consulta de sondeo y recibir los resultados.|  
|OracleStreamingDemo|Muestra cómo realizar-to-end de transmisión por secuencias de datos LOB mediante las operaciones Select UpdateLOB y tabla|  
|OracleTransactedDmlCM|Muestra cómo realizar operaciones en la base de datos de Oracle en una transacción mediante el modelo de canal WCF.|  
  

## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)